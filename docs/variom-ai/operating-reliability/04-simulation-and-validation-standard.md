# VARIOM — Simulation & Validation Standard

**Document ID:** V-OR-04  
**Version:** 0.1  
**Status:** DRAFT — OWNER REVIEW REQUIRED  
**Document type:** Operational companion standard  
**Parent authority:** VARIOM — Intelligent Advertising Strategy & Operating Framework, Version 1.2  
**Scope:** R4 — Simulation, Negative Testing, Regression, and Owner Evidence

---

## 1. Purpose and authority

This standard defines how the R1–R3 operating controls are tested before they are treated as reliable in the VARIOM methodology or implemented as platform behavior.

It follows the approved master strategy's Simulation and Validation requirements. It does not replace or amend the master strategy or the six approved knowledge documents. A successful qualitative simulation is not statistical proof, production readiness, or evidence of platform implementation.

R4 tests both successful task handling and the ability to detect, stop, reject, and explain deliberately defective cases.

## 2. Validation principles

1. Test meaningful decisions and material risks, not repeated equivalent examples.
2. Use the same acceptance criteria for comparable cases.
3. Record actual inputs, decisions, rationale, brief, route, artifact where available, findings, repairs, and owner assessment.
4. Distinguish simulation-only results from real provider execution and real campaign performance.
5. A test passes only when its expected result is observed and recorded.
6. Do not claim a provider capability was tested if no real provider execution occurred.
7. Do not claim statistical reliability from a small qualitative sample.
8. Retest affected cases after a material rule, prompt, provider, or workflow change.
9. Preserve failures and limitations as evidence; do not silently remove failed cases.
10. Owner acceptance is required before draft operational standards become approved shared policy or before platform implementation is authorized.

## 3. Test layers

### Layer A — Rule conformance

Verify that each operating rule is correctly represented and does not conflict with the master strategy or approved knowledge documents.

### Layer B — Decision and brief simulation

Use supplied task facts and controlled missing/conflicting inputs to assess R1. Check knowledge applicability, evidence classification, safe omission, brief completeness, and readiness status.

### Layer C — Asset and route assessment

Assess R2 classification and route selection. Where a provider capability is material, distinguish paper reasoning from an actual test. A simulated assessment cannot upgrade provider evidence from DECLARED/UNKNOWN to OBSERVED.

### Layer D — Artifact inspection

Where an actual output is available, assess it under R3. If no artifact exists, the test can validate the inspection procedure or expected decision but cannot establish output quality.

### Layer E — Regression and consistency

Re-run cases affected by changes and compare decisions across similar cases to detect contradictions, unintended permissiveness, or excessive blocking.

### Layer F — Owner acceptance

Present results, failures, limitations, unresolved risks, and proposed policy changes for explicit owner review.

## 4. Minimum scenario coverage

The validation set must include materially different brands, task types, and information conditions. At minimum, include:

- Complete and incomplete Brand DNA.
- Different products, audiences, languages, and markets.
- Monthly marketing plans and individual content requests.
- Static images and multi-panel/carousel content.
- Video generation and video editing/montage.
- Existing-content editing and enhancement.
- Text/copy and prompt preparation.
- Missing essential and non-essential assets.
- Unsupported or ambiguous product claims.
- Conflicting approved instructions.
- Provider-declared capabilities with no independent test.
- Observed capabilities with narrow test conditions.
- Provider failure, malformed output, and missing artifact.
- Critical, major, minor, and preference-level defects.
- Missing approvals and missing financial authorization.
- Repair success, repair regression, and exhausted repair allowance.

The set must be risk-based. It need not contain the same number of cases for every route, but no materially different route may be declared validated solely because another route passed.

## 5. Test case structure

Each case must include:

| Field | Required content |
|---|---|
| Test ID | Stable identifier |
| Objective | Rule or failure mode under test |
| Scenario | Brand/task context and relevant conditions |
| Inputs | Exact facts, assets, missing items, and approvals supplied |
| Expected result | Required decision/status and prohibited outcomes |
| Observed result | What the process actually did |
| Evidence | Brief, route record, artifact, screenshots, inspection notes, or execution record as applicable |
| Verdict | PASS, FAIL, BLOCKED, or NOT_RUN |
| Failure severity | Critical, major, minor, or preference where relevant |
| Root cause | Rule gap, application error, asset issue, provider limitation, or evaluation failure |
| Remediation | Specific corrective action |
| Regression links | Related cases to rerun after change |

Do not use PASS when the required artifact or evidence was unavailable. Use BLOCKED or NOT_RUN.

## 6. Required R4 test suite

The suite must include, at minimum, the following groups.

### 6.1 R1 decision and brief tests

- All R1-N01 through R1-N10 cases in V-OR-01.
- Verify that approved objectives and concepts are not silently changed.
- Verify that irrelevant libraries are not artificially applied.
- Verify that material claims are supported or excluded.
- Verify that missing non-essential information does not create unnecessary customer questions.
- Verify that readiness does not imply production authorization.

### 6.2 R2 route and asset tests

