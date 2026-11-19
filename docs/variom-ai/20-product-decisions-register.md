# VARIOM — Product Decisions Register

**Version:** 1.0  
**Status:** Initial register; this is the canonical index for owner decisions.  
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
| VAR-OD-001 | Resolve Basic/Pro/Max (1/3/10 brands) versus Starter/Pro/Agency (1/3/up to 8) and whether plan information remains hidden in the first release. | OPEN | Conflicting product/commercial requirements; cannot safely expose or enforce tiers. | Dashboard, account limits, billing, credits |
| VAR-OD-002 | Select one of the three recovered VARIOM identity-board variants as canonical, or declare all non-final. | OPEN | Prevents inconsistent brand/UI implementation. | Visual system, frontend |
| VAR-OD-003 | Recover the original final UI Design Prompt or authorize creating a replacement from the approved identity baseline. | OPEN | Visual identity tokens alone do not define the full UI design system. | Frontend design |
| VAR-OD-004 | Provide the exact VARIOM-approved Virtual Character questionnaire/Character Sheet source, or authorize adaptation of MAX Virtual Character v1.0 into VARIOM-specific UX and contract. | OPEN | The referenced VARIOM questionnaire and output contract are not present. | Character Studio, consent, UX |
| VAR-OD-005 | Confirm monthly 8/12/16-post image/video distribution rules, or explicitly defer the distribution algorithm pending product/provider evidence. | OPEN | “Smart distribution” is not deterministic enough to implement. | Monthly Content |
| VAR-OD-006 | Confirm exact image/video output ratios, pixel dimensions, formats and quality rules where current labels are insufficient; otherwise defer provider-specific values until capability verification. | OPEN | Portrait/Landscape labels do not establish technical output contracts. | Image/Video Studio, providers |
| VAR-OD-007 | Decide which launch markets, currency/tax assumptions and payment/top-up scope are in first release. | OPEN | Affects commercial and legal contracts. | Billing, credits, launch |
| VAR-OD-008 | Confirm content/asset retention and deletion behavior, account/brand deletion behavior and any legal retention constraints. | OPEN | Security/privacy and data lifecycle require explicit policy. | Storage, library, account |
| VAR-OD-009 | Confirm supported signup/login/recovery and email-verification expectations for first release, or authorize a bounded technical recommendation. | OPEN | Establishes identity and account security contract. | Authentication |
| VAR-OD-010 | Confirm voice/dialect behavior and whether any user-selectable voice controls are in scope for video/characters. | OPEN | Must not invent voice, language or synthetic identity behavior. | Video, Character Studio |

## C. Deferred pending evidence or stage gate

| ID | Item | Status | Required evidence / gate |
|---|---|---|---|
| VAR-DD-001 | Provider/model selection, region, exact capabilities, pricing, limits, rights and data terms. | DEFERRED | Current official provider documentation, account/region access, cost review and approved practical test. |
| VAR-DD-002 | Hosting, managed database, object storage, KMS/secret manager, backup and deployment topology. | DEFERRED | Repository technical baseline plus owner constraints, cost/security review and environment evidence. |
| VAR-DD-003 | Provider-specific output resolution, duration/format constraints and repair limits beyond already approved product bounds. | DEFERRED | Verified provider capability and cost evidence; owner approval if product behavior changes. |
| VAR-DD-004 | Legal wording for user uploads, likeness/voice/consent, music rights, retention and provider data transfers. | DEFERRED | Jurisdiction-specific legal review before relevant production/launch activity. |

## D. Existing product decisions carried forward from controlling documents

These are inherited only from VARIOM's controlling product baseline, not inferred from MAX.

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
- Open owner decisions: 10
- Deferred evidence/legal/technical items: 4
- No open item may be silently converted into an approved product requirement by Claude Code.
