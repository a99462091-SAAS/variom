# VARIOM — MAX Creative Style Field-Level Audit

**Date:** 2026-11-19  
**Source:** Branch `creative-library-review-completion`, files `data/styles.p1.json` through `data/styles.v4.json`  
**Status:** Read-only structural and editorial risk audit. Not owner approval, production validation, or an import authorization.

## 1. Scope and method

All 144 detailed records (18 in each of P1–P4 and V1–V4) were fetched and parsed. This audit checked:
- Required top-level and nested field presence.
- Category/content-type/ID consistency and duplicate IDs/names.
- Modality-specific prompt availability.
- Selection alternatives and referenced style IDs.
- Category-level family distribution, suitability/cost/complexity metadata.
- Reference and evidence coverage.
- Production requirements and quality-check coverage.
- Representative video-card content and the known product-decision conflicts.

This is not a full human rewrite or a model-output test. It does not establish that prompts work well with any particular image/video provider, nor that references are licensed for reuse.

## 2. Structural integrity — PASS, with important qualification

| Check | Result |
|---|---:|
| Detailed records | 144 |
| Records per category | 18 × 8 |
| Unique IDs | 144 |
| Duplicate IDs | 0 |
| Duplicate English names | 0 |
| ID prefix matches category | 144/144 |
| Required major sections present | 144/144 |
| Selection alternatives containing an unknown style ID | 0 |
| Image records with image prompt | 72/72 |
| Video records with video prompt | 72/72 |
| Record status | 144/144 remain `review` |

Every record contains the nine principal sections checked: full definition, creative execution, selection rules, fit, copywriting profile, prompt instructions, evidence, production requirements and quality checks.

The modality-specific nulls are mostly intentional: image records have no video prompt; video records have no image prompt; video copywriting records do not need image-text fields. Null optional fields are not counted as a defect merely because the shared schema allows them.

**Interpretation:** the dataset is structurally complete enough for continued editorial review. This does not mean the content is approved, sufficiently evidenced, or technically executable.

## 3. Category-level findings

| Category | Family distribution | Suitability / cost / complexity | References | Evidence |
|---|---|---|---:|---|
| P1 | 18 distinct families | AI suitability medium for all; complexity mostly low; cost mostly low | 18 | E3 × 18 |
| P2 | 18 distinct families | AI suitability medium; complexity low; cost low for all | 0 | E3 × 18 |
| P3 | 18 distinct families | AI suitability medium; complexity medium; cost medium | 0 | E3 × 18 |
| P4 | 18 distinct families | AI suitability medium; complexity medium; cost medium | 0 | E3 × 18 |
| V1 | 7 families; one generic family contains 12 records | AI suitability, cost and complexity unknown for all | 0 | unknown × 18 |
| V2 | One family contains all 18 records | AI suitability, cost and complexity unknown for all | 0 | unknown × 18 |
| V3 | One family contains all 18 records | AI suitability, cost and complexity unknown for all | 0 | unknown × 18 |
| V4 | One family contains all 18 records | AI suitability, cost and complexity unknown for all | 0 | unknown × 18 |

### Finding A — Video creative_family is too coarse to distinguish the styles

The image categories use 18 distinct families per category. Video does not:
- V1 groups 12 materially different styles under `creator_led` (after six more specific families).
- All 18 V2 records use `product_demonstration`.
- All 18 V3 records use `motion_explainer`.
- All 18 V4 records use `directed_commercial`.

The individual names and prompts still distinguish many of these styles, so this is not a missing-record issue. It is a taxonomy/metadata issue: a family field with one value for an entire category does not help selection, grouping or analytics.

**Recommendation:** retain a broad category-level family only if it has an explicit documented purpose. Add or derive a separate, controlled `style_subfamily` or `execution_pattern` for useful distinctions (for example, V2 product-angle showcase vs operation demo vs installation vs comparison; V3 typography vs data visualization vs 2D/3D vs hybrid overlays; V4 narrative vs offer-led vs cinematic treatment). Do not rename stable style IDs as a side effect. This is an editorial/schema proposal, not an automatic bulk rewrite.

### Finding B — Video fit metadata is correctly cautious but incomplete for product decisions

All 72 video records intentionally use unknown AI suitability, relative cost and complexity. This is preferable to invented estimates. However, the records cannot yet support user-facing feasibility, cost comparison, recommendation ranking or a reliable execution plan.

**Recommendation:** keep unknown until representative tests and provider-specific cost/quality measurements exist. Add evidence with provider/model/version, duration, resolution, reference requirements, success/failure rate, repair rate, human effort and estimated cost. Never infer these values from the style name alone.

### Finding C — Image metadata looks complete but is not performance evidence

All 72 image records mark AI suitability as medium and human review as required. P1–P4 use E3, which is descriptive production-practice guidance, not comparative performance evidence. Do not describe any style as higher-converting or more effective based on these labels.

**Recommendation:** keep E3 explicitly labeled as practice-level guidance. Only add E1/E2 or internal test evidence when a traceable method and context exist.

## 4. References and rights

