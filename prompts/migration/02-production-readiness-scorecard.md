# Production Readiness Review (PRR) Scorecard

**Use when:** deciding whether a service is ready to move to a new platform or launch.
**Grounded in:** Google SRE book (launch checklist, production readiness review) and Kubernetes production best practices.

## Prompt
~~~
You are an SRE-minded Senior Staff TPM. Build a weighted Production Readiness Review scorecard.

STEP 1 - INTAKE (one batch, then wait): target platform, service types (stateless/stateful/batch), tier definitions, existing standards (SLOs, runbooks, security baseline), who signs off. Default to Kubernetes if I do not say.

STEP 2 - BUILD:
Sheet "Criteria": criterion, what "2 (complete)" means, what "1 (partial)" means, what "0 (absent)" means, evidence required, weight. Use these default criteria and weights, adapting wording to my platform: Observability 15 (metrics, logs, traces, dashboards); SLOs, alerting and on-call runbooks 15; Resilience 15 (probes, disruption budgets, resource requests/limits, autoscaling, graceful shutdown); Deploy and rollback 15 (automated pipeline, tested rollback); Security 10 (image scanning, secrets management, network policy, RBAC); Capacity and load test at 1.5x peak 10; Data and state 10 (backup/restore tested, migration plan); Dependencies and config parity 5; Docs and ownership 5.
Sheet "Scorecard": one row per service with a 0/1/2 score per criterion, weighted total as a percentage (formula), result (formula): PASS >=85%, CONDITIONAL 70-84% (needs action owner + date), FAIL <70%; Tier 0/1 require >=90%; ANY score of 0 on rollback, alerting or secrets management is an automatic FAIL regardless of total. Add reviewer, date, exceptions granted with expiry date.
Sheet "Actions": gaps from conditional services with owner, due date, status.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~

## Notes
Weights, pass thresholds and auto-fail rules are defaults. Run it on 3 pilot services, see where the scores bunch up, then recalibrate.
