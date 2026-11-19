# MAX — Approved Product Architecture and Decision Baseline

**Document status:** Approved product and architecture direction captured from user decisions through 2026-10-31.  
**Implementation status:** Specification only. This document does not authorize product-code implementation, provider selection, dependency changes, or deployment.  
**Repository:** `a99462091-SAAS/ai-content-creation-platform-max`

## 1. Product direction and non-negotiable principles

MAX is a Saudi/Gulf-first AI marketing-content SaaS for business owners, brand owners, e-commerce businesses, and agencies managing multiple brands. Initial regional priorities are Saudi Arabia, followed by the UAE, Kuwait, Oman, and Egypt. The interface is Arabic and English. One account can manage multiple brands; employee roles and granular permissions are out of initial scope.

The product should deliver high-quality, useful marketing outputs through a simple user experience. Internal sophistication is permitted only where it materially improves quality, reliability, or cost.

**Maximum Quality, Minimum Overhead**
- Prefer the smallest workflow that meets the quality bar.
- Do not add independent agents, skills, models, services, or review stages without a demonstrated need.
- Merge compatible reasoning and processing steps; use deterministic code/libraries when sufficient.
- Reuse approved context and successful outputs; rerun only affected work after a change.
- Run only the skills needed for the selected task.
- Avoid feature expansion that increases generation time, cost, operational load, or user complexity without clear value.
- Unknown provider/API capabilities, prices, and performance must remain explicitly unverified until tested.

Do not implement a feature merely because it appears in a future architecture section. Follow the phase roadmap and active task brief.

## 2. Product scope and boundaries

### In-scope product capabilities (phased)
- Brand DNA and reusable brand/product/character assets.
- Marketing idea suggestions and marketing copywriting.
- Image creation, advertising creatives, carousel content, scripts, and video creation.
- Creative style selection and prompt assembly.
- Typography and multilingual/Arabic text rendering.
- Spoken content, dialogue, voice-over, dialect, voice identity, and lip-sync where verified capabilities permit.
- Video storyboard, shot planning, generation, continuity, editing/post-production, and simple user-uploaded-video enhancement.
- Reusable virtual characters.
- Project library, versions, credits, subscriptions, and later payment activation.

### Explicit exclusions / scope corrections
- **No monthly content calendar or publishing-planning product feature.** The user explicitly excluded Content Planning & Calendar. Remove it from future product scope and do not build it.
- No general-purpose professional timeline editor or Premiere/DaVinci replacement.
- No unrestricted free-form video editor, frame-by-frame editing, complex VFX/3D, or automatic cinematic reconstruction in the simple montage tool.
- No unnecessary external integrations, employee-role system, microservices, or extra agents.
- No invented provider capability, model availability, price, or API support.

## 3. Brand and context foundation

Brand DNA is created once and reused: brand name, logo, sector, description, personality/tone, audience, differentiators/advantages, colors/visual identity where available, language, explicit dialect, typography preferences/fonts, product facts, and approved assets.

The platform may derive useful brand attributes from supplied information, but must distinguish confirmed facts from inferred suggestions. It must not invent product specifications, claims, offers, testimonials, certifications, guarantees, or availability.

A shared context layer stores and retrieves only what a task needs:
- Brand DNA snapshot.
- Product reference package and original product images.
- Character sheet and character version.
- Language, dialect, and brand-voice profile.
- Typography profile and licensed/custom fonts.
- User/task constraints and approved decisions.

Do not alter original reference assets silently. Isolate accounts and brands; never leak context or assets across them.

## 4. Creative Content Intelligence Library

The library is an internal decision resource. The user chooses content type and primary category; MAX selects detailed execution style automatically.

