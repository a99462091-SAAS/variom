# VARIOM — Output Quality, Repair & Acceptance Standard

**Document ID:** V-OR-03  
**Version:** 0.1  
**Status:** DRAFT — OWNER REVIEW REQUIRED  
**Document type:** Operational companion standard  
**Parent authority:** VARIOM — Intelligent Advertising Strategy & Operating Framework, Version 1.2  
**Scope:** R3 — Actual Output Quality, Repair, and Acceptance

---

## 1. Purpose and authority

This standard operationalizes the approved master strategy's Stage 4 requirements to inspect actual outputs, identify defects, apply bounded repairs, re-evaluate, and accept content only after applicable quality criteria are met.

It complements V-OR-01 (Decision & Brief Readiness) and V-OR-02 (Production Method & Asset Readiness). It does not replace the master strategy or the six approved knowledge documents. Where a conflict exists, the approved source remains authoritative and the conflict must be escalated.

R3 evaluates the actual produced artifact—not the prompt, provider response message, generation status, or a verbal claim that the task succeeded.

## 2. Quality inspection principles

1. Inspect the actual output at the intended delivery size, format, and context wherever possible.
2. Evaluate against the approved brief and task-specific criteria, not personal preference alone.
3. Apply quality checks appropriate to the production route; do not force identical tests onto images, video, montage, editing, or text.
4. Separate factual integrity, brand fidelity, technical correctness, and creative quality. Strength in one category cannot compensate for a critical failure in another.
5. Treat source fidelity and identity-bearing details as high-risk when they affect truth or brand recognition.
6. Distinguish objective defects from subjective creative preferences.
7. Never mark an inspection as passed unless the check was actually performed and its evidence is available.
8. Preserve failed, blocked, and unresolved states. Do not relabel them as complete to advance workflow.
9. A successful API call, completed render, or file export is not proof of creative or technical acceptance.
10. Final content acceptance, financial authorization, and publication authorization remain separate decisions.

## 3. Inspection record

For each output version, record:

- Content ID and output version.
- Approved brief ID/version.
- Production route, provider/model/version where known.
- Source asset references and protected-element requirements.
- Actual output artifact reference.
- Inspection date and reviewer or inspection process.
- Applicable quality checks and their results.
- Defects, severity, location, and evidence.
- Repair decision and attempt number.
- Final disposition and unresolved limitations.

Use a concise record linked to the R1/R2 evidence. Do not duplicate the full brief or asset manifest.

## 4. Shared quality dimensions

Assess the following dimensions when relevant:

### 4.1 Factual and claim integrity

- Product identity and category are correct.
- Model numbers, specifications, compatibility, and quantities match verified sources.
- Claims, proof, certifications, warranty, prices, offers, comparisons, and testimonials are supported.
- No unsupported performance or outcome is implied visually or verbally.
- No generated detail is presented as a verified fact.

### 4.2 Brand fidelity

- Correct brand identity and approved logo asset.
- Brand colors and visual language follow available approved guidance.
- Brand personality and audience suitability are preserved.
- No invented brand assets or identity specifications are presented as official.
- Approved message and concept remain intact.

### 4.3 Copy and language

- Exact approved wording is preserved where required.
- Spelling, grammar, punctuation, tone, and locale are appropriate.
- Arabic shaping, joining, direction, alignment, and glyph integrity are correct.
- No accidental text substitution, duplication, truncation, or illegible text.
- CTA and message hierarchy match the brief.

### 4.4 Visual/creative quality

- Composition and hierarchy support the objective.
- Subject and product are clear and not misleadingly distorted.
- Spacing, contrast, cropping, and balance are appropriate.
- No visible artifacts, malformed elements, unintended overlays, or inconsistent details.
- The design remains legible in its intended viewing context.

### 4.5 Technical delivery

- Correct file type, dimensions, aspect ratio, resolution, duration, frame rate, and audio properties as applicable.
- No corruption, missing frames, unintended borders, black frames, clipping, or export defects.
- Output is suitable for the intended platform and delivery use.
- Required editable/layered source is present only when the brief requires and the tool supports it; unsupported source formats must be disclosed rather than fabricated.

## 5. Route-specific quality checks

### 5.1 Static images

Check:
- Authenticity and fidelity of protected logos/products/packaging.
- Text accuracy and Arabic shaping.
- Visual hierarchy, contrast, spacing, and crop safety.
- Correct ratio, dimensions, and export quality.
- Absence of invented labels, claims, badges, or specifications.

### 5.2 Carousel and multi-panel content

Check:
- Each panel independently for factual and visual defects.
- Message progression and consistency across panels.
- Repeated product/brand elements remain consistent.
- No contradictions, duplicated claims, missing steps, or broken sequence.
- Cover and final CTA match the approved plan.

### 5.3 Generated video

Check:
- Brand/product identity and protected-asset integrity across relevant scenes and frames.
- Temporal consistency, scene continuity, object persistence, and transitions.
- Correct duration, aspect ratio, resolution, frame rate, and audio.
- Speech, subtitles, language, pronunciation, and synchronization where applicable.
- No unauthorized likeness, voice imitation, or unsupported claims.
- No transient defects that are invisible in a single thumbnail; inspect the playback.

### 5.4 Montage and editing

Check:
- Shot order and narrative continuity.
- Trim points, pacing, transitions, and synchronization.
- Audio levels, clipping, silence, and unintended noise.
- Aspect ratio, safe areas, subtitles, and export settings.
- Original footage and protected details are not materially misrepresented.

### 5.5 Existing-content editing and enhancement

Check:
- Requested change was made and unrelated content preserved.
- Protected details remain authentic.
- No unintended content removal, substitution, or visual damage.
- Before/after comparison confirms scope adherence.
- Output is not described as an enhancement if only a superficial change occurred.

