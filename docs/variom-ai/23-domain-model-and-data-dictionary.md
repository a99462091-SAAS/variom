# VARIOM — Domain Model & Data Dictionary

**Version:** 0.1  
**Date:** 2026-11-19  
**Status:** NORMATIVE DOMAIN CONTRACT — technology-neutral; cross-contract review recorded in Document 36 and Gate C in Document 37  
**Authority:** Documents 19–22; Product Vision V2.0 controls product scope; UX/Frontend V2.1 controls subordinate screen behavior.  
**Branch:** `work/variom-documentation-readiness`  
**Related contracts:** 21 Gate B Plan; 22 Functional Requirements & Acceptance Catalogue.

## 1. Purpose and boundaries

This document defines the technology-neutral conceptual domain model, entity responsibilities, relationships, ownership boundaries and lifecycle vocabulary required by VARIOM. It is the source for subsequent workflow/state-machine and API/schema contracts.

It does **not** select a database, ORM, storage vendor, framework, service boundary, provider, payment rail or deployment topology. Names below describe logical domain concepts, not mandatory tables, collections, services or microservices.

Normative terms:
- **MUST**: required domain invariant.
- **MUST NOT**: prohibited behavior.
- **DEFERRED**: no implementation assumption until the stated evidence or owner/legal gate.
- **DEFERRED**: the concept is established; the owning specialist contract either defines the behavior or records the specific external evidence/owner gate required before implementation.

## 2. Domain-wide invariants

1. Every private business record and media object MUST be scoped to exactly one owning account. Where a record is brand-specific, it MUST also reference exactly one brand within that account.
2. A user MUST only access records through an authenticated account context and server-verified authorization. Client-supplied account or brand identifiers are never proof of access.
3. Brand-specific records MUST NOT be reassigned across accounts by ordinary update operations.
4. Product reference images uploaded for a generation task are task inputs, not a persistent Product Catalog. They MUST NOT silently become reusable product records.
5. A generated output, an uploaded input, a Brand Asset and a Content Library entry are distinct concepts even when they reference the same underlying media bytes.
6. A completed output MUST have a durable asset record and a corresponding Content Library entry. Failed or incomplete work MUST NOT be represented as completed output.
7. Preview/mock data MUST be distinguishable from real user data and MUST NOT mutate real jobs, assets, library entries or credit records.
8. Billable operations MUST be traceable to a server-derived quote, explicit user confirmation, a credit reservation and a settlement/release outcome. Exact accounting mechanics belong to B-05.
9. Records with legal/security retention obligations MUST be distinguishable from user content subject to deletion. Exact retention periods and legal exceptions remain deferred under VAR-OD-008.
10. The model MUST preserve source provenance and approval status for creative styles, provider capabilities and other controlled reference data. A candidate is not an approved production option.
11. No domain concept in this document authorizes multi-user collaboration, team approvals, a Product Catalog, publishing, scheduling, analytics, ZIP export or any other excluded product scope.

## 3. Conceptual context and ownership hierarchy

The logical ownership hierarchy is:

`Account → Brand → Brand-scoped records`

A user authenticates and acts within an account. The first-release product scope is an individual account experience; team/agency collaboration and shared memberships are excluded. The exact account-to-user persistence and recovery mechanics are defined in B-06/B-04 and MUST NOT introduce collaboration features.

- **Account-owned:** account preferences, account security records, credit account/ledger, account-level audit/security events.
- **Brand-owned:** Brand DNA, Brand Assets, Virtual Characters, and brand-specific creative context.
- **Task-owned:** briefs, per-task uploads, idea requests/results, storyboards, generation/editing jobs, job attempts and task-specific quotes/reservations.
- **Output-owned:** generated media assets and their Content Library entries; each output retains its originating account, brand (when applicable), job and provenance.
- **System reference data:** approved taxonomies, creative-style records, provider capability evidence and controlled templates. These are not user-owned and require explicit governance/provenance.

No entity may rely on a client-provided brand name or account identifier as its ownership authority.

## 4. Core entities

### 4.1 Identity and account

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| User | Authenticated human principal | Authenticates into an Account; no collaboration membership is implied | Stable identifier; normalized email; credential reference (never plaintext password); verification status/time; account status; security timestamps |
| Account | Root tenant and ownership boundary | Owns account-scoped records and one or more Brands | Stable identifier; owner User reference; lifecycle status; created/updated timestamps; locale/preferences where approved |
| Account Security Record | Security events and account-protection state | Account and User scoped | Event/type; occurrence time; outcome; relevant session/security reference; minimal metadata |
| Session | Authenticated access context | Belongs to User and Account | Stable identifier; issued/expiry/revocation timestamps; security metadata; token material handled securely and never exposed in logs |

