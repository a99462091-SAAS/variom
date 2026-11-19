# MAX — Implementation Roadmap

**Status:** Planning baseline aligned with approved product architecture  
**Last reviewed:** 2026-10-31  
**Repository:** https://github.com/a99462091-SAAS/ai-content-creation-platform-max  
**Detailed product decisions:** `docs/approved-product-architecture.md`

## 1. Objective and delivery principles

Build MAX as a simple-to-use Saudi/Gulf-first SaaS for businesses and brands to create marketing content with AI. Use Brand DNA, confirmed product facts, reusable assets, a curated creative library, and task-specific instructions to reduce random outputs.

The internal system may be sophisticated only where it materially improves output quality, reliability, or economics. Apply **Maximum Quality, Minimum Overhead**: selective Skills, merged compatible work, deterministic processing where sufficient, reusable context/results, affected-only reruns, no unnecessary agents/services/review stages, and no speculative infrastructure.

One active implementation task at a time. Product specifications may be prepared ahead of implementation, but implementation follows dependencies and explicit task approval.

## 2. Approved decisions and scope boundaries

- One unified creation entry point with only relevant controls.
- Target users: brand/business owners, multi-brand users, and agencies.
- Saudi/Gulf-first, Arabic and English UI; one account may manage multiple brands.
- Brand DNA and reusable product, logo, character, language/dialect, and typography context.
- Internal creative library with Image categories P1–P4 and Video categories V1–V4; detailed styles are selected internally.
- Marketing Ideas and Marketing Copywriting Intelligence; default three distinct idea suggestions.
- No monthly content calendar or publishing-planning feature (explicitly excluded by the user).
- Central Orchestrator plus six Skills: Brand & Context; Marketing; Creative Direction; Typography; Production; Spoken Content.
- Skill contracts, selective routing, approval/version binding, asset identity, dependency fingerprints, safe recovery, account/brand isolation, and cost/performance controls.
- Mandatory unified Master Storyboard for every generated video; continuity-aware segmented generation; capability-aware model routing.
- Prompt Engineering & Generation Intelligence with eight coordinated systems.
- Simple task-based montage: captions, audio enhancement, silence removal, music/rhythm, six motion-graphics categories with multi-selection, and additional instructions. Per-task and total cost shown before execution. No preview before export.
- Credits/subscriptions are planned; payment activation is a later phase.
- Claude is the reasoning/orchestration layer; evaluate suitable generation providers/models, but exact vendor/API remains unapproved until verified.
- Do not assume API support for duration, aspect ratio, start/end frames, references, audio, motion, voice, dialect, or lip-sync.

## 3. Scope control

1. Execute only the active task.
2. Inspect live files and changes before editing.
3. Preserve existing creative library assets and schemas.
4. No feature creep, speculative abstractions, microservices, extra Skills/agents, unnecessary dependencies, or unrelated refactors.
5. No monthly publishing calendar/planner.
6. No professional video timeline editor or advanced VFX in the simple montage module.
7. No provider, model, price, stack, payment, security, or hosting decision without evidence and approval.
8. Unknown product/provider facts remain unknown.
9. Cost estimates must use verified current pricing and actual selected processing paths.
10. Failed jobs and retries must not cause duplicate or incorrect credit deductions.
11. Every task requires purpose, scope, exclusions, files, acceptance criteria, tests, and completion report.
12. Update the Markdown tracker with verified facts; never self-approve a task.

## 4. Phased roadmap

### Phase 0 — Project control and documentation
**Purpose:** establish a consistent source of truth and reconcile repository facts before application implementation.

Deliverables:
- Product/system specification and approved product architecture.
- Roadmap, tracker, repository instructions, and task briefs.
- Existing repository and creative-library inventory.
- Evidence-backed list of confirmed stack/tooling facts and unresolved decisions.

Exit criteria:
- Live repository inspected and documented.
- No conflicting source of truth.
- Current phase/task and next action are explicit.
- Existing library data/schema and draft/approved statuses are preserved.

