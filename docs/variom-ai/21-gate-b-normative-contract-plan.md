# VARIOM — Gate B Normative Contract Plan

**Version:** 1.0  
**Date:** 2026-11-19  
**Status:** ACTIVE — documentation planning and contract authoring only  
**Branch:** `work/variom-documentation-readiness`  
**Authority:** Documents 19 and 20; Product Vision V2.0; UX/Frontend V2.1.

## 1. Purpose and boundary

Gate B converts the approved VARIOM product baseline and owner decisions into a coherent, implementation-grade set of normative contracts. Its goal is to let a future authorized implementation proceed without inventing product behavior, data ownership, state transitions, API semantics, cost handling, security rules or acceptance criteria.

This plan authorizes documentation work only. It does not authorize application code, repository creation for application code, framework/database/provider selection, schema migration, provider activation, paid generation, billing/payment configuration, deployment, merge to `main` or production claims.

The documentation repository `a99462091-SAAS/variom` is established. The separate application implementation repository/branch and technical stack are not yet established or authorized; do not confuse the documentation home with an implementation target.

## 2. Authoritative inputs and owner decisions

- Product Vision V2.0 is the controlling product authority.
- UX/Frontend V2.1 is subordinate and defines the 19-screen behavior.
- Product Decisions Register is authoritative for explicit owner decisions and deferrals.
- Execution Charter defines source provenance, authority and stop conditions.
- The owner will provide the latest refined visual identity image and the intended UI Design Prompt directly to Claude Code. Do not reconstruct or replace either input.
- VAR-OD-004 authorizes adaptation of the recovered MAX Virtual Character v1.0 product contract into VARIOM documentation; it does not authorize implementation or copying unrelated MAX UI.
- VAR-OD-005 authorizes intelligent image/video distribution but defers fixed ratios/counts.
- VAR-OD-006 retains existing Product Vision output choices and defers provider-specific technical details.
- VAR-OD-007 approves a limited-market launch strategy; exact first market and commercial/legal terms remain open.
- VAR-OD-008 approves deletion/retention principles only; retention periods and legal wording remain deferred.
- VAR-OD-009 approves email/password, email verification and email password recovery as the first-release direction.
- VAR-OD-010 approves Arabic/English and capability-bounded licensed/provider-approved voice behavior; exact voice/dialect catalogue remains provider-dependent.
- Starter / Pro / Agency = 1 / 3 / up to 8 brands is presentation-only. No pricing, billing, entitlements or enforcement is approved.

## 3. Contract architecture — one normative source per concern

Create or consolidate the following normative documents. Existing documents should be upgraded where practical rather than duplicated. Each contract must state: purpose, authority/status, scope, explicit exclusions, inputs, outputs, invariants, validation, failure behavior, security/ownership rules, dependencies, acceptance criteria, unresolved items and source provenance.

| ID | Normative contract | Primary coverage | Priority |
|---|---|---|---|
| B-01 | Functional Requirements & Acceptance Catalogue | Requirement IDs for all 19 screens and end-to-end workflows; preconditions, inputs, outputs, errors, observable acceptance evidence | P0 |
| B-02 | Domain Model & Data Dictionary | Accounts, users, brands, Brand DNA, assets, briefs, ideas, styles, characters, storyboards, jobs, outputs, credits, library; relations, ownership, lifecycle, versioning | P0 |
| B-03 | Workflow & Job State Machines | Signup/brand setup; monthly batch; image; video/storyboard; editing; character; library; cancellation, retries, timeouts, partial failures and recovery | P0 |
| B-04 | API & Schema Contracts | Authenticated operations, request/response/error shapes, validation, authorization, pagination, upload/download and idempotency semantics | P0 |
| B-05 | Credit Ledger & Commercial Boundaries | Quote, balance check, hold, settle, release/refund, actual provider usage, rounding, idempotency, insufficient balance, failure and payment boundary | P0 |
| B-06 | Security, Privacy & Data Lifecycle | Threat boundaries, tenant isolation, auth/session controls, upload safety, private media, secrets, prompt injection, logs, deletion and provider data transfer | P0 |
| B-07 | Provider & Capability Evidence Register | Provider/model identity, region/access, supported inputs/outputs, limits, latency, cost, rights, data terms, verification evidence and status | P0 before live provider work; evidence-dependent |
| B-08 | UX Interaction & Content Specification | Field-level behavior, defaults, validation, component states, accessibility, responsive behavior, RTL/LTR and owner-supplied visual inputs | P1 |
| B-09 | Master Storyboard & Video Production Contract | Scene schema, timing allocation, continuity, references, optional review, validation and provider handoff | P1 |
| B-10 | Simple Smart Editing Contract | Six approved task entries and six Motion Graphics categories; per-task inputs/outputs/options, unsupported cases, preservation and cost disclosure | P1 |
| B-11 | Virtual Character Contract | VARIOM questionnaire, Character Sheet, locked/variable traits, references, versioning, approval, consent/rights and capability gates | P1 |
| B-12 | Creative Intelligence & Style Registry Contract | Approved taxonomy, style record schema, selector behavior, provenance, review status and explicit holds; no automatic approval of candidates | P1 |
| B-13 | Test & Traceability Strategy | Requirement-to-test mapping, unit/integration/E2E, security, RTL/accessibility, provider evidence and manual acceptance | P0 |
| B-14 | Operations, Backup & Release Readiness | Environment boundaries, secrets, queues/schedulers, monitoring, backup/restore, incident response, cost controls and release gates | P1; hosting choices evidence/owner-gated |

