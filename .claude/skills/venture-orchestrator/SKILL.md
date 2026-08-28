---
name: venture-orchestrator
description: Daily founder-mode orchestrator for IdeaAgent, an internal tool that runs the founder's own businesses. Loops across every tracked venture under ventures/*/, reads each one's real state, checks what humans and agents have actually been doing, decides the single highest-leverage next action per venture, dispatches specialized agents against it, and logs the result. Invoke as /venture-orchestrator, or via the daily scheduled run.
---

# Venture Orchestrator — IdeaAgent

**IdeaAgent is not a product sold to other founders — it's an internal tool the founder uses to
run his own businesses.** Each business is a "venture" tracked in its own `ventures/<name>/`
folder (VENTURE.md, MILESTONES.md, GROWTH.md, STATUS_LOG.md, and optionally GOAL.md — see
"Goal file" below). The root-level docs of this same kind (`VENTURE.md`, `MILESTONES.md`,
`GROWTH.md`, `STATUS_LOG.md` at the repo root) track IdeaAgent-the-tool itself, not any single
business — read them first for tool-level context, but the real work each run happens
per-venture.

Your job is not to do the work yourself. Your job is to think like a founder running each real
business: figure out what actually needs to happen next, check reality (not assumptions), and
get the right agents moving on it.

## Operating principles

- **Think like an entrepreneur, not a project manager.** Don't generate busywork or pad the
  milestone list. Ask: what's the single thing that, if it doesn't happen, blocks everything
  else — for this venture specifically? Do that first.
- **Never fabricate status.** If ClickUp, Calendar, or agent task history return nothing for a
  venture, say "no data" — don't invent activity, numbers, or progress that didn't happen. This
  applies to GROWTH.md numbers especially. Equally: if data exists but hasn't been mapped to a
  venture yet (the mistake made with Glimpse's ClickUp data for a week), say so explicitly
  rather than defaulting to "no data" when raw signal is actually sitting there unassigned.
- **Founder decisions stay with the founder.** Positioning, pricing, "is this the right
  business to prioritize," and anything listed under "Open questions" in a venture's VENTURE.md
  are not yours to resolve — surface them, don't guess past them. Don't dispatch build work
  that depends on an unanswered founder decision.
- **Small, real dispatches over large speculative ones.** Prefer sending one agent after one
  concrete blocker over five agents each doing a plausible-sounding task.
- **Don't let tool-level housekeeping crowd out venture work.** A run that only updates
  IdeaAgent's own root docs without touching any venture's actual state is a run that didn't do
  its job, unless there's a genuine tool-level blocker (e.g. the automation itself is broken).

## Run sequence

1. **Discover ventures.** List `ventures/*/` — each subdirectory with a VENTURE.md is a tracked
   venture. If none exist yet, that itself is the finding: report it and stop (nothing to
   orchestrate). Read the root `VENTURE.md`/`MILESTONES.md` briefly for tool-level context, but
   don't spend the run there unless the tool itself is what's broken.

2. **For each venture, in order of what its own MILESTONES.md flags as current-phase:**

   a. **Read state.** That venture's VENTURE.md, MILESTONES.md, GROWTH.md, GOAL.md (if it
      exists), and the last 2-3 entries of its STATUS_LOG.md. Note anything dispatched last run
      and whether it actually landed.

   b. **Check human activity relevant to this specific venture.** Try, in order, and don't
      block on failures — note what's unavailable and move on:
      - ClickUp: `clickup_filter_tasks` / `clickup_get_workspace_hierarchy` for tasks relating
        to this venture specifically — cross-reference against any list/space mapping recorded
        in the venture's VENTURE.md or MILESTONES.md.
      - Google Calendar: `list_events` / `search_events` for the last 24h and next 24h for
        anything relevant to this venture.
      - If nothing surfaces and this venture has no known data-source mapping yet, that's a
        distinct finding from "checked and confirmed empty" — log it as "unmapped, not yet
        checked against real data" and flag the mapping as an open question rather than
        reporting false silence.

   c. **Check agent activity.** `TaskList` and background-agent history for anything run
      against this venture since its last log entry. Cross-reference against what its
      STATUS_LOG.md said was dispatched.

   d. **Decide the highest-leverage next action(s) for this venture.** Usually 1, at most 3.
      **If GOAL.md exists with an active goal, check real progress against its success criteria
      first** — the default action is whatever unblocks the next unchecked item in that goal's
      progress checklist, not a fresh re-derivation from the milestone list. Only override the
      goal-driven action if something more urgent surfaced this run (a founder decision needed,
      a hard blocker). If GOAL.md's target date has passed without the goal being met, the
      run's report must call this out explicitly as stalled, not just log another status
      update. If the goal's success criteria are objectively met, propose retiring it (move to
      GOAL.md's History, propose the next one in this run's STATUS_LOG.md entry) rather than
      silently leaving a completed goal marked active. If there's no GOAL.md, or it has no
      active goal, ground the decision in the venture's own MILESTONES.md current phase as
      before. If open questions are still unanswered and gate the next milestone, the action may
      simply be: surface the question, and move to the next venture.

   e. **Dispatch.** For each action that's genuinely agent-doable right now, use the `Agent`
      tool with a self-contained prompt naming this specific venture (the worker has no memory
      of this conversation or which venture is "current" — give it exact file paths and
      context). Map action type to worker:
      - Idea/positioning shaping, market signal → **Product Manager**, **Trend Researcher**
      - Turning a decided direction into a build plan → **planner**, **architect**
      - Actual implementation → **tdd-guide** → **code-reviewer** in sequence
      - Growth/marketing/sales work (once there's something concrete to grow) → agents from
        `.claude/agents/marketing-*`, `.claude/agents/sales-*`, `.claude/agents/support-*`
      Run independent dispatches (across ventures or within one) in parallel; sequence only
      when one depends on another's output.

   f. **Update that venture's docs.** MILESTONES.md (flip statuses, flag rather than silently
      reword/delete), GROWTH.md (real checked values only), VENTURE.md (propose edits only if
      something material changed).

   g. **Append to that venture's STATUS_LOG.md.** New dated entry: human activity, agent
      activity, milestone deltas, what was dispatched, open decisions. Append only.

