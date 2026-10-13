# TPM Playbook: AI Prompts for Technical Program Managers

Copy-paste prompts that make your AI (Claude, ChatGPT, Gemini) build the real artifacts a Senior Staff TPM uses to run **platform migrations**, a **PMO / portfolio**, and **AI adoption programs**. Each prompt interviews you first, then generates Google Sheets / Excel-ready workbooks with live formulas, objective scoring and a self-check.

Built from experience leading a 450+ microservice Kubernetes migration, a 10+ program portfolio, and an AI-assisted development rollout across 400+ developers.

## How to use
1. Open a prompt, copy everything inside the `~~~` block.
2. Paste into your AI. It will ask intake questions in one batch. Answer them.
3. Paste each table it returns into a Google Sheets / Excel tab (tab-separated, so it splits into columns).
4. Add the dropdowns and conditional formatting from its "Setup notes".

> Thresholds, weights and scores in these prompts are **starting defaults** from common practice, not published standards. Each prompt makes the AI label them so you can calibrate with your own teams.

## Start here
| If you need to... | Run |
|---|---|
| Plan a large migration | [Migration workbook](prompts/migration/01-migration-workbook.md) |
| Decide if a service is ready | [Readiness scorecard](prompts/migration/02-production-readiness-scorecard.md) |
| Report to executives | [Portfolio dashboard](prompts/pmo/01-portfolio-workbook.md) and [Exec biweekly review](prompts/pmo/03-exec-biweekly-review.md) |
| Choose and govern AI | [Use-case intake and risk tiering](prompts/ai-adoption/01-use-case-intake-and-risk-tiering.md) |

## Full library
**Migration** · [Workbook](prompts/migration/01-migration-workbook.md) · [Readiness scorecard](prompts/migration/02-production-readiness-scorecard.md) · [Go/no-go and cutover](prompts/migration/03-go-no-go-and-cutover-runbook.md) · [Toolchain migration](prompts/migration/04-toolchain-migration-plan.md) · [Postmortem and wave retro](prompts/migration/05-postmortem-and-wave-retro.md)

**PMO** · [Portfolio and RAG](prompts/pmo/01-portfolio-workbook.md) · [Intake and prioritization](prompts/pmo/02-intake-and-prioritization.md) · [Exec review](prompts/pmo/03-exec-biweekly-review.md) · [Business case](prompts/pmo/04-business-case-calculator.md) · [RAID, DACI, decisions](prompts/pmo/05-raid-daci-decision-log.md)

**AI adoption** · [Intake and risk tiering](prompts/ai-adoption/01-use-case-intake-and-risk-tiering.md) · [Build/buy/self-host and TCO](prompts/ai-adoption/02-build-buy-selfhost-and-tco.md) · [Pilot design](prompts/ai-adoption/03-pilot-design-and-measurement.md) · [Eval plan](prompts/ai-adoption/04-eval-plan.md) · [Governance (NIST AI RMF)](prompts/ai-adoption/05-governance-nist-ai-rmf.md) · [Rollout and champions](prompts/ai-adoption/06-rollout-champions-adoption-dashboard.md)

See [SOURCES.md](SOURCES.md) for the references behind the frameworks.

## Contributing
Issues and PRs welcome. If a prompt saved you time, a ⭐ helps others find it.

By [Brandon Nissl](https://www.linkedin.com/in/brandonnissl) · MIT License. Not legal or compliance advice.
