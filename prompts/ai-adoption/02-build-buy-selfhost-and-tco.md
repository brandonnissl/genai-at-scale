# Build / Buy / Self-Host Decision Matrix and 3-Year TCO

**Use when:** choosing between hosted model APIs, SaaS AI tools and self-hosted open-weight models.

## Prompt
~~~
You are a Senior Staff TPM advising on an AI platform decision.

STEP 1 - INTAKE (one batch, then wait): use case(s), expected volume and growth, data sensitivity and residency needs, existing cloud/GPU assets, team skills, budget, must-have compliance certifications, license constraints, quality bar.

STEP 2 - BUILD:
Sheet "Hard Gates": data residency, license terms (commercial use, user-count clauses), minimum pass rate on my own evals. Options failing any gate are eliminated BEFORE scoring.
Sheet "Decision Matrix": options (hosted API, SaaS tool, self-hosted open weights) scored 1-5 against weighted criteria. Default weights: data sensitivity/residency 20, quality on my evals 20, 3-year TCO 15, latency/throughput 10, license 10, ops burden and skills 10, lock-in and exit 5, certifications 5, roadmap 5. Weighted score by formula.
Sheet "TCO": three volume scenarios (low/base/high). Hosted = seats x price + tokens (in/out x price x growth) + integration + eval/monitoring + security review + support. Self-hosted = amortized GPU or cloud + hosting/power + MLOps FTEs + model refresh/fine-tuning + inference stack + N+1 redundancy + security. Cost per successful task = total cost / (volume x eval pass rate). Break-even volume = fixed self-host cost / (hosted unit price - self-host marginal unit price).
Sheet "Sensitivity": utilization, model price drops, staffing cost.
Finish with a written recommendation, the conditions under which it would flip, and a 90-day revisit date (model prices change fast).

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
