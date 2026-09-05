# EVAL — Orchestration Guide for Claude Code

This file is the operational guide for running an Eval analysis. Claude Code reads this file and follows it step by step when a run is triggered.

---

## How to Start a Run

The user says something like:
> "Starte einen Eval-Run mit input.yaml"
> "Run eval on this business case"
> "Start the eval system"

Claude Code then:
1. Reads `input/input.yaml`
2. Reads this `run.md` file
3. Creates the output directory for this run
4. Follows the phase sequence below

---

## Pre-Run Setup

### Step 1: Read and validate input
Read `input/input.yaml`. Check:
- All required fields are filled (company.name, company.description, business_case.topic, business_case.solution_direction)
- `run_options.mode` is set ("step" or "auto")
- `run_options.research_depth` is set ("quick" or "deep")

If any required field is empty: stop and ask the user to complete it.

### Step 2: Create run directory and status file
Create: `output/run_{{YYYYMMDD_HHMMSS}}/`
This is the `{{run_id}}` used in all prompts.

Then create `output/{{run_id}}/STATUS.md` — the single source of truth for the state of this run:

```
# Run status — {{run_id}}
mode: {{mode}} · research_depth: {{research_depth}} · debate_rounds: {{debate_rounds}} · language: {{language}}

| Phase | Status | Files |
|---|---|---|
| 1 Research | pending | |
| 2 Status quo | pending | |
| 3 Hypotheses | pending | |
| 4 Debate R1 | pending | |
| 4 Debate R2 | pending / skipped | |
| 5 Final report | pending | |
| 6 Flow doc | pending | |
```

Update this table after every phase (status `done`, file names). Before starting any phase, read `STATUS.md` and decide the next step from it — not from memory. This keeps the run safe across context compaction and makes "Starte den Lauf ab Phase 4" possible: read `STATUS.md`, verify the listed files exist, continue.

### Step 3: Prepare context variables
Extract from input.yaml:
```
{{company_name}}            = company.name
{{company_description}}     = company.description
{{tech_stack}}              = company.tech_stack (joined as comma-separated list)
{{strategy_direction}}      = strategy.direction
{{strategy_constraints}}    = strategy.constraints (joined as list)
{{business_case_topic}}     = business_case.topic
{{solution_direction}}      = business_case.solution_direction
{{target_market}}           = business_case.target_market
{{debate_rounds}}           = run_options.debate_rounds
{{research_depth}}          = run_options.research_depth
{{language}}                = run_options.language
{{mode}}                    = run_options.mode
{{min_searches}}            = 3 if research_depth=="quick" else 6
{{current_year}}            = current year
{{date}}                    = today's date
{{run_id}}                  = the output directory name
```

---

## Phase Execution

### MODE: "step" (testing mode)
After each phase: output a brief summary of what was produced, and wait for the user to type "weiter" / "next" / "ok" before proceeding to the next phase.

### MODE: "auto" (production mode)
Run all phases sequentially without pausing. Output a one-line status after each phase.

---

## Working Rules for the Orchestrator

These rules keep the orchestrator's growing context from influencing any result:

1. **The orchestrator never judges content — it only transports.** Every judgment (status quo synthesis, moderation, final report) happens inside a dedicated agent with a fresh, narrow context. Agents write their own files and return only a short confirmation. The orchestrator writes a file in exactly one case: when an agent reports `WRITE REFUSED` and returns the document as text. Then it writes that text to the target file **verbatim** — no summarizing, no smoothing, no commentary. Never write a file "to be safe", and never write one a second time when the agent already created it.
2. **Agents read their inputs from disk, never from the conversation.** The orchestrator passes file paths and the context variables, not file contents. What the orchestrator remembers or has forgotten is irrelevant; the truth is in `output/{{run_id}}/`.
3. **The state of the run lives in `STATUS.md`**, not in the orchestrator's memory (see Pre-Run Step 2).
4. **Fallback when an agent cannot write its file.** Claude Code refuses `Write` calls from subagents for `.md` files whose name starts with `report`, `summary`, `findings` or `analysis` ("Subagents should return findings as text, not write report files"). No file in this system uses those prefixes — the status quo analysis is deliberately named `status_quo_analysis.md` for that reason (this is a controlled pipeline with fixed readers, not the stray-report case the rule targets). If a write is still refused, the agent returns the complete document as its final message (marked `WRITE REFUSED — full document follows`) and the orchestrator writes it verbatim to the target path. Without that marker, the agent has written its file itself — do not write it again. Never rename files or use the shell to get around the rule.

---

## PHASE 1 — Research (parallel)

**Launch 3 agents simultaneously** (in the same message, as parallel Agent tool calls):

| Agent | Prompt file | Output file |
|---|---|---|
| research-market | `scripts/p1_research_market.md` | `output/{{run_id}}/research_market.md` |
| research-technology | `scripts/p1_research_technology.md` | `output/{{run_id}}/research_technology.md` |
| research-problems | `scripts/p1_research_problems.md` | `output/{{run_id}}/research_problems.md` |

Before launching: replace all `{{variable}}` placeholders in each prompt with the actual values from input.yaml.

Each agent:
- Uses WebSearch and WebFetch tools for research
- Writes its output to the specified .md file
- Includes a Research Log section with all searches conducted

**Phase 1 complete when:** All 3 output files exist and each contains a Research Log section.

**[STEP MODE: Pause here. Show user: "Phase 1 abgeschlossen. 3 Research-Dokumente erstellt. Weiter mit Ist-Analyse?"]**

