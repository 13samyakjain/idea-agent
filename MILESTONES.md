# IdeaAgent — Milestones

> Status legend: `[ ]` not started · `[~]` in progress · `[x]` done · `[!]` blocked
> The orchestrator updates status and appends new milestones as they're identified. It does not
> delete or reword existing milestones without flagging the change in STATUS_LOG.md.

## Phase 0 — Foundation (done)

- [x] Define venture-orchestrator agent and its playbook
- [x] Stand up venture docs (this file, VENTURE.md, GROWTH.md, STATUS_LOG.md)
- [x] Daily cloud routine's push-permission issue found and fixed (2026-08-18) — reliability
      clock for "3 consecutive clean days" now actually running, not evidence of the days
      themselves yet
      **Correction 2026-08-27:** the "fixed" framing was premature — the push step has since
      failed intermittently (2026-08-24, 2026-08-25, 2026-08-27 morning), most recently stranding
      4 days / 5 commits before a later run caught and pushed it. Not reverting this checkbox
      (the original permission issue is genuinely resolved) but the broader "runs reliably end
      pushed" property is not yet true — see root STATUS_LOG.md 2026-08-27 for detail and an open
      recommendation to harden the push step itself rather than keep relying on the next run's
      defensive recovery.
- [x] First dogfood cycle produces a status report a human would actually find useful (the
      Venture Console artifact, shipped 2026-08-10, used same-day to act on 3 real decisions)

## Phase 1 — Multi-venture structure (current, revised 2026-08-18)

> Replaces the original "concept validation" phase, which was about testing whether other
> founders would want to buy IdeaAgent. Retired 2026-08-18 — IdeaAgent is not sold to other
> founders (see VENTURE.md). `DISCOVERY_GUIDE.md` removed; the 3–5 discovery-conversation task
> is dropped, not just deferred.

- [x] Human answers the open questions in VENTURE.md (product surface, ship model, first user)
- [x] Pivot decision locked: internal tool, not sold to founders (2026-08-18)
- [x] Multi-venture repo structure stood up (`ventures/<name>/`); Glimpse onboarded as the
      first tracked venture
- [x] Orchestrator completes a full daily pass against Glimpse specifically (not just
      IdeaAgent-tool housekeeping) for 3 consecutive days — satisfied across 2026-08-18,
      2026-08-19 (multiple passes), and 2026-08-20; see `ventures/glimpse/STATUS_LOG.md`
- [ ] Founder confirms the orchestrator surfaced something genuinely useful for Glimpse

## Phase 2 — Additional ventures (not started, re-scoped 2026-08-18)

> Was "MVP: package IdeaAgent as an installable skill pack for others." Retired along with the
> sell-to-founders model — flagging rather than deleting per this file's own convention.

- [ ] Onboard any additional existing businesses the founder wants tracked, using the
      `ventures/glimpse/` structure as the template
- [ ] Harden the orchestrator's multi-venture loop (SKILL.md) based on what actually breaks
      running it against a real business instead of a scaffold

## Phase 3 — Sales-engine expansion (not started, not scoped)

> Was generic "Growth." Repurposed 2026-08-18 to track Glimpse's planned expansion — see
> `ventures/glimpse/MILESTONES.md` Phase 2 for the venture-level version of this; this row
> tracks it only if it becomes a cross-venture concern.

- [ ] TBD — defined once Glimpse's "sales engine for other businesses" model is scoped
