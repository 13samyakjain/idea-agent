# Glimpse — Growth Framework

> What to measure at each stage, and the current honest values. The orchestrator updates the
> "Current" column only with real, checkable numbers — never estimates or placeholders dressed
> up as data. If something isn't measurable yet, it says "not yet measurable," not "0."

## Stage-appropriate metrics

| Stage | What matters | Why |
|---|---|---|
| Onboarding (current) | Is Glimpse's real operational data (ClickUp) actually visible and correctly interpreted by the orchestrator? | Can't optimize what isn't seen yet |
| Operational visibility | Reservation volume, PE Kit procurement cost/cadence, event count vs. intake | Baseline before the orchestrator can suggest real improvements |
| Sales engine expansion | Once scoped: pipeline/leads for the sales-engine offering | Only relevant after Phase 2 in MILESTONES.md is defined |

## Current metrics

| Metric | Value | As of |
|---|---|---|
| Reservation volume (task count, title-matched — see method caveat) | Sprint 14 (6/7–9/8): 9 tasks (2 open, 7 closed). Sprint 15 (10/8–13/9, current): 2 tasks (0 open, 2 closed) — re-confirmed 2026-08-23, unchanged. Excludes 5 visa-processing tasks across both sprints, which don't cleanly fit "reservation" per the current tag definitions — see MILESTONES.md Phase 1 note. | 2026-08-23 |
| PE Kit procurement volume (task count, title-matched — see method caveat) | Sprint 14: 9 tasks (3 open, 6 closed) — not re-pulled 2026-08-23. Sprint 15 (current, re-pulled from raw task list 2026-08-23 second pass): **6 tasks (4 open, 2 closed)** on unambiguous merch/PE-Kit titles only, or up to **9 tasks (5 open, 4 closed)** including ambiguous overlaps ("Bookings and Merch Request..." ×2, "Stock Check For All the Universities"). Earlier same-day figures of 11 and 4 were both keyword-overlap artifacts, not real swings — see Instrumentation TODO below for the root cause and a fix recommendation. | 2026-08-23 |
| PE Kit procurement cost baseline | still not yet measurable — task counts above are volume only, no cost/financial data available from ClickUp | 2026-08-21 |
| Events managed (university/program-named task count, title-matched) | Sprint 14: 6 tasks (1 open, 5 closed — all SLU/IC3). Sprint 15 (current): 4 tasks (4 open, 0 closed) — re-confirmed 2026-08-23, unchanged (BGSU, Catalystia, SLU, IC3). | 2026-08-23 |
| Sprint 15 total volume (all categories, title-matched + unclassified) | 27 tasks total: 21 open, 6 closed (5 complete + 1 cancelled). First time this total has been pulled — no prior-date comparison exists. | 2026-08-23 |
| Team size | 6 confirmed via ClickUp assignees: Samyak Jain (founder), Babita, Kaustav Saha, Sachin Poddar, Syed Afsha Ali, Kanchan Thakur | 2026-08-18 |
| Sales Engine milestones | 2 of 5 core milestones done (M1, M2); M3-M5 open | 2026-08-18 |
| Leads in qualification funnel (`Lead Sourcing Queue`) | **25 of 25 reviewed and written to ClickUp** (complete as of 2026-08-21): **8 Qualified**, **9 Borderline** (each with an escalation comment tagging Samyak for a judgment call), **8 Disqualified**. Stage 2 assignment process approved by the founder 2026-08-20 (confirmed 2026-08-22) — no longer gated. Promotion of the 8 Qualified leads to GHL is now unblocked but still not done; that's human/BDE work, flagged to the team via ClickUp comment 2026-08-22. | 2026-08-22 |
| Orchestrator passes completed against Glimpse | 6+ (2026-08-18 through 2026-08-21, multiple same-day passes on some dates) | 2026-08-21 |

## Instrumentation TODO

- [x] Get the ClickUp list/space mapping from MILESTONES.md Phase 0 done — that unlocks real
      numbers for every row above
- [ ] Ask the founder for a baseline read on current reservation volume, PE Kit costs, and
      event cadence rather than inferring from incomplete ClickUp data — still needed for cost
      data specifically, since task counts alone don't give a cost baseline
