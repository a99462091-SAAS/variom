# VARIOM — Product Decisions Register

**Version:** 1.0  
**Status:** Active canonical index for owner decisions; updated after the owner’s Gate A decisions.  
**Last updated:** 2026-11-19

## Decision recording rules

- Only explicit owner decisions are marked **APPROVED**.
- A proposal, MAX source, audit recommendation or technical convention is not an owner decision.
- **OPEN** means owner input is required before the affected behavior is specified or implemented.
- **DEFERRED** means implementation is prohibited until the stated evidence or gate is satisfied.
- **REFERENCE-ONLY** means useful source material, not an approved VARIOM requirement.
- When an owner changes a decision, append a superseding decision entry; do not erase history.
- Each decision must identify scope, rationale/source, date, status and affected documents.

## A. Confirmed owner decisions

| ID | Decision | Status | Source / evidence | Scope |
|---|---|---|---|---|
| VAR-D-001 | VARIOM has a separate repository named `a99462091-SAAS/variom`; the MAX repository remains the planning/source reference. | APPROVED | Owner instruction, 2026-11-19; migration verified against MAX branch `work/variom-ai-documentation`, source commit `cc68f8f407a625d807ee167d2766be6de6343736` | Repository boundary |
| VAR-D-002 | Product Vision V2.0 is the highest product authority; UX/Frontend V2.1 is subordinate and may clarify implementation but not expand product scope. | APPROVED | `00-product-vision-simplified-ux-v2.md` | Product authority |
| VAR-D-003 | MAX planning documents are a source foundation for reusable planning material, but each source must be reconciled and recorded; historical MAX decisions are not automatically VARIOM decisions. | APPROVED | VARIOM README and source-reconciliation policy | Source governance |
| VAR-D-004 | Documentation readiness must be completed before platform implementation begins; no code, paid provider activation, paid generation, migration, merge or deployment is authorized by the planning documents alone. | APPROVED | Owner-directed documentation readiness task; audit 18 safety boundary | Phase boundary |

## B. Owner decisions required

| ID | Decision required | Status | Why it matters | Affected work |
|---|---|---|---|---|
| VAR-OD-001 | Confirm the provisional plan labels and brand-count presentation, while deferring the commercial model. | RESOLVED — PRESENTATION ONLY | Explicit owner decision, 2026-11-19: Starter / Pro / Agency, displayed as 1 / 3 / up to 8 brands. This is a temporary presentation convention only; it does not approve pricing, subscriptions, billing, entitlements, or enforcement. | Plan labels and non-binding UI/document presentation only; commercial model remains deferred |
| VAR-OD-002 | Use the latest owner-approved VARIOM identity image, incorporating the best refinements, as the canonical visual reference. The owner will provide the image directly to Claude Code; it is not required to be re-uploaded into this repository. | APPROVED — 2026-11-19 | Explicit owner instruction. The latest approved image supersedes the three similar recovered variants for implementation reference. | Visual identity and frontend styling; do not substitute another variant |
| VAR-OD-003 | The owner will provide the intended UI Design Prompt directly to Claude Code. Do not recreate or replace it. | APPROVED — INPUT TO BE SUPPLIED BY OWNER | Explicit owner instruction, 2026-11-19. The prompt is an external implementation input and will be supplied by the owner; absence from this repository is not authorization to draft a substitute. | Frontend design; implementation must wait until the owner supplies the prompt |
| VAR-OD-004 | Adapt the recovered MAX Virtual Character v1.0 product contract into a concise VARIOM-specific questionnaire and Character Sheet, preserving its applicable safeguards and not copying unrelated MAX UI. | APPROVED — ADAPTATION AUTHORIZED | Explicit owner approval of the recommendation, 2026-11-19; source and limits documented in audit 17. | Character Studio, consent, UX; adaptation remains documentation work until separately authorized for implementation |
| VAR-OD-005 | Use intelligent image/video distribution for 8/12/16-post plans; defer fixed ratios and exact counts until quality, product and provider evidence is available. | APPROVED — RULE DEFERRED | Explicit owner approval of the recommendation, 2026-11-19. Do not invent fixed distribution ratios. | Monthly Content; detailed algorithm remains deferred |
| VAR-OD-006 | Retain the output choices already specified in Product Vision V2.0; defer pixel dimensions, technical formats, resolution and provider-specific quality details until capability verification. | APPROVED — EXISTING PRODUCT BOUNDS RETAINED | Explicit owner approval of the recommendation, 2026-11-19. No new output option or 4K support is implied. | Image/Video Studio and provider contracts; technical details remain deferred |
| VAR-OD-007 | Adopt a limited initial-market launch strategy and defer currency, tax, pricing, payment, top-up and subscription decisions until commercial and legal review. The exact first launch market remains to be named before launch planning is finalized. | PARTIALLY RESOLVED — MARKET STRATEGY ONLY | Explicit owner approval of the recommendation, 2026-11-19. No country, currency, tax treatment or payment method is inferred. | Launch planning, billing, credits and legal review; exact market and commercial terms remain open |
| VAR-OD-008 | Adopt separate user-controlled deletion for generated assets, brands and accounts; distinguish legally required financial/security records from content; deletion must account for backups and processors. Exact retention periods and legal wording remain deferred pending jurisdiction-specific review. | APPROVED — PRINCIPLES ONLY | Explicit owner approval of the recommendation, 2026-11-19. | Storage, library, account and privacy; retention periods/legal details remain deferred |
| VAR-OD-009 | First-release authentication uses email and password, email verification, password recovery by email and appropriate session/security controls; do not add social login by default. | APPROVED | Explicit owner approval of the recommendation, 2026-11-19. | Authentication; implementation details must follow the security contract |
| VAR-OD-010 | Support Arabic and English; expose dialect/voice choices only where useful and verified as available; use licensed/provider-approved voices and do not imitate real-person voices without documented rights and consent. Keep voice controls limited and integrated into the relevant workflow. | APPROVED — CAPABILITY-BOUNDED | Explicit owner approval of the recommendation, 2026-11-19. Specific dialects and voice catalogue depend on provider verification. | Video and Character Studio; provider catalogue remains deferred |

