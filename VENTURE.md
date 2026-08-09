# IdeaAgent — Venture Definition

> Maintained by the venture-orchestrator skill. Human-editable at any time; the orchestrator
> reads this before every run and proposes edits rather than silently rewriting it.

## What it is

IdeaAgent turns a raw idea into a structured venture: a vision, a milestone-driven roadmap,
growth targets, and a dispatched team of AI agents (backed by a human founder) executing
against them — with continuous check-ins on what the humans did and what the agents did.

## Who it's for

Solo founders / small teams who have an idea but no structured process to execute it, and
who are willing to use AI agents as most of the "team."

## Why now

Agentic coding tools (Claude Code, subagents with real tool access) can credibly do delegated,
multi-step work. The gap isn't agent capability — it's orchestration discipline: turning a vague
idea into milestone-driven execution, keeping a founder's-eye view on progress, and not letting
agent busywork substitute for real movement.

## Stage

**Pre-idea / tooling.** No product built yet beyond this orchestrator scaffold. The first
real test is dogfooding: use IdeaAgent's own orchestrator to run IdeaAgent itself.

## Founder decisions (locked 2026-08-09)

- **Product surface:** installable Claude Code skill/agent pack — a `.claude/skills` +
  `.claude/agents` bundle (the `venture-orchestrator` skill already built is the first piece
  of it). No separate hosted infra or CLI binary.
- **Ship model:** distributed like this user's own ECC rules/skills repo pattern — others
  clone/install it into their own Claude Code setup. Not a standalone branded product.
- **First user:** the founder only, dogfooding. IdeaAgent runs on itself via the daily
  orchestrator routine until the loop is proven. No outside pilot user yet.

## Open questions (founder decisions — not agent-decidable)

None currently open. The orchestrator should re-surface new ones here as they come up,
rather than guessing past them.
