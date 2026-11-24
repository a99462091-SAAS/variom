# VARIOM — Production Method & Asset Readiness Standard

**Document ID:** V-OR-02  
**Version:** 0.1  
**Status:** DRAFT — OWNER REVIEW REQUIRED  
**Document type:** Operational companion standard  
**Parent authority:** VARIOM — Intelligent Advertising Strategy & Operating Framework, Version 1.2  
**Scope:** R2 — Production Method and Asset Readiness

---

## 1. Purpose and authority

This standard operationalizes Stage 4 provider selection and the pre-generation gate in the approved master strategy, together with the relevant requirements of V-KD-03, V-KD-04, V-KD-05, and V-KD-06.

It does not replace or amend those sources. If a conflict appears, record it and request owner review. This document is a proposed operational companion, not an approved knowledge-library entry.

R2 begins only after the task has passed R1 with a suitable status. R2 determines whether the selected production route and assets are sufficiently suitable for the requested task. Passing R2 does not authorize paid execution, which remains subject to the master strategy's approval and financial-authorization boundaries.

## 2. Required asset classification

Every material visual, audio, text, or reference input must be assigned to one of these classes:

### 2.1 Protected source asset

An asset whose identity or content must remain authentic and must not be regenerated or materially altered. Examples include:

- Official brand logos and registered marks.
- Actual product and package photographs where exact appearance matters.
- Labels, model identifiers, serial/product codes, printed specifications, and certification marks.
- Customer-supplied photographs or footage that must remain faithful to the source.
- Approved legal, compliance, or brand elements.

The task record must state what must remain unchanged. A reference image supplied to a generative model is not proof that the model will preserve it.

### 2.2 Generatable element

An element that may be created by a production model because it is not itself a factual or identity-bearing source asset. Examples may include:

- Backgrounds and abstract environments.
- Decorative shapes and non-factual visual accents.
- Generic lighting atmospheres and non-identifying scene elements.
- Illustrative elements that do not depict a specific real product, person, certification, or factual result.

### 2.3 Editable element

An existing element that may be transformed within explicit boundaries, such as cropping, resizing, background removal, color adjustment, or retouching. The allowed operations and prohibited changes must be stated.

### 2.4 Verified information asset

A fact, approved text, specification, or claim that must be transferred accurately from an identified source. It may not be treated as decorative prompt material or reconstructed from a low-resolution visual if a reliable source is available.

## 3. Asset manifest

Before selecting the production route, create a concise asset manifest for every required or material asset:

| Field | Required content |
|---|---|
| Asset ID | Stable task-level identifier |
| Asset name/type | Logo, product photo, packaging, copy, footage, reference, etc. |
| Source | Supplied file, approved brand source, verified URL, or record reference |
| Availability | Available, missing, inaccessible, or uncertain |
| Classification | Protected, generatable, editable, or verified information |
| Required fidelity | Exact, content-preserving, approximate, or illustrative |
| Permitted operations | Explicit allowed edits |
| Prohibited operations | Explicit changes that would misrepresent the asset |
| Usage constraints | Rights, territory, channel, expiry, or other known restrictions |
| Verification status | Checked, not checked, or unable to verify |

Do not infer usage rights merely from possession of a file. If rights or permissions are material and unknown, record the limitation and block the affected use where necessary.

## 4. Protected-asset handling rules

1. Never ask an image/video generation model to recreate a protected logo, package, product label, model code, certification, or factual mark when exact fidelity is required.
2. Prefer direct placement/compositing of the authentic source asset over generative recreation.
3. If a source asset requires cropping, masking, background removal, or color correction, preserve the protected content and inspect the transformed result against the source.
4. Keep generated scene elements separate from protected source assets whenever the production tools permit.
5. Never present a generated substitute as an authentic product or official brand asset.
6. If the original asset is missing, use a clearly marked placeholder only in a draft/mock-up, or change the composition to avoid implying the asset exists. Do not fabricate a replacement.
7. Do not infer product compatibility, specifications, certification, warranty, or performance from visual resemblance.
8. A provider's reference-image feature is only a declared or observed capability until tested under relevant conditions. It is not a guarantee of pixel-level preservation.
9. When a protected asset is transformed by any tool, record the operation and perform a direct source-to-output inspection.
10. If fidelity cannot be verified, do not pass the affected deliverable as final.

## 5. Production route selection

Select the least complex route that can meet the approved brief and preserve required fidelity.

Potential route patterns include:

- **Direct composition:** place original protected assets and precisely typeset text into a designed layout.
- **Generative scene + compositing:** generate only the environment/background, then insert authentic assets and approved text.
- **Controlled editing:** edit the supplied original while protecting specified content.
- **Full generation:** use only when the task permits generated content and no protected source element requires exact reproduction.
- **Video generation with source references:** only when the relevant continuity and asset-preservation requirements have been tested sufficiently for the intended use.
- **Conventional montage/editing:** assemble supplied footage, audio, and overlays where exact timing, identity, and source fidelity matter.

A route may combine methods. Do not force all tasks through one provider or one generation mode.

### Route decision record

Record:

- Candidate route(s) considered.
- Selected route and concise rationale.
- Protected assets and how each is preserved.
- Generatable/editable elements.
- Known route limitations.
- Relevant provider and tool versions/settings when available.
- Evidence level for each critical capability.
- Fallback route or safe stop condition.

## 6. Provider capability evidence

The master strategy distinguishes provider-declared, observed, and repeatedly validated capabilities. Preserve these distinctions exactly.