### Hierarchy
- Level 1: Image or Video.
- Level 2 image categories: P1 Product Photography; P2 Static Advertising Creative; P3 Carousel Content; P4 Lifestyle & Contextual Photography.
- Level 2 video categories: V1 Creator-Led / UGC-Style Video; V2 Product Showcase / Demonstration; V3 Motion Graphics / Animation; V4 Commercial / Advertising Video.
- Level 3: detailed creative execution styles, internal to MAX and not exposed as a long technical choice list.

Keep category separate from marketing objective, subject/topic, publishing format, production method, and copywriting style. Do not turn every objective, format, or topic into a category.

Style records should capture stable ID/version, bilingual names, definitions, category/family, aliases, visual/narrative execution, composition, camera, lighting, color, movement, pacing, brand/product visibility, text-safe areas, fit and poor-fit conditions, required assets, complexity/cost only when evidenced, AI suitability, human review, selection signals, alternatives/combination rules, references/rights, copy guidance, prompt instructions, and quality checks. Unknowns remain unknown.

Do not imply commercial effectiveness without evidence. Separate style-match confidence, evidence strength, and product-fact confidence. Keep seed examples separate from approved production records. Validate records against schemas before production use.

## 5. Marketing and copywriting intelligence

### Marketing Ideas Intelligence
- Marketing Context Intelligence.
- Marketing Objective Intelligence: Awareness, Reach, Engagement, Lead Generation, Direct Sales, Product Education, Trust Building, Customer Retention, Product Launch.
- Marketing Angle Intelligence: Problem-Solution, Benefits, Features, Emotional Appeal, Social Proof, Comparison, Curiosity, Storytelling, Educational, Offer & Promotion, Lifestyle, Seasonal.
- Creative Marketing Idea Generator.
- Idea Evaluation & Ranking.
- Marketing Diversity & Repetition Intelligence.
- Campaign & Content Series Intelligence only for creative idea continuity, not a monthly publishing calendar.
- Trend & Occasion Intelligence.
- Idea-to-Production Handoff.

Show the best three distinct ideas by default, with concise reasons. Allow the user to request more, select, or edit. Initial ranking weights are provisional and require calibration; do not claim guaranteed marketing performance.

### Marketing Copywriting Intelligence
Twelve coordinated systems:
1. Marketing Context & Brief Intelligence.
2. Copywriting Strategy Intelligence.
3. Hook & Headline Intelligence.
4. Persuasive Messaging Intelligence.
5. Platform-Specific Copywriting Intelligence.
6. Copywriting by Content Format.
7. CTA & Conversion Intelligence.
8. Brand Voice & Dialect Integration.
9. Copy Length & Density Intelligence.
10. Copy Variations & Creative Diversity.
11. Copy Accuracy & Claims Validation.
12. Copy Quality & Finalization Intelligence.

It owns written marketing messages, headlines, hooks, captions, body copy, and CTAs. It does not own visual design, typography rendering, spoken audio, or generation. Never invent claims or compress long copy arbitrarily after design; account for space and duration from the beginning.

### Dialect & Brand Voice Intelligence
Nine coordinated components:
1. Brand Language Profile.
2. Dialect Selection Intelligence.
3. Dialect Accuracy Engine.
4. Fus'ha & Dialect Separation.
5. Dialect Adaptation by Content Type.
6. Brand Voice Consistency.
7. Dialect Validation & Correction.
8. Dialect Learning & Brand Feedback.
9. Dialect Reference Library.

**Explicit Dialect Lock:** a dialect explicitly selected by the user for a brand or task is binding across all text and speech-producing components unless the user explicitly changes it. Language, dialect, and tone of voice are separate dimensions. Do not infer dialect from audience nationality alone or mix dialects randomly. Learn corrections per brand, not globally.

## 6. Typography Intelligence

