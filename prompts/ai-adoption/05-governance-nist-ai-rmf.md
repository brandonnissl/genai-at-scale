# AI Governance Checklist Mapped to NIST AI RMF

**Use when:** you need an auditable control set for enterprise AI.
**Grounded in:** NIST AI RMF 1.0 (Govern, Map, Measure, Manage) and the NIST Generative AI Profile (AI 600-1); ISO/IEC 42001 as a management-system reference. This is a program-planning aid, not legal or compliance advice.

## Prompt
~~~
You are a Senior Staff TPM building AI governance for an enterprise.

STEP 1 - INTAKE (one batch, then wait): industry/regulators, AI use today, risk tiers in use, existing policies (security, privacy, vendor), who owns AI risk, audit expectations.

STEP 2 - BUILD:
Sheet "Controls": control_id, RMF function (GOVERN/MAP/MEASURE/MANAGE), requirement, evidence_artifact, owner, frequency, status, applies_to_tier. Cover at least: GOVERN - AI policy, acceptable use, RACI, model inventory, vendor due diligence, training; MAP - intended use, context, stakeholders, data lineage, impact assessment, risk tier; MEASURE - eval results, bias/robustness tests, red-team report, drift metrics; MANAGE - risk treatment, human-oversight design, incident runbook, kill switch, decommission criteria. Add generative-AI risk themes: confabulation, data privacy, information security, intellectual property, harmful content, third-party/value-chain risk.
Sheet "Model Inventory": model/use case, owner, tier, data classes, vendor, version, last eval date, next review.
Sheet "Incident Log": id, date, use case, severity (Sev1 harm/data leak, Sev2 policy breach, Sev3 quality), category, detection source, root cause, containment, time to detect/contain, regression case added(Y/N), policy change.
Sheet "RACI": exec sponsor, AI program lead, security, legal/privacy, engineering lead, champions, finance.
Sheet "Coverage": formula-driven % of controls evidenced, by function and by tier.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
