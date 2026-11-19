# VARIOM — Owner Input and Source Recovery Audit

**Date:** 2026-11-19  
**Status:** PARTIAL RECOVERY — several planning inputs recovered; exact owner-authored UI prompt and canonical image selection remain open.  
**Target branch:** `work/variom-ai-documentation`  
**Authority:** Product Vision V2.0 is the product authority; UX/Frontend Master Specification V2.1 is subordinate. MAX sources are reusable planning evidence only where compatible with those VARIOM decisions.

## 1. Purpose and boundary

This audit locates the source inputs previously identified as missing from the VARIOM documentation set. It checks the MAX repository branches and the user's ChatGPT Library. It does not reconstruct missing owner-authored prompts, invent questionnaire fields, or treat historical MAX decisions as automatic VARIOM approval.

No application code, schemas, database, provider configuration, production data, or MAX source files were changed. No tests, builds, paid generation, or provider activation were performed.

## 2. Executive result

| Input | Recovery result | Disposition |
|---|---|---|
| Separate final VARIOM UI Design Prompt | Not located in inspected MAX repository branches or Library search | Remains open; do not recreate it from the UX spec |
| VARIOM visual identity board | Three near-duplicate image files located in Library | Visual direction recovered; canonical file/variant not explicitly selected |
| Simple Smart Editing task catalogue | Recovered in MAX approved architecture §12 and the MAX tracker decision D-25 | Exact task and motion-category scope recovered; reconcile with VARIOM screen behavior |
| Virtual Character specification | Recovered in `virtual-character-spec-v1.0-review`; owner editorial acceptance recorded in the document on 2026-10-30 | Reusable product-contract source; not by itself proof of the exact VARIOM UI questionnaire |
| Exact concise VARIOM Character questionnaire / final Character Sheet prompt | No separate VARIOM-specific questionnaire or final prompt located | Use the accepted specification as constraints; do not invent a final questionnaire |
| Product Vision V2.0 and UX Master Prompt V2.1 verbatim originals | Current VARIOM docs explicitly identify themselves as structured consolidations, not verbatim copies | Original wording remains open if verbatim preservation is required |
| Creative Content Intelligence Library original source | Existing MAX blocker B-012 states the verbatim source from 2026-10-28 was not recovered | Remains open; do not reconstruct from summaries or taxonomy data |

## 3. Visual identity source recovery

Three VARIOM identity boards are present in the user's Library:

- `لوحة هوية VARIOM المستقبلية البحرية.png` — uploaded 2026-11-18.
- `لوحة هوية VARIOM المستقبلية.png` — uploaded 2026-11-18.
- `لوحة هوية VARIOM المستقبلية(1).png` — uploaded 2026-11-18.

The inspected boards consistently show the jellyfish symbol, VARIOM wordmark/tagline, the palette below, and the three typefaces. They are visually similar iterations, not byte-identical or identical compositions. The prior owner discussion supports the VARIOM name, jellyfish symbol and general image-inspired visual direction, but does not identify one of these three files as the canonical final source.

### Recovered identity values

| Element | Recorded value |
|---|---|
| Product name | VARIOM |
| Tagline | Create Beyond the Ordinary |
| Symbol direction | Jellyfish |
| Deep Ocean Navy | `#071426` |
| Midnight Blue | `#0B1D35` |
| Electric Cyan | `#22DDF2` |
| Turquoise | `#16B9C8` |
| Ice Blue | `#DDF8FC` |
| Pure White | `#F5FAFC` |
| Headings | Sora |
| English UI/body | Inter |
| Arabic UI/body | IBM Plex Sans Arabic |

These values match `05-visual-identity-baseline.md`. The boards also contain illustrative app mockups and decorative treatments; those are visual references, not approved screen-by-screen UX or a replacement for the separate UI Design Prompt.

The MAX document `docs/VISUAL_DESIGN_SYSTEM_FOUNDATION_DRAFT_2026-11-01.md` is a MAX design draft and explicitly says MAX's final identity was not confirmed. It is not a VARIOM visual authority and must not be used to override the recovered VARIOM board direction.

## 4. Simple Smart Editing — recovered exact catalogue

MAX `docs/approved-product-architecture.md` §12 and the MAX workbook decision D-25 establish six user-facing task entries:

1. Auto Captions.
2. Audio Enhancement.
3. Silence Removal.
4. Music & Rhythm.
5. Motion Graphics.
6. Additional Instructions.

Motion Graphics contains six selectable categories:

- Kinetic Typography.
- Highlights & Callouts.
- Icons & Infographics.
- Product Features.
- Shapes & Effects.
- Titles & Lower Thirds.

Multiple Motion Graphics categories may be selected in one video. Each category uses ready-made templates; the system selects, places and times suitable templates. Additional Instructions clarifies selected supported tasks; it does not authorize arbitrary new editing capabilities.

The associated MAX constraints are: no pre-export preview; no professional multi-track timeline or frame-by-frame editor; no automatic story reconstruction/new-scene generation in this tool; no complex VFX/3D or advanced cinematic grading; preserve the original and create a separate output; show per-task and total cost before explicit approval; execute selected supported operations and return one final validated video.