Typography is a shared capability, not a copywriting engine:
- Provide a professional built-in font library and allow users to add brand fonts.
- MAX selects fonts, hierarchy, layout, and placement automatically; the user may adjust before approving a design.
- Prefer programmatic text composition after image/video generation to guarantee text accuracy. Direct generation of text inside an image/video is allowed only when reliability is demonstrated.
- Support Arabic RTL, connected glyphs, mixed Arabic/Latin, numerals, punctuation, and multilingual layouts.
- Do not rewrite approved copy or change dialect.
- Do not use unlicensed fonts.
- Do not regenerate a visual asset when a text-layout correction is sufficient.

## 7. Central orchestration and six Skills

The **Orchestrator Agent** is the central manager, not a seventh Skill. It interprets intent, chooses and orders only necessary skills, packages context, manages dependencies and parallelism, obtains required approvals, resolves conflicts, tracks versions, propagates changes only to dependent outputs, and optimizes cost/time.

Conflict priority:
1. Explicit user decisions.
2. Approved platform rules.
3. Brand DNA and approved assets.
4. Specialized skill decisions.

### Skill 01 — Brand & Context Intelligence
Owns Brand DNA Manager, Product & Asset Context, Language & Brand Voice Profile, User Preferences & Decision Memory, and Context Retrieval & Packaging. Primarily storage/retrieval; do not re-analyze unchanged saved information.

### Skill 02 — Marketing Intelligence
Owns Marketing Ideas Engine, Copywriting Engine, Dialect & Brand Voice Engine, and Marketing Copy Packaging. Produces structured idea/copy packages. Does not design, generate visuals, or produce audio.

### Skill 03 — Creative Direction Intelligence
Owns Creative Content Intelligence Library, Creative Concept & Story Intelligence, Director's Decision Engine, Cinematic Storyboard Engine, and Production Feasibility Intelligence. Converts the approved idea into visual direction, scenes, shots, and storyboard. Does not rewrite copy or silently change approved creative decisions.

### Skill 04 — Typography Intelligence
Owns typography style/font, hierarchy/layout, Arabic/multilingual rendering, image/video typography, and brand typography consistency. Formats approved text; does not rewrite it.

### Skill 05 — Production Intelligence
Owns Prompt Engineering & Generation Intelligence, Model Routing/Capability Registry, Reference & Continuity Management, image/video generation, editing, post-production, and export. Does not silently change the approved script/storyboard or replace product/character references.

### Skill 06 — Spoken Content Intelligence
Owns Speech Strategy, Dialogue & Voiceover, Natural Speech & Dialect, Voice Identity & Performance, Speech Timing & Lip-Sync, and Audio Production & Track Management. Owns spoken content and audio tracks, not on-screen text. No dialogue for a silent character; keep voice identity stable when the character speaks.

Skills are coordinated modules and contracts, not necessarily six independent AI agents. Do not create one model call or agent per component.

## 8. Skill contracts and workflow controls

Every Skill contract defines:
1. Purpose.
2. Inputs.
3. Outputs.
4. Dependencies.
5. Execution Rules.
6. Completion Status.

Shared task envelope:
`task_id`, `brand_id`, `project_id`, `workflow_type`, `input_data`, `approved_decisions`, `asset_references`, `version`, `status`, `output_data`, `errors`.

Skill result statuses: `SUCCESS`, `NEEDS_INPUT`, `NEEDS_APPROVAL`, `PARTIAL_SUCCESS`, `BLOCKED`, `FAILED`.

Operation statuses: `PENDING`, `RUNNING`, `WAITING_APPROVAL`, `WAITING_INPUT`, `RETRYING`, `PARTIAL_SUCCESS`, `COMPLETED`, `FAILED`, `CANCELLED`, `BLOCKED`.

Each operation has a stable `operation_id` to prevent duplicate work/charges. Persist successful partial results and resume from the last valid point. Use bounded retries, provider timeouts, explicit errors, and safe recovery.

### Image workflow
Orchestrator → Skill 01 → Skill 02 if needed → Skill 03 → Skill 04 if text is needed → approval where required → Skill 05 generation/composition/export.