## 4. Dependency order and authoring sequence

Do not author all documents independently. Use the following dependency sequence to reduce contradictions and rework:

1. **B-01 Functional Requirements & Acceptance Catalogue** — establish stable requirement IDs and behavior boundaries from V2.0/V2.1 and owner decisions.
2. **B-02 Domain Model & Data Dictionary** — derive entities and ownership from the requirements; do not select a database or ORM.
3. **B-03 Workflow & Job State Machines** — define lifecycle and failure/recovery behavior using the requirements and domain model.
4. **B-04 API & Schema Contracts** — derive interfaces from requirements, domain and state machines; remain technology-neutral.
5. **B-05 Credit Ledger & Commercial Boundaries** — specify safe accounting semantics without inventing prices, packages, payment rails or production billing.
6. **B-06 Security, Privacy & Data Lifecycle** — define enforceable security principles and data flows; mark legal/retention questions explicitly deferred.
7. **B-13 Test & Traceability Strategy** — map every normative requirement and invariant to evidence.
8. **B-08 through B-12 specialist contracts** — UX, storyboard, editing, character and creative registry, linked to the foundational contracts.
9. **B-07 and B-14 evidence registers** — record provider and operations facts only when supported by current authoritative evidence; do not turn research into activation approval.
10. **Cross-document consistency review** — resolve duplicate/conflicting rules, stale wording and missing traceability before Gate C.

## 5. Existing-source disposition

- Documents 00 and 04 remain the product/screen authorities; do not rewrite their scope as part of Gate B.
- Documents 01 and 02 are high-level foundations and should be updated only to link to the normative contracts and correct architecture-level inconsistencies.
- Document 03 and documents 11–14 remain candidate/library evidence. No style candidate or ID mapping becomes production-approved without its defined owner/review process.
- Document 17 is source-recovery evidence, not a normative behavior contract.
- Document 18 is a historical readiness snapshot from before the latest owner decisions and repository governance updates. Preserve it; later documents supersede its stale status statements.
- Document 19 and 20 govern execution authority and owner decisions.
- Document 07 is the live progress tracker and must be updated as each contract is authored and reviewed.

## 6. Open and deferred gates that must not block unrelated contract work

| Item | Current handling |
|---|---|
| Exact first launch market (VAR-OD-007) | Keep open; avoid country-specific tax/payment claims until owner names the market |
| Pricing, subscriptions, payments, top-ups and enforceable plan entitlements | Deferred; presentation-only plan names/brand counts do not authorize commercial implementation |
| Provider/model, region, capability, cost, rights and data terms | Evidence-gated; no provider selection or activation by assumption |
| Exact image/video pixel dimensions, technical formats and provider quality | Retain product-level options; provider-specific details deferred |
| Retention periods, legal wording and jurisdictional obligations | Principles documented; legal review required before launch |
| Hosting, database, object storage, KMS and backup provider | Technology-neutral contract first; selection requires technical, cost and security evidence plus required owner approval |
| Exact voice/dialect catalogue | Capability-gated; no invented catalogue |
| Owner-supplied identity image and UI Design Prompt | Owner will provide directly to Claude Code; do not reconstruct or replace |

## 7. Gate B exit criteria

Gate B is complete only when:

- Every in-scope screen and workflow has stable requirement IDs and testable acceptance criteria.
- Domain entities, ownership, relationships, lifecycle and versioning are defined without prematurely selecting infrastructure.
- All asynchronous workflows have explicit states, transitions, idempotency, cancellation, timeout, retry, partial-failure and reconciliation behavior.
- API/schema contracts define validation, authorization, errors and idempotency.
- Credit accounting semantics cannot double-charge, lose holds silently or mutate the ledger during preview/mock flows.
- Security, privacy and data lifecycle requirements cover account/brand isolation, private assets, uploads, secrets, deletion and provider data boundaries.
- Storyboard, editing, character and creative-style contracts agree with Product Vision and their approved scope.
- Every normative requirement maps to verification evidence; provider-dependent tests are clearly distinguished from mocks.
- Deferred owner/legal/provider/hosting decisions are explicit and do not appear as approved requirements.
- No unresolved cross-document contradiction remains in the Gate B scope.

Passing Gate B does not itself authorize implementation. Gate C must independently verify evidence, consistency, traceability and the implementation entry point; implementation requires a separate explicit owner authorization.

## 8. Immediate execution slice

Start with B-01, then B-02 and B-03. Do not begin detailed API or database design until their inputs are stable. The first deliverable is the requirements catalogue with IDs and acceptance criteria, not code or a technology stack decision.