**VARIOM reconciliation:** the recovered catalogue is the source for the previously referenced "repository-approved Simple Smart Editing task list". Apply it only within VARIOM's narrower Simple Smart Editing scope and V2.1 S13 behavior. Do not add Logo Overlay as a seventh task. The VARIOM UI may expose only capabilities that have a verified processing path; catalogue presence is not proof of provider support or implementation.

## 5. Virtual Character — recovered source and limits

Source: `docs/virtual-character-specification.md` on branch `virtual-character-spec-v1.0-review`. The document records owner editorial acceptance dated 2026-10-30 and explicitly limits that acceptance to the product/operational contract; it does not claim application implementation, provider integration, or production approval.

The specification defines a structured character brief with:
- Intended brand role.
- Fictional/synthetic confirmation.
- Adult age presentation.
- User-directed visible appearance and visual realism.
- Wardrobe baseline and allowed variation.
- Personality, energy, mannerisms and on-camera behavior.
- Intended content contexts/channels.
- Optional language, explicitly selected dialect/register, voice direction and speech behavior.

It defines a canonical reference package that may include front, three-quarter and profile views, a neutral appearance reference, full-body/wardrobe reference, and optional expression/pose/voice references where relevant and supported.

Important safeguards include brand/account binding, owner approval, versioned identity, locked traits versus permitted variations, rights/consent for real-person likeness or voice, no synthetic-character false testimonials, and capability-gated voice/dialect/lip-sync.

**VARIOM reconciliation:** this is the strongest located source for the character contract and may inform the approved concise questionnaire and Character Sheet. However, no separate VARIOM-specific finalized questionnaire or copy-ready Character Sheet prompt was found. The MAX spec itself leaves exact UI flow and number of candidates open. Do not copy the unrelated Perwej Design real-person Character Sheet prompt from the Library; it is a separate watch-commercial workflow and does not define VARIOM's synthetic-character product.

## 6. Separate UI Design Prompt

No separate final VARIOM UI Design Prompt was found in the inspected repository branches or Library search. The V2.1 UX master specification explicitly treats it as a separate owner-supplied input and prohibits inventing missing tokens or motifs.

Therefore:
- Do not promote the 19-screen UX specification into a substitute visual prompt.
- Do not treat the MAX 2026-11-01 visual design foundation draft as the VARIOM prompt.
- Do not generate a new prompt and label it "original" or "approved".
- Final visual styling acceptance remains open until the original prompt is recovered or the owner explicitly authorizes a new replacement prompt.

## 7. Remaining owner/source inputs

| Item | Minimum action to close |
|---|---|
| Canonical identity board | Owner identifies which of the three Library images is the canonical reference, or confirms they are all non-final iterations |
| Final UI Design Prompt | Locate the original owner-authored prompt or explicitly authorize drafting a replacement |
| Character questionnaire / Character Sheet | Locate the exact approved VARIOM source, or authorize adapting the accepted MAX v1.0 contract into a concise VARIOM questionnaire and sheet |
| Verbatim V2.0 / V2.1 | Supply original files/text only if exact wording is required; current structured consolidations remain usable as the governing decision record |
| Creative library original | Recover the 2026-10-28 source or retain B-012 as an explicit source gap |

## 8. Disposition

- **Recovered:** VARIOM identity direction and token values; exact six Simple Smart Editing tasks and six Motion Graphics categories; accepted MAX Virtual Character product-contract specification.
- **Partially recovered:** visual identity board (three variants, no canonical selection); Virtual Character brief/reference requirements (no separate final VARIOM questionnaire/prompt).
- **Not recovered:** separate final UI Design Prompt; verbatim V2.0/V2.1 originals; verbatim Creative Content Intelligence Library source.
- **Not authorized:** reconstructing missing originals, selecting a canonical image on the owner's behalf, changing product scope, application implementation, provider activation, paid generation, merge or deployment.

## 9. Sources

- VARIOM Product Vision V2.0: `docs/variom-ai/00-product-vision-simplified-ux-v2.md`.
- VARIOM UX/Frontend Master Specification V2.1: `docs/variom-ai/04-ux-frontend-interface-master-spec-v2.1.md`.
- VARIOM Visual Identity Baseline: `docs/variom-ai/05-visual-identity-baseline.md`.
- MAX Smart Editing contract: `docs/approved-product-architecture.md` §12, branch `main`.
- MAX tracker decision D-25: Library file `MAX_Project_Execution_Tracker(1).xlsx`, Decisions sheet.
- MAX Virtual Character contract: `docs/virtual-character-specification.md`, branch `virtual-character-spec-v1.0-review`.
- MAX visual design draft (explicitly not VARIOM authority): `docs/VISUAL_DESIGN_SYSTEM_FOUNDATION_DRAFT_2026-11-01.md`, branch `docs/repository-safety-and-ui-roadmap-2026-11-01`.
- VARIOM identity boards: three image files in the user's ChatGPT Library, listed in §3.

**No code or MAX planning source was modified by this audit.**
