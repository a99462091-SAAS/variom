# VARIOM — Workflow & Job State Machines

**Version:** 1.0 | **Status:** NORMATIVE DRAFT — Gate B | **Authority:** Documents 19–23 and Product Vision V2.0.

## 1. Purpose and boundaries
Defines technology-neutral user workflows, job lifecycle, transitions, failure handling and recovery. It does not choose a queue, scheduler, database, provider or framework. One user-visible Production Task may coordinate multiple internal Jobs; implementation must preserve one coherent user-facing outcome.

## 2. Shared job lifecycle
Canonical states:
- **DRAFT** — editable task intent; no billable execution.
- **VALIDATING** — server checks inputs, ownership, capability and policy.
- **AWAITING_CONFIRMATION** — valid quote is available; no reservation or provider call yet.
- **QUEUED** — explicit confirmation accepted and reservation recorded.
- **RUNNING** — execution is active.
- **RECONCILING** — outcome is uncertain (timeout, lost callback, worker interruption); do not blindly retry or settle.
- **PARTIALLY_COMPLETED** — some batch items succeeded and others failed/remain unresolved.
- **SUCCEEDED** — all required outputs validated, persisted and linked to the library.
- **FAILED** — terminal failure with reservation released or actual usage reconciled.
- **CANCEL_REQUESTED** — cancellation requested while execution may still be active.
- **CANCELLED** — cancellation confirmed; usage reconciled and unused reservation released.
- **EXPIRED** — confirmation/quote/queued-work validity expired under an explicit policy.

Transitions MUST be validated server-side. Terminal states are immutable except for separately recorded reconciliation/correction events. A job MUST NOT transition from terminal failure/cancellation back to RUNNING; a new attempt or job is created under defined idempotency rules.

## 3. Shared transition rules
1. DRAFT → VALIDATING on submit.
2. VALIDATING → DRAFT with actionable validation errors; → AWAITING_CONFIRMATION only when inputs and a current quote are valid.
3. AWAITING_CONFIRMATION → QUEUED only after explicit user confirmation and successful credit reservation; cancellation/expiry creates no provider work.
4. QUEUED → RUNNING when a worker claims the job; claim must be concurrency-safe.
5. RUNNING → SUCCEEDED only after output validation, durable asset persistence and library linkage.
6. RUNNING → RECONCILING when external outcome is unknown; → PARTIALLY_COMPLETED for mixed batch outcomes; → FAILED/CANCEL_REQUESTED only after safe reconciliation.
7. Cancellation before provider execution releases the full reservation. During execution, cancellation is best-effort; settle confirmed actual usage and release unused amount.
8. A timeout is not proof of provider failure. Reconcile provider status/idempotency before retry.
9. Duplicate submit/confirm/callback requests MUST be idempotent.
10. User-visible progress is derived from persisted state and item counts, not client timers or fabricated percentages.

## 4. Workflow contracts

### 4.1 Authentication and onboarding
- Register → verify email → authenticate → create initial Brand Profile → optional Brand DNA steps → Dashboard.
- Required initial profile: brand name, activity, target audience; logo optional.
- Known answers are prefilled; optional steps can be skipped, edited and saved.
- Unverified users cannot enter protected brand/content workflows. Exact session/recovery security is in Document 27.

### 4.2 Brand and Brand DNA
- Read/edit only brands authorized to the current account.
- Save creates a new version when a change affects task context; tasks pin the version used.
- Brand deletion starts the governed deletion workflow; it is not a hard-delete shortcut.
- No Product Catalog or cross-account brand transfer.

### 4.3 Ideas
- Image/Video Studio accepts one idea or five suggestions.
- Idea generation is distinct from paid media generation. It MUST NOT reserve credits unless a separately approved and priced operation contract exists.
- User edits are versioned and become the selected brief input.

### 4.4 Monthly Content
1. Select 8/12/16 posts, up to three goals (one primary), up to ten manual product images with optional per-image price, optional character and product-level formats.
2. Build a plan with smart image/video distribution. Do not invent fixed ratios/counts.
3. Optional template review; skip proceeds directly. In review only idea and copy/dialogue are editable. Reference images are illustrative.
4. Validate each item: images/videos only, no carousel, monthly video <=10 seconds.
5. Quote full billable work; explicit confirmation reserves credits.
6. Execute item jobs; one parent task aggregates progress.
7. Each completed item is independently validated and saved to Content Library. Failed items remain visibly failed; never mark the whole batch complete while required items are unresolved.
8. Results expose view/open/download only.

