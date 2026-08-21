# Glimpse — Growth Framework

> What to measure at each stage, and the current honest values. The orchestrator updates the
> "Current" column only with real, checkable numbers — never estimates or placeholders dressed
> up as data. If something isn't measurable yet, it says "not yet measurable," not "0."

## Stage-appropriate metrics

| Stage | What matters | Why |
|---|---|---|
| Onboarding (current) | Is Glimpse's real operational data (ClickUp) actually visible and correctly interpreted by the orchestrator? | Can't optimize what isn't seen yet |
| Operational visibility | Reservation volume, PE Kit procurement cost/cadence, event count vs. intake | Baseline before the orchestrator can suggest real improvements |
| Sales engine expansion | Once scoped: pipeline/leads for the sales-engine offering | Only relevant after Phase 2 in MILESTONES.md is defined |

## Current metrics

| Metric | Value | As of |
|---|---|---|
| Reservation volume | not yet measurable (data exists, tag-based extraction not built yet) | 2026-08-18 |
| PE Kit procurement cost baseline | not yet measurable (data exists, tag-based extraction not built yet) | 2026-08-18 |
| Events managed (period TBD) | not yet measurable (data exists, needs university/tag rollup) | 2026-08-18 |
| Team size | 6 confirmed via ClickUp assignees: Samyak Jain (founder), Babita, Kaustav Saha, Sachin Poddar, Syed Afsha Ali, Kanchan Thakur | 2026-08-18 |
| Sales Engine milestones | 2 of 5 core milestones done (M1, M2); M3-M5 open | 2026-08-18 |
| Leads in qualification funnel (`Lead Sourcing Queue`) | **25 of 25 reviewed and written to ClickUp** (complete as of 2026-08-21): **8 Qualified**, **9 Borderline** (each with an escalation comment tagging Samyak for a judgment call), **8 Disqualified**. None yet promoted to GHL — that's the next step, gated on founder sign-off of the Stage 2 assignment process (task 86d3t4bg7, still pending). | 2026-08-21 |
| Orchestrator passes completed against Glimpse | 6+ (2026-08-18 through 2026-08-21, multiple same-day passes on some dates) | 2026-08-21 |

## Instrumentation TODO

- [ ] Get the ClickUp list/space mapping from MILESTONES.md Phase 0 done — that unlocks real
      numbers for every row above
- [ ] Ask the founder for a baseline read on current reservation volume, PE Kit costs, and
      event cadence rather than inferring from incomplete ClickUp data
- [x] Retry the ClickUp writes for the 17 leads whose verdicts were ready but unwritten — done
      2026-08-21, all 17 plus one missing comment written cleanly in one serialized pass, zero
      rate-limit errors. See STATUS_LOG.md 2026-08-21 entry.
- [x] Structural fix validated: a single agent making ClickUp calls strictly sequentially (no
      parallel dispatches) completed 44 ClickUp tool calls (17 status/description updates + 7
      comments) with zero `RATE_LIMIT_EXCEEDED` errors, where 3 parallel agents tripped a ~24h
      block after only 8 writes on 2026-08-20. Confirms concurrency (not call volume) was the
      actual cause. Serialize future ClickUp-heavy dispatches against this venture as the
      default going forward.