## C. Deferred pending evidence or stage gate

| ID | Item | Status | Required evidence / gate |
|---|---|---|---|
| VAR-DD-001 | Provider/model selection, region, exact capabilities, pricing, limits, rights and data terms. | DEFERRED | Current official provider documentation, account/region access, cost review and approved practical test. |
| VAR-DD-002 | Hosting, managed database, object storage, KMS/secret manager, backup and deployment topology. | DEFERRED | Repository technical baseline plus owner constraints, cost/security review and environment evidence. |
| VAR-DD-003 | Provider-specific output resolution, duration/format constraints and repair limits beyond already approved product bounds. | DEFERRED | Verified provider capability and cost evidence; owner approval if product behavior changes. |
| VAR-DD-004 | Legal wording for user uploads, likeness/voice/consent, music rights, retention and provider data transfers. | DEFERRED | Jurisdiction-specific legal review before relevant production/launch activity. |

## D. Existing product decisions carried forward from controlling documents

These are inherited only from VARIOM's controlling product baseline, not inferred from MAX.

## F. Gate A decisions recorded on 2026-11-19

The owner approved the latest refined identity image as the canonical visual reference and will supply it directly to Claude Code. The owner will also supply the intended UI Design Prompt directly; no replacement prompt is authorized. The owner approved the recommendations for Character Studio adaptation, intelligent Monthly Content distribution with ratios deferred, existing output bounds with technical details deferred, limited-market launch strategy with exact market/commercial terms deferred, deletion/retention principles with legal details deferred, email/password authentication, and capability-bounded Arabic/English voice and dialect behavior. See VAR-OD-002 through VAR-OD-010 for exact scope and remaining gates.

- Four logical product systems: Brand Intelligence, Marketing & Creative Intelligence, Content Production, Content Library.
- No Product Catalog; product photos are uploaded per relevant task.
- Monthly Content: 8, 12 or 16 posts; images and videos only; no carousel; up to three marketing goals; no publishing-platform selection; monthly video maximum 10 seconds.
- Video Studio: 10, 20 or 30 seconds; mandatory internal Master Storyboard; optional scene review; no direct-generation bypass.
- Arabic and English, with RTL/LTR support.
- Completed outputs are automatically saved to Content Library.
- No professional timeline editor, scheduling/publishing, analytics, team approvals, ZIP export or other excluded scope in the Product Vision.
- The six Simple Smart Editing tasks and six Motion Graphics categories were recovered in audit 17, but still require promotion into a normative task-level specification before implementation.
- No bulk adoption of the 144 MAX creative styles; individual styles remain subject to VARIOM review and approval.

## E. Decision status summary

- Confirmed owner decisions: 4
- Resolved owner decisions: 9 (including VAR-OD-001 presentation-only)
- Partially resolved owner decisions: 1 (VAR-OD-007; exact first market remains open)
- Open owner decisions: 1 (remaining portion of VAR-OD-007)
- Deferred evidence/legal/technical items: 4
- No open item may be silently converted into an approved product requirement by Claude Code.
