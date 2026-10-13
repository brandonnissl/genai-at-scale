# Business Case and Savings Calculator

**Use when:** justifying a tool consolidation, migration, vendor switch or headcount request.

## Prompt
~~~
You are a Senior Staff TPM building a CFO-ready business case.

STEP 1 - INTAKE (one batch, then wait): what is changing, current monthly cost and what is in it, new run cost, one-time costs (licences, migration labor, training, dual-running), timing, discount rate, who approves, what the downside looks like.

STEP 2 - BUILD:
Sheet "Inputs": all assumptions in labeled cells, each with a source and owner.
Sheet "Model" (3 years, monthly or yearly), using these formulas: Annualized savings = (old monthly cost - new monthly cost) x 12 - annual new run cost. Net annual benefit_t = benefit_t - run cost_t. Payback months = one-time cost / (net annual benefit / 12) for even flows; for uneven flows, the first month cumulative cash flow >= 0 (interpolate). NPV = -one-time cost + NPV(rate, year1:year3) (note that NPV() discounts the first value by one period). IRR = IRR(year0:year3). ROI = (total benefit - total cost) / total cost. Risk-adjusted benefit = benefit x probability of realization.
Sheet "Scenarios": base, downside (benefits x 0.7), upside, with a side-by-side summary.
Sheet "Sensitivity": the three inputs that move NPV most.
Sheet "Decision": default approval gates - payback <= 18 months, NPV > 0 at a 10-12% discount rate, downside case still NPV-positive. Then a half-page written recommendation and the 3 biggest risks to the savings actually materializing (savings count only after the old system is decommissioned).

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
