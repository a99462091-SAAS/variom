# VARIOM – Product Vision & Simplified UX Specification V2.0

**Status:** Owner-approved product vision and UX baseline.  
**Authority:** Highest product-level source of truth for VARIOM.  
**Version:** V2.0.

This repository copy is a structured consolidation of the owner-approved V2.0 decisions available in the project context; it is not claimed to be a verbatim export of the original conversation document. Product scope and behavior here override older MAX assumptions. If the exact original source file is later supplied or recovered, preserve its wording while retaining this reconciliation as needed. The UX/frontend master specification is subordinate and may clarify implementation, not expand scope.

## 1. Vision
VARIOM is an intelligent marketing and creative content platform that understands the brand, thinks through marketing and creative decisions, and produces useful content with minimum user effort.

**Brand Understanding → Marketing Thinking → Creative Production.**

The system performs complex reasoning internally while keeping the user experience simple. It reuses known information, avoids repeated questions, chooses detailed creative styles internally, shows actual costs before execution, and never presents mock output as real production.

## 2. Four product systems
1. **Brand Intelligence:** Brand Profile, Brand DNA, Brand Voice, Visual Identity, Brand Assets, Virtual Character.
2. **Marketing & Creative Intelligence:** Marketing Strategies, Creative Content Taxonomy, Content Styles, Marketing Ideas, Copywriting Intelligence, Prompt Engineering & Generation Intelligence.
3. **Content Production:** Monthly Content, Image Generation, Video Generation, Smart Video Editing.
4. **Content Library:** generated images, videos and monthly content.

These are logical product systems, not a mandate for four services or four agents.

## 3. Brand setup and Brand DNA
- Initial profile asks for brand name, activity, audience, and optional logo.
- Reuse information already provided; do not repeat questions.
- Fill gaps only when useful; never invent brand facts.
- Allow skip/edit/save for optional setup.
- Brand DNA includes profile, audience, personality, voice, language/dialect where specified, visual identity and brand assets.
- Brand Assets management is in scope.
- **No Product Catalog.**
- Product photos are manually uploaded for each relevant generation task; do not assume a persistent product catalogue.

## 4. Approved content taxonomy
Image categories:
- **P1 — Product Showcase**
- **P2 — Static Ad**
- **P3 — Carousel**
- **P4 — Lifestyle**

Video categories:
- **V1 — UGC**
- **V2 — Product Demo**
- **V3 — Motion Graphics**
- **V4 — Story / Testimonial**

Do not carry over old MAX definitions where their meaning differs. Detailed Content Styles are selected internally, not exposed as long technical menus. Keep category distinct from objective, topic, format, production method and copywriting approach.

## 5. Marketing objectives and Monthly Content
Approved objectives:
1. Brand Awareness
2. Product Awareness
3. Product Launch
4. Campaign Launch
5. Sales Growth
6. Engagement
7. Lead Generation
8. Trust Building

Select up to three goals: one primary and up to two supporting.

Monthly generation rules:
- 8, 12 or 16 posts.
- Smart image/video distribution; user may adjust within approved behavior.
- Images and videos only; no carousel.
- Up to 10 manually uploaded product photos; optional price per image.
- Optional virtual character.
- Optional template review; user may proceed directly.
- Show actual cost before generation; never hardcode illustrative prices as live prices.
- Template review shows content type, illustrative reference image, idea, and copy/dialogue when applicable. Clearly label reference imagery as illustrative, not generated output.
- Only idea and copy/dialogue are editable in template review.
- No publishing-platform selection.
- Image sizes: Instagram Portrait or Instagram Landscape.
- Video sizes: Reels Portrait or Reels Landscape Video.
- Monthly video duration: **maximum 10 seconds per video**.
- Internal stages: Planning → Content Preparation → Generation → Final Quality Check.
- One progress indicator and completed posts/total.
- Results: view/open/download only; completed outputs automatically saved to Content Library.

## 6. Image Studio
- P1–P4.
- One idea or five idea suggestions.
- Manually upload the product image for the relevant task.
- Optional product price and optional character.
- Instagram Portrait or Instagram Landscape.
- System selects detailed style internally.
- Show actual cost before generation.
- No initial paid post-generation image-editing loop.
- Save completed outputs automatically to Content Library.

## 7. Video Studio
- V1–V4.
- One idea or five idea suggestions.
- Manually upload product image; optional character.
- Durations: **10, 20 or 30 seconds**.
- Formats: Reels Portrait or Reels Landscape Video.
- Optional scene review; show scene description and dialogue/text only, with approved editable fields.
- No separate audio controls.
- Internal Master Storyboard is mandatory; no direct video generation bypass.
- Save completed outputs automatically to Content Library.

