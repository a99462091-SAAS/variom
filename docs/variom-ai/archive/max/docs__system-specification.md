# MAX — Product and System Specification

**Status:** Approved product and architecture baseline; implementation details remain subject to repository inspection and technical verification.  
**Detailed decision record:** `docs/approved-product-architecture.md`.

## 1. Product outcome

MAX is a Saudi/Gulf-first SaaS for business owners, brand owners, e-commerce businesses, and agencies managing multiple brands. It helps users create marketing images, advertising creatives, carousels, scripts/copy, videos, and improve uploaded videos without learning complex production tools.

**Product test:** the user selects a task and brand, supplies only missing context, reviews/approves decisions where required, and receives a usable result with traceable versions and transparent usage.

## 2. Users and initial market

- Brand/business owner managing one brand.
- User managing several brands.
- Agency managing multiple client brands.
- Saudi Arabia first, then UAE, Kuwait, Oman, and Egypt as expansion priorities.
- Arabic and English interface.
- One account may manage multiple brands. Employee roles and granular permissions are not part of the initial scope.

## 3. Product scope

Phased capabilities:
- Brand DNA, product facts, approved assets, character references, language/dialect, and typography profile.
- Marketing ideas and copywriting.
- Image/ad creation, carousel content, scripts, and video.
- Internal creative-style library and automatic creative execution selection.
- Typography and Arabic/multilingual rendering.
- Spoken content, voice-over, dialogue, dialect, voice identity, and lip-sync when verified capabilities support them.
- Unified Master Storyboard, shot planning, segmented video production, continuity, editing, and export.
- Simple task-based enhancement of user-uploaded video.
- Reusable virtual characters.
- Project library, versions, credits, subscriptions, and later payment activation.

**Explicitly excluded:** monthly content calendars and publishing-planning features; professional timeline editing; complex VFX/3D; unrestricted manual frame editing; unnecessary integrations, agents, services, or role systems.

This is product direction, not permission to implement every future capability at once. Follow the roadmap and active task.

## 4. Operating principles

1. **Maximum Quality, Minimum Overhead:** choose the simplest path that meets the quality bar.
2. **Brand consistency:** reuse approved Brand DNA and assets; ask only for missing information that materially changes output.
3. **Truthfulness:** never invent product facts, prices, claims, testimonials, guarantees, credentials, or brand details.
4. **User control:** preserve explicit decisions and bind approvals to exact versions.
5. **Simple UX:** show only controls relevant to the chosen task.
6. **Selective orchestration:** run only required Skills; merge compatible work and avoid redundant AI calls.
7. **Incremental recovery:** save successful partial work and rerun only affected dependencies.
8. **Traceability:** retain task, version, asset, prompt/model, provider, status, and usage metadata where supported.
9. **Provider flexibility:** isolate vendor-specific behavior behind adapters and verified capability checks.
10. **Cost awareness:** distinguish estimate, actual provider cost, internal processing cost, customer price, and credits.
11. **Rights and consent:** track reference provenance; do not present generated/scripted characters as real customers or genuine testimonials.
12. **No scope creep:** do not add a feature or infrastructure merely because it is technically possible.

## 5. Brand and context

Brand DNA includes brand identity, sector, description, personality/tone, audience, differentiators, colors/visual identity where available, language, explicit dialect, typography preferences/fonts, product facts, logo, and approved references/assets.

Use shared, selective context packages: Brand DNA Snapshot, Product Reference Package, Character Reference, Language & Dialect Profile, Typography Profile, and user constraints/approved decisions. Preserve original assets and isolate all account/brand data. Derived attributes must be distinguished from confirmed facts.

## 6. Creative library and marketing intelligence

The creative library hierarchy is:
- Content type: Image or Video.
- Image categories: P1 Product Photography; P2 Static Advertising Creative; P3 Carousel Content; P4 Lifestyle & Contextual Photography.
- Video categories: V1 Creator-Led / UGC-Style Video; V2 Product Showcase / Demonstration; V3 Motion Graphics / Animation; V4 Commercial / Advertising Video.
- Detailed execution styles are internal; MAX selects them automatically.

Keep category distinct from objective, subject, publishing format, production method, and copywriting approach. Unknown facts remain unknown. Preserve reference rights and evidence metadata. The library remains a foundation until records and retrieval are validated.

