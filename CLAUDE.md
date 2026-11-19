# VARIOM — Claude Code Instructions

This repository is the dedicated VARIOM project. These instructions apply to all work performed here. Do not import or follow root instructions from the MAX repository.

## Mandatory reading order

1. `docs/variom-ai/19-execution-charter-and-authority-map.md`
2. `docs/variom-ai/20-product-decisions-register.md`
3. `docs/variom-ai/00-product-vision-simplified-ux-v2.md`
4. `docs/variom-ai/04-ux-frontend-interface-master-spec-v2.1.md`
5. `docs/variom-ai/07-project-tracker.md`
6. The active task's relevant normative specifications and source references.

The Product Decisions Register records explicit owner decisions. The Product Vision is the controlling product baseline; UX V2.1 is subordinate. If sources conflict or an owner decision is open, stop the affected work and ask rather than infer.

## Current authorization boundary

Gate B and Gate C documentation-integrity work are complete. The next possible phase is application-target readiness, but it is not active until the owner identifies the application repository/branch and explicitly authorizes that task. Documentation and governance updates explicitly included in the active owner request are allowed.

**Application implementation is not authorized.** Gate C's documentation-integrity PASS is not implementation approval. Do not create application code, select a production stack, add dependencies, configure providers, run paid generation, change billing/payment behavior, migrate data, deploy or publish externally unless separately and explicitly authorized.

## Product and source discipline

- MAX is a planning/source repository, not the VARIOM implementation parent.
- MAX planning material may be reused only after exact source provenance and VARIOM adoption status are recorded.
- Archived MAX material is historical context, not automatic approval.
- Never assume MAX product behavior, code, schemas, provider choices or decisions apply to VARIOM.
- Never invent product features, pricing, plan limits, output specifications, consent/legal wording, retention policy or provider capabilities.
- Preserve all explicit exclusions in Product Vision V2.0.
- Do not convert OPEN or DEFERRED entries in the Product Decisions Register into approved requirements.

## Execution discipline

- Work only within the active task's bounded scope.
- Inspect the relevant files and current Git state before changes; preserve existing work.
- Avoid broad scans, unrelated refactors, opportunistic features and unnecessary dependencies.
- Do not modify secrets, real customer data or local environment files.
- Stop before destructive operations, schema/data migrations, security-boundary changes, provider activation, paid usage, billing changes or external publication.
- Keep mocks clearly separated from real provider output and never report mock output as real AI generation.
- Record material requirements, contracts and decisions in their single normative source; link to them rather than duplicating rules.
- Update the tracker when phase status or evidence changes.

## Verification and reporting

Run only checks relevant to the documentation task. Distinguish passed, failed, skipped and not run. Review the final diff for unintended changes.

Report: outcome, changed files, evidence/checks, unresolved owner decisions, deferred evidence gates and the next bounded action. Do not claim owner acceptance or implementation readiness without explicit evidence.
