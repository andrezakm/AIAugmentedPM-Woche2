# EVAL System — Flow Diagram

```mermaid
flowchart TD
    INPUT["📋 input.yaml\n(Company · Strategy · Business Case)"]

    INPUT --> SETUP["Pre-Run Setup\n• Validate input\n• Create output/run_ID/\n• Extract variables"]

    SETUP --> P1["PHASE 1 — Research\n(3 parallel background agents)\neach: 6–26 WebSearch + WebFetch calls"]

    P1 --> R1["🔍 Market Research\nresearch_market.md"]
    P1 --> R2["🔍 Technology Research\nresearch_technology.md"]
    P1 --> R3["🔍 Problem Research\nresearch_problems.md"]

    R1 & R2 & R3 --> STEP1{{"step mode:\npause?"}}
    STEP1 -->|"confirmed"| P2

    P2["PHASE 2 — Status Quo Analysis\n(1 agent · sequential)\nreads all 3 research files"]
    P2 --> IST["📊 Status Quo Analysis\nanalysis_status_quo.md"]

    IST --> STEP2{{"step mode:\npause?"}}
    STEP2 -->|"confirmed"| P3

    P3["PHASE 3 — Solution Hypotheses\n(3 parallel background agents)"]

    P3 --> H1["💡 Solution Hypothesis\nhypothesis_solution.md"]
    P3 --> H2["⚙️ Technology Hypothesis\nhypothesis_technology.md"]
    P3 --> H3["💰 Business Model Hypothesis\nhypothesis_business_model.md"]

    H1 & H2 & H3 --> STEP3{{"step mode:\npause?"}}
    STEP3 -->|"confirmed"| P4

    P4["PHASE 4 — Agent Debate Round 1\n(5 parallel background agents)"]

    P4 --> OPT["🟢 Optimist\n→ appends to debate_round_1.md"]
    P4 --> CRIT["🔴 Critic\n→ appends to debate_round_1.md"]
    P4 --> TECH["⚙️ Technician\n→ appends to debate_round_1.md"]
    P4 --> MKT["📈 Market Expert\n→ appends to debate_round_1.md"]
    P4 --> STRAT["♟️ Strategist\n→ appends to debate_round_1.md"]

    OPT & CRIT & TECH & MKT & STRAT --> MOD1["🎯 Moderator R1\n(sequential, reads full file)\n→ appends synthesis to debate_round_1.md"]

    MOD1 --> R2DEC{{"Moderator recommends\nRound 2?"}}

    R2DEC -->|"Yes + user confirms"| P4B
    R2DEC -->|"No"| STEP4

    P4B["PHASE 4 — Agent Debate Round 2\n(5 parallel background agents)\nfocused on unresolved questions"]

    P4B --> OPT2["🟢 Optimist R2"]
    P4B --> CRIT2["🔴 Critic R2"]
    P4B --> TECH2["⚙️ Technician R2"]
    P4B --> MKT2["📈 Market Expert R2"]
    P4B --> STRAT2["♟️ Strategist R2"]

    OPT2 & CRIT2 & TECH2 & MKT2 & STRAT2 --> MOD2["🎯 Moderator R2\n→ debate_round_2.md"]

    MOD2 --> STEP4{{"step mode:\npause?"}}
    STEP4 -->|"confirmed"| P5

    P5["PHASE 5 — Final Report\n(1 agent · sequential)\nreads all 9 documents"]

    P5 --> FINAL["📄 Final Report\nfinal_report.md\nGO / CONDITIONAL GO / PIVOT / NO-GO\n+ Scorecard + Next Steps"]

    FINAL --> P6["PHASE 6 — Documentation\nFLOW.md updated"]
```

---

## Parallelization Summary

| Phase | Parallel agents | Sequential agents | Notes |
|---|---|---|---|
| Phase 1 | 3 (market, tech, problems) | — | Background; each runs 6–26 searches |
| Phase 2 | — | 1 (status quo analysis) | Reads all 3 research files |
| Phase 3 | 3 (solution, tech, business) | — | Background; reads research + analysis |
| Phase 4 R1 | 5 (debate personas) | 1 (moderator) | Personas append to shared file |
| Phase 4 R2 | 5 (debate personas) | 1 (moderator) | Optional; triggered by Moderator R1 |
| Phase 5 | — | 1 (synthesis) | Reads all 9 intermediate files |

**Total agents per run:**
- 1-round debate: **13 agents**
- 2-round debate: **20 agents**

**Parallel launch points:** 4 (Phases 1, 3, 4 R1 personas, 4 R2 personas)

**Step mode pause points:** After Phases 1, 2, 3, and 4 (before Phase 5)

---

## Output Files per Run

```
output/run_YYYYMMDD_HHMMSS/
├── research_market.md            Phase 1
├── research_technology.md        Phase 1
├── research_problems.md          Phase 1
├── analysis_status_quo.md        Phase 2
├── hypothesis_solution.md        Phase 3
├── hypothesis_technology.md      Phase 3
├── hypothesis_business_model.md  Phase 3
├── debate_round_1.md             Phase 4 R1 (5 personas + moderator appended sequentially)
├── debate_round_2.md             Phase 4 R2 (optional — same structure, focused)
└── final_report.md               Phase 5
```

---

## Architecture Notes (from the NeoEmployee run — see `results/neoemployee/`)

**Shared-file append pattern:** All 5 debate personas write to a single file by appending. This works reliably but requires the file to be pre-created with a header before agents are launched. The moderator runs sequentially *after* all personas complete (waiting for all task notifications).

**Research depth:** `deep` mode agents typically perform 20–26 searches (not just 6) when allowed to follow leads. The 6-search minimum is a floor, not a ceiling.

**WebSearch permissions:** Subagents require `WebSearch` and `WebFetch` in the `permissions.allow` array of `~/.claude/settings.json`. Without this, Phase 1 agents silently fail on search calls. Verify before starting a run.

**Round 2 focus:** When the Moderator recommends Round 2, it identifies specific unresolved questions. Round 2 agents should be given those exact questions as their sole focus — not a full repeat of Round 1. This produces sharper, faster convergence.

**ICP precision matters commercially:** This run surfaced that a 1–2 hires/year difference in the ICP qualification threshold (30 vs. 35) changes a below-break-even ROI to above-break-even. Future runs should instrument the commercial analysis with explicit break-even calculations, not just directional sizing.