Progress stages shown to user: Planning → Content Preparation → Generation → Final Quality Check. Display one progress indicator and completed/total count. Internal retries do not inflate completed count.

### 4.5 Image Studio
- Validate P1–P4, one/five ideas, per-task product image, optional price/character and Instagram Portrait/Landscape.
- System selects approved internal style.
- Show actual quote before confirmation. No initial paid post-generation edit loop.
- Persist validated image and library entry before SUCCEEDED.

### 4.6 Video Studio and Storyboard
- Validate V1–V4, one/five ideas, per-task product image, optional character, 10/20/30 seconds and Reels Portrait/Landscape Video.
- Create and validate Master Storyboard before any provider video-generation call. Direct bypass is prohibited.
- Scene review is optional; if used, only approved scene description and dialogue/text are editable.
- Storyboard duration allocations must reconcile to requested total within the tolerance defined by the storyboard contract.
- No separate user-facing audio controls.
- Provider orchestration, segmenting and continuity failures are handled as one coherent task; do not expose unnecessary orchestration complexity.

### 4.7 Smart Editing
- Preserve original input as immutable source; create separate output.
- Validate only the six approved tasks and six Motion Graphics categories in Document 31.
- Only verified executable capabilities may be selected.
- Quote selected operations before execution; do not offer live pricing without evidence.
- Partial task failure must identify completed/failed operations and reconcile actual usage.

### 4.8 Virtual Character
- Create/edit/save/reuse through the VARIOM questionnaire and versioned Character Sheet.
- Character changes create a new version; running tasks retain pinned version.
- Consent/rights and synthetic-character checks precede use where applicable.
- Capability-dependent voice/dialect/lip-sync controls remain unavailable until verified.

### 4.9 Content Library and deletion
- Successful output persistence and library linkage are part of completion, not a later best-effort action.
- Filters: type/date; grid, open/preview and authorized download.
- Delete entry, delete output and delete brand/account are distinct commands with explicit confirmation and lifecycle orchestration.
- Deletion must include storage, references, processors and backups as governed by Document 27/35.

## 5. Batch and recovery rules
- Parent task owns the requested batch; child item jobs own individual execution outcomes.
- A completed item is counted once, even if callbacks/retries duplicate.
- If the worker stops, recovery resumes from persisted state and idempotency keys; it does not repeat confirmed external work without reconciliation.
- Unknown provider outcome enters RECONCILING and blocks duplicate charge/generation.
- Partial batches expose completed/total and item-level outcomes. Only completed items are library outputs.
- If persistence/library linkage fails after provider success, keep the job in a recoverable reconciliation state; do not report success until durable linkage is restored.
- Retry policy, backoff ceilings and provider-specific retryability are configured only after capability evidence; no universal blind retry.

## 6. Credit coupling
Every billable transition is coordinated with the Credit contract:
- quote before confirmation;
- reserve before dispatch;
- no provider dispatch if reservation fails;
- reconcile actual usage exactly once;
- release unused reservation;
- preserve an auditable outcome on failure/cancellation.
Job state and ledger state must be cross-referenced but neither is inferred from the other.

## 7. Acceptance criteria
- Every user workflow has valid, invalid, cancellation, timeout and partial-failure paths.
- Video cannot bypass storyboard.
- Monthly batches enforce 8/12/16, no carousel and <=10-second videos.
- Duplicate requests/callbacks cannot duplicate outputs or charges.
- Unknown provider outcomes reconcile before retry.
- User progress matches persisted backend state.
- Success requires durable output and library linkage.
- Preview/mock never mutates real jobs/assets/credits.
- No provider, stack or infrastructure assumption is introduced.

## 8. Deferred implementation parameters
Provider retry limits, queue scheduling, timeout durations, concurrency, quote expiry, retention windows and precise storyboard timing tolerances require verified evidence or explicit contract decisions. They must not be invented in implementation.