---

## PHASE 2 — Status Quo Analysis (sequential)

**Launch 1 agent:**
- Prompt: `scripts/p2_analysis.md`
- Input: reads the 3 research files from Phase 1
- Output: `output/{{run_id}}/status_quo_analysis.md`

**Phase 2 complete when:** `status_quo_analysis.md` exists and contains all 5 required sections including "Key Tensions & Open Questions".

**[STEP MODE: Pause here. Show user: "Phase 2 abgeschlossen. Ist-Analyse erstellt. Weiter mit Lösungshypothesen?"]**

---

## PHASE 3 — Solution Hypotheses (sequential, then parallel)

**Step 3a — Launch 1 agent first:**

| Agent | Prompt file | Output file |
|---|---|---|
| hypothesis-solution | `scripts/p3_hypothesis_solution.md` | `output/{{run_id}}/hypothesis_solution.md` |

Wait until `hypothesis_solution.md` exists. The technology and business agents build on this concrete solution design — launching them earlier makes them guess the solution from the status quo analysis.

**Step 3b — Then launch 2 agents simultaneously:**

| Agent | Prompt file | Output file |
|---|---|---|
| hypothesis-technology | `scripts/p3_hypothesis_technology.md` | `output/{{run_id}}/hypothesis_technology.md` |
| hypothesis-business | `scripts/p3_hypothesis_business.md` | `output/{{run_id}}/hypothesis_business_model.md` |

All three agents read Phase 1 outputs + `status_quo_analysis.md`; technology and business additionally read `hypothesis_solution.md`.

**Phase 3 complete when:** All 3 hypothesis files exist.

**[STEP MODE: Pause here. Show user: "Phase 3 abgeschlossen. 3 Hypothesen-Dokumente erstellt. Weiter mit Agenten-Debatte?"]**

---

## PHASE 4 — Agent Debate (parallel personas → sequential moderator)

### Round 1:

**Launch 5 persona agents simultaneously:**

| Agent | Prompt file | Appends to |
|---|---|---|
| debate-optimist | `scripts/p4_debate_optimist.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-critic | `scripts/p4_debate_critic.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-technician | `scripts/p4_debate_technician.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-market | `scripts/p4_debate_market.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-strategist | `scripts/p4_debate_strategist.md` | `output/{{run_id}}/debate_round_1.md` |

> Note: All 5 agents append to the same file. Each writes a clearly marked section (## OPTIMIST, ## CRITIC, etc.).
> Initialize the file with a header before launching agents:
> `# Debate Round 1 — {{company_name}} — {{date}}`

**After all 5 persona agents complete:**

**Launch Moderator agent (sequential):**
- Prompt: `scripts/p4_moderator.md` with `{{round_number}} = 1`
- Reads: `debate_round_1.md` + hypothesis files + analysis
- Appends moderator synthesis to `debate_round_1.md`

**[STEP MODE: Pause. Show user: "Phase 4 Runde 1 abgeschlossen. Empfiehlt der Moderator Runde 2?"]**

### Round 2 (if applicable):

Run Round 2 only if:
- `run_options.debate_rounds == 2` AND
- The Moderator recommended a second round in their synthesis

If yes: repeat the process with `debate_round_2.md` and `{{round_number}} = 2`.
The Round 2 persona prompts should instruct agents to focus on the specific tensions identified by the Round 1 Moderator.

**[STEP MODE: Pause after Round 2 if applicable.]**

---

## PHASE 5 — Synthesis & Final Report (sequential)

**Launch 1 agent:**
- Prompt: `scripts/p5_synthesis.md`
- Reads: all output files from all previous phases
- Output: `output/{{run_id}}/final_report.md`

**Phase 5 complete when:** `final_report.md` exists and contains the Assessment Scorecard and a clear Recommendation.

**[STEP MODE: Pause. Show user: "Phase 5 abgeschlossen. Final Report erstellt."]**

---

## PHASE 6 — Flow Documentation

After all phases complete:
- Write `output/{{run_id}}/flow.md`: the actual Mermaid diagram of **this** run (agents launched, files produced, whether Round 2 ran). Do not touch the root `FLOW.md` — that is the system's documentation, and the project rule is to write only inside the run folder.
- Mark all phases `done` in `STATUS.md`
- Output a brief run summary to the user:
  - Files created
  - Overall recommendation (from final_report.md)
  - Key next steps (from final_report.md)

---

## Error Handling

If an agent's `Write` call is refused with "Subagents should return findings as text…":
- The agent returns the document as text; the orchestrator writes it verbatim (Working Rule 4). This is not a failure.

If an agent fails to produce its output file:
- Report which agent failed and why
- Do not proceed to the next phase automatically
- Ask user: "Agent [X] konnte nicht abgeschlossen werden. Soll ich es erneut versuchen oder fortfahren?"

If research returns no useful results:
- The research agent should note this in its output with "Insufficient public data"
- The analysis phase notes the gap
- The synthesis agent weights this accordingly

---

## File Checklist (successful run)

```
output/{{run_id}}/
  ✓ STATUS.md
  ✓ research_market.md
  ✓ research_technology.md
  ✓ research_problems.md
  ✓ status_quo_analysis.md
  ✓ hypothesis_solution.md
  ✓ hypothesis_technology.md
  ✓ hypothesis_business_model.md
  ✓ debate_round_1.md
  ○ debate_round_2.md  (optional)
  ✓ final_report.md
  ✓ flow.md
```
