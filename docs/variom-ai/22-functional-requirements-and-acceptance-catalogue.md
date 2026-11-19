# VARIOM — Functional Requirements & Acceptance Catalogue

**Version:** 1.0  
**Date:** 2026-11-19  
**Status:** NORMATIVE REQUIREMENTS BASELINE — Gate B authored; cross-document and Gate C status recorded in Documents 36–37. Product scope is controlled by Documents 00 and 20  
**Authority:** Subordinate to Product Vision V2.0; screen behavior is aligned with UX/Frontend V2.1.  
**Related plan:** Document 21, Gate B Normative Contract Plan.

## 1. Purpose and interpretation

This catalogue assigns stable requirement IDs to observable VARIOM product behavior. It is the normative functional/acceptance index for Gate B. It does not select a technology stack, database, provider, price, payment rail or implementation architecture.

- **MUST** means required for the defined product behavior.
- **MUST NOT** means explicitly excluded or prohibited.
- **DEFERRED** means no implementation assumption may be made until the stated evidence/decision gate is satisfied.
- **VERIFY** means implementation evidence is required before claiming the requirement works. The normative behavior is defined in the linked specialist contract; mocks or document presence do not satisfy verification.
- Acceptance is based on observable behavior and evidence, not merely the presence of a UI screen or mock.

## 2. Product-wide requirements

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-001 | The product MUST operate around four logical systems: Brand Intelligence, Marketing & Creative Intelligence, Content Production and Content Library. These are logical product groupings, not a mandate for four services or agents. | Product/system map and workflow trace show all in-scope capabilities mapped without assuming service boundaries. |
| VAR-FR-002 | The product MUST support Arabic and English, including correct RTL/LTR layout behavior. | Language-switch test and screen-by-screen RTL/LTR evidence; direction, alignment, icons and mixed text remain correct. |
| VAR-FR-003 | The experience MUST minimize user effort, reuse known brand information and avoid asking users to repeat information already supplied. | Workflow tests demonstrate prefill/reuse and no duplicate questions for known fields. |
| VAR-FR-004 | The system MUST NOT invent brand facts, prices, provider capabilities, generation outputs, credit balances or billing state. | Negative tests prove unknown values are omitted or clearly marked; UI/API never fabricates values. |
| VAR-FR-005 | Actual generation cost MUST be shown before the user authorizes a billable generation operation. | Quote-to-confirm test shows a current, backend-derived quote before any hold or generation. |
| VAR-FR-006 | Preview/mock behavior MUST be clearly identified and MUST NOT create real generation jobs, real assets or real credit-ledger mutations. | Isolation test confirms preview/mock cannot change production job, asset or ledger state. |
| VAR-FR-007 | Completed generated image, video, editing and monthly outputs MUST be saved automatically to the Content Library. | End-to-end completion test verifies durable library record and authorized retrieval. |
| VAR-FR-008 | Account and brand data MUST be isolated and every read/write/download MUST be authorized server-side. | Cross-account and cross-brand negative authorization tests. |
| VAR-FR-009 | The product MUST NOT introduce any explicit Product Vision exclusion without a later owner decision. | Scope review confirms exclusions in section 12 remain absent. |
| VAR-FR-010 | A capability MUST NOT be represented as working solely because a screen, mock, local renderer or placeholder exists. | Evidence report separately identifies UI, API, persistence, worker, provider, output, credits, security and end-to-end proof. |

## 3. Authentication and account — S01

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-101 | First-release account access MUST use email and password, with email verification and password recovery by email. | Registration, verification, login, logout and recovery flows pass; unverified behavior follows the authentication contract. |
| VAR-FR-102 | The UI MUST NOT expose signup, login or recovery actions that are not connected to a working authorized backend flow. | UI/API integration test; no dead-end or simulated success action. |
| VAR-FR-103 | Session handling and security controls MUST follow the Security & Data Lifecycle contract. | Session expiry/revocation, rate-limit and account-boundary tests. |
| VAR-FR-104 | Social login MUST NOT be added by default in the first-release scope. | Scope inspection shows no unapproved social authentication path. |

