# VARIOM — Operating Reliability Controls

**Status:** OWNER-APPROVED — Version 0.2  
**Authority:** [Intelligent Advertising Strategy & Operating Framework V1.2](../intelligent-advertising-strategy/00-master-strategy.md) and the six approved knowledge documents.

These controls operationalize relevant existing requirements. They are subordinate to the approved strategy and knowledge libraries; they do not create a second strategy, customer questionnaire, or parallel approval flow.

## Controls

| Control | Focus |
|---|---|
| [R1 — Task Readiness & Creative Brief](01-decision-and-brief-readiness-standard.md) | Approved direction, applicable knowledge, evidence, essential assets, and task readiness |
| [R2 — Production Route & Asset Readiness](02-production-method-and-asset-readiness-standard.md) | Route suitability, asset handling, fidelity, and provider evidence |
| [R3 — Output Inspection, Repair & Acceptance](03-output-quality-repair-and-acceptance-standard.md) | Actual artifact quality, defects, bounded repair, and acceptance |
| [R4 — Reliability Simulation & Validation](04-simulation-and-validation-standard.md) | Testing, evidence levels, negative cases, and regression |

## Unified Task Execution Record

Maintain **one concise record per content/task**, containing only relevant fields:

1. Identity/version/status and requested deliverable.
2. Approved objective/plan/concept and approval references.
3. Applicable knowledge sources and versions/statuses.
4. Material claims, evidence states, and disposition.
5. Essential assets, classification, source, and restrictions.
6. Brief and task-specific acceptance criteria.
7. Route, rationale, provider/model evidence state, and limitations.
8. Artifact/version inspected, findings/severity, repair attempts, and reinspection.
9. Test evidence/verdict and regression references where applicable.
10. Approvals, cost/execution evidence when relevant, final status, and next gate.

Do not create four separate task reports. A separate test-suite index is permitted only for multi-case validation campaigns; link cases to task records and artifacts.

## Boundaries

- R1 readiness is not execution permission.
- R2 route readiness is not financial authorization.
- Provider success is not quality acceptance.
- Output PASS is not customer final-content acceptance.
- Final-content acceptance is not publication authorization.
- Desk simulation is not provider, artifact, software, or campaign evidence.
- Draft controls are not approved policy or deployed software behavior.

## Adoption path

1. Standards approved by the owner at Version 0.2.
2. Run risk-based simulations and negative cases; use real provider/artifact/software tests only when separately authorized and actually executed.
3. Resolve critical findings and run affected regression.
4. Obtain explicit authorization before platform implementation.

## Evidence

- [perFIX POST 01 readiness replay — 2026-11-24](test-results/perfix-readiness-replay-2026-11-24.md): logic simulation/document consistency only; no provider test, fresh artifact inspection, or software test.

**Do not claim controls are implemented until platform behavior exists and is tested.**
