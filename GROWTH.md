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
| Orchestrator runs completed | 4 (bootstrap, founder decisions, discovery guide, this run) | 2026-08-10 |
| Active ventures tracked | 1 (IdeaAgent itself) | 2026-08-09 |

## Instrumentation TODO

- [ ] Decide how "orchestrator run completed cleanly" gets verified (STATUS_LOG.md entry with
      no `[!]` blocked items is the working definition for now)
- [ ] Once there's a product surface, define real activation/retention events
