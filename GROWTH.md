# IdeaAgent — Growth Framework

> What to measure at each stage, and the current honest values. The orchestrator updates the
> "Current" column only with real, checkable numbers — never estimates or placeholders dressed
> up as data. If something isn't measurable yet, it says "not yet measurable," not "0."

## Stage-appropriate metrics

| Stage | What matters | Why |
|---|---|---|
| Tool foundation (done) | Vision/milestone stability, orchestrator reliability | Churn/breakage = the tool isn't ready to point at a real business yet |
| Multi-venture onboarding (current) | # ventures tracked, orchestrator passes actually completed per venture | Proves the tool works against real business data, not just IdeaAgent's own scaffold |
| Operational | Per-venture: did the orchestrator surface something the founder actually acted on? | The real test — same bar as any dogfood loop, now applied to real businesses |
| Portfolio growth | Ventures tracked, agent-dispatch success rate vs. rework rate, founder time saved | Whether this is actually worth running across more than one business |

## Current metrics

| Metric | Value | As of |
|---|---|---|
| Vision stability | 2 revisions (open questions → locked decisions 08-09; sell-to-founders → internal tool 08-18) | 2026-08-18 |
| Orchestrator runs completed (tool-level, IdeaAgent itself) | 6 (bootstrap, founder decisions, discovery guide, incident-found run, discovery-guide pressure-test, 6-day-gap run) | 2026-08-18 |
| Active ventures tracked | 1 (Glimpse — glimpse.net.in) | 2026-08-18 |
| Orchestrator passes completed against Glimpse specifically | 0 — onboarded 2026-08-18, no pass run yet | 2026-08-18 |
| Daily cloud routine reliability | Root cause found and fixed: the Claude GitHub App was never installed on the founder's GitHub account, so every cloud-session `git push`/GitHub MCP write 403'd (read-only access only) — commits were made inside the ephemeral container each run but never reached origin, then lost when the container was reclaimed. Founder reinstalled the GitHub App with Contents Read & write on 2026-08-18. Verified live: a manual re-trigger of the daily routine committed and pushed `f9805a7` cleanly. Reliability clock (3 consecutive clean days) starts from the next scheduled fire, not before. | 2026-08-18 |
| Dogfood status report — activation signal | First real one shipped (Venture Console) and used same-day to act on 3 real decisions (routine-fix approval, ClickUp target list, live-polling tradeoff) | 2026-08-10 |

## Instrumentation TODO

- [ ] Decide how "orchestrator run completed cleanly" gets verified (STATUS_LOG.md entry with
      no `[!]` blocked items is the working definition for now)
- [ ] Once Glimpse's ClickUp data is mapped to its three service lines, define real
      activation/retention-equivalent events per venture (not a generic product funnel — this
      isn't sold, so "activation" means "founder acted on what the orchestrator surfaced")