## 4. Brand onboarding, DNA and management — S02, S03, S17, S18

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-201 | Initial brand profile MUST collect brand name, activity and target audience; logo is optional. | Required/optional field validation and save/reload test. |
| VAR-FR-202 | Brand DNA setup MUST reuse known answers and allow optional setup fields to be skipped, edited and saved. | Prefill, skip, edit and persistence tests. |
| VAR-FR-203 | Brand DNA MUST represent the approved brand profile, audience, personality, voice, language/dialect where specified, visual identity and brand assets. | Data dictionary maps each approved concept to a typed field/relationship; no unapproved inferred values. |
| VAR-FR-204 | Brand Assets management MUST be supported within the approved scope. | Upload/list/replace/remove behavior and authorization are specified and tested. |
| VAR-FR-205 | The product MUST NOT provide a Product Catalog. Product reference images MUST be uploaded manually for each relevant generation task. | No persistent product-catalog workflow; generation task requires its own applicable upload. |
| VAR-FR-206 | Users MUST be able to view and edit the approved Brand DNA fields for an accessible brand. | Read/update tests verify persistence, validation and brand authorization. |
| VAR-FR-207 | Users MUST be able to switch only among brands they are authorized to access. | Server-side authorization tests prevent cross-account and unauthorized brand switching. |
| VAR-FR-208 | Starter / Pro / Agency labels and 1 / 3 / up to 8 brand counts are presentation-only. The product MUST NOT infer price, subscription, entitlement, billing or enforceable limits from them. | No billing/entitlement enforcement is derived from these labels; presentation clearly avoids implying an active commercial offer. |

## 5. Dashboard — S04

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-301 | Dashboard MUST show accessible brands, the active brand, actual credit balance/usage where available and primary product actions. | Data-backed dashboard test; values reconcile with backend records. |
| VAR-FR-302 | Dashboard MUST NOT display invented subscription state, raw internal IDs or unsupported billing information. | UI review and API fixture tests with missing commercial data. |
| VAR-FR-303 | Recent content MAY be shown only when backed by actual authorized library records. | Empty and populated states; no fabricated sample outputs presented as user assets. |

## 6. Monthly Content — S05–S08

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-401 | Monthly Content MUST support exactly the approved post-count choices: 8, 12 or 16. | Input validation rejects other counts. |
| VAR-FR-402 | A user MUST be able to select up to three approved marketing goals: one primary and up to two supporting. | Validation enforces maximum three and primary/supporting distinction. |
| VAR-FR-403 | Monthly Content MUST contain images and videos only; carousel content MUST NOT be generated in this workflow. | Generated plan validation contains no carousel item. |
| VAR-FR-404 | The workflow MUST support up to 10 manually uploaded product images and optional price information per applicable image. | Upload count boundary, file validation and optional-price tests. |
| VAR-FR-405 | A virtual character MAY be selected optionally where the relevant workflow supports it. | Character selection is optional and only uses authorized saved character records. |
| VAR-FR-406 | Template review MUST be optional; the user may proceed without reviewing templates. | Both paths reach the same valid generation preparation state. |
| VAR-FR-407 | Template review MUST show content type, illustrative reference image, idea and copy/dialogue where applicable. Reference imagery MUST be labeled illustrative and MUST NOT be presented as generated output. | UI/content test confirms labels and semantic distinction. |
| VAR-FR-408 | During template review, only the idea and copy/dialogue fields are editable. | Attempted edits to other fields are unavailable/rejected. |
| VAR-FR-409 | Monthly Content MUST NOT ask the user to select a publishing platform. | Screen and API contract contain no platform-selection requirement. |
| VAR-FR-410 | Monthly image/video distribution MUST use an intelligent system-selected distribution. No user-facing adjustment control is required in the initial implementation until an explicit behavior is approved; fixed ratios/counts and adjustment semantics remain deferred. | System selects the distribution without exposing an unapproved adjustment control; no invented fixed ratio or unsupported user override. |
| VAR-FR-411 | Monthly image size choices MUST remain Instagram Portrait or Instagram Landscape. | Validation accepts only these product-level options. |
| VAR-FR-412 | Monthly video size choices MUST remain Reels Portrait or Reels Landscape Video. | Validation accepts only these product-level options. |
| VAR-FR-413 | Monthly videos MUST NOT exceed 10 seconds each. | Request validation and generated-output metadata checks reject/flag over-limit output. |
| VAR-FR-414 | Monthly workflow MUST expose one progress indicator and completed-posts/total count; internal stages are Planning, Content Preparation, Generation and Final Quality Check. | State-to-progress mapping and partial-completion tests. |
| VAR-FR-415 | Results MUST support view/open/download only; publishing, scheduling, approval, analytics and ZIP export are excluded. | UI/API scope tests verify only allowed result actions. |
| VAR-FR-416 | Every completed monthly output MUST be automatically saved to Content Library. | End-to-end batch test verifies each completed item has an authorized library record. |
| VAR-FR-417 | Actual cost MUST be disclosed before generation authorization; illustrative template references MUST NOT be counted as completed billable outputs. | Quote and preview-isolation tests. |