### Video workflow
Orchestrator → Skill 01 → Skill 02 → Skill 03 → user approves the complete Master Storyboard → Skill 04 and Skill 06 in parallel when needed → Skill 05 prepares and generates segments according to continuity → final assembly, typography/audio integration, export.

A silent video can skip Skill 06. A video with no text can skip Skill 04. Run only what is needed.

### Handoff, versions, and asset identity
- Use structured handoff contracts, not free-form prompts alone.
- Every asset has stable identity metadata such as `asset_id`, `asset_type`, `version`, `source`, `status`, and `content_fingerprint`.
- Bind approvals to exact versions (for example, Storyboard V2 — Approved). Any change creates a new version and invalidates only dependent outputs.
- Use dependency, version, and resource locks to prevent mixed-version output.
- Separate account, brand, project, and asset ownership at every access boundary.
- Keep one unified video timeline for image/shot timing, dialogue, voice-over, music, effects, and on-screen text.

## 9. Video creation architecture

### User workflow and duration
The user chooses a duration from 10, 20, 30, or 40 seconds. MAX recommends a duration based on the concept and objective; the user may change it. Character and product image are optional inputs. The user selects/enters an idea, reviews the scene/shot script, edits it, and approves it. The user selects aspect ratio: 9:16, 4:5, 1:1, or 16:9.

### Mandatory storyboard
Every video, regardless of duration, passes through one unified **Master Storyboard**. No direct video-generation path bypasses it.
- Includes Start Frame and End Frame for each planned shot where useful/feasible.
- Includes the selected character reference from the approved Character Sheet when a character is used, plus the original product reference.
- Shows the user one coherent storyboard to approve before generation.
- Stores structured data for scenes, shots, frames, timing, character/wardrobe, product, environment, motion, transitions, and references.
- Internally derives shot-specific reference packages; do not send a collage blindly to every provider.
- After storyboard edits, create a new version and require approval again. Lock the approved production snapshot.

Storyboard levels: Basic, Standard, Advanced, Production Critical, chosen adaptively by complexity and risk. Sketch, Visual Storyboard (primary for advertising video), and optional Animatic are presentation forms; do not add costly previews by default. Smart Frame Allocation selects meaningful event/motion/interaction/ending frames, not one image per second. Reference priority: original product, approved Character Sheet, environment, wardrobe, then style. Wardrobe choices must come from available character references, not invented unsupported clothing.

### Direction and camera
Director's Decision Engine components:
1. Creative Intent Analyzer.
2. Shot Selection Intelligence.
3. Camera Movement Intelligence.
4. Shot Sequencing Intelligence.
5. Pacing & Timing Intelligence.
6. Transition Intelligence.
7. Shot Feasibility Analysis.
8. Director's Final Shot Plan.

Shot sizes: ECU, CU, MCU, MS, MWS, WS, EWS, OTS. Angles: Eye Level, Low, High, Bird's Eye, Worm's Eye, Dutch, Profile, Three-Quarter. Movements: Dolly, Tracking, Truck/Slide, Pan, Tilt, Crane/Jib, Orbit/Arc, Handheld/Gimbal, Zoom, Rack Focus, Whip Pan, Push/Pull, FPV, Aerial/Drone, Dolly Zoom. Do not confuse camera movement with optical zoom or focus change.

Each shot and movement must serve a purpose. Realism, rhythm, variety, and feasibility take precedence over complexity. Do not add seconds merely to fill duration or use unsupported movement without adaptation.

### Video continuity and segmenting
- The creative story and storyboard remain unified even if generation is split into multiple segments.
- If a model's verified maximum duration is 10 seconds, a 27-second video could be generated as 10 + 10 + 7 seconds. This is an example, not a fixed provider limit.
- Segment boundaries may fall inside a scene/shot when planned; segmentation does not mean separate unrelated stories.
- Generate sequentially when continuity requires it, using a valid selected end frame as the next segment's start reference.
- Validate the selected end frame. If unsuitable, find a nearby valid frame or repair/regenerate only the affected portion.
- Maintain character identity through the approved Character Sheet and stable voice identity when speaking.
- Use **Continuity Match** when space/action should remain continuous; use **Creative Transition** when a deliberate change of scene/environment is intended. Never force impossible spatial continuity.
- Plan overlap/transition handles where required and keep all audio/text timings attached to the master timeline.
- On a segment failure, preserve successful segments and resume only the failed/dependent part.