### Phase 1 — Technical foundation
**Purpose:** establish the smallest maintainable app foundation based on verified repository evidence.

Deliverables:
- Stack/architecture decision record after inspection only.
- Minimal app structure, configuration, environment example, error handling, tests, formatting/linting, and CI where appropriate.
- Basic shell/navigation only if appropriate to the existing app.

Exclusions: product workflow implementation, payment activation, broad refactoring, speculative infrastructure.

Exit criteria: documented start command, relevant checks pass, no secrets committed, structure proportionate to project.

### Phase 2 — Accounts, workspace, brand and asset foundation
**Purpose:** safely store account, brand, and reusable context.

Deliverables:
- Authentication/account lifecycle using approved stack.
- Multi-brand creation, selection, and switching.
- Minimal data model, authorization boundaries, uploads/storage.
- Brand DNA onboarding and validated product/asset records.
- Shared context retrieval and account/brand isolation.

Exit criteria: persistent brand data, safe switching, no context leakage, confirmed facts distinguished from assumptions.

### Phase 3 — Unified creation entry and brief
**Purpose:** capture a creation request with minimal user effort.

Deliverables:
- One creation entry point.
- Image/video content type and primary category controls based on existing taxonomy.
- Brief assembly from task, selected brand, product facts, and uploaded assets.
- Conditional follow-up only for materially missing information.
- Explicit asset roles: product reference, logo, character, inspiration, other.

Exit criteria: validated brief, no repeated questions for saved context, conflicts surfaced rather than guessed.

### Phase 4 — Creative library retrieval and prompt intelligence
**Purpose:** turn the brief into a conflict-checked, provider-ready instruction.

Deliverables:
- Library retrieval/ranking within the selected content type/category.
- Safe fallback when style coverage is weak.
- Prompt Engine: normalize context, detect gaps/conflicts, select internal style, plan execution, assemble, validate, and emit traceable metadata.
- Provider-neutral request/response contracts.
- Regression fixtures for representative briefs.

Exit criteria: schema-validated prompt, explicit brand/product/reference constraints, no unsupported claims, low-confidence matches handled safely.

### Phase 5 — First end-to-end image workflow
**Purpose:** prove one complete production path before multiplying features.

Deliverables:
- Provider adapter only after actual model/API access and capabilities are verified.
- Image generation, progress/error states, safe retry, output storage, prompt/provider/version/source metadata.
- Preserve supplied product/logo references to the extent supported.

Exit criteria: real result through app, recoverable failures, retrievable output/context, provider details isolated.

### Phase 6 — Marketing ideas and copywriting
**Purpose:** provide grounded creative ideas and approved copy for production.

Deliverables:
- Marketing context/objective/angle interpretation.
- Three distinct default idea suggestions, editable and selectable.
- Copywriting strategy, hooks, messaging, platform/format adaptation, CTA, dialect/brand voice, claim validation.
- Structured handoff to Creative Direction.

Exclusions: monthly content calendars, publishing schedules, and content-planning dashboards.

Exit criteria: ideas and copy are grounded, editable, brand/dialect-consistent, and feed the creation brief.

### Phase 7 — Typography, editing and controlled iteration
**Purpose:** render accurate text and support bounded changes.

Deliverables:
- Font library and brand font support.
- Arabic/multilingual text composition and layout.
- Versioned edit/variation workflow preserving unchanged elements.
- Simple Smart Editing specification and, when implementation phase is authorized, selected montage tasks.

Simple montage scope: Auto Captions with styles; Audio Enhancement; Silence Removal; Music & Rhythm; Motion Graphics (six categories, multi-selection); Additional Instructions. Per-task and total price before approval; no preview before export; no professional timeline editor.

Exit criteria: text rendering and edits preserve approved content; montage runs only selected supported tasks and exports one final file.

### Phase 8 — Video and spoken-content workflow
**Purpose:** extend the proven creation path to structured video production.

