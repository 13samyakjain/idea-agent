# IdeaAgent — Venture Definition

> Maintained by the venture-orchestrator skill. Human-editable at any time; the orchestrator
> reads this before every run and proposes edits rather than silently rewriting it.

## What it is

IdeaAgent is an internal orchestration tool — a Claude Code skill/agent pack — the founder uses
to run his own businesses. It reads each business's real state, decides the single
highest-leverage next action, dispatches specialized agents against it, and logs what happened
daily, per venture.

**It is not a product sold to other founders.** Each tracked business lives in its own
`ventures/<name>/` folder (VENTURE.md, MILESTONES.md, GROWTH.md, STATUS_LOG.md); this root-level
set of docs tracks IdeaAgent-the-tool itself, not any single business.

## Who it's for

The founder, across his own portfolio of businesses. First business onboarded: **Glimpse**
(glimpse.net.in) — see `ventures/glimpse/VENTURE.md`.

## Why now

Agentic coding tools (Claude Code, subagents with real tool access) can credibly do delegated,
multi-step work. The gap isn't agent capability — it's orchestration discipline: turning a real
business's messy day-to-day into a founder's-eye view of what actually needs to happen next,
and not letting agent busywork substitute for real movement. That discipline is now pointed at
running actual businesses instead of validating whether other founders would want to buy it.

## Stage

**Operational, multi-venture.** The orchestrator scaffold and daily cloud automation are built
and working (see STATUS_LOG.md for the automation-reliability history). First real venture
(Glimpse) onboarded 2026-08-18; the orchestrator has not yet completed a full pass against it.

## Founder decisions (locked 2026-08-09, revised 2026-08-18)

- **2026-08-09:** Product surface = installable Claude Code skill/agent pack. Ship model =
  distributed like the founder's own ECC rules/skills repo pattern. First user = founder only,
  dogfooding.
- **2026-08-18 — pivot:** IdeaAgent is not sold to other founders. It's an internal tool that
  runs the founder's own businesses, starting with Glimpse. The discovery-conversation
  validation work (testing whether *other* founders would want this) is retired —
  `DISCOVERY_GUIDE.md` removed. Repo restructured to `ventures/<name>/` per business, with this
  root tracking the tool itself.

## Open questions (founder decisions — not agent-decidable)

- Are there other existing businesses beyond Glimpse that should be onboarded as ventures?
- Does the old Phase 2/3 roadmap below (packaging IdeaAgent as an installable pack for others)
  still apply to anyone, or is it fully retired now that the sell-to-founders model is gone?