### Video production intelligence
Approved systems include Creative Concept Engine, Story & Narrative Engine, Cinematic Direction & Shot Planning, Production Feasibility Check, V1 Human Performance Intelligence, V2 Product Fidelity Intelligence, V3 Motion Design Intelligence, V4 Advertising Film Direction Intelligence, Model Routing Intelligence, Continuity Frame Selection Engine, Continuity State, Continuity Match vs Creative Transition, Overlap & Transition Handles, Pacing & Timing Engine, Video Quality Intelligence, Prompt Package, Editing & Post-production Engine, and Benchmark Suite.

Adaptive Production, Hybrid Production, AI Video Repair, Storyboard/Keyframe Planning, and Motion Reference are future-capability paths, subject to actual provider support and cost/quality testing; they do not authorize speculative feature implementation.

### Model routing and benchmark
Maintain a Model Capability Registry for actually accessible APIs: duration, aspect ratio, resolution, start/end frames, reference images, audio, motion controls, cost, latency, and limitations. Do not assume a model shown in a provider UI is accessible through its API. Do not bind MAX to one provider or version. Route only using verified capability data.

Benchmark V1–V4 with stored model/version, references, prompt, cost, time, failure modes, and quality evaluation. Initial example model preferences are hypotheses, not fixed vendor decisions.

## 10. Prompt Engineering & Generation Intelligence

Eight coordinated systems:
1. Storyboard-to-Prompt Intelligence.
2. Prompt Architecture.
3. Model-Specific Prompt Compiler.
4. Reference Intelligence.
5. Action & Motion Intelligence.
6. Prompt Consistency Engine.
7. Negative & Error Prevention Intelligence.
8. Prompt Validation & Optimization.

The internal prompt architecture covers Scene Context, Visual Anchor, Subject Identity, Subject Action, Camera Direction, Composition, Environment Motion, Lighting & Look, Timing, Continuity Locks, Audio Direction, and Output Requirements. This is a structured internal representation, not a literal fixed prompt for every provider.

The compiler adapts instructions to verified model/API capabilities. Reference intelligence defines each reference's role and priority. Validation checks storyboard alignment, completeness, consistency, feasibility, reference validity, motion feasibility, and output requirements. Do not add repeated model review calls or expensive repair passes without measured value.

## 11. Spoken content and audio

Spoken Content Intelligence has ten coordinated concerns:
1. Speech Strategy Intelligence (Character Dialogue, Voiceover, Narration, Natural Conversation, Mixed Speech, No Speech).
2. Dialogue Writing Intelligence.
3. Voiceover Scriptwriting Intelligence.
4. Natural Speech Intelligence.
5. Dialect & Language Intelligence.
6. Speech Timing & Scene Synchronization.
7. Voice Identity & Consistency.
8. Lip-Sync & Performance Compatibility.
9. Audio Production & Track Management.
10. Speech & Audio Prompt Integration.

Avoid ten separate calls. Combine compatible analysis/writing; reuse voice settings. Voiceover should be one continuous track where appropriate. Dialogue, voiceover, and silent scenes must be explicitly distinguished. Do not add dialogue to a silent character. The visual script separately identifies visual action, character dialogue, voice-over, and on-screen text.

## 12. Simple Smart Editing Engine (user-uploaded video montage)

This is a simple task-based enhancement tool inside Skill 05, **not** a professional timeline editor. User flow: upload a video → select desired tasks/styles → see per-task and total cost → approve → MAX executes directly → receive one final video.