Deliverables:
- Master Storyboard, scene/shot breakdown, Start/End Frames where feasible, approval/version lock.
- Director's shot/camera/pacing/transition/feasibility decisions.
- Prompt compiler and provider capability registry.
- Segmented generation with continuity, unified timeline, safe end-frame selection, recoverable partial jobs.
- Spoken content, voice identity, dialect, voice-over/dialogue, audio and lip-sync only where verified.
- Editing/post-production within the approved boundaries.

Exit criteria: no unsupported controls, validated durations/formats, one coherent storyboard, recoverable jobs, consistent asset and credit records.

### Phase 9 — Reusable virtual character
**Purpose:** create and reuse an approved synthetic character when needed.

Deliverables:
- Character brief, proposal, user approval, editable attributes, Character Sheet/reference assets.
- Versioned reuse in compatible image/video workflows.
- Consent, rights, and synthetic-person safeguards.

Exit criteria: character identity/version explicit; no false claim of real customer/testimonial.

### Phase 10 — Project library and focused dashboard
**Purpose:** retrieve and reuse prior work.

Deliverables:
- Search/filter projects and generations, statuses, versions, downloads, and source context.
- Dashboard for selected brand, usage balance, recent activity, and plan state.
- Basic settings and usage history.

Exclusions: complex reporting/analytics without demonstrated need.

Exit criteria: work is retrievable and usage/status match underlying records.

### Phase 11 — Credits, subscriptions, payment activation
**Purpose:** monetize with auditable balances and clear costs.

Deliverables:
- Credit ledger: grants, reservations, charges, refunds/reversals, provider usage.
- Subscription and top-up rules.
- Pricing based on verified provider/internal costs and approved commercial policy.
- Payment integration, webhook verification, idempotency, and reconciliation only after provider/legal requirements are confirmed.

Exit criteria: duplicate events cannot duplicate balance changes; failed-job policy explicit; balances auditable.

### Phase 12 — Production readiness and launch
**Purpose:** verify critical journeys and release safely.

Deliverables:
- End-to-end tests for accounts, brands, briefs, generation, editing, retrieval, usage, and billing.
- Security, file access, secret management, validation, rate limits, and logging review.
- Arabic/English, RTL, mobile, accessibility, and error-message checks.
- Monitoring, backups/recovery, deployment/rollback, support, privacy/terms/legal review.
- Closed beta, defect triage, launch checklist.

Exit criteria: no launch-blocking defects; critical journeys pass; deployment/rollback documented; beta feedback triaged.

## 5. Cross-phase architecture requirements

- Central Orchestrator and six Skills; selective execution only.
- Structured Skill contracts and task envelope.
- Version-bound approvals and stable asset identities.
- Dependency fingerprints and affected-only reruns.
- Unified video timeline and continuity-aware segments.
- Capability-aware provider routing; no assumed API support.
- Bounded retries, idempotent operations, persisted partial success.
- Account/brand isolation and authorization at every access boundary.
- Cost monitoring and separate provider cost/internal cost/customer price/credits.
- Design-level acceptance suite of 52 cases; tests must be implemented and run before claiming pass.

## 6. Open decisions

Authentication, hosting provider/region, deployment, final infrastructure/service providers (Next.js, TypeScript, PostgreSQL, private object storage and simple background jobs were initially approved on 2026-10-29 as architectural choices, not verified production decisions, with no programming authorization), model/API, voice/transcription/music providers, licensing, actual prices, upload/export limits, ranking/complexity weights, and production legal/privacy requirements remain open until their phase requires them. Record evidence and obtain approval for material choices.

## 7. Definition of done

A task is done only when it meets approved scope, related existing files were inspected, relevant checks were run and outcomes recorded, failure/security/cost cases were handled where relevant, final diff is in scope, limitations are stated, tracker is updated, and the reviewer accepts it. File creation alone is not completion.

## 8. Resume protocol

1. Read this roadmap, `docs/approved-product-architecture.md`, and `docs/project-tracker.md`.
2. Inspect the live default branch and recent changes.
3. Reconcile actual repository state with the tracker.
4. Confirm the last accepted task and unreviewed changes.
5. Continue only the next approved task; do not start a later phase implicitly.