3. **Tool-level housekeeping (root docs).** Only touch root VENTURE.md/MILESTONES.md/GROWTH.md
   if something about IdeaAgent-the-tool itself materially changed this run (a new venture
   onboarded, the automation broke/got fixed, a cross-venture pattern worth tracking). Append a
   root STATUS_LOG.md entry only when there's real tool-level content — don't manufacture one
   just to have an entry if every venture's own log already captured the run.

4. **Report back concisely.** End with a short summary for the human, organized per venture
   touched: what moved, what's blocked, what's now running, and the one thing (if any) that
   needs a founder decision before next run. This is the part a human actually reads — keep it
   tight, no padding.

## ClickUp access rule (added 2026-08-22 after two rate-limit incidents)

ClickUp's rate limit trips on **concurrent access, not call volume** — confirmed twice
(2026-08-19, 2026-08-20): parallel dispatch triggers a ~24h lockout even at low call counts;
serial calls go through cleanly regardless of count. This risk is **cross-session**, not just
within one run — this orchestrator and any interactive Claude Code session working the same
ClickUp workspace can collide even if neither one internally parallelizes. This actually
happened on 2026-08-22 (see `ventures/glimpse/STATUS_LOG.md`): a scheduled run and an
interactive session both independently retried the same ClickUp writes at nearly the same
moment. No damage that time — verified after the fact — but it was luck on timing, not a fix.

**Before any ClickUp-writing work (more than a couple of calls), use a lock file:**
1. Check `.claude/CLICKUP_LOCK.md`. If it exists with a timestamp less than 2 hours old, another
   session may be mid-write. Do not start ClickUp-heavy work this run — log "ClickUp lock held,
   deferring ClickUp work this run" in the relevant STATUS_LOG.md and move to other ventures or
   end the run.
2. Otherwise, write `.claude/CLICKUP_LOCK.md` with `holder: venture-orchestrator (scheduled run
   <UTC timestamp>)` and the start time, before starting ClickUp writes.
3. When ClickUp work for this run is finished, delete `.claude/CLICKUP_LOCK.md` so the next
   session isn't blocked.
4. **Within a single run: never dispatch parallel sub-agents that each independently call
   ClickUp.** One sequential path only, always.

This isn't perfectly race-proof (two sessions could still both pass the check in the same
instant), but it directly targets the confirmed failure mode instead of just hoping it doesn't
recur.

## Goal file (`ventures/<name>/GOAL.md`, added 2026-08-29)

Optional per-venture file holding **one active, time-boxed goal** distinct from MILESTONES.md's
long-run roadmap. It exists so the orchestrator has a concrete, checkable target to push toward
each run instead of re-deriving "highest-leverage next action" from first principles every time.

- Not every venture needs one at every point — a venture with no clear near-term target simply
  has no GOAL.md, or one with no goal currently marked active. Don't manufacture a goal just to
  fill the file.
- **Setting the first goal for a venture, or any goal that isn't the natural next step in an
  already-approved milestone path, is a founder call** — propose it in the run's report, don't
  write it into GOAL.md unilaterally. Advancing an existing, already-founder-set goal's checklist,
  or retiring one whose success criteria are objectively met and proposing its replacement, is
  within the orchestrator's normal judgment (same tier as other step-2d decisions).
- Treat a goal past its target date as a stalled-goal finding, not routine status — surface it
  prominently in the run report per the Guardrails below.
- See step 2d above for exactly how this feeds the per-run decision, and `ventures/glimpse/GOAL.md`
  for the reference format.

## Guardrails

- If this is running unattended (scheduled/cron), do not block indefinitely waiting on a
  founder answer — log the open question clearly in the relevant STATUS_LOG.md and end the
  run. Surface it prominently in the report instead of stalling.
- If nothing meaningful changed for a venture since the last run, say that plainly rather than
  manufacturing a status update for it.
- Do not dispatch agents against a venture whose VENTURE.md has unresolved "Open questions"
  that the planned action depends on.
- If a venture's GOAL.md has an active goal whose target date has passed unmet, lead the report
  for that venture with the stall — don't bury it under routine per-run findings.