**There is no preview stage before final export.** The user explicitly rejected preview and it must not be added.

### Approved user-facing tasks
1. **Auto Captions:** transcribe speech, synchronize text, and choose from a varied style library (e.g. Minimal, Dynamic, Highlight, Cinematic, UGC/Social, Bold Impact). Support Arabic/English and dialects only to the accuracy the transcription system can actually provide. Allow text correction when available.
2. **Audio Enhancement:** noise reduction, speech clarity, wind/distortion reduction where recoverable, and level balancing. Do not promise restoration of irrecoverably damaged audio or alter speaker identity.
3. **Silence Removal:** detect and remove unnecessary long pauses while preserving natural short pauses, word boundaries, music, and meaningful sound.
4. **Music & Rhythm:** select from a properly licensed music library or accept a user upload; support mood selection, volume balancing, ducking under speech, fade in/out, and appropriate beat synchronization. Do not build a music composition studio.
5. **Motion Graphics:** when enabled, expose six visible categories; user may select multiple categories in one video:
   - Kinetic Typography.
   - Highlights & Callouts.
   - Icons & Infographics.
   - Product Features.
   - Shapes & Effects.
   - Titles & Lower Thirds.
   Each category contains ready-made templates. MAX selects/places/times suitable templates; user may add instructions. Avoid clutter and protect product, face, and important text.
6. **Additional Instructions:** a free-text field to clarify the selected supported tasks. MAX must identify unsupported requests and state limitations rather than pretend to perform them.

The duplicate mention of audio enhancement in the user's initial list is one function, not two.

### Explicit montage exclusions
- No professional multi-track timeline editor or frame-by-frame editing.
- No automatic story reconstruction or generation of new scenes from this tool.
- No complex VFX/3D or advanced cinematic color grading.
- No unrestricted manual motion editor.
- No preview stage before export.

### Montage implementation principles
- Use deterministic libraries/local processing where sufficient; call AI/external services only when necessary.
- Combine compatible operations and process only selected tasks.
- Preserve the original video and create a separate output.
- Per-task cost must be shown separately, with a total before execution; no work or credit deduction before user approval.
- Distinguish provider cost, internal processing cost, estimated customer price, and credits charged.
- Cost calculation uses actual selected processing path, duration, complexity, licensed assets, and verified current pricing. Do not invent fixed prices.
- Use a stable operation ID, reserve/settle credits idempotently, and avoid duplicate charges on retry.
- Preserve successful outputs and rerun only affected tasks.
- When silence is removed, update the unified timeline and downstream caption/music/motion timing.
- Final export produces one validated video file. No preview is inserted as an extra step.

### Cost drivers (not fixed prices)
- Captions: duration, speech recognition, language/dialect, and rendering path.
- Audio enhancement: duration and processing method.
- Silence removal: duration and analysis/processing.
- Music/rhythm: duration, licensed track terms, and synchronization.
- Motion graphics: selected templates, number of elements, duration, and complexity.
- Additional instructions: cost only if they invoke a supported task that adds processing.

## 13. Editing, post-production, and responsibility boundaries

- Skill 02 owns written message and meaning.
- Skill 04 owns typography and visual text layout.
- Skill 05 owns visual assembly, video processing, final integration, and export without changing approved copy.
- Skill 06 owns spoken script/audio tracks, voice generation, timing, and audio mix preparation.
- Skill 05 integrates audio mix with video, applies timing, music/visual elements, and exports the final asset.
- The shared script separates visual event, character dialogue, voice-over, and on-screen text.
- Montage tasks must remain within the simple task-based scope in Section 12.

## 14. Cost, performance, reliability, and data integrity

