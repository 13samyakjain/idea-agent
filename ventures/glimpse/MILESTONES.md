# Glimpse — Milestones

> Status legend: `[ ]` not started · `[~]` in progress · `[x]` done · `[!]` blocked
> The orchestrator updates status and appends new milestones as they're identified. It does not
> delete or reword existing milestones without flagging the change in STATUS_LOG.md.

## Phase 0 — Onboarding (done)

- [x] Business defined in VENTURE.md (service lines, stage, known data sources)
- [x] Map ClickUp lists/spaces to Glimpse's three service lines — done 2026-08-18: no clean
      per-category lists exist for reservations/merchandise/events (all three flow through
      date-based Sprint lists, tag-identified); Sales Engine work is the exception with its own
      dedicated lists. See VENTURE.md's mapping table.
- [x] First orchestrator pass against real Glimpse ClickUp data completes and surfaces a
      genuinely useful next action (not just "no data" or IdeaAgent-tool housekeeping) — done
      as of 2026-08-20: ran the first-ever ICP qualification review against all 25
      `Lead Sourcing Queue` leads (previously 0 reviewed since the 2026-08-19 Apollo export)
- [ ] Founder confirms that surfaced action was actually useful

## Phase 1 — Operational visibility (in progress, first pass 2026-08-21)

> First real pull done 2026-08-21 against Sprint 14 + Sprint 15 (52 tasks), but not by tag as
> originally planned — only 1 of 52 tasks in that window carries any ClickUp tag, so the
> category counts below are title-keyword matches, a fragile proxy until tag hygiene improves
> or the method changes. See GROWTH.md Instrumentation TODO and STATUS_LOG.md 2026-08-21.

- [~] Reservations: current state, volume, pain points visible to the orchestrator — first
      count in GROWTH.md (title-matched, not tag-based); pain points found: a Deborah/Peter visa
      case unresolved across 2 sprints (6+ weeks). **Update 2026-08-23 (second pass):** comments
      finally checked (rate limit had blocked this earlier today). Corrects the "no activity"
      framing — there was real movement: Babita commented 2026-07-27 that Deborah's (and her
      son's) visa application was submitted with an appointment scheduled for **2026-08-30**,
      but Peter's Invitation Letter is still waiting on a signature. Kanchan Thakur nudged
      Babita directly in a comment on 2026-08-05 ("kindly update on this") — **18 days with no
      reply**, and the task record itself shows no update since. The real story isn't "stalled
      task," it's "a direct internal ask has gone unanswered for over two weeks, with a
      client-facing appointment 7 days out that depends on the missing piece (Peter's signed
      invite letter)." Worth the founder's direct attention now, more so than before.
      **Update 2026-08-24:** still no reply from Babita — Kanchan's nudge is now 19 days
      unanswered, and the appointment is 6 days out. Escalated with a direct comment to Samyak
      on the task itself (previously only Kanchan had asked Babita); see STATUS_LOG.md
      2026-08-24.
      **Update 2026-08-25:** re-read all 4 comments on the task directly — still zero reply from
      Babita or any other movement since yesterday's direct escalation to Samyak. Appointment is
      now 5 days out (2026-08-30), signature has been pending 29 days, Kanchan's original nudge
      is 20 days unanswered. Did not post a second escalation comment today (yesterday's direct
      tag to Samyak already stands unanswered; a repeat this soon would be noise, not new
      information) — flagged directly to the founder via notification instead. See
      STATUS_LOG.md 2026-08-25.
      **Update 2026-08-26:** re-checked directly (task record + all 4 comments) — still no reply
      from Babita, no new comments, `date_updated` unchanged since the 2026-08-24 03:35 UTC
      escalation. Appointment is now **4 days out** (2026-08-30), signature pending 30 days,
      Kanchan's nudge unanswered 21 days, and Samyak's own direct escalation now unanswered 2
      days. No new ClickUp comment posted (same reasoning as 2026-08-25 — would be noise on an
      already-unanswered thread); flagged to the founder via notification again given the
      shrinking runway. See STATUS_LOG.md 2026-08-26.
      **Update 2026-08-26 (second pass, ~11h later):** ClickUp thread itself still unchanged, but
      Google Calendar shows a "Call with Glimpse" meeting was scheduled same-day and held
      12:30–13:00 UTC, with Peter (the person whose signature is the blocker) as an attendee
      alongside Samyak, Kaustav, and Babita. Outcome not visible from the calendar event or
      ClickUp — no comment or status update reflecting it yet. Not re-notifying the founder (he
      was an invitee). See STATUS_LOG.md 2026-08-26 second entry.
      **Update 2026-08-27:** re-checked directly (task record + all 4 comments) — still zero
      reply from Babita, no new comments, `date_updated` unchanged since the 2026-08-24 03:35 UTC
      escalation. Yesterday's call (Peter/Babita/Samyak/Kaustav) has still left no trace in
      ClickUp — nothing confirms whether the signature issue was actually resolved. Appointment
      is now **3 days out** (2026-08-30), signature pending 31 days, Kanchan's nudge unanswered
      22 days, Samyak's own escalation unanswered 3 days. Notified the founder again given the
      combination of shrinking runway and an unconfirmed outcome from a call he already attended
      — the risk now is assuming the call resolved it when the record doesn't show that. See
      STATUS_LOG.md 2026-08-27.
- [~] Merchandise/PE Kits: procurement cadence, cost baseline, storage/fulfillment visible —
      task-count cadence now in GROWTH.md; cost baseline still not measurable (no financial data
      in ClickUp)
- [~] Events: intake-to-event pipeline visible — task count now in GROWTH.md (title-matched,
      keyed to university/program name in the title, not a tag)

## Phase 2 — Sales engine expansion (in progress, scoped 2026-08-18)

> Already underway per ClickUp's `Sales Engine Milestones`, `BDE Team Ops`, and
> `Lead Sourcing Queue` lists — not something to newly define, just to sync and track here.

- [x] M1: Learn Sales & Marketing Fundamentals
- [x] M2: Draft Sales Engine Offer Hypothesis
- [ ] M3: Validate Offer With Real Prospects — not done yet. Update 2026-08-21: all 25/25
      `Lead Sourcing Queue` leads now qualified/disqualified in ClickUp (8 Qualified, 9
      Borderline pending Samyak's judgment calls, 8 Disqualified) — the qualification pass
      itself is complete. **Update 2026-08-22: the Stage 2 assignment-process gate is now
      cleared** — Samyak approved it via comment on task 86d3t4bg7 (round-robin assignment,
      Kanchan Thakur as process owner; see `SALES_ENGINE_PROCESS.md`). What's left for M3 is no
      longer a founder decision — it's the actual human work of promoting the 8 Qualified leads
      to GHL and a BDE making first contact. IdeaAgent has no GHL/CRM connector, so the
      orchestrator can't do the promotion itself; it flagged the unblock to the team (see
      STATUS_LOG.md 2026-08-22).
- [ ] M4: Refine Offer Based on Feedback
- [ ] M5: First Pilot / Signed Commitment
- [ ] Supporting: hire 1x full-time BDE + 2-3x BDE interns (in progress in ClickUp)
- [ ] Supporting: set Sales Engine pricing (deliberately last, per ClickUp task title)
- [ ] Supporting: set up basic business plumbing (contract + invoicing)
- [ ] Supporting: finalize delivery capacity plan
- [ ] Supporting: build proof asset (internal Glimpse BDE/KPI result)