**Rules**
- First-release authentication is email/password, email verification and email-based password recovery (VAR-OD-009).
- Password hashes/credential material MUST be managed by an approved authentication implementation; this document does not prescribe a library or storage format.
- Session expiry, revocation, rate limits, recovery-token handling and security-event retention are specified in B-06.
- Social login is not part of the default first-release scope.
- Team memberships, invitations, roles for collaborators and cross-account sharing are out of scope.

### 4.2 Brand Intelligence

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| Brand | A user's managed brand context | Exactly one Account; parent of Brand DNA, Brand Assets and Characters | Stable identifier; account reference; name; activity; target audience; lifecycle status; timestamps |
| Brand DNA | Structured, editable understanding of a Brand | Exactly one Brand; versioned revisions | Approved profile attributes; audience; personality; voice; language/dialect when specified; visual identity references; source/completeness metadata; version |
| Brand Asset | Reusable brand-owned media/reference | Exactly one Brand; references a private Media Object | Asset type/category; media reference; display name/metadata; status; created/updated timestamps |
| Virtual Character | Saved synthetic character identity for a Brand | Exactly one Account and one Brand; has versioned Character Sheets and reference assets | Name/label; fictional/synthetic declaration; adult-presentation baseline; status; active version; provenance |
| Character Sheet Version | Immutable or historically preserved character definition | Exactly one Virtual Character; may reference one or more character reference Media Objects | Structured brief; intended brand role; locked traits; permitted variations; appearance/wardrobe/personality/behavior; approved language/voice direction where supported; version/status |
| Character Reference | Visual or other approved reference for a Character Sheet Version | Character version; private Media Object | Reference view/type; purpose; source/provenance; status |

**Rules**
- Brand DNA fields MUST derive from approved concepts in Product Vision and must not be invented to fill empty values.
- Brand DNA revisions MUST retain enough version/provenance information to explain which context informed a task.
- Brand Assets are reusable brand resources; per-task product uploads are not Brand Assets by default.
- Virtual Characters are fictional/synthetic. Real-person likeness or voice use is subject to documented rights/consent gates; voice, dialect, lip-sync and reference-view options are capability-gated.
- Character identity is brand/account-bound. A task MUST record the exact Character Sheet version it used so later edits do not silently alter historical jobs or outputs.

### 4.3 Marketing and creative intelligence

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| Marketing Goal | Controlled objective selected for a task | System reference data | Stable code; approved label; active status |
| Creative Category | Approved image/video taxonomy | System reference data | Stable code; modality; label; definition; status |
| Creative Style | Controlled detailed style used internally by selection/generation | System reference data; may be selected for a task | Stable identifier; name; description; modality/category compatibility; provenance; approval status; version |
| Style Selection Record | Records why a style was selected for a task | Task and selected Creative Style | Selection source/rationale reference; compatibility result; style version; timestamp |
| Idea Request | Request for one idea or five suggestions | Account, Brand and originating task context | Requested mode/count; brief/context references; status; timestamp |
| Idea | A generated or owner-edited creative idea | Belongs to an Idea Request and task context | Text; optional supporting metadata; origin (generated/user-edited); version/status |
| Copy/Dialogue | Text associated with an idea, monthly post, storyboard scene or output | Parent task/idea/scene as appropriate | Text; language; optional verified dialect/register; origin/version |

**Rules**
- Marketing goals are limited to the eight approved objectives in Product Vision; Monthly Content allows one primary and up to two supporting goals.
- Image categories P1–P4 and video categories V1–V4 remain separate from goals, topics, formats, production methods and copywriting approaches.
- P3 Carousel is an Image Studio category; it does not authorize carousel items in Monthly Content.
- Detailed styles are selected internally; users are not exposed to an unapproved technical style menu.
- No creative-style candidate, ID mapping or historical MAX record becomes production-approved solely by appearing in the repository. Approval/provenance belongs to B-12.
- Idea suggestion and billable generation are separate operations. Whether idea requests consume credits remains governed by an explicit approved B-05 rule; no charge is inferred here.

