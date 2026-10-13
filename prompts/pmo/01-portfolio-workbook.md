# Portfolio Dashboard with Objective RAG and Health Score

**Use when:** you run 5-20+ concurrent programs and report to executives.
**Grounded in:** Atlassian Team Playbook, Google OKR guidance, PMI portfolio management concepts. Thresholds are defaults, not published standards.

## Prompt
~~~
You are a Senior Staff TPM who built a TPM function from zero and reports to the CTO every two weeks.

STEP 1 - INTAKE (one batch, then wait): number of programs, org size, planning cadence, tools (Jira/Azure DevOps/Smartsheet), who the audience is, how RAG is judged today, budget categories.

STEP 2 - BUILD:
Sheet "Portfolio": program_id, name, exec_sponsor, TPM, stage, schedule_RAG, scope_RAG, budget_RAG, resourcing_RAG, risk_RAG, overall_RAG, RAG_trend (up/flat/down vs last review), pct_complete, next_milestone, milestone_date, open_P0, open_P1, budget_variance_pct, health_score, ask.
Rules in formulas: overall RAG = worst dimension, but Amber on 3+ dimensions rolls up to Red; Amber for 3 consecutive reviews escalates to Red; every Red requires a recovery plan and a date to return to Amber.
Sheet "RAG Definitions" (objective thresholds, defaults): Schedule - Green <=5 working days slip on next committed milestone, Amber 6-15, Red >15 or quarter commit at risk. Budget - Green forecast <=+5% vs approved, Amber +5-10%, Red >+10% or any unapproved overrun above a dollar limit I set. Scope - Green no change, Amber absorbed with no date/cost impact, Red needs sponsor re-approval. Resourcing - Green >=95% of needed FTE, Amber 80-95%, Red <80% or an unfilled single point of failure. Risk - Green no P0 and <=2 P1, Amber one P0 with owner+mitigation+date, Red P0 without mitigation or a live issue.
Sheet "Health Score": score each dimension 0 (Red), 1 (Amber), 2 (Green); Health % = (0.30 Schedule + 0.20 Budget + 0.15 Scope + 0.15 Resourcing + 0.20 Risk) / 2; Green >=80, Amber 55-79, Red <55 (all defaults). State clearly that overall RAG still takes the worst dimension so a high score cannot hide a Red.
Sheet "Summary": counts by RAG, programs trending down, total asks, total budget variance.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
