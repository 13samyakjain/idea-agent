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

## Open questions (founder decisions — not agent-decidable)

- [ ] What's the actual product surface? A CLI wrapper, an installable ECC skill pack, a
      hosted app? (Affects nearly every downstream milestone.)
- [ ] Ship as a standalone product, or as a skill/agent pack others install into their own
      Claude Code setup?
- [ ] Who is the first real user — is it just the founder (dogfooding), or an outside pilot user?

These stay open until a human answers them. The orchestrator should surface them, not guess.