- All R2-N01 through R2-N10 cases in V-OR-02.
- Verify that protected assets are not regenerated where exact fidelity is required.
- Verify that reference-image claims are evidence-labeled accurately.
- Verify that provider capability evidence is scoped to actual test conditions.
- Verify that route suitability and financial authorization remain separate.

### 6.3 R3 quality and acceptance tests

- All R3-N01 through R3-N14 cases in V-OR-03.
- Verify that an actual artifact is inspected.
- Verify that critical and major defects prevent acceptance.
- Verify that subjective preference is not misclassified as objective failure.
- Verify that repairs trigger reinspection of affected criteria.
- Verify that final content acceptance and publication authorization remain separate.

### 6.4 Cross-route tests

At least one end-to-end representative case for each applicable route:
- Static image.
- Carousel/multi-panel.
- Generated video.
- Montage/editing.
- Existing-content editing.
- Text/copy or prompt preparation.

A route without an actual artifact test must be labeled as method-only or not yet validated for output quality.

## 7. Expected failure behavior

A reliable process must demonstrate not only successful completion but correct failure handling:

- Missing critical inputs cause BLOCKED or an explicit safe alternative.
- Unsupported claims are removed or blocked.
- Incompatible instructions are surfaced, not silently combined.
- Unverified provider capabilities are not assumed.
- Protected-asset fidelity failures cause rejection.
- Critical/major output defects prevent final acceptance.
- Repair exhaustion stops further attempts.
- Missing financial authorization prevents paid execution.
- Missing final-content approval prevents final acceptance where required.
- Missing publication authorization prevents publication.

A system that produces attractive outputs but passes these failure cases incorrectly has failed validation.

## 8. Verdict and release criteria

Use these test verdicts:

- **PASS:** expected behavior was observed with adequate evidence.
- **FAIL:** behavior violated the expected result or a mandatory rule.
- **BLOCKED:** the test could not be performed because a required dependency or artifact was unavailable.
- **NOT_RUN:** the case has not been executed.

R4 suite status:

- **NOT_READY:** one or more critical tests failed or required test coverage is absent.
- **READY_FOR_OWNER_REVIEW:** required cases have been executed, results and limitations are documented, and no critical failure remains unresolved.
- **OWNER_ACCEPTED:** the owner explicitly accepts the evidence and residual limitations.
- **IMPLEMENTATION_AUTHORIZED:** a separate explicit authorization exists to implement the accepted methodology in the platform.

Passing R4 does not itself authorize platform implementation. The master strategy requires separate explicit authorization.

## 9. Change impact and regression policy

After any material change to an operating rule, knowledge reference, prompt template, provider/model, asset-handling method, or quality criterion:

1. Identify the affected test cases.
2. Re-run those cases and their direct dependencies.
3. Re-run cross-route regression cases where shared controls changed.
4. Compare results against the previous accepted baseline.
5. Record any new failures or changed behavior.
6. Do not replace the previous baseline until the new evidence is reviewed.

Provider version changes do not automatically invalidate every historical result, but they require reassessment of capabilities materially affected by the change.

## 10. Reporting requirements

The validation report must be concise and evidence-led. Include:

- Scope and version of standards tested.
- Test counts by PASS / FAIL / BLOCKED / NOT_RUN.
- Critical and major failures.
- Defects and root causes.
- Remediation and regression results.
- Provider tests actually performed versus simulation-only assessments.
- Routes with output-quality evidence versus method-only evidence.
- Remaining risks, limitations, and dependencies.
- Owner decisions required.
- Explicit statement of what has not been validated.

Do not report a single aggregate score that hides critical failures. Do not claim production readiness from qualitative simulation alone.

## 11. Required adversarial scenarios

In addition to the referenced R1–R3 cases, include cross-stage scenarios:

| Test | Scenario | Expected result |
|---|---|---|
| R4-X01 | Polished output conflicts with approved product facts | Reject; factual integrity takes precedence |
| R4-X02 | All brief headings are populated but a critical source is absent | R1 blocked |
| R4-X03 | Provider advertises perfect reference adherence; no test evidence exists | Capability remains declared/unknown |
| R4-X04 | One image test passes; system generalizes to video | Fail; route-specific evidence required |
| R4-X05 | A failed attempt is omitted from the record | Fail traceability check |
| R4-X06 | Minor preference causes repeated unnecessary generations | Fail efficiency/proportionality check |
| R4-X07 | Repair improves typography but alters protected packaging | Reject repaired version |
| R4-X08 | Creative approval is treated as spending authorization | Fail approval-boundary check |
| R4-X09 | Content is accepted and automatically published | Fail publication-boundary check |
| R4-X10 | Small qualitative sample is described as statistical proof | Fail evidence interpretation |
| R4-X11 | Rule change is committed without affected regression tests | Not ready for owner acceptance |
| R4-X12 | A task has no artifact, but output quality is marked passed | Fail; mark BLOCKED or method-only |

## 12. Governance

This standard remains **DRAFT — OWNER REVIEW REQUIRED**. Test evidence may inform revisions but does not silently approve them. Shared rules and platform behavior require the applicable owner review and separate implementation authorization.

---

## Final operating rule

**VARIOM is reliable only when it can explain both why it proceeds and why it stops—and can show evidence that it did so correctly.**