## 7. Image Studio — S09–S10

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-501 | Image Studio MUST support approved categories P1 Product Showcase, P2 Static Ad, P3 Carousel and P4 Lifestyle. | Category validation matches exact taxonomy; P3 is not confused with Monthly Content carousel exclusion. |
| VAR-FR-502 | The user MUST be able to request one idea or five idea suggestions. | API/UI validation supports the two approved modes only. |
| VAR-FR-503 | Product reference image upload MUST be manual for each relevant task; product price and virtual character are optional where applicable. | Upload/optional-field tests and no Product Catalog dependency. |
| VAR-FR-504 | Image output choices MUST remain Instagram Portrait or Instagram Landscape. | Request validation rejects unapproved product-level options. |
| VAR-FR-505 | Detailed creative style MUST be selected internally; the user MUST NOT be required to navigate an unapproved technical style menu. | UI hides internal style identifiers; selection provenance is recorded internally. |
| VAR-FR-506 | Actual cost MUST be disclosed before billable generation. | Quote-confirm test; no generation/hold before confirmation. |
| VAR-FR-507 | An initial paid post-generation image-editing loop MUST NOT be introduced. | Workflow and billing tests show no unapproved paid edit cycle. |
| VAR-FR-508 | Idea suggestion MUST remain distinct from image generation and MUST NOT be assumed billable under an unverified credit rule. | Separate operation contracts and no ledger mutation unless explicitly specified/approved. |
| VAR-FR-509 | Completed images MUST be automatically saved to Content Library. | Durable asset/library integration test. |

## 8. Video Studio and Master Storyboard — S11–S12

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-601 | Video Studio MUST support approved categories V1 UGC, V2 Product Demo, V3 Motion Graphics and V4 Story/Testimonial. | Category validation matches taxonomy. |
| VAR-FR-602 | The user MUST be able to request one idea or five idea suggestions. | API/UI validation supports the approved modes. |
| VAR-FR-603 | Product image upload MUST be manual per relevant task; character selection is optional. | Upload and optional-character tests. |
| VAR-FR-604 | Video Studio duration choices MUST be exactly 10, 20 or 30 seconds. | Validation rejects all other requested durations. |
| VAR-FR-605 | Video Studio formats MUST remain Reels Portrait or Reels Landscape Video. | Validation rejects unapproved product-level options. |
| VAR-FR-606 | Master Storyboard MUST be an internal mandatory stage; direct video-generation bypass MUST NOT exist. | Workflow trace proves storyboard is created/validated before provider generation. |
| VAR-FR-607 | Scene review MUST be optional. If shown, it MUST expose scene description and dialogue/text only, with only approved editable fields. | Reviewed and skip paths; unauthorized scene/technical controls absent. |
| VAR-FR-608 | Separate user-facing audio controls MUST NOT be introduced into Video Studio. | Screen/API review shows no separate audio-control surface. |
| VAR-FR-609 | Storyboard orchestration MUST preserve character identity, product appearance, style, language/voice where approved, scene order, timing and transitions. Exact schema and provider mapping are defined in the Master Storyboard contract. | Continuity contract and validation tests; unsupported continuity guarantees are not claimed. |
| VAR-FR-610 | Completed videos MUST be automatically saved to Content Library. | Durable output/library integration test. |

