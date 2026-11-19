# VARIOM — API & Schema Contracts

**Version:** 1.0 | **Status:** NORMATIVE DRAFT — technology-neutral | **Authority:** Documents 19–24.

## 1. Purpose
Defines the API contract rules and logical operation surface. It intentionally does not prescribe REST/GraphQL/RPC, URL paths, database types, framework or transport. A later implementation mapping may choose a protocol without changing these semantics.

## 2. Universal request rules
- Every protected operation requires an authenticated session and server-derived account context.
- Brand/task/asset IDs supplied by clients are selectors only; server verifies ownership and relationship on every request.
- Validate shape, length, type, size, enum, cross-field rules and current lifecycle state server-side.
- Reject unknown enum values and unsupported options; never silently coerce into a different product behavior.
- Mutations require idempotency semantics. Repeated same-key/same-payload requests return the original operation outcome; same key with different payload is rejected.
- Use stable opaque identifiers; never expose storage paths, secrets, provider credentials or internal stack traces.
- Use consistent timestamps and explicit timezone semantics; server timestamps are authoritative.
- Responses distinguish persisted state from pending work and distinguish mock/preview from real execution.

## 3. Logical operation groups
### Identity
- Register, verify email, authenticate, logout, request password recovery, complete recovery, read/update account preferences.
- Do not expose social-login operations in first-release scope.

### Brands and Brand DNA
- Create/read/update/archive-or-delete brand; list/switch accessible brands.
- Read/update Brand DNA; read/manage Brand Assets.
- Updates validate account ownership and create a version when task-relevant context changes.

### Ideas and briefs
- Request one/five ideas; retrieve request status/results; edit selected idea/copy.
- Idea suggestion is not a generation job and does not imply a credit charge.

### Production tasks
- Create/validate Monthly, Image, Video or Smart Editing task.
- Retrieve task/plan/brief; request quote; confirm billable operation; cancel; retrieve progress and item outcomes.
- Video task creation must result in a storyboard before generation is dispatchable.

### Virtual Characters
- Create/read/update/version character; read/edit Character Sheet; select authorized character version.
- Consent/rights evidence and capability checks are server-enforced.

### Library and assets
- List/filter library; read asset detail; request authorized preview/download; request deletion.
- Never return a permanent public URL for private media. Use short-lived authorized access mechanism selected by implementation.

### Credits
- Read balance/ledger summary; request quote; confirm reservation; read operation settlement.
- Clients cannot directly mutate balances or ledger entries.

## 4. Request/response envelope
Each operation response MUST identify:
- operation result/status;
- resource identifier(s) where applicable;
- current persisted lifecycle state;
- server timestamp;
- validation issues or actionable next step where relevant;
- correlation/request identifier for support without exposing secrets.

Asynchronous submissions return an accepted task/job reference and current state, not a fabricated completed result. Polling or event delivery is implementation-specific but must expose the same canonical state model in Document 24.

## 5. Error taxonomy
Use stable machine-readable error categories:
- AUTHENTICATION_REQUIRED
- EMAIL_VERIFICATION_REQUIRED
- ACCESS_DENIED (avoid leaking whether another tenant's resource exists)
- NOT_FOUND
- VALIDATION_FAILED (field-level safe details)
- INVALID_STATE_TRANSITION
- IDEMPOTENCY_CONFLICT
- QUOTE_REQUIRED / QUOTE_EXPIRED
- INSUFFICIENT_CREDITS
- CAPABILITY_UNAVAILABLE
- POLICY_REJECTED
- RATE_LIMITED
- INPUT_MEDIA_INVALID
- PROVIDER_TEMPORARILY_UNAVAILABLE
- PROVIDER_OUTCOME_UNKNOWN
- OPERATION_CANCELLED
- STORAGE_UNAVAILABLE
- INTERNAL_ERROR

Errors MUST not include credentials, raw provider payloads, private storage locations or stack traces. Retryability is explicit and only indicated when safe.

## 6. Logical data schemas
All records follow Document 23 ownership and provenance rules. Common metadata: stable ID, account scope, optional brand scope, created/updated timestamps, lifecycle status, version where mutable, and provenance references where task-influencing. Do not duplicate account/brand names as authority.

Key payload concepts:
- Brand Profile: name, activity, audience, optional logo reference.
- Brand DNA: approved profile/audience/personality/voice/language/visual identity/asset references and version.
- Task: type, brand, brief, validated inputs, requested product options and state.
- Monthly plan: 8/12/16 count, up to three goals, item modality/format, manual input refs, optional review, smart distribution.
- Image: P1–P4, one/five idea mode, manual product image, optional price/character, Instagram Portrait/Landscape.
- Video: V1–V4, 10/20/30 seconds, manual product image, optional character, Reels Portrait/Landscape, mandatory storyboard reference.
- Editing: approved task selection, selected motion categories, source asset and additional instructions.
- Job: operation, state, idempotency, attempts, progress, terminal outcome.
- Quote/reservation/ledger/settlement: Document 26.
- Library entry: output reference, type/date metadata, authorized visibility/deletion state.

## 7. Upload and download contract
- Upload initiation and completion are separate validated steps if required by the selected transport.
- Enforce approved file types, byte limits, dimensions/duration limits and malware/content checks before use; exact values remain evidence-gated.
- Quarantine untrusted uploads until validation completes.
- Media is private by default; downloads require current authorization and short-lived access.
- Validate ownership and task linkage at upload completion; abandoned uploads are cleaned under documented lifecycle policy.
- Never accept a client-provided storage path as proof of uploaded content.

## 8. Pagination and filtering
Library listing supports type/date filters and bounded pagination. Ordering is stable; cursor/page semantics are documented by the chosen protocol. Reject unsupported filters rather than silently ignore them.

## 9. Security and compatibility
- Server-side authorization is mandatory for reads, writes, downloads and state changes.
- Use explicit schema versions for persisted payloads and external contracts.
- Breaking changes require compatibility/migration plan and owner authorization when product behavior/data loss is implicated.
- Rate limits and abuse controls are defined in Document 27.
- No API may expose excluded features: Product Catalog, publishing, scheduling, analytics, team collaboration, approvals, ZIP export or professional timeline editing.

## 10. Acceptance criteria
- Every logical operation maps to requirements and a state machine.
- Authorization is verified on every resource access.
- All mutation operations define idempotency and valid-state behavior.
- Error taxonomy is stable and safe.
- Async responses never claim completion prematurely.
- Uploads are validated and private; downloads are authorized.
- Credit and provider data are server-derived.
- No technology-specific schema or API path is falsely presented as approved.