### Cost/performance
- Prefer code for deterministic operations.
- Merge compatible model tasks and reuse context/results.
- Maintain dependency fingerprints; invalidate only descendants of changed inputs.
- Use adaptive complexity and bounded smart retries.
- Parallelize independent tasks; sequence dependent tasks.
- Monitor AI calls, provider cost, internal processing cost, total cost, execution time, queue time, retry count, success rate, quality score, and reuse rate.
- Separate estimated cost, actual provider cost, customer price, and customer credits.
- Show estimates only when grounded in current pricing and known processing paths.

### Failure and recovery
- Preserve successful partial results.
- Use bounded retries, provider timeouts, explicit errors, and safe resumption.
- A failure in audio should not regenerate successful video unless lip-sync or visual timing depends on it.
- A failure in one video segment must not regenerate successful unrelated segments.
- A repeated request must not duplicate generation or credit charges.

### Security and concurrency
- Enforce account/brand/project/asset isolation.
- Use dependency/version/resource locks.
- Prevent mixing outputs from different approved versions.
- Validate uploads and treat external references as untrusted.
- Never commit secrets or real customer data.

## 15. Design acceptance suite

The previously agreed design acceptance suite contains 52 cases across:
- Image workflows (6).
- Video workflows (8).
- Modification workflows (8).
- Failure and recovery (9).
- Concurrency and data integrity (6).
- Cost and credits (7).
- Quality and consistency (8).

Three end-to-end scenarios are defined: (1) static product ad, (2) multi-segment video with character and speech, and (3) partial edit plus provider failure. These are **design-level acceptance cases, not executed software tests**.

Key required cases include: 27-second video split 10+10+7 under a verified 10-second provider limit while preserving one storyboard; failed segment recovery without regenerating successful segments; single-shot changes; storyboard version reapproval; no duplicate charge; account/brand isolation; audio-only failure recovery; and montage operation without preview.

## 16. Confirmed decisions vs. unresolved technical matters

### Confirmed product/architecture decisions
- Central Orchestrator + six Skills.
- Skill contracts, workflow/routing map, and cost/performance architecture.
- The nine integration controls: responsibility boundaries, version/dependency control, asset identity, approval binding, operation/error states, unified video timeline, concurrency/version locks, account/brand isolation, and acceptance tests.
- Creative taxonomy P1–P4 and V1–V4 and internal style selection.
- Marketing Ideas and Copywriting structures, explicit dialect lock, Typography rules, Spoken Content structure.
- Mandatory Master Storyboard and sequential continuity-aware segmented video generation.
- Simple task-based montage features and six motion categories; multi-category selection is allowed.
- Montage pricing per task plus total before approval.
- No preview before export.
- No monthly content calendar/publishing planning feature.

### Initially approved technology choices (user, 2026-10-29)
- Next.js.
- TypeScript.
- PostgreSQL.
- Private object storage.
- Simple background jobs.

These are **initially approved architectural choices, not verified production decisions**. They remain subject to verification (below). **This approval does not authorize programming.** Programming authorization is **NOT granted**; it requires the completed documentation and the user's explicit authorization. Nothing in this document states that implementation has started.

### Requires verification before any related choice is final
- Suitability, current pricing, and availability of the concrete services behind the approved choices (for example the managed PostgreSQL, the private object-storage service, and the background-job mechanism), and compatibility with Arabic/RTL, security, and data-residency needs.
- Everything under "Open" below that depends on a provider's actual capabilities, prices, licensing, or terms.

### Open; do not assume or silently decide
- Authentication approach, hosting provider and region, deployment, and the final infrastructure/service providers.
- Exact generation model/API/provider and verified access/capabilities.
- Actual speech recognition, voice, music licensing, audio processing, motion-template, and video-editing tools.
- Current provider pricing and customer credit conversion.
- Detailed technical thresholds for supported upload duration, resolution, file size, and export formats.
- Empirically calibrated ranking weights, complexity thresholds, and quality benchmarks.
- Legal/privacy/rights requirements for production launch.

Resolve each open item only at the relevant roadmap phase, using evidence and explicit approval where the decision is material.