| Evidence level | Meaning | Permitted interpretation |
|---|---|---|
| DECLARED | Provider documentation or interface states the capability | Candidate capability; not independently proven |
| OBSERVED | A real test or task demonstrated it under recorded conditions | Demonstrated only for those conditions |
| REPEATEDLY_VALIDATED | Relevant repeated cases show consistent performance | Stronger evidence within the tested scope; not universal guarantee |
| UNKNOWN | No adequate evidence | Must not be assumed |

For each critical provider capability, record:

- Provider, model/tool, and version/date where available.
- Capability being assessed.
- Source of evidence.
- Test input and conditions.
- Expected behavior.
- Observed result.
- Known failure modes.
- Scope and limitations.
- Evidence level and reviewer.

One successful example must never be described as universal reliability. Old evidence must be rechecked when provider versions, workflows, or material task conditions change.

## 7. Route suitability decision

A production route is suitable only when all critical requirements of the approved brief are supported by adequate evidence or can be safely handled outside the model.

Assess, where relevant:

- Protected-asset fidelity.
- Reference adherence and identity consistency.
- Language and script rendering.
- Text accuracy.
- Required image/video format, ratio, resolution, duration, and output type.
- Scene/shot continuity.
- Audio, voice, and rights constraints.
- Editing/compositing capability.
- Reliability, availability, and known failure modes.
- Cost, latency, and execution limits.

Decision statuses:

- **SUITABLE_FOR_PRE-GENERATION_GATE:** route is suitable for the task assessment; paid execution still requires the separate authorization check.
- **SUITABLE_WITH_LIMITATIONS:** non-critical limitations are explicit and the deliverable remains truthful and acceptable.
- **UNSUITABLE:** route cannot satisfy one or more critical requirements.
- **INSUFFICIENT_EVIDENCE:** a critical capability is unknown or supported only by inadequate evidence.
- **OWNER_DECISION_REQUIRED:** rights, policy, brand, cost, or material exception needs owner authority.

## 8. Pre-generation gate handoff

R2 supplies the following to the master strategy's pre-generation gate:

1. R1 brief ID/version and readiness status.
2. Asset manifest and protected-element map.
3. Selected route and rationale.
4. Provider capability evidence and limitations.
5. Required output specifications.
6. Factual, brand, rights, and technical restrictions.
7. Expected cost/latency or the fact that they are unknown.
8. Fallback route or stop condition.
9. Outstanding approvals and authorization requirements.

R2 must not grant financial authorization. The master strategy's rule remains controlling: paid production cannot begin without the required authorization for the relevant task and spending scope.

## 9. Mandatory stop conditions

Stop the affected route or task when:

- A required protected source asset is missing and cannot be safely omitted.
- A route would need to fabricate an authentic logo, product, label, factual mark, or proof.
- A critical fidelity requirement is unsupported by provider evidence.
- A provider limitation makes a material output requirement infeasible.
- Rights or usage restrictions create an unresolved material risk.
- A required output format or technical constraint cannot be met.
- The route would turn an unverified claim into a visual assertion.
- No safe fallback exists for a critical failure.

Do not stop unrelated deliverables if they can proceed independently without misleading the audience or violating the approved brief.

## 10. R2 acceptance criteria

R2 passes only when evidence shows that:

1. All material assets are classified.
2. Protected assets have explicit preservation requirements.
3. Missing assets are disclosed and not fabricated.
4. Permitted and prohibited transformations are recorded.
5. The route is appropriate to the approved brief.
6. Critical provider capabilities have evidence levels and test scope.
7. Declared capability is not mislabeled as verified capability.
8. Known limitations and failure modes are recorded.
9. A fallback or stop condition exists for critical failures.
10. The pre-generation handoff is complete.
11. Financial authorization remains a separate decision.

## 11. Required negative tests

| Test | Input condition | Expected R2 result |
|---|---|---|
| R2-N01 | Official logo must be exact, but only generative recreation is available | Route unsuitable; do not regenerate logo |
| R2-N02 | Product package includes small printed model text | Preserve original asset; generation may create only surrounding scene |
| R2-N03 | Provider claims reference adherence but no relevant test exists | DECLARED/UNKNOWN only; no claim of verified preservation |
| R2-N04 | One reference test succeeds | OBSERVED for that test only; not repeatedly validated |
| R2-N05 | Required original product image is missing | Block affected product-specific execution or use a clearly marked placeholder in draft only |
| R2-N06 | Background generation is feasible but product fidelity is not | Use generated background plus authentic product compositing, if feasible |
| R2-N07 | Provider cannot meet required Arabic text fidelity | Keep text outside generative rendering or select another route |
| R2-N08 | Rights/usage permission for a required asset is materially uncertain | Stop affected use pending resolution |
| R2-N09 | Model/version changes after previous capability tests | Reassess affected critical capabilities |
| R2-N10 | Paid route is suitable but no financial authorization exists | Route may be assessed; paid execution remains prohibited |

## 12. Relationship to other reliability standards

- V-OR-01 controls decision and brief readiness.
- V-OR-02 controls production method and asset readiness.
- V-OR-03 will control actual output inspection, defects, repair, and final acceptance.
- V-OR-04 will control simulation and validation evidence.

The master strategy remains the controlling source for the overall workflow and approval boundaries.

## 13. Governance

This standard remains **DRAFT — OWNER REVIEW REQUIRED**. It is not an approved knowledge-library entry and does not authorize platform implementation or production execution. Changes must be versioned, justified, and tested against the cases in this document.

---

## Final operating rule

**A reference is not a guarantee, a provider claim is not proof, and a generated imitation is not an authentic source asset. Select a production route only when its evidence and asset-handling method are suitable for the actual brief.**
