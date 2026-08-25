# Glimpse — Venture Definition

> Maintained by the venture-orchestrator skill. Human-editable at any time; the orchestrator
> reads this before every run and proposes edits rather than silently rewriting it.

## What it is

Glimpse (glimpse.net.in) is an operating business serving university representatives who
travel across regions for admissions/outreach work. Three current service lines:

1. **Reservations** — manages travel/reservation logistics for university reps travelling in
   different parts (regions/countries).
2. **Merchandise** — procures and stores promotional/merchandise material ("PE Kits") in bulk
   at one place, supplying it to reps at lower cost than they'd get sourcing it themselves.
3. **Events** — manages events based on intake volume and requirement.

**Expansion in progress: "Sales Engine."** A model within Glimpse to be sold as a sales
engine for other businesses. Already scoped and underway per ClickUp's `Sales Engine
Milestones` list: M1 Learn Sales & Marketing Fundamentals (done), M2 Draft Sales Engine Offer
Hypothesis (done), M3 Validate Offer With Real Prospects (open), M4 Refine Offer Based on
Feedback (open), M5 First Pilot/Signed Commitment (open) — plus supporting milestones (set
pricing, basic business plumbing/contracts/invoicing, delivery capacity plan, an internal
proof asset from Glimpse's own BDE/KPI results). Backed by `BDE Team Ops` and `Lead Sourcing
Queue` lists (hiring and running Business Development Executives) — see
`ventures/glimpse/MILESTONES.md` Phase 2 for the live-synced version of this roadmap.

## Who it's for

University representatives and the institutions/platforms they work for (per prior ClickUp
signal: prospects span US/UK/AU/CA university admissions, NZ/EU/Asia universities, and
study-abroad platforms).

## Why IdeaAgent is being applied here

Glimpse is a real, already-operating business (not pre-idea) — this is the first venture
IdeaAgent's orchestrator runs against as an internal tool, rather than the dogfood-only
scaffold-testing IdeaAgent did on itself in Phase 0. The orchestrator's job here: read what's
actually happening in Glimpse's operations, find the single highest-leverage next action, and
get the right agents moving on it — same discipline, now pointed at a real business instead of
IdeaAgent's own bootstrap.

## Stage

**Operating, established.** Real team of at least 6 (founder Samyak Jain, Babita, Kaustav
Saha, Sachin Poddar, Syed Afsha Ali, Kanchan Thakur) with continuous task history in ClickUp
back to at least February 2026 (Sprint 9) across dozens of university partners (RIT, SLU,
Rockhurst, BGSU, Catalystia, IC3, and more). This is a running operating business, not an
early-stage one — revenue/financial figures specifically are still not known to the
orchestrator (no finance connector wired up), but operational activity is now fully visible.

## Known data sources — ClickUp mapping (confirmed 2026-08-18)

Workspace has two spaces: **Tasks** and **Vendors**. Day-to-day work does not use the
category-named lists below as working lists — it flows through **Sprint Folder → Sprint N**
(date-ranged, e.g. "Sprint 15 (10/8–13/9)"), which mixes all three service lines together by
date rather than by category. Mapping:

| Area | Where it actually lives | Notes |
|---|---|---|
| Reservations (flights/hotels/cabs/trains/venues) | Sprint N lists, described as tagged (`flight reservation`, `hotel reservations`, `cab reservations`, `venue booking`) — **correction 2026-08-21: tagging is barely used in practice**, see note below | Dedicated `Flight Reservations` / `Hotel Reservations` / `Venue Bookings` lists exist but aren't the live working lists |
| Merchandise / PE Kits | Sprint N lists, described as tagged (`merch`, `merch procurement`, `merch delivery`, `admit kit`, `pe`) — same correction | Dedicated `Merchendise` list exists but isn't the live working list |
| Events | Sprint N lists, described as identified by university/program tag (`rit`, `slu`, `ru`, `bgsu`, `catalystia`, `ic3`, `tiger pride`, `yield event`) — same correction | No dedicated events list — events are implicit in which university/tag a sprint task carries |

**Correction 2026-08-21:** the table above (written 2026-08-18) assumed tags exist but are used
*inconsistently*. A direct pull of Sprint 14 + Sprint 15 (52 tasks) found only **1 of 52** tasks
carries any ClickUp tag at all — tagging isn't inconsistent, it's essentially unused. Category
counts in `ventures/glimpse/GROWTH.md` are currently built by title-keyword matching instead,
which is workable but fragile (visa processing, vendor sourcing, and person-named tasks like
"Kanan Event" don't map cleanly). See MILESTONES.md Phase 1 and STATUS_LOG.md 2026-08-21.
| Sales Engine expansion | `Sales Engine Milestones` list (dedicated, actively used) + `BDE Team Ops` + `Lead Sourcing Queue` | This is the one area already organized by category, not by sprint |
| Vendors | `Vendors` space → `Vendor Master List` | Supports merchandise procurement |
| Misc/personal-admin | `Backlog` folder → `List` | Genuine catch-all — mixes real ops (stock checks, portal updates) with unrelated personal items (loan balances, gift arrangements) |
| IdeaAgent-tool housekeeping | `Tasks` space → `IdeaAgent` list | Already correctly separate — not Glimpse data |

**Implication for the orchestrator:** don't expect a clean per-category list to filter on.
Reservations/merchandise/events signal has to be pulled from the live Sprint list by tag/title
keyword, not by list ID. Sales Engine work is the exception — it already has clean, dedicated
lists.

## Founder decisions (locked 2026-08-18)

- IdeaAgent's orchestrator is now applied to Glimpse as a real, running business — not a
  hypothetical dogfood target.
- Glimpse is tracked as its own venture folder (`ventures/glimpse/`) with its own
  VENTURE.md / MILESTONES.md / GROWTH.md / STATUS_LOG.md, separate from IdeaAgent-the-tool's
  root-level docs.
- ClickUp itself is not being reorganized (moving ~300 historical, mostly-closed tasks between
  lists for a live 6-person tool has real risk and little payoff) — the orchestrator instead
  reads the existing sprint-based structure as-is, per the mapping above.

## Open questions (founder decisions — not agent-decidable)

- Are there other existing businesses beyond Glimpse that should also be onboarded as
  ventures under this same repo? (Founder: "later.")
- Should *new* (not historical) tasks going forward be filed into the category lists
  (Flight Reservations, Hotel Reservations, Merchandise, etc.) instead of only Sprint lists,
  to make future tracking cleaner? Not decided — flagging as a lightweight process change the
  founder may or may not want, not something to impose unilaterally.
- **New 2026-08-21:** should the team be asked to actually tag Sprint tasks going forward
  (reservation/merch/events)? Only 1 of 52 tasks in the current + prior sprint carries any tag,
  which is what forced a title-matching fallback for Phase 1 operational metrics (see GROWTH.md
  and MILESTONES.md Phase 1). Not imposing a process change unilaterally.
- **New 2026-08-22:** IdeaAgent has no GHL/CRM connector wired up. Now that the Stage 2 process
  is approved, the remaining M3 work (promoting the 8 Qualified leads to GHL, first contact) is
  genuine human/BDE work regardless — but even the mechanical "create the GHL record" step
  can't be automated by the orchestrator without one. Not urgent (this step was always meant to
  be a BDE's job per the approved process, not the orchestrator's), but worth the founder
  knowing the ceiling exists if he ever wants more of this loop automated.
- **New 2026-08-21, operational not strategic — worth the founder's eyes, not a blocker:** three
  separate, near-identical "hire BDE" tasks in `BDE Team Ops` (Sprint 15) — "Hire 2-3x BDE
  Interns," "Hire 1x Full-Time BDE," "Hire BDE(s) — Business Development Executive Recruitment"
  — all assigned to Samyak, same urgent priority, same due date 2026-07-22 (a month overdue),
  all still open. Reads as the same need logged three times rather than genuinely distinct work;
  the orchestrator did not merge/close any of them (no unilateral ClickUp reorganization, per
  this file's own founder decision above) — flagging for a human call. **Update 2026-08-23:**
  confirmed still all open, unmerged, same due date — now 32 days overdue. Also turned up
  cross-listed in the Sprint 15 pull (not just `BDE Team Ops`), which wasn't independently
  verified before; noting the discrepancy rather than assuming either list membership is wrong.
  **Update 2026-08-24:** still open, unchanged, now 33 days overdue.
  **Update 2026-08-25:** not re-verified directly this run (conserving ClickUp read quota); the
  BDE hiring gate task (86d3ucd9p) was checked directly and is still unchanged since
  2026-08-19, which is consistent with no hiring movement, but that's an inference for the
  duplicate tasks specifically, not a fresh read of them.