### 5.6 Text, copy, and production prompts

Check:
- Alignment with approved objective, concept, audience, and brand voice.
- Factual support and absence of unsupported claims.
- No contradictions, ambiguous requirements, or missing critical constraints.
- Prompt instructions distinguish protected source assets from generated elements.
- Prompt is executable by the selected route and does not request mutually incompatible outcomes.

## 6. Defect severity and disposition

Classify each defect by its effect on truth, brand integrity, usability, and approved requirements.

| Severity | Definition | Required disposition |
|---|---|---|
| **CRITICAL** | Misrepresentation, fabricated product/brand proof, materially false claim, protected-asset identity corruption, unauthorized content, or a defect that makes the deliverable unsafe/unacceptable | Reject output; block delivery; repair only after cause and safe method are established |
| **MAJOR** | Failure of an explicit brief requirement, material text/language error, significant brand mismatch, broken sequence, or technical defect affecting intended use | Reject current version; repair and re-inspect affected output |
| **MINOR** | Localized defect that does not alter meaning, identity, or core usability | Repair if efficient and within scope; re-inspect affected area |
| **PREFERENCE** | Subjective alternative with no breach of approved brief or acceptance criteria | Do not treat as a failure; change only if within approved discretion or separately approved |

Severity is determined by impact, not by how visually noticeable the defect is. A small incorrect model code can be CRITICAL even if most of the design looks excellent.

## 7. Repair policy

1. Identify the defect precisely before attempting repair.
2. Determine whether the cause is the brief, asset, production route, provider limitation, prompt, editing operation, or inspection process.
3. Repair only the affected part where this preserves consistency and truth.
4. Do not use a repair method that risks damaging a protected asset.
5. Preserve the approved objective, concept, and material message.
6. A material change to the concept or message requires the applicable approval before repair execution.
7. Record each repair attempt, change made, and resulting inspection.
8. Re-inspect every criterion affected by the repair; do not assume a local edit has no side effects.
9. Stop when the repair limit or another stopping condition is reached.
10. Do not hide a failed attempt or unresolved defect from the final record.

The maximum repair count must be taken from the approved product/workflow policy for the applicable production route. If no applicable limit is defined, do not invent one; use the configured policy or require owner decision before repeated repair attempts. The master strategy's bounded-repair principle remains controlling.

## 8. Acceptance states

Assign one state to each output version:

- **PASS:** all applicable mandatory criteria are met and no unresolved critical/major defect remains.
- **PASS_WITH_LIMITATIONS:** all mandatory acceptance criteria are met, but a clearly disclosed non-critical limitation remains and is acceptable for the intended use.
- **REPAIR_REQUIRED:** identified defects are repairable within the authorized scope and remaining repair allowance.
- **REJECTED:** output fails a mandatory requirement, contains a critical defect, or cannot be safely repaired.
- **BLOCKED:** inspection cannot be completed because required artifact, source, evidence, or reviewer capability is unavailable.
- **OWNER_ACCEPTANCE_REQUIRED:** a material exception, subjective decision outside delegated authority, or unresolved risk requires owner decision.

A content item is not **FINAL** merely because a version has a PASS state. Required customer final-content acceptance must also be obtained where applicable. Publication remains separately controlled.

## 9. Mandatory finalization gate

Before marking an output final, verify:

1. The actual artifact inspected is the same version proposed for delivery.
2. The approved brief and relevant R1/R2 evidence are linked.
3. All applicable mandatory criteria were checked.
4. No unresolved critical or major defects remain.
5. Protected assets and material facts are correct.
6. Repairs are within the allowed scope and attempt limit.
7. Required approvals are recorded with their exact scope.
8. Remaining limitations are disclosed.
9. Production cost and relevant execution record are captured where applicable.
10. The status does not imply financial or publication authorization that was not granted.

## 10. Required negative tests

| Test | Deliberate defect | Expected result |
|---|---|---|
| R3-N01 | Logo letters or proportions changed | CRITICAL; reject |
| R3-N02 | Product model code is altered | CRITICAL; reject |
| R3-N03 | Arabic headline contains broken joining or wrong spelling | MAJOR or CRITICAL according to meaning; not pass |
| R3-N04 | Design looks polished but includes unsupported certification | CRITICAL; reject |
| R3-N05 | Image has correct content but wrong required aspect ratio | MAJOR; repair/reject based on feasibility |
| R3-N06 | Video has a one-frame product identity mutation | CRITICAL; reject or repair and inspect temporal sequence |
| R3-N07 | Carousel contains contradictory product claims | CRITICAL/MAJOR by impact; reject current version |
| R3-N08 | Montage audio clips or subtitles desynchronize materially | MAJOR; repair and re-inspect |
| R3-N09 | Editing changes unrelated protected content | CRITICAL/MAJOR by impact; reject |
| R3-N10 | Prompt contains contradictory instructions about exact assets and regeneration | MAJOR; repair brief/prompt before execution |
| R3-N11 | Provider reports success but no output artifact is available | BLOCKED; no quality pass |
| R3-N12 | Repair changes approved core message | Stop; obtain applicable approval before continuing |
| R3-N13 | Repair allowance is exhausted and defect remains | Stop; REJECTED or OWNER_ACCEPTANCE_REQUIRED |
| R3-N14 | Visual preference differs but brief and criteria are satisfied | Do not mark as defect |

## 11. Governance

This document remains **DRAFT — OWNER REVIEW REQUIRED**. It is not an approved knowledge-library entry and does not grant production, financial, final-content, or publication authorization. Revisions must be versioned and tested against affected negative cases.

---

## Final operating rule

**Inspect the artifact, not the promise. A result is accepted only when the actual output passes the criteria that matter for its task, its protected assets, and its approved brief.**
