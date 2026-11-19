# VARIOM — Project Tracker

**Last updated:** 2026-11-19.  
**Status:** Documentation Readiness phase active on `work/variom-documentation-readiness`; implementation remains NOT AUTHORIZED.  
**Important:** No MAX phase, percentage, task state, acceptance or test result is inherited.

| Workstream | Status | Evidence / closure condition |
|---|---|---|
| Documentation consistency | Earlier review completed; superseded where newer findings exist | Audit 15; reconcile against audit 18 |
| Owner input recovery | Partially closed | Latest refined identity image selected as canonical; owner will supply it and the UI Design Prompt directly to Claude Code; Character questionnaire/Character Sheet adaptation authorized. See VAR-OD-002–004. |
| Full documentation readiness | NOT READY FOR IMPLEMENTATION | Audit 18; close P0 owner decisions and normative technical contracts |
| Documentation target | ESTABLISHED | Dedicated repository `a99462091-SAAS/variom`, working branch `work/variom-documentation-readiness` |
| Application implementation target | NOT ESTABLISHED / NOT AUTHORIZED | Separate application repository/branch and implementation authorization are still required before code work |
| Claude Code authority | ESTABLISHED FOR DOCUMENTATION WORK | Root `CLAUDE.md` is VARIOM-specific; document 19 defines authority and stop conditions. Application implementation remains unauthorized |
| Product/commercial plans | PRESENTATION CONVENTION RESOLVED; COMMERCIAL MODEL DEFERRED | Starter / Pro / Agency shown as 1 / 3 / up to 8 brands for non-binding presentation only; no pricing, subscriptions, entitlements or enforcement approved. See VAR-OD-001. |
| Functional requirements and acceptance | BASELINE CREATED — SPECIALIST REFINEMENT REQUIRED | Document 22 establishes stable requirement IDs and product-level acceptance evidence for all 19 screens/workflows; detailed contracts and failure-state expansion continue in B-02–B-13 |
| Domain model and data dictionary | DRAFT CREATED — REVIEW REQUIRED | Document 23 defines conceptual entities, ownership, relationships, versioning, provenance, deletion and privacy classifications; cross-contract validation remains open |
| API and schema contracts | INCOMPLETE | Request/response/error contracts and authorization |
| Job/workflow state machines | INCOMPLETE | Monthly, image, video/storyboard, editing, character, credits and recovery |
| Credit/commercial rules | INCOMPLETE | Quote/hold/settle/release/refund, idempotency, rounding, failure and payment boundary |
| Security/privacy/data lifecycle | INCOMPLETE | Adapt MAX working source into normative VARIOM requirements; legal and retention decisions |
| Provider/capability register | NOT VERIFIED | Current official sources, account/region access, pricing, rights and practical test evidence |
| Smart Editing | Catalogue recovered; normative contract incomplete | Six tasks and six Motion Graphics categories in audit 17; task-level controls and IO contract required |
| Virtual Character | Source adaptation authorized | Adapt MAX Virtual Character v1.0 into VARIOM questionnaire/Character Sheet; preserve safeguards and define validation, consent and versioning. |
| Creative library | Candidate policy only | No production-approved style records; P3 mapping IDs remain held; V2 modifiers unresolved |
| Master Storyboard | Concept specified; contract incomplete | Versioned scene schema, duration allocation, continuity, review and provider constraints |
| UX/visual design | Owner inputs identified | Latest refined identity image is canonical and will be supplied by owner; UI Design Prompt will also be supplied by owner. Field-level validation and component/state specifications remain documentation work. |
| Test strategy and traceability | INCOMPLETE | Map every requirement/contract to unit, integration, E2E, security, RTL/accessibility and manual tests |
| Operations and deployment | NOT STARTED | Environments, secrets, jobs, monitoring, backup/restore, incident response and launch gates |
| Production readiness | NOT STARTED | Legal, provider, cost, security, operations and owner acceptance |

## Current product baseline

Product Vision V2.0 is the controlling product authority; UX/Frontend V2.1 is subordinate. MAX planning material is the source foundation for reusable planning decisions, but each source must be reconciled against VARIOM and classified by branch/commit/status. Historical MAX decisions are not automatically current VARIOM decisions.

Document 17 recovers the Smart Editing task catalogue, identity board variants and MAX Virtual Character product-contract source. Document 18 is the latest full readiness assessment and records the remaining implementation blockers and required normative documents.

## Current documentation-readiness progress

- Repository target established: `a99462091-SAAS/variom`; MAX remains source/reference only. See document 19 and decision `VAR-D-001`.
- Working branch: `work/variom-documentation-readiness`.
- Document 19 establishes the VARIOM authority hierarchy, source-adoption rules, execution boundaries and stop conditions.
- Document 20 establishes the canonical Product Decisions Register: 4 baseline confirmed decisions, 9 resolved owner decisions (including the presentation-only plan convention), 1 partially resolved market/commercial decision, and 4 deferred evidence/legal/technical items.
- VAR-OD-001 is resolved for presentation only: Starter / Pro / Agency = 1 / 3 / up to 8 brands. Do not price, bill, grant entitlements or enforce brand limits.
- VAR-OD-002 and VAR-OD-003: owner will provide the latest refined identity image and UI Design Prompt directly to Claude Code; no replacement prompt is authorized.
- VAR-OD-004 through VAR-OD-006 and VAR-OD-008 through VAR-OD-010: recommendations approved within the limits and deferred details recorded in Document 20.
- VAR-OD-007: limited-market launch strategy approved; exact first market and commercial/legal terms remain open.
- Root `CLAUDE.md` is VARIOM-specific; no MAX root instructions are inherited.

## Gate B progress

- Gate A owner direction is substantially recorded. VAR-OD-007 remains partially open only for naming the exact first launch market; commercial terms, legal details and provider-dependent choices remain deferred.
- Document 21 is the active Gate B plan: 14 normative contracts, dependency order, evidence gates and Gate B exit criteria.
- Document 22 is the normative requirements baseline, covering product-wide invariants, all 19 screens, workflow scope, exclusions and deferred decisions. It is not implementation authorization.
- Document 23 is the first technology-neutral Domain Model & Data Dictionary draft, derived from Document 22 and the approved owner decisions. It deliberately leaves database, ORM, provider and infrastructure choices open; it requires review against B-03 through B-06.
- Immediate authoring sequence: B-01 Functional Requirements & Acceptance Catalogue, then B-02 Domain Model & Data Dictionary, then B-03 Workflow & Job State Machines.
- Application implementation target/stack remains unestablished and unauthorized. No application code, provider activation, paid generation, database migration, merge or deployment is authorized.

## Next action

Review Document 23 for cross-contract consistency, then author B-03 Workflow & Job State Machines using Documents 22–23. Refine Document 22 acceptance criteria only where the domain/state contracts expose a material gap. Keep all work documentation-only.
