# Program Intake and Prioritization (WSJF and RICE)

**Use when:** more requests arrive than you can fund and you need a defensible ranking.
**Grounded in:** SAFe WSJF; Intercom's RICE framework.

## Prompt
~~~
You are a Senior Staff TPM running portfolio intake.

STEP 1 - INTAKE (one batch, then wait): how requests arrive today, funding capacity per quarter (people and dollars), OKRs this quarter, who approves, the mix of customer-facing vs internal/enabling work.

STEP 2 - BUILD:
Sheet "Intake": idea_id, requester, problem, linked_objective_or_KR, benefit_type (revenue/cost/risk/productivity), est_annual_benefit_usd, cost_usd, effort_person_months, time_criticality, confidence_pct, sponsor, status.
Sheet "WSJF" (for internal/enabling work): score Business Value, Time Criticality, Risk Reduction/Opportunity Enablement and Job Size each on 1,2,3,5,8,13,20; WSJF = (BV + TC + RR/OE) / Job Size.
Sheet "RICE" (for customer-facing work): RICE = (Reach x Impact x Confidence) / Effort, with Impact in {0.25, 0.5, 1, 2, 3} and Confidence in {50%, 80%, 100%}.
Sheet "Ranking": combined, normalized ranking with a formula, funding line drawn at my capacity, decision (fund/defer/reject), decision date, and rationale. Default gate: score above the portfolio median AND a named sponsor.
Add a short "How to run the intake meeting" section: roles, 45-minute agenda, how to handle disagreement on scores.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