- 18 reference links are attached, all to P1.
- All 18 are `link_only_reference`; none grants reproduction or redistribution rights.
- Three direct shot analyses are recorded (P1-004, P1-014, P1-015).
- P2, P3, P4 and V1–V4 have zero attached references (126 styles).
- A page-level URL check is not equivalent to direct inspection of every image or clip.

**Recommendation:** do not make 18 references per category a mechanical requirement. Source examples only where they materially clarify a difficult distinction or a production behavior. For video, inspect an actual clip or timecoded segment; a still is not evidence of motion. Preserve attribution and rights status.

## 5. Selection and editorial quality

- Every record has positive and exclusion signals, alternatives, and combination rules.
- The alternative strings across the 144 records contain no broken style-ID references when the IDs are parsed from their explanatory text.
- The P1 alternatives are still written in explanatory prose rather than normalized ID objects; normalize only if VARIOM needs machine-readable recommendations.
- The historical quality audit reports no exact duplicate values within categories for selected editorial fields after its remediation. The current read-only pass confirms 18 distinct core ideas within each category, but that is not proof that neighboring styles are sufficiently distinguishable in real briefs.
- Average quality-check counts range from approximately 5 to 9 per record; these are checklist counts, not a quality score.
- V1 has 101 quality checks across 18 records and 59 production requirements; the slight variation in counts is not automatically an error, but those records deserve manual consistency review.

**Priority neighboring-style review pairs** already identified in the historical quality audit should remain on the acceptance checklist:
- P1-005 macro detail vs P1-011 material/finish detail.
- P1-009 top-down vs P1-010 side/low angle.
- P3-001 step-by-step vs P3-009 process stages.
- P3-007 sequential story vs P3-008 progressive reveal.
- P4-002 product in use vs P4-016 routine in context.
- P4-008 professional context vs P4-018 workplace context.
- V1-006 FAQ answer vs V1-007 objection response.
- V1-001 personal experience vs V1-008 creator-led use vs V2-003 how-to demo vs V2-004 product operation.

## 6. High-risk content and truthfulness controls

The existing records contain useful prohibitions, but some concepts require verified inputs before they can be selected or generated:
- Price, discount, urgency, offer, guarantee and bundle claims.
- Comparative claims and competitor references.
- Testimonials, real-person reactions, creator identity, paid partnership and consent.
- Before/after transformations and measurable results.
- Product dimensions, ingredients, materials, components, installation and operational behavior.
- Professional/expert credentials and safety-sensitive instructions.
- Cultural or demographic representations.
- 3D models, simulation, complex motion, camera movement and compositing.

**Recommendation:** model these as explicit input/evidence gates in VARIOM, not merely as prose buried in prompt instructions. If required evidence or permission is absent, the style should be unavailable for that brief or should generate a clearly fictional/non-claim alternative.

## 7. Product decisions remain blockers

1. **P3-013…P3-018:** unresolved canonical ID/name mapping. Current inventory and cards agree with one another but conflict with the earlier approved mapping. Do not alter stable IDs or approve P3 until the owner decides.
2. **V2-016 and V2-017:** decide whether voice-over and on-screen annotation are standalone selectable styles or production modifiers.
3. **V4:** MAX V4 means Commercial / Advertising Video; VARIOM V4 means Story / Testimonial. Reclassify each record; do not bulk-map the category.
4. **V1 truth distinction:** keep genuine testimonial, paid creator, actor/scripted scenario and synthetic presenter separate. Never fabricate a real customer experience.
5. **Minimum VARIOM library:** decide whether VARIOM needs all 144 candidates at launch. MAX's 18-per-category structure is not a reason to expose all of them in the first release.

## 8. Recommended disposition

| Group | Disposition |
|---|---|
| P1 | Candidate concepts; retain selectively after product-fidelity and adjacent-style review |
| P2 | Candidate concepts; retain selectively after claims/offer/evidence gates |
| P3 | Hold until P3 ID decision; then retain only for Image Studio |
| P4 | Candidate concepts; retain selectively after context/representation review |
| V1 | Hold for truthful identity/testimonial/consent model and provider feasibility |
| V2 | Candidate concepts; hold V2-016/017 decision and validate real demonstration capability |
| V3 | Candidate concepts; capability-check advanced 2D/3D/simulation/hybrid work |
| V4 | Reclassify record by record against VARIOM Story / Testimonial; no category-level import |

## 9. What is not authorized by this audit

- No status change from `review` to `approved`.
- No bulk import into VARIOM application data.
- No assumption that every MAX concept belongs in VARIOM V1.
- No reuse of reference media without rights.
- No claims that provider capabilities, production costs, quality or commercial outcomes have been tested.
- No change to application code, APIs, database schemas or UI.

## 10. Next recommended action

Resolve the three product taxonomy questions first (P3 mapping, V2-016/017 role, V4 reclassification). Then select a deliberately small VARIOM candidate set and perform manual record-by-record acceptance against VARIOM V2.0, V2.1, repository capabilities, required inputs, safety/truthfulness gates and actual provider tests. Only accepted records should be rewritten into a VARIOM-owned schema.
