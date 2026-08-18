# IdeaAgent — Growth Framework

> What to measure at each stage, and the current honest values. The orchestrator updates the
> "Current" column only with real, checkable numbers — never estimates or placeholders dressed
> up as data. If something isn't measurable yet, it says "not yet measurable," not "0."

## Stage-appropriate metrics

| Stage | What matters | Why |
|---|---|---|
| Pre-idea (current) | Vision/milestone stability — is VENTURE.md still churning weekly, or has it settled? | Churn = the idea isn't structured enough yet to execute against |
| Validation | # real conversations had, # of those confirming the problem | Cheapest signal before building anything |
| MVP | Activation: did a full orchestrator cycle run end-to-end and produce a decision a human acted on? | Proves the core loop works, not just that code runs |
| Growth | WAU, ventures actively tracked, agent-dispatch success rate vs. rework rate | Real usage and whether agent delegation is actually saving founder time |

## Current metrics

| Metric | Value | As of |
|---|---|---|
| Vision stability | 1 revision (open questions → locked decisions) | 2026-08-09 |
| Validation conversations | 0 | 2026-08-09 |
| Orchestrator runs completed | 6 (bootstrap, founder decisions, discovery guide, incident-found run, discovery-guide pressure-test, 6-day-gap run) | 2026-08-18 |
| Active ventures tracked | 1 (IdeaAgent itself) | 2026-08-09 |
| Daily cloud routine reliability | Still 0 confirmed clean automated fires. 6-day gap in STATUS_LOG (2026-08-12 → 2026-08-18) with zero entries despite the described twice-daily schedule — either the routine stopped firing or it fired and failed silently before logging, same failure mode as the two earlier tested runs. This run (2026-08-18) is itself an automated fire; whether it lands cleanly depends on this run's own commit succeeding. | 2026-08-18 |
| Dogfood status report — activation signal | First real one shipped (Venture Console) and used same-day to act on 3 real decisions (routine-fix approval, ClickUp target list, live-polling tradeoff) | 2026-08-10 |

## Instrumentation TODO

- [ ] Decide how "orchestrator run completed cleanly" gets verified (STATUS_LOG.md entry with
      no `[!]` blocked items is the working definition for now)
- [ ] Once there's a product surface, define real activation/retention events
