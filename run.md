# EVAL — Orchestration Guide for Claude Code

This file is the operational guide for running an Eval analysis. Claude Code reads this file and follows it step by step when a run is triggered.

---

## How to Start a Run

The user says something like:
> "Starte einen Eval-Run mit input.yaml"
> "Run eval on this business case"
> "Start the eval system"

Claude Code then:
1. Reads `eval/input.yaml`
2. Reads this `run.md` file
3. Creates the output directory for this run
4. Follows the phase sequence below

---

## Pre-Run Setup

### Step 1: Read and validate input
Read `eval/input.yaml`. Check:
- All required fields are filled (company.name, company.description, business_case.topic, business_case.solution_direction)
- `run_options.mode` is set ("step" or "auto")
- `run_options.research_depth` is set ("quick" or "deep")

If any required field is empty: stop and ask the user to complete it.

### Step 2: Create run directory
Create: `eval/output/run_{{YYYYMMDD_HHMMSS}}/`
This is the `{{run_id}}` used in all prompts.

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

## PHASE 1 — Research (parallel)

**Launch 3 agents simultaneously** (in the same message, as parallel Agent tool calls):

| Agent | Prompt file | Output file |
|---|---|---|
| research-market | `eval/prompts/p1_research_market.md` | `output/{{run_id}}/research_market.md` |
| research-technology | `eval/prompts/p1_research_technology.md` | `output/{{run_id}}/research_technology.md` |
| research-problems | `eval/prompts/p1_research_problems.md` | `output/{{run_id}}/research_problems.md` |

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
- Prompt: `eval/prompts/p2_analysis.md`
- Input: reads the 3 research files from Phase 1
- Output: `output/{{run_id}}/analysis_status_quo.md`

**Phase 2 complete when:** `analysis_status_quo.md` exists and contains all 5 required sections including "Key Tensions & Open Questions".

**[STEP MODE: Pause here. Show user: "Phase 2 abgeschlossen. Ist-Analyse erstellt. Weiter mit Lösungshypothesen?"]**

---

## PHASE 3 — Solution Hypotheses (parallel)

**Launch 3 agents simultaneously:**

| Agent | Prompt file | Output file |
|---|---|---|
| hypothesis-solution | `eval/prompts/p3_hypothesis_solution.md` | `output/{{run_id}}/hypothesis_solution.md` |
| hypothesis-technology | `eval/prompts/p3_hypothesis_technology.md` | `output/{{run_id}}/hypothesis_technology.md` |
| hypothesis-business | `eval/prompts/p3_hypothesis_business.md` | `output/{{run_id}}/hypothesis_business_model.md` |

Each agent reads Phase 1 outputs + `analysis_status_quo.md`.

**Phase 3 complete when:** All 3 hypothesis files exist.

**[STEP MODE: Pause here. Show user: "Phase 3 abgeschlossen. 3 Hypothesen-Dokumente erstellt. Weiter mit Agenten-Debatte?"]**

---

## PHASE 4 — Agent Debate (parallel personas → sequential moderator)

### Round 1:

**Launch 5 persona agents simultaneously:**

| Agent | Prompt file | Appends to |
|---|---|---|
| debate-optimist | `eval/prompts/p4_debate_optimist.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-critic | `eval/prompts/p4_debate_critic.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-technician | `eval/prompts/p4_debate_technician.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-market | `eval/prompts/p4_debate_market.md` | `output/{{run_id}}/debate_round_1.md` |
| debate-strategist | `eval/prompts/p4_debate_strategist.md` | `output/{{run_id}}/debate_round_1.md` |

> Note: All 5 agents append to the same file. Each writes a clearly marked section (## OPTIMIST, ## CRITIC, etc.).
> Initialize the file with a header before launching agents:
> `# Debate Round 1 — {{company_name}} — {{date}}`

**After all 5 persona agents complete:**

**Launch Moderator agent (sequential):**
- Prompt: `eval/prompts/p4_moderator.md` with `{{round_number}} = 1`
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
- Prompt: `eval/prompts/p5_synthesis.md`
- Reads: all output files from all previous phases
- Output: `output/{{run_id}}/final_report.md`

**Phase 5 complete when:** `final_report.md` exists and contains the Assessment Scorecard and a clear Recommendation.

**[STEP MODE: Pause. Show user: "Phase 5 abgeschlossen. Final Report erstellt."]**

---

## PHASE 6 — Flow Documentation

After all phases complete:
- Update `eval/FLOW.md` with the actual Mermaid diagram reflecting this run
- Output a brief run summary to the user:
  - Files created
  - Overall recommendation (from final_report.md)
  - Key next steps (from final_report.md)

---

## Error Handling

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
eval/output/{{run_id}}/
  ✓ research_market.md
  ✓ research_technology.md
  ✓ research_problems.md
  ✓ analysis_status_quo.md
  ✓ hypothesis_solution.md
  ✓ hypothesis_technology.md
  ✓ hypothesis_business_model.md
  ✓ debate_round_1.md
  ○ debate_round_2.md  (optional)
  ✓ final_report.md
```