### 4.4 Production requests and source media

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| Creative Brief | Normalized task intent and context | Exactly one Account; one Brand when brand-specific; linked to a task | Objective; category; idea/copy references; relevant Brand DNA version; optional character version; requested product-level format/duration; user instructions |
| Production Task | User-visible unit of image, video or monthly-content preparation | Account; Brand when applicable; owns brief and task inputs | Task type; requested mode; status; created/updated timestamps; request provenance |
| Task Input | A media/text input supplied for one task | Exactly one Production Task; references Media Object where applicable | Input role; source; validation status; ordering; metadata |
| Media Object | Private stored media bytes plus safe metadata | Exactly one owning Account; may be referenced by Brand Asset, Task Input, Character Reference or Output Asset | Stable identifier; storage reference (not public URL); media type; size; checksum; validation/security status; created/deleted timestamps |
| Monthly Content Plan | Structured plan for a batch of 8/12/16 posts | One Production Task; Account and Brand scoped | Approved post count; up to three goals; planned items; smart distribution result; review preference; version/status |
| Monthly Content Item | One planned/completed post within a Monthly Content Plan | Exactly one plan; one item may produce an image or video output | Sequence; modality; idea/copy; applicable product input references; format; duration where video; item status |
| Scene | One ordered segment in a Video Storyboard | Exactly one Storyboard; has sequence/timing/content and optional references | Sequence; description; dialogue/text; intended action; duration allocation; transition reference; optional visual reference |
| Storyboard | Mandatory internal video-production plan | Exactly one video Production Task; versioned; contains ordered Scenes | Version; continuity context; scene order; total target duration; validation status; selected Brand DNA/Character/style versions |
| Editing Instruction Set | User-selected Simple Smart Editing operations | Exactly one editing Production Task | Selected supported tasks; selected Motion Graphics categories; additional instructions; validated operation set |

**Rules**
- A Task Input uploaded as a product reference is scoped to that task and MUST NOT create a Product Catalog record.
- Media Objects MUST remain private by default. Download/preview access is mediated by authorization, not by exposing storage references.
- Monthly Content supports 8, 12 or 16 items; image/video distribution is intelligent, but fixed ratios/counts remain deferred. Each monthly video is at most 10 seconds.
- Image Studio supports P1–P4; Video Studio supports V1–V4 and exactly 10/20/30-second product-level duration choices.
- A Video Storyboard is mandatory before video generation. Scene review is optional; if exposed, the user-facing editable content remains limited to approved scene description and dialogue/text.
- Smart Editing remains task-based. Its recovered six tasks and six Motion Graphics categories are recorded in B-10; only verified executable capabilities may be offered. Original input media is preserved and the edited result is a separate output.
- Exact scene schema, time allocation rules and provider handoff are specified in Documents 24 and 30; shared task transitions are specified in Document 24.

### 4.5 Jobs, attempts and outputs

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| Job | Asynchronous execution record for a Production Task or task item | Account and Brand scoped; linked to source task and operation | Stable identifier; operation type; status; idempotency reference; created/started/finished timestamps; progress summary; terminal outcome |
| Job Attempt | One execution attempt for a Job | Exactly one Job; may reference provider capability record | Attempt number; start/end; outcome; retry classification; external correlation reference where safe; failure category |
| Provider Operation Record | Evidence-backed record of an external provider operation | Job Attempt; references a verified Provider Capability entry | Provider/model/region/version; request/response correlation metadata; usage facts; status; evidence reference; no secrets |
| Output Asset | Resulting media or structured output from a completed operation | Account; Brand when applicable; originating Job and Job Attempt; references Media Object | Output type; media reference; dimensions/duration/format only when verified; completion/validation status; provenance |
| Content Library Entry | User-facing library record for an Output Asset | Exactly one Account; references one Output Asset; Brand where applicable | Asset reference; display metadata; type/date classification; visibility/deletion status |

**Rules**
- A Job is not the same as a Production Task: a task captures user intent; a job captures execution and recovery.
- Retries create or record distinct Job Attempts under a stable Job identity; they MUST NOT create duplicate charges or duplicate completed outputs.
- Provider timeouts/unknown outcomes require reconciliation before retry. Exact state transitions and idempotency rules belong to B-03/B-05.
- Output Asset provenance MUST identify the task/job and relevant versions of Brand DNA, Character Sheet, Creative Style, Brief and Storyboard where applicable.
- Only validated completed outputs are surfaced as completed library content.
- Each completed generated image, video, editing result and monthly output automatically receives a Content Library Entry.
- Failed/intermediate media may be retained temporarily for safe recovery only under the lifecycle rules in B-06; it MUST NOT be represented as a completed user output.

