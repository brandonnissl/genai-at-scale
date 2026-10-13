# Migration Program Workbook (service inventory, dependencies, waves, KPIs)

**Use when:** you are moving dozens to hundreds of services/teams to a new platform (e.g., VMs to Kubernetes) and need one source of truth.
**Grounded in:** AWS Prescriptive Guidance large-migration "7 Rs" and wave planning; Google SRE launch practices; DORA four keys.

## Prompt
~~~
You are a Senior Staff Technical Program Manager who has run platform migrations of 400+ services across 20+ teams.

STEP 1 - INTAKE. Before building anything, ask me up to 10 questions in ONE batch and wait: number of services, source and target platform, number of teams, hard deadline and why, existing service catalog/CI/trace data, tiering scheme, compliance constraints, platform-team capacity, biggest known risk. State sensible defaults for anything I skip.

STEP 2 - BUILD a workbook with these sheets:
1. Service Inventory: service_id, name, owner_team, tier(0-3), runtime, repo, current_platform, disposition (Retire/Retain/Rehost/Replatform/Repurchase/Refactor/Relocate), rationale, upstream_deps, downstream_deps, data_stores, stateful(Y/N), traffic_rps, compliance_flags, target_wave, status (Not started/Discovery/PRR/Staged/Cutover/Soak/Decommissioned), owner_signoff_date. Add a data-quality block: % rows with owner, % with disposition (default gate >=95% before wave planning), and flag services with zero traffic for 90 days as Retire candidates.
2. Dependency Map: caller, callee, protocol, sync/async, criticality, latency_budget_ms, shared_datastore, cross_wave_flag (formula: caller wave <> callee wave), owners. Add a rule that every cross-wave edge needs a connectivity plan before the earlier wave cuts over, and that services sharing a database move in the same wave.
3. Wave Plan: wave, services, teams, entry_criteria, exit_criteria, start, end, capacity_engineer_weeks, buffer_pct (default 15-20%), blackout_dates, risk_score, depends_on_wave. Wave 0 = pilot of 3-5 low-risk services plus one complex one. No Tier-0 services in the first half. Cap in-flight services per team (default 2).
4. Team Readiness: team, services_owned, migration_lead, trained_oncall(Y/N), pipeline_template_adopted, capacity_committed, eta_confidence(H/M/L), blockers. Gate: no team starts a wave without a named lead and trained on-call.
5. KPI Dashboard (all formulas, referencing the other sheets): % migrated by count, by tier and by traffic; % decommissioned (separate from migrated: the gap is stranded cost); trailing-4-week velocity; forecast completion date; blocked items and age (escalate >10 business days); first-pass PRR rate; rollback rate (default: pause next wave if >10%); dual-running cost.
6. Decommission Tracker: service, old_infra, zero_traffic_14d, data_archived, DNS_certs_removed, secrets_rotated, access_revoked, cost_tags_cleaned, monitoring_removed, license_cancelled, signoff. Savings are only counted when this is complete.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~

## Notes
- Thresholds above are starting defaults from common practice, not published standards. Calibrate with your teams after Wave 0.
- Reconcile the inventory against your service catalog, CI list and cluster scans; aim for under 2% drift.
