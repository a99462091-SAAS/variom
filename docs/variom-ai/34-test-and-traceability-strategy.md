# VARIOM — Test & Traceability Strategy

**Version:** 1.0 | **Status:** NORMATIVE DRAFT | **Authority:** Documents 19–33.

## 1. Purpose
Defines how requirements and contracts are verified. Passing unit tests alone does not establish provider capability, production readiness or owner acceptance.

## 2. Traceability model
Every requirement uses a stable ID (VAR-FR-xxx) and maps to:
- contract section(s);
- implementation component when one exists;
- automated test(s);
- manual evidence where automation is unsuitable;
- test status and evidence reference;
- unresolved limitation/owner gate.

A requirement without evidence is NOT VERIFIED, not implicitly passed.

## 3. Test layers
1. **Unit:** validation, domain rules, state transitions, accounting calculations, formatting and localization helpers.
2. **Contract/API:** schemas, authorization, idempotency, errors, version compatibility and upload/download behavior.
3. **Integration:** persistence, job orchestration, ledger coordination, storage, library linkage and deletion.
4. **End-to-end:** complete user journeys for all 19 screens and core workflows.
5. **Security/privacy:** tenant isolation, access control, upload abuse, secret leakage, session controls, prompt injection boundaries and deletion.
6. **Localization/accessibility:** Arabic/English, RTL/LTR, keyboard/touch, focus, labels and responsive layouts.
7. **Provider capability:** real provider tests only after provider, rights, data, cost and owner gates; mocks are separately labeled.
8. **Operational resilience:** worker interruption, retries, reconciliation, backup/restore and incident exercises.

## 4. Minimum critical test scenarios
### Identity and tenancy
- unverified account denied protected operations;
- session expiry/revocation;
- account A cannot list/read/update/download/delete account B resources;
- cross-brand task/character/asset references rejected;
- recovery token single-use and expiry.

### Product behavior
- exact Monthly choices 8/12/16; up to 3 goals; no carousel; monthly video <=10 seconds;
- Image P1–P4; Video V1–V4; idea modes one/five;
- Video Studio only 10/20/30 seconds and cannot dispatch without validated storyboard;
- Smart Editing only approved six tasks/categories; source immutable;
- Character version pinned and unauthorized voice controls unavailable;
- library filters and authorized preview/download;
- all 19 screens have empty/loading/error/disabled/success/partial states where relevant.

### Credits and jobs
- no dispatch before quote, confirmation and reservation;
- insufficient balance blocks dispatch;
- duplicate confirmation/callback does not double charge;
- timeout enters reconciliation and prevents blind retry;
- partial usage settles verified amount and releases remainder;
- cancellation before dispatch releases full reservation;
- preview/mock/idea operation does not mutate real ledger;
- worker restart recovers persisted state safely;
- completed output requires durable media and library linkage.

### Data lifecycle and operations
- output, brand and account deletion are distinct;
- retained financial/security records are minimized and separated;
- backup/processor deletion semantics tested when infrastructure exists;
- backup restore does not silently resurrect erased user content;
- secret rotation and incident response exercised before production.

## 5. Provider vs mock evidence
Test reports MUST label each result as:
- unit/mock;
- local integration;
- provider sandbox;
- real provider account test;
- production observation.

A mock provider or local renderer cannot pass a real-provider acceptance criterion. Provider evidence records exact model/version/region/date/cost/rights and output observations.

## 6. Acceptance gates
- **Contract gate:** requirements and test cases agree; no ambiguous expected behavior.
- **Implementation gate:** automated and manual checks pass for changed scope; failures disclosed.
- **Provider gate:** capability, cost, rights, data terms and practical evidence verified.
- **Security gate:** no unresolved critical/high-risk tenant, credential, media or ledger issues.
- **Release gate:** operations, backup/restore, incident, legal and owner approvals complete.

## 7. Reporting format
Report exact commit/branch, changed paths, environment, commands, tests passed/failed/skipped, test category, evidence references, known baseline failures, provider/mock distinction and residual risks. Do not repeat successful broad suites without a reason; rerun only affected checks and required release gates.

## 8. Acceptance criteria
- Every normative requirement maps to verifiable evidence.
- Critical security, billing and workflow failure paths are covered.
- Provider and mock results are never conflated.
- RTL/LTR/accessibility and all 19 screens are included.
- Unverified evidence and known failures remain explicit.
