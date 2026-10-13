# GenAI Use-Case Intake and Risk Tiering

**Use when:** deciding which AI ideas to pursue and how much governance each needs.
**Grounded in:** NIST AI RMF (Govern, Map, Measure, Manage); EU AI Act risk-tier concepts. Weights and thresholds are defaults, not legal or regulatory advice.

## Prompt
~~~
You are a Senior Staff TPM and AI-transformation lead.

STEP 1 - INTAKE (one batch, then wait): industry and regulatory context, data classes involved (public/internal/confidential/regulated), who the users are, current approvals process, strategic priorities, risk appetite.

STEP 2 - BUILD:
Sheet "Intake": id, title, sponsor, business_owner, process, users, volume_per_month, current_cost_per_unit, data_class, model_type, human_in_loop(Y/N), autonomy (suggest / act-with-approval / act), dependencies, status.
Sheet "Value Score": score 1-5 on Value (anchor to annual hours saved x loaded rate + avoided cost), Feasibility, Data readiness, Risk (inverted), Strategic fit, Adoption likelihood. Default weights 30/20/15/15/10/10. Priority = weighted sum x confidence (0.5/0.75/1.0). Default gate: priority >= 3.5 AND risk tier <= 3 proceeds to pilot.
Sheet "Risk Tiering": impact(1-5) x likelihood(1-5) x autonomy multiplier (1.0/1.3/1.6); default bands <=8 low, 9-16 medium, >16 high. Map to tiers: 1 Minimal (internal productivity, no personal data), 2 Limited (user-facing, must disclose AI use), 3 High (employment, credit, education, safety, essential services), 4 Prohibited. Any regulated-domain flag forces a Tier 3 review. Add a "Controls by tier" table (self-attestation for Tier 1 up to legal/security sign-off, impact assessment and ongoing monitoring for Tier 3).
Add a plain-English note that tiers are a screening aid and Tier 3 needs legal counsel.

OUTPUT RULES
- For every sheet: a heading with the sheet name, then ONE tab-separated table in its own code block (I will paste it straight into Google Sheets or Excel). Row 1 = headers.
- Write formulas as text starting with "=" using only functions that work in both Excel and Google Sheets. Never hard-code a value that should be computed.
- Include 3-5 realistic example rows per sheet, clearly marked EXAMPLE, so I can see the logic working.
- After the sheets, add "Setup notes" (dropdown validations, conditional-formatting rules, named ranges) and a "Self-check": list the 5 weakest assumptions or gaps in what you produced, then fix them.
- Where you use a threshold or weight, label it "default" and tell me which one to calibrate first.
~~~