### 4.6 Credits and commercial boundary

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| Credit Account | Account-level balance view derived from ledger entries | Exactly one Account | Currency/unit definition; current derived balance; status; last reconciled time |
| Credit Quote | Server-derived estimate for one proposed billable operation | Account; references task/operation and pricing evidence | Quote identifier; inputs/quantity; amount/unit; basis/version; expiry; status |
| Credit Reservation | Temporary hold against an accepted quote | Account; one operation/Job; linked to quote and ledger entries | Reservation identifier; reserved amount; status; expiry; idempotency key |
| Credit Ledger Entry | Append-only accounting fact | Exactly one Credit Account; linked to operation/reservation where applicable | Entry type; signed amount; unit; effective time; idempotency reference; source reference; balance-after only if defined by B-05 |
| Settlement Record | Final reconciliation of reserved amount against actual usage | Reservation and completed/failed operation | Actual amount; released remainder; evidence basis; status; timestamp |

**Rules**
- The ledger is the accounting source of truth; displayed balance is derived from ledger facts, not independently mutable UI state.
- A preview/mock operation MUST NOT create a quote that implies live pricing, a reservation, settlement or ledger mutation.
- A real billable operation requires a current server-derived quote and explicit user confirmation before reservation/execution.
- No live price, subscription, package, top-up, payment method, tax or enforceable entitlement is approved by the presentation-only plan labels.
- Starter / Pro / Agency and 1 / 3 / up to 8 brands are presentation-only under VAR-OD-001. The older Basic / Pro / Max values in Product Vision §12 are superseded for this presentation scope by the later owner decision; the inconsistency must be reconciled in the source document during the cross-document review.
- Detailed quote, hold, settle, release/refund, rounding, insufficient-balance and failure semantics belong to B-05. Commercial pricing and payment rails remain deferred under VAR-OD-007.

### 4.7 Provider evidence and controlled reference data

| Entity | Purpose | Ownership / key relationships | Minimum conceptual data |
|---|---|---|---|
| Provider | Identifies an external service/vendor under evaluation or approval | System reference | Name; service category; status; source links; review date |
| Provider Model/Capability | Specific model or capability with verified limits | Provider; may be referenced by Job Attempt and enabled feature | Model/capability identifier; region/access; supported input/output; limits; cost basis; rights/data terms; verification status/date |
| Evidence Record | Auditable support for a capability, cost, right or operational claim | Provider/Capability or controlled reference item | Source type; exact source/version/date; observation; reviewer; status; expiry/recheck date |
| Taxonomy Record | Approved goal/category/task/category option | System reference | Stable code; label; definition; version/status; source/approval |
| Creative Style Record | Approved style candidate and its governance lifecycle | System reference | Stable ID; description; compatible categories/modalities; source provenance; review/approval status; version |

**Rules**
- Provider/model capabilities, regions, costs, rights and data terms remain unverified until supported by current authoritative evidence and any required practical test.
- A provider evidence record is not activation approval. Provider activation and paid generation require separate explicit owner authorization.
- Exact output dimensions, codecs, quality limits, latency and provider-specific restrictions remain deferred under VAR-DD-001/003.
- Reference records require provenance and status. Historical MAX sources remain reference-only unless explicitly adopted for VARIOM.

## 5. Relationship summary

