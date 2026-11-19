# VARIOM — Complete UX & Frontend Interface Design Master Specification V2.1

**Status:** Consolidated from the approved V2.0 vision and latest V2.1 refinements recorded in the project context. This is not claimed as a verbatim transcript of the original conversation prompt.
**Authority:** Subordinate to `00-product-vision-simplified-ux-v2.md`.

## 1. Inputs and precedence
Use: (1) Product Vision V2.0; (2) this UX/frontend specification; (3) separate owner-supplied UI Design Prompt; (4) owner-supplied visual identity image; (5) verified repository code/API/schema evidence. Product vision controls product scope. This document controls screen behavior. Identity references control styling. Repository evidence controls implementation claims.

## 2. Global shell
Dashboard; brand selector/active brand; real credit balance; Arabic/English switcher; account menu; responsive navigation/mobile drawer. Do not finalize deferred-tool placement without an approved tool mapping. RTL/LTR are mandatory.

## 3. Nineteen screens
S01 Authentication; S02 Initial Brand Profile; S03 Brand DNA Setup; S04 Dashboard; S05 Monthly Content Creation; S06 Monthly Content Template Review; S07 Monthly Generation Progress; S08 Monthly Content Results; S09 Image Studio; S10 Image Idea Generation (embedded interaction, not separate app); S11 Video Studio; S12 Video Storyboard Review; S13 Smart Video Editing; S14 Content Library; S15 Content Detail/Preview; S16 Virtual Character Studio; S17 Brand DNA Management; S18 Brand Management/Switching; S19 Settings.

## 4. Screen requirements
- **S01:** Reuse verified authentication; do not show nonfunctional sign-up/reset actions.
- **S02:** Brand name, activity, audience, optional logo; reuse already supplied information.
- **S03:** Concise guided DNA setup; prefill known answers; skip/edit/save; Brand Voice, Visual Identity and Brand Assets; no Product Catalog.
- **S04:** Brands, active brand, real credits/usage, primary actions and useful recent content; no raw internal IDs or invented subscription state.
- **S05:** Up to three goals (one primary + two supporting); 8/12/16 posts; up to 10 manual product images; optional prices and character; smart image/video distribution; no carousel; no platform selection; approved sizes; actual cost; monthly videos <=10 sec.
- **S06:** Optional; show content type, illustrative reference (label as reference), idea and copy/dialogue. Only idea/copy editable. No platform/format suggestion. Never imply reference is generated output.
- **S07:** One progress indicator and completed/total; internal stages Planning, Content Preparation, Generation, Final Quality Check.
- **S08:** Completed posts; view/open/download only; automatic library save. No publish/schedule/approve/ZIP/analytics.
- **S09:** P1–P4; one idea or five suggestions; manual product image; optional price/character; Instagram Portrait/Landscape; internal style; actual cost; no initial paid edit loop.
- **S10:** Idea suggestions embedded in Image Studio; distinguish idea suggestion from image generation and apply only verified credit rules.
- **S11:** V1–V4; one idea or five suggestions; manual product image; optional character; 10/20/30 seconds; Reels Portrait/Landscape Video; optional review; no separate audio controls; mandatory internal Master Storyboard.
- **S12:** Optional user review; scene description and dialogue/text only; no exposed continuity orchestration or unsupported audio controls.
- **S13:** Simple task-based editing; inspect approved repository task list; no professional timeline or unsupported controls.
- **S14:** Images/videos/monthly content; type/date filters; grid/open/preview/download; no collections/projects/approvals/ZIP.
- **S15:** Real selected asset and available metadata; download only with valid authorized asset URL.
- **S16:** Approved concise questionnaire and Character Sheet; save/edit/reuse only where backend supports it; no invented fields.
- **S17:** Edit approved Brand DNA and Brand Assets; no Product Catalog.
- **S18:** Show/switch only accessible brands; enforce authorization server-side; no fake plan limits.
- **S19:** Language/account/available preferences; no nonfunctional billing/integration controls.

## 5. Design and interaction
Apply the supplied UI Design Prompt and identity reference; do not invent missing tokens or motifs. Use shared primitives, consistent spacing/typography/controls, accessible focus/labels/contrast/keyboard/touch behavior, responsive layouts, and explicit loading/empty/error/retry/disabled/success/partial-failure states. Test actual Arabic RTL, not just translated strings. Autosave approved work.

## 6. Credits and preview truth
Actual cost before generation; UI follows real quote/reserve/settle/refund responses. Preview/mock must be clearly labelled and isolated from real jobs, assets and credits. Never present local renderer or mock output as AI generation.

## 7. Implementation sequence
Inspect and map current routes/components/APIs to S01–S19; verify data/capability reality; prepare shared shell/localization/tokens; implement brand setup; dashboard/brand switching; monthly; image; video/storyboard; smart editing; library; virtual character/settings; then responsive/accessibility/RTL/LTR/regression QA. Do not start a later stage before required contracts and approvals.

## 8. Acceptance
All 19 screens mapped or explicitly marked missing; no unsupported behavior claims; categories/formats/durations match V2.0; monthly video <=10 seconds; Video Studio only 10/20/30; no Product Catalog or monthly carousel; no fake credit mutation; mock isolation; automatic library saving; Arabic/English RTL/LTR; responsive and state coverage; no unrelated backend/schema changes in frontend-only tasks.
