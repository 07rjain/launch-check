---
name: launch-check
description: Check a software product's launch readiness against an evidence-based checklist and produce a short report of completed items, gaps, and next actions. Use before launching or releasing a SaaS, web app, API, developer tool, or mobile app, or when asked what is done and what remains before launch.
---

# Launch Check

Assess the product the user intends to launch. Produce a concise, evidence-based report; do not implement fixes or launch anything unless separately requested.

## Establish scope

Read applicable repository instructions. Infer the product type, audience, launch stage, core user journey, monetization, and intended launch target from the request and available project evidence. Reuse existing context. Ask only when ambiguity materially changes the assessment; otherwise state assumptions briefly and continue.

Read [references/checklist.md](references/checklist.md) and assess every item for applicability. Adapt to the product: a private beta, public SaaS, downloadable CLI, API, and mobile app have different launch requirements. Do not require a website, SDK, payment system, public status page, or every checklist item for every product.

## Gather evidence

- Inspect relevant source, routes, docs, assets, configuration, existing test results, and deployment information. Prefer targeted searches over reading the entire repository.
- When a launch URL or connected environment is available, inspect relevant pages and use non-mutating checks where permitted. If only source is available, make the assessment explicitly repository-only.
- Run focused existing checks when they materially resolve uncertainty and fit the environment. Report failures and checks you could not run. Avoid installing dependencies or broad audit tooling solely to inflate coverage.
- Test the main user journey only within the user's authorization. Creating accounts, sending emails, charging cards, changing production data, deployments, or destructive tests require appropriate existing authorization. Use a sandbox when authorized and available; otherwise mark the behavior unverified.
- A dependency, placeholder page, environment-variable name, or README claim alone does not prove an integration works. Source can verify implementation; production delivery, external configuration, payment behavior, backups, and restores need evidence appropriate to those claims.
- Inspect configuration without printing secrets or personal data. A launch check is a readiness assessment, not a comprehensive security audit or legal certification. Verify current authoritative guidance if a finding depends on changing provider rules, platform policies, or legal requirements; do not invent compliance obligations.

## Record findings

Keep one internal ledger row per checklist ID, with status, applicability reason where needed, evidence, scope of verification, severity, and next action. For items with multiple applicable criteria, mark Done only when all are supported; otherwise use the appropriate incomplete status.

| Status | Meaning |
| --- | --- |
| Done | Applicable criteria are supported by evidence at the stated scope. Label source-only implementation explicitly when live behavior has not been verified. |
| Partial | Some applicable criteria are verified; others are missing or unverified. |
| Missing | Evidence shows the applicable item is absent or broken. A targeted search can establish absence in the repository, but cannot establish absence in an external service. |
| Unverified | Evidence or access is insufficient. Never silently convert this to Missing or Done. |
| N/A | Outside this product's current launch scope; record a brief reason. |

Classify actionable findings by consequence:

- **Blocker:** Prevents the promised core journey or creates a concrete serious exposure, such as cross-user data access, unrecoverable data loss, or broken checkout for a paid launch.
- **Before launch:** Material onboarding, trust, support, observability, or quality gap that should be addressed for the stated audience and stage.
- **Later:** Useful improvement with limited impact on this launch. Cosmetic polish, extra SDK languages, and public roadmaps are not automatic blockers.

An unverified critical requirement can prevent a readiness decision; describe the missing verification without claiming a confirmed defect. Deduplicate related findings and prioritize by impact. Do not manufacture blockers to fill a report.

## Deliver a short report

Default to about 250–400 words, shorter for small products. Return the report in chat; write a file only if requested or already required by project instructions. Do not print the full checklist unless requested.

Use this structure:

1. **Readiness:** Ready for the stated scope / Needs work / Cannot confirm. Add one sentence explaining why. Ready requires evidence for the core journey and no unresolved blocker or material before-launch gap; deferred improvements can remain.
2. **Scope:** Product/launch stage, evidence reviewed, assessment date, and material access limits. A repository-only result must not imply production readiness.
3. **Coverage:** `Done N · Partial N · Missing N · Unverified N · N/A N`. Counts use checklist IDs exactly once and must reconcile with the category table. Avoid a misleading percentage score.
4. **Category table:** One row per checklist category, with compact status counts and the most important finding or verified result. For fully excluded categories, say N/A and why. This shows what is done as well as what remains.
5. **Next actions:** Up to five specific, prioritized actions, each with severity, the gap, a concise evidence reference, and what would close it. Identify all blockers, combining related ones if needed; exceed five only when needed to avoid hiding a distinct blocker. When no actions are needed, say so.
6. **Verification limits:** Only material outstanding checks, such as live email delivery, payment webhooks, restore testing, or an unavailable deployment. Omit if already clear and nothing remains.

Use clickable file links or live URLs for key evidence. Keep verified facts separate from assumptions and user-reported claims. Do not present sample findings as actual results. If a previous report is available, highlight resolved and newly discovered gaps using fresh evidence; do not assume earlier Done items remain verified.