Marketing Ideas Intelligence provides context/objective/angle analysis, idea generation, diversity, ranking, and production handoff. The default presentation is three distinct ideas with concise rationale. This does not include a monthly content calendar.

Marketing Copywriting Intelligence comprises twelve coordinated systems: context/brief, strategy, hook/headline, persuasive messaging, platform-specific copy, format-specific copy, CTA/conversion, brand voice/dialect, length/density, variations/diversity, accuracy/claims validation, and quality/finalization.

## 7. Dialect and typography

**Explicit Dialect Lock:** a dialect explicitly selected for a brand or task binds all text- and speech-producing components unless the user changes it. Language, dialect, and tone are separate. Do not infer dialect from audience nationality alone or mix dialects randomly. Learn corrections per brand.

Typography uses a professional built-in font library and supports user brand fonts. MAX selects typography/layout automatically, with user adjustments before design approval. Prefer programmatic text composition after generation for accuracy; direct model-rendered text is allowed only when reliable. Support Arabic RTL and multilingual rendering. Typography formats approved text and does not rewrite it.

## 8. Central Orchestrator and six Skills

The Orchestrator Agent manages workflow, dependencies, context, approvals, conflicts, versions, selective execution, and cost/time optimization. It is not a seventh Skill.

1. **Brand & Context Intelligence:** Brand DNA, products/assets, language/voice, preferences/decision memory, context retrieval.
2. **Marketing Intelligence:** marketing ideas, copywriting, dialect/brand voice, structured copy packaging.
3. **Creative Direction Intelligence:** creative library, concept/story, director decisions, storyboard, feasibility.
4. **Typography Intelligence:** font/style, hierarchy/layout, Arabic/multilingual rendering, image/video typography.
5. **Production Intelligence:** prompt engineering, model routing, reference/continuity, generation, editing, post-production, export.
6. **Spoken Content Intelligence:** speech strategy, dialogue/voice-over, dialect, voice identity, timing/lip-sync, audio tracks.

These are coordinated Skills/contracts, not necessarily separate AI agents. Do not create one model call per subcomponent. Full inputs/outputs, rules, and handoffs are in `docs/approved-product-architecture.md`.

## 9. Video workflow

Every video passes through one unified Master Storyboard; no direct generation bypass. User chooses 10/20/30/40 seconds with MAX recommendation, selects optional character/product references, enters an idea, reviews/edits the script, approves it, and selects 9:16, 4:5, 1:1, or 16:9.

The Master Storyboard includes scenes/shots, Start/End Frames where useful, character/product references, timing, camera, environment, motion, and transitions. The user approves the complete storyboard before production. Structured shot-specific reference packages are derived internally.

Segmenting is a production constraint, not a story split. For example, a 27-second video under a verified 10-second generation limit may use 10+10+7 seconds. The actual segment limit must be verified for the chosen API. Maintain one timeline and continuity state; select valid end frames, preserve successful segments, and rerun only affected work. Use deliberate creative transitions instead of forcing spatial continuity between unrelated environments.

The Director's Decision Engine controls shot selection, camera movement, sequence, pacing, transitions, feasibility, and final shot plan. Camera/shot vocabulary and the eight prompt-engineering systems are specified in the detailed architecture document.

## 10. Spoken content and audio

The Spoken Content Skill separates character dialogue, voice-over, narration, natural conversation, mixed speech, and no-speech cases. It owns spoken script/audio, voice identity, dialect, timing, lip-sync compatibility, and audio tracks. The script separately identifies visual action, character dialogue, voice-over, and on-screen text. Do not add speech to a silent character. Keep voice identity stable when a character speaks; use one continuous voice-over track where appropriate. Avoid unnecessary separate calls.

## 11. Simple Smart Editing Engine

The montage tool is a task-based video enhancement tool inside Skill 05, not a professional timeline editor.

User flow: upload video → select tasks/styles → see each task's cost and total → approve → execute directly → receive one final video.

**No preview stage before export.** The user explicitly rejected previews.

Approved functions:
1. Auto Captions with varied styles (Minimal, Dynamic, Highlight, Cinematic, UGC/Social, Bold Impact examples), with language/dialect support only to the accuracy actually available.
2. Audio Enhancement (noise reduction, speech clarity, level balancing, recoverable wind/distortion reduction).
3. Silence Removal while preserving natural pauses, speech boundaries, music, and meaningful sound.
4. Music & Rhythm using licensed library tracks or user uploads, mood, level balancing, ducking, fades, and suitable beat synchronization.
5. Motion Graphics with six categories: Kinetic Typography; Highlights & Callouts; Icons & Infographics; Product Features; Shapes & Effects; Titles & Lower Thirds. The user may select multiple categories in one video. Use ready templates, maintain brand consistency, and avoid clutter/obscuring subjects.
6. Additional Instructions field to clarify supported selected tasks; clearly identify unsupported requests.

