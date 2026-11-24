# VARIOM — Output Inspection, Repair & Acceptance Control

**Document ID:** V-OR-03  
**Version:** 0.2  
**Status:** OWNER-APPROVED  
**Authority:** Master Strategy V1.2 and applicable approved knowledge documents.

## 1. Purpose

Inspect the actual output against its approved brief and task-specific criteria. A provider/API success message is not evidence of quality. Apply existing library criteria where relevant; this standard coordinates inspection and records outcomes rather than duplicating the libraries.

## 2. Defect classification

Classify findings by impact:

- **CRITICAL:** truth, identity, safety, legal, protected-asset, or core approved-direction failure that makes the output unusable or misleading. Reject/stop; repair only if a safe, authorized route exists.
- **MAJOR:** mandatory brief/technical/quality criterion failed or materially harms usability. Repair or reject.
- **MINOR:** non-mandatory defect with limited impact. Repair only if worthwhile and within scope.
- **PREFERENCE:** subjective preference despite satisfying the brief and acceptance criteria. Do not treat as a defect or trigger unnecessary regeneration.

Use task-specific criteria and applicable V-KD guidance; do not invent universal scoring or requirements.

## 3. Inspection

Check the exact artifact/version intended for delivery. Inspect all criteria relevant to the route and format, including factual accuracy, brand direction, typography/language, composition, technical specifications, protected assets, continuity/audio/subtitles for video, and any requested edit/montage details.

Record defect, severity, evidence/location, and disposition. Re-inspect criteria affected by any repair and check for regression to protected elements or approved messaging.

## 4. Repair control

- Repair the affected part when safe and sufficient.
- Preserve approved objective, concept, core message, and protected assets.
- Material changes to approved direction require the relevant approval before execution.
- Record each corrective execution and inspect its result.
- Maximum **two repair attempts per content item**, consistent with approved product constraints. An attempt is a new corrective execution after an inspected defect; diagnosis alone is not an attempt.
- Do not reset the count by switching provider, prompt, or version.
- Stop immediately if no safe route exists; stop after two unsuccessful attempts.

## 5. Output state

- **PASS:** all mandatory criteria satisfied; no unresolved critical/major defect.
- **PASS_WITH_LIMITATIONS:** mandatory criteria met; disclosed non-critical limitation is acceptable for intended use.
- **REPAIR_REQUIRED:** correctable defect and remaining attempt allowance.
- **REJECTED:** mandatory failure or unsafe/unrepairable output.
- **BLOCKED:** artifact/source/reviewer evidence unavailable.
- **OWNER_ACCEPTANCE_REQUIRED:** exception or unresolved material risk outside delegated authority.

Output PASS is not customer final-content acceptance or publication permission. Required customer acceptance must be recorded separately.

## 6. Record and final check

Use the **Unified Task Execution Record** for artifact/version, criteria, findings, severity, repair history, reinspection, result, limitations, reviewer, and acceptance references. Before final handoff confirm the inspected artifact is the delivered version; applicable criteria passed; protected assets and claims are correct; repair limit respected; limitations disclosed; and required approvals recorded.

## 7. Negative cases

Validate existing R3-N01–N14: altered logo/model code; broken Arabic; unsupported certification; wrong aspect ratio; video identity mutation; carousel claim contradiction; audio/subtitle issue; unrelated protected-content edit; contradictory prompt; provider success without artifact; changed approved message; exhausted repair allowance; and preference mistaken for defect.

## 8. Governance

OWNER-APPROVED as an operational standard. Platform implementation still requires separate explicit authorization.

**Operating rule:** Inspect the actual artifact. Accept only evidence-supported results against task requirements; success notifications, polish, or personal preference are not substitutes.
