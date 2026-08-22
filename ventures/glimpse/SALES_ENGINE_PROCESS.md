# Glimpse Sales Engine — Lead-to-Close Process

> **Approved by Samyak, 2026-08-20** (confirmed via ClickUp comment on task 86d3t4bg7, updated
> 2026-08-22). No longer a draft — this is the operating process. Proposed by the orchestrator
> 2026-08-18; the two open items below were resolved by the founder on approval.

## Stage 1 — Qualification funnel (already exists, working as designed)

Documented in ClickUp's `Lead Sourcing Queue` list description — not being redefined here,
just restated so it's visible in one place with Stage 2:

1. Apollo export → one task per company, status "New Export"
2. Reviewer runs the ICP Qualification Checklist, logs pass/fail per criterion, status
   "Under Review"
3. Qualified → contact/opportunity created in GHL's "Researched" stage, task marked complete
   ("Promoted to GHL")
4. Disqualified → task marked complete ("Disqualified" + reason, avoids re-researching later)
5. Borderline (missing exactly 1 criterion) → priority "urgent", tag Samyak for a judgment call

**Current status: unused, not broken.** Zero tasks have ever been logged in this list — the
process is sound but nothing has been fed into step 1 yet. That's a sourcing/execution gap
(someone needs to actually run Apollo exports), not a process gap.

## Stage 2 — Working a promoted lead (the actual gap — this is new)

Nothing currently defines what happens once a lead is "Promoted to GHL." This is the same gap
that let 5 real replies sit unassigned for 3-5+ weeks before anyone caught it. Proposed:

1. **Assignment trigger.** The moment a lead is promoted to GHL "Researched," it must be
   assigned to a specific BDE within 24 hours — not left in a shared/unassigned state. Whoever
   promotes it (per Stage 1) proposes an assignee; the BDE lead (or Samyak, until that role
   exists) confirms.
2. **First-touch SLA.** Assigned BDE makes first contact within 48 hours of assignment. If
   that can't happen (capacity, out of office), it gets explicitly reassigned — not silently
   dropped.
3. **Follow-up cadence.** If no response: re-touch at day 4, day 10. No response by day 14 →
   mark "stale," move to a recycling status (not deleted — revisit in a quarter), and log why
   it went cold (no fit, bad timing, wrong contact) so the qualification checklist can improve.
4. **Every call recorded.** Fathom notetaker on for every call — already flagged as a
   requirement in `BDE Team Ops`, just formalizing it as part of this process rather than a
   standalone task.
5. **Stale-lead escalation.** Any GHL lead untouched for 5+ days with no status update auto-
   flags to Samyak — same escalation pattern Stage 1 already uses for borderline leads, reused
   here for consistency rather than inventing a second pattern.
6. **Weekly rollup.** Each BDE reports: leads currently active, leads promoted this week,
   leads gone stale this week, and why. This is also what makes GROWTH.md's Sales Engine
   metrics real instead of "not yet measurable."

## Resolved by founder (2026-08-20)

- **Assignment rule:** round-robin by default. Takes effect once there's more than one BDE and
  a promoted lead to assign.
- **Process owner** (until the full-time BDE hire lands): Kanchan Thakur — she already owns
  BDE hiring coordination, so assignment confirmation + the weekly rollup fold into the same
  role.

## Correction (2026-08-22)

The institutional-partnerships onboarding brief referenced in task 86d3t4bg7's description
(the "217 researched contacts" / "5 stale replies" framing, drafted 2026-07-22) has been
superseded: verified live against GHL, then corrected again by Samyak — the entire 217-contact
backlog, including the 6 that reached opportunities, is not relevant. A new BDE's real
first-30-days plan starts at the Stage 1 qualification funnel above instead.