## 9. Simple Smart Editing — S13

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-701 | Smart Editing MUST remain a simple task-based workflow and MUST NOT become a professional timeline editor. | UI and API scope review. |
| VAR-FR-702 | The recovered catalogue consists of Auto Captions, Audio Enhancement, Silence Removal, Music & Rhythm, Motion Graphics and Additional Instructions. | Normative editing contract records source provenance and task-level definitions. |
| VAR-FR-703 | Motion Graphics categories are Kinetic Typography, Highlights & Callouts, Icons & Infographics, Product Features, Shapes & Effects, and Titles & Lower Thirds. | Validation accepts only these categories; multiple selections are permitted where the editing contract defines them. |
| VAR-FR-704 | Additional Instructions MUST clarify selected supported tasks and MUST NOT create arbitrary new editing capabilities. | Prompt/operation validation rejects unsupported task expansion. |
| VAR-FR-705 | The original input video MUST be preserved; editing creates a separate output. | Immutable input and separate output asset test. |
| VAR-FR-706 | Only capabilities with a verified processing path may be offered as executable controls. Catalogue presence alone is not proof of provider/implementation support. | Capability register evidence linked to enabled controls. |
| VAR-FR-707 | Cost for selected tasks and total operation MUST be disclosed before explicit authorization, once real pricing/cost evidence is available. No illustrative value may be presented as live cost. | Quote-confirm test; unresolved pricing blocks billable execution. |
| VAR-FR-708 | Unsupported features such as professional multi-track editing, frame-by-frame editing, automatic story reconstruction, new-scene generation in this tool, complex VFX/3D or advanced cinematic grading MUST NOT be added. | Scope and negative acceptance tests. |

## 10. Virtual Character Studio — S16

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-801 | Character creation MUST use the VARIOM-specific questionnaire and Character Sheet adapted under VAR-OD-004. | Normative character contract exists and traces every field to an approved source or explicit design rule. |
| VAR-FR-802 | Character creation MUST identify the character as fictional/synthetic and apply the approved adult-presentation baseline. | Validation and generated brief checks. |
| VAR-FR-803 | Character identity MUST be brand/account-bound, versioned and have explicit locked traits versus permitted variations. | Persistence/versioning tests and cross-brand access denial. |
| VAR-FR-804 | Character creation, save, edit and reuse MUST be exposed only where the supporting backend capability exists. | UI/API integration and persistence evidence. |
| VAR-FR-805 | Real-person likeness or voice use MUST require documented rights/consent; real-person voice imitation is not permitted without the applicable documented rights and consent. | Consent/rights gate tests and audit evidence. |
| VAR-FR-806 | Voice, dialect, lip-sync and reference-view options MUST be exposed only when supported by verified provider capability and approved policy. | Capability-register links and disabled/hidden states when unsupported. |
| VAR-FR-807 | Synthetic characters MUST NOT be used to present fabricated testimonials as genuine real-customer statements. | Content policy and negative acceptance test. |

