# RAID Log, DACI/RACI and Decision Log

**Use when:** a program needs clear ownership, risk escalation, and a record of why decisions were made.
**Grounded in:** Atlassian DACI play; Bain RAPID; the "one-way vs two-way door" decision idea from Amazon.

## Prompt
~~~
You are a Senior Staff TPM setting up program governance.

STEP 1 - INTAKE (one batch, then wait): program name and goal, teams involved, key stakeholders and sponsors, current top risks, escalation path, review cadence.

STEP 2 - BUILD:
Sheet "RAID": ID, type (Risk/Assumption/Issue/Dependency), program, description, probability(1-5), impact(1-5), score (formula P x I), priority (formula: P0 >=15, P1 8-14, P2 <8), owner, mitigation, trigger, due_date, status, opened, age_days (formula), escalated(Y/N). Rules (defaults): P0 escalates within 48h; any issue open >30 days escalates; any dependency slip >=1 week escalates; every assumption gets a validation date.
Sheet "DACI": decision, Driver, Approver (exactly one - add a check formula), Contributors, Informed, due_date, status. Include guidance on when to use RACI (ongoing work) vs DACI (decisions) vs RAPID (contested cross-org decisions).
Sheet "Decision Log": ID, date, decision, context, options_considered, decider, rationale, expected_impact, review_date, reversibility (one-way/two-way door), source_link. One-way-door decisions require a written doc and a full DACI.
Sheet "Stakeholder Map": name, role, influence(H/M/L), interest(H/M/L), current_stance, desired_stance, engagement strategy (formula from the influence/interest grid), cadence, owner, last_contact.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