## 8. Master Storyboard
An internal production workflow maintaining continuity of character identity, product appearance, creative style, voice/language/dialect, scene order, action, timing and transitions. Use start/end visual references when useful and technically supported. Segmenting must not fragment the story. Hide unnecessary orchestration complexity from users.

## 9. Smart Video Editing
The approved **Simple Smart Editing** task list consists of exactly six user-facing entries: Auto Captions, Audio Enhancement, Silence Removal, Music & Rhythm, Motion Graphics, and Additional Instructions. Motion Graphics has six selectable categories: Kinetic Typography, Highlights & Callouts, Icons & Infographics, Product Features, Shapes & Effects, and Titles & Lower Thirds. Multiple Motion Graphics categories may be selected in one video where the verified processing path supports them. Additional Instructions clarifies selected supported tasks and does not create arbitrary capabilities. Preserve the original video and create a separate output. No pre-export preview, professional multi-track timeline, frame-by-frame editing, automatic story reconstruction/new-scene generation, complex VFX/3D or advanced cinematic grading. Show per-task and total actual cost before explicit approval when verified pricing is available. Catalogue presence is not proof of provider support; expose only verified executable capabilities. Source provenance: Document 17, recovered MAX approved architecture §12 and tracker decision D-25, adapted within VARIOM scope.

## 10. Virtual Character Studio
Concise guided creation using approved questionnaire and Character Sheet requirements. Generate, save, edit and reuse. Character is optional in relevant generation flows. Do not invent missing questionnaire fields or claim implementation without evidence.

## 11. Content Library
Images, videos and monthly content; type/date filters; grid; open/preview; download. Save completed image, video, editing and monthly outputs automatically. No project management, approvals, ZIP export or collections unless separately approved.

## 12. Dashboard and brand limits
Dashboard focuses on brands, active brand, actual credits/usage and primary actions. **Superseding owner decision (2026-11-19, VAR-OD-001):** presentation labels are Starter / Pro / Agency, displayed as 1 / 3 / up to 8 brands, for non-binding presentation only. This later explicit owner decision supersedes the older Basic=1 / Pro=3 / Max=10 values in this consolidated V2.0 text. It does not approve pricing, subscriptions, entitlements, billing or enforcement. Never invent billing state. The exact commercial model remains deferred under VAR-OD-007.

## 13. Credit lifecycle
Show actual cost; check balance; reserve credits; execute; settle actual usage; return unused reservation after partial failure or lower consumption. Keep accounting mechanics unobtrusive. UI must reflect real backend state; never simulate real charges/refunds.

## 14. Language and responsive UX
Arabic and English are mandatory; RTL/LTR must work correctly. Support desktop and mobile. Use concise steps, smart defaults, minimal choices and autosave where specified. Users should not need to write professional marketing copy or complex prompts.

## 15. UX principles
Minimum steps/questions; smart defaults; internal complexity and simple external UX; actual costs before execution; preserve approved brand facts; clear progress/error/recovery; no fabricated providers, outputs, prices or credit actions.

## 16. Exclusions
No Product Catalog; no carousel in Monthly Content; no publishing/scheduling/social-account management; no analytics dashboards or ad campaign management; no approvals or team/agency collaboration; no ZIP; no professional timeline editor; no separate advanced audio phases; no 4K; no unapproved categories, formats, durations or ratios; no paid post-generation image-editing loop.

## 17. Commercial/provider truth
Use verified provider costs and actual consumption. Protect margin through evidence-based pricing. A mock provider or local renderer is not a production AI provider. Live provider activation requires separate approval, capability validation, cost review and safety checks.

## 18. Authority and change control
This V2.0 document is the product authority. UX/frontend implementation is subordinate. Architecture cannot silently change product behavior. New categories, workflows, commercial rules or excluded features require explicit owner approval.


## 19. Later owner-decision reconciliation
This V2.0 repository copy preserves the approved product vision while explicitly reconciling later owner decisions recorded in Document 20. Where a later explicit owner decision supersedes a specific older clause, the decision register controls that narrow point; all other product scope remains governed by this document. In particular, VAR-OD-001 supersedes the legacy plan labels/counts in §12 for presentation only. VAR-OD-002/003 require the owner to supply the canonical identity image and UI Design Prompt directly to Claude Code; this document does not replace those inputs.
