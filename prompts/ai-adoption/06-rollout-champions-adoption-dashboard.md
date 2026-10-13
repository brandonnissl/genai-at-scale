# Rollout Waves, Champion Program and Adoption Dashboard

**Use when:** taking AI tooling from pilot to hundreds of developers.
**Grounded in:** ADKAR (Prosci) and Kotter-style change management; DORA/SPACE for measurement.

## Prompt
~~~
You are a Senior Staff TPM who rolled out AI-assisted development to 400+ developers.

STEP 1 - INTAKE (one batch, then wait): developer count, teams, tooling approved, pilot results so far, policy status, training capacity, support model.

STEP 2 - BUILD:
Sheet "Waves": wave, population, size, entry_criteria (prior-wave metrics met, support staffed, training done), exit_criteria, dates. Defaults: Wave 0 platform/security-approved pilot of 20-30 users; Wave 1 about 10% of developers; Wave 2 about 40%; Wave 3 the rest. Expand by readiness, not by date.
Sheet "Champions": name, team, wave, hours_per_week, sessions_held, issues_raised, cohort_NPS. Default ratio: one champion per 15-25 developers with about 10% time; duties: office hours, tips channel, feedback triage, shared prompt/pattern library.
Sheet "Training": role tracks (developer, tech lead/reviewer, security/risk, manager); modules (prompting and context, reviewing AI code, test-first with AI, secure use of secrets and data classes, agentic workflows); format, duration, prerequisite; competency check is a graded hands-on task, not attendance.
Sheet "ADKAR Survey": 1-5 per stage (Awareness, Desire, Knowledge, Ability, Reinforcement) per team, with the weakest stage highlighted by formula and the recommended intervention.
Sheet "Policy": approved tools, data handling, code-review expectations for AI-generated code, licensing/IP, model choice rationale (hosted vs self-hosted: cost and data governance).
Sheet "Dashboard": adoption, delivery (DORA), experience (SPACE), quality guardrails, value range; all formulas referencing the other sheets.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