## 11. Content Library and asset detail — S14–S15

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-901 | Library MUST contain generated images, videos and monthly content. | Asset type classification and listing tests. |
| VAR-FR-902 | Library MUST support type/date filtering, grid display, open/preview and authorized download. | Filter, empty-state, preview and download tests. |
| VAR-FR-903 | Content detail MUST display only actual selected asset data and available metadata. | No fabricated metadata; empty/unknown values handled honestly. |
| VAR-FR-904 | Download MUST require a valid, authorized asset reference/URL; private assets MUST not become public by default. | Expired/unauthorized URL tests and access-control verification. |
| VAR-FR-905 | Projects, collections, approvals, ZIP export and project-management features MUST NOT be introduced. | Scope review. |

## 12. Settings, responsive behavior and explicit exclusions — S19

| ID | Requirement | Acceptance evidence |
|---|---|---|
| VAR-FR-1001 | Settings MUST expose only language, account and preferences that are actually supported. | No nonfunctional billing/integration controls. |
| VAR-FR-1002 | Desktop and mobile layouts MUST be supported across the 19-screen map. | Responsive test matrix across agreed viewport classes; exact browser/device matrix is defined in test strategy. |
| VAR-FR-1003 | All interactive controls MUST have accessible labels, focus behavior, keyboard/touch support and visible state feedback. | Accessibility checks and manual keyboard/touch review. |
| VAR-FR-1004 | Loading, empty, error, retry, disabled, success and partial-failure states MUST be defined for each relevant workflow. | State inventory and workflow test evidence. |
| VAR-FR-1005 | The product MUST NOT add scheduling, publishing, social-account management, analytics dashboards, ad campaign management, team/agency collaboration, approvals, ZIP export, professional timeline editing, Product Catalog, 4K or unapproved formats/categories/durations. | Product scope regression review and negative tests. |

## 13. Cross-workflow acceptance invariants

These invariants apply to every applicable generation/editing workflow and must be refined in B-02 through B-06:

1. Every operation is scoped to an authenticated account and authorized brand.
2. A billable operation has a server-derived quote and explicit user confirmation before credit reservation/execution.
3. Every mutating operation has defined idempotency and duplicate-request behavior.
4. A job has explicit states and terminal outcomes; unknown provider outcomes are reconciled rather than blindly retried.
5. Cancellation, timeout, partial failure and retry cannot silently double-charge or lose a reservation.
6. Preview/mock flows cannot mutate real jobs, assets or credits.
7. Private source and output media remain access-controlled.
8. Completed outputs are saved to the library; failed/incomplete outputs are not represented as completed.
9. UI progress and success/failure messages reflect persisted backend state.
10. Provider capability and cost claims are backed by evidence; unknowns remain unknown.

## 14. Explicit deferred items

The following are intentionally not specified by this catalogue:

- Exact first launch country/market, currency, tax treatment, pricing, subscriptions, top-up/payment methods and commercial entitlement enforcement (VAR-OD-007).
- Provider/model selection, regions, actual prices, output resolution/pixel dimensions, codecs/formats, quality limits, durations beyond product bounds, repairs, latency and rights/data terms (VAR-DD-001/003).
- Fixed monthly image/video distribution ratios or exact counts (VAR-OD-005).
- Exact dialect/voice catalogue and provider-specific voice/lip-sync capability (VAR-OD-010).
- Exact retention periods, legal copy, statutory exceptions and provider/backup deletion timelines (VAR-OD-008; VAR-DD-004).
- Hosting, database, object storage, KMS, backup provider and deployment topology (VAR-DD-002).
- Exact API paths, database schema, technology-specific data types and service boundaries; these belong to B-02/B-04 after domain/state contracts.
- Detailed field-level UI copy and component design; owner-supplied identity image and UI Design Prompt remain direct inputs to Claude Code.

## 15. Gate B completion status

The B-01 requirements catalogue is authored and linked to the specialist contracts B-02–B-14 (Documents 23–35). Gate B coherence is recorded in Document 36 and Gate C evidence/readiness in Document 37. Requirement implementation evidence remains future work and is not implied by this documentation status.

No application implementation is authorized by this catalogue.