- [ ] **New 2026-08-21 — tag hygiene is broken, task counts above are a fragile proxy.** Pulled
      Sprint 14 + Sprint 15 (52 tasks total) directly: only **1 of 52** carries any ClickUp tag
      at all (verified against a raw task fetch, not just the list-summary endpoint). The
      reservation/merch/events counts above were built by title-keyword matching instead of the
      tag taxonomy VENTURE.md describes, because the taxonomy isn't actually being used day to
      day. Title-matching is fragile: several tasks don't cleanly categorize (5 visa-processing
      tasks that aren't literal bookings, vendor-sourcing tasks upstream of reservations, a
      "Kanan Event" merch task where "Kanan" is a person not a university). Until tagging is
      adopted by the team or the method changes, treat these counts as directional, not exact —
      flagged in ventures/glimpse/STATUS_LOG.md 2026-08-21, not something to silently trust.
- [x] Retry the ClickUp writes for the 17 leads whose verdicts were ready but unwritten — done
      2026-08-21, all 17 plus one missing comment written cleanly in one serialized pass, zero
      rate-limit errors. See STATUS_LOG.md 2026-08-21 entry.
- [x] Structural fix validated: a single agent making ClickUp calls strictly sequentially (no
      parallel dispatches) completed 44 ClickUp tool calls (17 status/description updates + 7
      comments) with zero `RATE_LIMIT_EXCEEDED` errors, where 3 parallel agents tripped a ~24h
      block after only 8 writes on 2026-08-20. Confirms concurrency (not call volume) was the
      actual cause. Serialize future ClickUp-heavy dispatches against this venture as the
      default going forward.
- [ ] **New 2026-08-23 — even strictly sequential reads now hit the account-level rate limit
      after only 5 calls** (vs. 44 sequential writes clean on 2026-08-21, and an unrelated
      4-read cooldown on 2026-08-22). The limit appears to be a rolling account-wide quota, not
      specific to write volume or this venture's call pattern — worth the founder knowing this
      is a ClickUp-account-level ceiling, not something the orchestrator's call discipline can
      fully work around. Blocked a same-run comment check on the Deborah/Peter visa task and a
      direct `BDE Team Ops` list query (see STATUS_LOG.md 2026-08-23); retry window given as
      ~184 minutes from the 2026-08-23 pull.
- [x] **2026-08-23 (second pass) — PE Kit/Merch count swing root-caused, not a real business
      change.** Pulled the raw Sprint 15 task list directly (27 tasks, via `clickup_filter_tasks`
      on the list ID, not title-keyword search) and hand-checked every title. Finding: the
      11→4 swing wasn't a real 2-day change, it's **category keyword overlap causing
      double-counting** that different passes resolve differently. Two "Bookings and Merch
      Request..." tasks (both complete) match both the reservations keyword ("bookings") and
      the merch keyword ("merch") — they're the entire reservations=2 count *and* also get
      pulled into merch counts by some passes but not others. Similarly "Merchandise
      Procurement Request for IC3 and Upcoming Fairs" and "Change Of Slu Merch Confirmation"
      match both the merch keyword and an events keyword (IC3, SLU). Depending on inclusion
      rules, the honest current merch/PE-Kit-titled task count in Sprint 15 ranges from **6
      tasks (4 open, 2 closed)** — unambiguous "merch"/"merchandise"/"PE Kit" titles only — up
      to **9 tasks (5 open, 4 closed)** if "Bookings and Merch Request..." (×2) and "Stock
      Check For All the Universities" are included. Neither the earlier 11 nor the 4 reflects a
      real business swing; both were artifacts of which keyword set that pass happened to use.
      **This is the actual limitation of title-matching, not a data problem to re-pull past** —
      fixing it needs either team tag adoption (flagged in VENTURE.md open questions) or a
      fixed, documented category-assignment rule that resolves overlaps (e.g. "Bookings and
      Merch" tasks count toward reservations only, not merch) rather than ad hoc per-pull
      keyword lists. Recommend the latter as a lightweight fix the orchestrator can make
      unilaterally next pass, since it's a measurement-method decision, not a founder call.
