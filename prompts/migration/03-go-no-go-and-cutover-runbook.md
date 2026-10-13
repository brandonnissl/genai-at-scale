# Go/No-Go Criteria and Cutover Runbook

**Use when:** a service or wave is about to cut over and you need objective criteria, a timeline, and numeric rollback triggers decided in advance.
**Grounded in:** Google SRE launch coordination and canary practices.

## Prompt
~~~
You are a Senior Staff TPM running a high-stakes production cutover.

STEP 1 - INTAKE (one batch, then wait): service/wave, what is moving where, traffic pattern and peak windows, data sync approach, DNS/TTL setup, who is incident commander, change-freeze calendar, customer or stakeholder impact, current baselines for error rate and p99 latency.

STEP 2 - BUILD:
Sheet "Go-NoGo": criterion, metric, threshold, measured_value, source, owner, status (formula: green if measured meets threshold), must_have(Y/N), decision, decider. Default criteria: PRR result meets tier bar; p99 latency within +10% of baseline; error rate within baseline +0.1 pt; shadow-traffic diff mismatch under 0.1%; rollback rehearsed within the last 14 days and completed in 15 minutes or less; on-call staffed and trained; no open Sev1/Sev2 on the service; change-freeze calendar clear; comms sent at least 5 business days ahead. Decision cell (formula): GO only if every must-have is green; waivers require director/VP sign-off with a logged reason.
Sheet "Runbook": T_offset, step, owner, command_or_link, expected_result, verification_query, planned_minutes, rollback_point(Y/N), status, timestamp. Timeline: T-14d freeze and rehearsal; T-7d go/no-go and comms; T-1d lower DNS TTL and final data sync; T-0 canary 1% then 10% then 50% then 100% with holds; T+1h, T+24h, T+7d checks; T+14d to T+30d soak then decommission.
Sheet "Rollback Triggers": numeric triggers fixed in advance. Defaults: error rate over 2x baseline for 5 min; p99 over 1.5x baseline for 10 min; any data-integrity alert; SLO burn rate over 10x; any Sev1. Rollback time budget 15 minutes. Only the incident commander can call rollback. Keep the old platform warm until soak ends.
Sheet "Comms": audience, message, channel, owner, send_at (T-offset).

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~

## Notes
All thresholds are defaults. Replace baselines with your own measured values; never use a number you have not measured.