Do not duplicate Audio Enhancement: the user's repeated mention refers to one function. Exclude professional multi-track timeline editing, frame-by-frame editing, complex VFX/3D, story reconstruction, and new-scene generation in this tool.

Use deterministic/local tools when sufficient. Preserve the original, create a separate output, process only selected tasks, show per-task and total cost before approval, and rerun only affected tasks. When silence changes the timeline, update caption/music/motion timings. Final output is one validated video. Do not invent fixed prices; use verified actual processing paths and current provider/licensing costs.

## 12. Responsibility boundaries

- Skill 02 owns copy and message meaning.
- Skill 04 owns typography and visual text layout.
- Skill 05 owns visual assembly, video processing, montage execution, final integration, and export without rewriting approved copy.
- Skill 06 owns dialogue, voice-over, voice identity, speech timing, and audio track preparation/mix.
- Skill 05 integrates prepared audio with video and exports the final asset.

## 13. Contracts, versions, reliability, and cost

Each Skill contract includes purpose, inputs, outputs, dependencies, execution rules, and completion status. Shared task envelope includes task/brand/project IDs, workflow type, input data, approved decisions, asset references, version, status, outputs, and errors.

Skill results: SUCCESS, NEEDS_INPUT, NEEDS_APPROVAL, PARTIAL_SUCCESS, BLOCKED, FAILED. Operation states: PENDING, RUNNING, WAITING_APPROVAL, WAITING_INPUT, RETRYING, PARTIAL_SUCCESS, COMPLETED, FAILED, CANCELLED, BLOCKED.

Each asset has stable identity/version/source/status/fingerprint. Bind approvals to exact versions. Use dependency/version/resource locks. Maintain one unified video timeline. Save successful partial results; use bounded retries/timeouts and stable operation IDs. Prevent duplicate generation/charges and isolate all account/brand data.

Cost architecture includes selective AI calls, context/result reuse, dependency fingerprints, verified model routing, adaptive generation, bounded retry, safe parallelism, monitoring, and an auditable credit ledger. Never charge twice after retry. Failed-job charging/refund rules must be explicit.

## 14. Design-level acceptance tests

The approved design suite contains 52 cases: Image (6), Video (8), Modifications (8), Failure/Recovery (9), Concurrency/Data Integrity (6), Cost/Credits (7), and Quality/Consistency (8). Three end-to-end scenarios cover a static product ad, a multi-segment video with character/speech, and partial editing plus provider failure.

These are design acceptance cases, not executed software tests. Do not report them as passing until implemented and run.

## 15. Open technical decisions

The following remain open until their relevant roadmap phase:
- Authentication, hosting provider/region, deployment, and final infrastructure/service providers. (Next.js, TypeScript, PostgreSQL, private object storage and simple background jobs were initially approved by the user on 2026-10-29 as architectural choices; they are not verified production decisions and do not authorize programming. See `docs/approved-product-architecture.md` §16.)
- Exact generation model/API/provider and actual capabilities/access.
- Speech recognition, voice, music licensing, audio processing, motion-template, and editing tools.
- Current provider prices, licensing costs, and customer credit conversion.
- Upload size/duration/resolution and export-format limits.
- Empirical ranking/complexity weights and quality benchmarks.
- Production legal, privacy, rights, and operational requirements.

Do not assume or silently decide these items. Verify with current documentation and real tests, then record material decisions with evidence and user approval.

## 16. Source of truth

1. `docs/approved-product-architecture.md`: consolidated approved product/architecture decisions.
2. This document: product boundaries and system responsibilities.
3. `docs/implementation-roadmap.md`: phased implementation order and gates.
4. `docs/project-tracker.md`: live status, evidence, blockers, and next action.
5. `CLAUDE.md` and `docs/claude-code-rules.md`: execution discipline.
6. Phase-specific task briefs and technical ADRs: bounded implementation contracts.

If documents conflict, do not guess. Report the exact conflict and seek the smallest necessary decision.
