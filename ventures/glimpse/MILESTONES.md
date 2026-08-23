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
      case unresolved across 2 sprints (6+ weeks). **Update 2026-08-23:** confirmed still open,
      due date 2026-08-02 (21 days overdue), `date_updated` 2026-08-06 (17 days with no recorded
      activity) — comments not checked this pull (rate-limited), so recent human activity on the
      task itself can't be ruled out, but the task's own timestamps show no movement in over two
      weeks. Worth a direct human check given how much time has passed.
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
