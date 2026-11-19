# VARIOM — Provider & Capability Evidence Register

**Version:** 1.0 | **Status:** NORMATIVE REGISTER TEMPLATE — no provider approved | **Authority:** Documents 19–27.

## 1. Purpose
A controlled evidence register for evaluating generation, editing, storage, email and other external capabilities. This document contains no provider selection or activation approval.

## 2. Approval states
- **UNASSESSED:** no review.
- **RESEARCHED:** public information collected; not practically verified.
- **ACCOUNT_ACCESS_VERIFIED:** access confirmed for the intended account/region.
- **CAPABILITY_TESTED:** a bounded practical test produced evidence.
- **LEGAL_SECURITY_REVIEWED:** terms, privacy and security reviewed.
- **COST_VERIFIED:** current cost basis and unit conversion verified.
- **OWNER_APPROVED:** explicit owner approval for the specified use.
- **ENABLED:** separately authorized activation and controlled rollout.
- **REJECTED / EXPIRED:** unsuitable or evidence no longer current.

A capability is production-eligible only when all required evidence and approvals are present. A research record or successful demo is not activation authorization.

## 3. Required register fields
Each provider/model/capability entry records:
- provider and exact model/service name/version;
- capability and supported task/category;
- account and region/access status;
- official documentation URL and retrieval/review date;
- supported inputs, outputs and media types;
- product-level constraints and provider-specific limits;
- latency/throughput observations where measured;
- pricing unit, current price source, currency, effective date and conversion basis;
- data processing, retention, training use, deletion and subprocessors;
- input/output rights and usage restrictions;
- authentication/secret method and security review;
- error, timeout, cancellation, idempotency and usage-reporting behavior;
- test case, test input class, output evidence and reviewer;
- confidence, known gaps, expiry/recheck date;
- approval state and linked owner decision.

## 4. Capability families to evaluate
- Image generation for P1–P4 and approved formats.
- Video generation for V1–V4, 10/20/30-second product choices and supported aspect ratios.
- Storyboard/scene orchestration, reference conditioning and continuity.
- Smart Editing: each approved task and Motion Graphics category separately.
- Voice/dialect/lip-sync only where lawful, consented and capability-verified.
- Email verification/password recovery delivery.
- Private object storage, media processing, backup and key management.

Do not infer that one provider supports every task in a family. Record each capability independently.

## 5. Test evidence requirements
A practical test record must identify:
- exact model/version, region and account tier;
- timestamp and test operator;
- sanitized prompt/input class and settings;
- requested versus actual output metadata;
- observed quality, limitations, latency and failure behavior;
- usage/cost reported by provider and reconciliation;
- rights/data terms checked at test time;
- whether output is suitable for VARIOM acceptance criteria.
No real customer data is used during exploratory testing unless the provider data gate is cleared and owner authorizes it.

## 6. Capability gating
A UI option may be enabled only if:
1. the product feature is approved in V2.0/requirements;
2. exact capability is verified for the intended account and region;
3. inputs/outputs and operational limits are documented;
4. cost basis is current and can be quoted before billable use;
5. rights, privacy and security checks pass;
6. fallback/error/reconciliation behavior is specified;
7. owner authorization for activation exists.

Otherwise the option remains hidden/disabled or explicitly marked unavailable; no mock is presented as live generation.

## 7. Current evidence status
No provider/model/capability is approved by this register. Provider-specific resolution, codecs, quality, repairs, latency, voice/dialect catalogue, costs and data terms remain unverified until current evidence is attached. Do not fill the register with guessed values.

## 8. Acceptance criteria
- Every enabled provider capability maps to product requirement and practical evidence.
- Costs and rights are current and sourced.
- Account/region access is verified.
- Unknown capabilities remain unavailable.
- Provider activation remains a separate owner-controlled action.
