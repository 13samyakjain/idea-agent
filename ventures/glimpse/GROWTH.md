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
| Leads in qualification funnel (`Lead Sourcing Queue`) | 25 total. **8 reviewed and written to ClickUp**: 3 Qualified, 3 Borderline, 2 Disqualified. **17 more researched (verdicts ready: 5 Qualified, 6 Borderline, 6 Disqualified) but NOT yet written to ClickUp** — blocked by a hard rate limit (~24h) hit mid-run; ClickUp itself still shows these 17 as unreviewed "to do" until a retry lands them. Full per-company verdicts preserved in STATUS_LOG.md 2026-08-20 entry so the research isn't lost. | 2026-08-20 |
| Orchestrator passes completed against Glimpse | 5+ (2026-08-18 through 2026-08-20, multiple same-day passes on some dates) | 2026-08-20 |

## Instrumentation TODO

- [ ] Get the ClickUp list/space mapping from MILESTONES.md Phase 0 done — that unlocks real
      numbers for every row above
- [ ] Ask the founder for a baseline read on current reservation volume, PE Kit costs, and
      event cadence rather than inferring from incomplete ClickUp data
- [ ] Retry the ClickUp writes for the 17 leads whose verdicts are ready but unwritten (see
      STATUS_LOG.md 2026-08-20) once the rate limit clears — do not re-research, the verdicts
      are already final, only the ClickUp write needs to happen
- [ ] Structural fix needed: parallel agent dispatches against ClickUp exhaust its rate limit
      fast (8 successful writes before lockout on 2026-08-20, running 3 agents at once) —
      future ClickUp-heavy dispatches against this venture should be serialized, not
      parallelized, until the actual per-minute/per-day quota is known