| Parent / owner | Child / related entity | Relationship rule |
|---|---|---|
| User | Account | Account has one owner User in the first-release conceptual model; collaboration/multiple memberships are out of scope |
| Account | Brand | One account owns zero or more brands; all brand access is account-authorized |
| Brand | Brand DNA | One brand has versioned Brand DNA revisions |
| Brand | Brand Asset | One brand owns zero or more reusable Brand Assets |
| Brand | Virtual Character | One brand owns zero or more saved Virtual Characters |
| Virtual Character | Character Sheet Version | One character has one or more versions; tasks pin the version used |
| Account | Production Task | One account owns each task |
| Brand | Production Task | A brand-specific task references exactly one authorized brand |
| Production Task | Task Input | One task owns zero or more ordered inputs |
| Task Input | Media Object | Media-backed inputs reference a private Media Object |
| Production Task | Brief / Idea Request | Task has its applicable brief and zero or more idea requests |
| Production Task | Storyboard | Video task has a mandatory validated storyboard before generation |
| Production Task | Editing Instruction Set | Editing task has one validated selected operation set |
| Production Task | Job | One task may have one or more jobs where workflow decomposition requires it; exact cardinality is finalized in B-03 |
| Job | Job Attempt | One job has one or more attempts; retry semantics are defined in B-03 |
| Job Attempt | Provider Operation Record | An attempt may have zero or one or more provider operation records, subject to provider orchestration contract |
| Job | Output Asset | A job may produce zero or more validated outputs |
| Output Asset | Content Library Entry | Every completed user-facing output has a corresponding library entry |
| Account | Credit Account | One account has one logical credit account |
| Credit Account | Credit Ledger Entry | Ledger entries are append-only facts for one credit account |
| Credit Quote | Credit Reservation | A reservation references the accepted quote it consumes |
| Credit Reservation | Settlement Record | A reservation is reconciled by a settlement/release outcome |
| Provider | Provider Model/Capability | Provider has zero or more documented capabilities |
| Provider Model/Capability | Evidence Record | Capability claims link to dated evidence |

## 6. Versioning and provenance requirements

The following inputs can change over time and MUST be versioned or otherwise historically pinned where they influence generated work:
- Brand DNA.
- Virtual Character and Character Sheet.
- Creative Brief and user-edited Idea/Copy.
- Storyboard and its Scenes.
- Creative Style record and selector version.
- Provider Model/Capability evidence and cost basis.
- Credit Quote and its pricing/evidence basis.
- Editing Instruction Set.

A Job/Output MUST retain references to the exact versions used, or an immutable snapshot sufficient to reproduce the decision context. Updating a brand, character, style or provider record MUST NOT rewrite the historical provenance of an existing Job or Output.

Source media and outputs MUST retain integrity metadata sufficient to detect accidental substitution or corruption where supported by the eventual storage design. The specific checksum algorithm and storage implementation are technology decisions for later review.

## 7. Deletion, retention and data lifecycle

- Users have separate deletion controls for generated outputs, brands and accounts, consistent with VAR-OD-008.
- Deleting a Content Library Entry MUST be distinguished from deleting the underlying Output Asset or Media Object when another authorized reference still exists.
- Deleting a Brand MUST not silently delete legally required financial/security records. Brand-owned content and references must be processed according to the approved deletion workflow.
- Account deletion MUST trigger a defined cascade/erasure workflow for account-owned content, private media, tasks, jobs and derived references, subject to documented legal/security retention exceptions.
- Financial/security records that must be retained MUST be minimized and separated from user content; retained records MUST not preserve unnecessary content payloads.
- Backups and external processors MUST be included in deletion/expiry semantics; exact purge windows, retention periods, legal text and statutory exceptions remain DEFERRED pending jurisdiction-specific legal review and infrastructure evidence.
- Tombstones, deletion requests and erasure progress may be required for reliable asynchronous deletion; their exact model and states are specified in B-03/B-06/B-14.
- No deletion implementation or destructive migration is authorized by this conceptual model.

## 8. Security and privacy classification

B-06 must assign a formal classification and handling rule to every field/media class. The initial conceptual handling categories are:

| Class | Examples | Minimum handling |
|---|---|---|
| Authentication/security | Credential hashes/references, recovery/session material, security events | Restricted; never log secrets or raw tokens; access only to security/auth flows |
| Personal/account | Email, account preferences, account identifiers | Private; account-scoped; minimize exposure |
| Brand confidential | Brand DNA, strategy, voice, brand assets, prompts and briefs | Private; brand/account-scoped; not public by default |
| User media | Uploaded product images, character references, source videos | Private; validate type/size/content; malware/content safety checks as defined in B-06 |
| Generated content | Images, videos, text, storyboards and outputs | Private; authorized preview/download only |
| Financial/accounting | Quotes, reservations, ledger entries, settlements | Restricted; integrity and audit controls; separate from deletable content |
| Provider/operational evidence | Provider identifiers, request correlation, capability/cost evidence, operational logs | Restricted as appropriate; no secrets or unnecessary user payloads |
| Controlled reference data | Approved taxonomy/style records | System-managed; provenance and approval state required |

Prompt and uploaded-content handling must account for untrusted instructions and prompt-injection boundaries. User-provided text, image metadata, retrieved content and provider responses are data, not authority to override system policy or owner-approved requirements.

## 9. Explicit non-entities and prohibited inferences

The following are intentionally not part of the VARIOM domain model:
- Product Catalog or persistent product inventory.
- Social publishing accounts, scheduled posts or publishing calendar.
- Analytics/ad campaign management records.
- Team, agency collaboration, member invitations, shared approval workflows.
- Professional editing timeline, tracks, frame-level edits or arbitrary effect graph.
- Payment method, subscription, invoice, top-up or tax entities as approved first-release product behavior; commercial model remains deferred.
- Provider-specific technical fields treated as guaranteed before verification.
- A public asset URL as the canonical identity of a private Media Object.
- An automatically approved creative-style record derived from MAX archives or candidate lists.

## 10. Open questions and deferred decisions

| ID | Question / detail | Handling |
|---|---|---|
| DM-OPEN-01 | Exact account/user persistence cardinality and authentication implementation | Individual-account product scope is fixed; B-04/B-06 define exact secure mechanics without adding collaboration |
| DM-OPEN-02 | Whether a task decomposes into one Job or multiple coordinated Jobs | Define in B-03 from workflow needs; preserve one user-visible task and traceable attempts |
| DM-OPEN-03 | Exact Brand DNA field dictionary and validation/optional-field rules | Derive only from approved source material; do not invent missing profile fields |
| DM-OPEN-04 | Exact media formats, upload limits, scanning and storage metadata | B-06/B-07/B-14 after capability and infrastructure evidence |
| DM-OPEN-05 | Exact credit unit, quote expiry, rounding and ledger-entry taxonomy | B-05; no prices or payment assumptions |
| DM-OPEN-06 | Retention periods, legal exceptions and backup/processor deletion timelines | Deferred under VAR-OD-008/VAR-DD-004 pending jurisdiction-specific legal review |
| DM-OPEN-07 | Provider/model-specific capability and output metadata | Evidence-gated under VAR-DD-001/003 |
| DM-OPEN-08 | Creative style schema, approval workflow and exact selected production set | B-12; no candidate auto-approval |
| DM-OPEN-09 | Exact API identifiers, database types, indexing and storage topology | B-04 and later technical architecture, not this conceptual contract |
| DM-OPEN-10 | Whether account-level deletion/security records require specific legal retention | Legal review before production/launch; minimize and separate retained records |

No open item above blocks the technology-neutral conceptual model. Each is either defined in its owning specialist contract (Documents 24–35) or explicitly recorded as deferred in Documents 20, 28, 35 and 37. Do not leave a TBD field to be guessed during implementation.

## 11. Acceptance criteria for this contract

- Every entity has a clear purpose, ownership boundary and relationship to the approved product scope.
- Account and brand isolation are explicit and testable.
- Product task uploads are distinct from reusable Brand Assets; no Product Catalog is implied.
- Production Task, Job, Job Attempt, Output Asset and Content Library Entry are distinct and traceable.
- Brand DNA, Character Sheet, Storyboard, Creative Brief and Creative Style provenance can be pinned to historical work.
- Credit records are conceptually separated into quote, reservation, append-only ledger facts and settlement.
- Provider capability claims are linked to evidence and do not imply activation.
- Deletion distinguishes user content from financial/security records and marks legal/infrastructure-dependent details deferred.
- No database, ORM, provider, service, billing or deployment technology is selected.
- All unresolved details are assigned to a later contract or explicit evidence/owner gate.

## 12. Source provenance

- VARIOM Product Vision V2.0: `docs/variom-ai/00-product-vision-simplified-ux-v2.md`.
- VARIOM UX/Frontend Master Specification V2.1: `docs/variom-ai/04-ux-frontend-interface-master-spec-v2.1.md`.
- VARIOM Execution Charter: `docs/variom-ai/19-execution-charter-and-authority-map.md`.
- VARIOM Product Decisions Register: `docs/variom-ai/20-product-decisions-register.md`.
- Gate B plan: `docs/variom-ai/21-gate-b-normative-contract-plan.md`.
- Functional requirements: `docs/variom-ai/22-functional-requirements-and-acceptance-catalogue.md`.
- Owner input/source recovery: `docs/variom-ai/17-owner-input-source-recovery-audit.md` (source evidence only; not a VARIOM implementation authority).
- Full readiness audit: `docs/variom-ai/18-full-documentation-readiness-audit.md` (historical readiness snapshot, superseded by later owner decisions where recorded).

No MAX source is automatically adopted as a VARIOM requirement by this document. Any future use of MAX source details must be recorded with exact provenance and adoption status under Document 19.
