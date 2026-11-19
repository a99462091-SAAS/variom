# VARIOM — UX Interaction & Content Contract

**Version:** 1.0 | **Status:** NORMATIVE DRAFT — subordinate to Product Vision V2.0 and UX V2.1 | **Authority:** Documents 19–28; owner-supplied UI prompt and identity image remain direct inputs to Claude Code.

## 1. Purpose and boundaries
Defines shared interaction rules and field-level behavior needed for consistent implementation. It does not recreate the owner-supplied UI Design Prompt, invent visual tokens, or replace the identity image. Owner will provide both directly to Claude Code.

## 2. Global shell
- Show authenticated account context, accessible brand selector, active brand, real available credit balance where supported, Arabic/English switch and account menu.
- Brand selector lists only brands the account may access.
- Do not show subscription/plan state or fake limits.
- Keep navigation limited to the 19 approved screens and embedded interactions.
- Desktop and mobile layouts are required; exact breakpoints are selected during implementation and validated against owner-provided design input.
- RTL/LTR direction must be structural, not a simple text alignment toggle.

## 3. Shared interaction contract
Every interactive element defines:
- label and purpose;
- initial/default value (only where product-approved);
- required/optional status;
- validation and error message;
- disabled/loading/success/failure state;
- keyboard, focus and touch behavior;
- persistence/autosave behavior where approved;
- authorization and backend dependency;
- RTL/LTR behavior.

No control may display success before the backend confirms persistence. Unknown or unsupported values are omitted or clearly unavailable, never guessed.

## 4. Screen interaction matrix
| Screen | Required interaction and constraints |
|---|---|
| S01 Authentication | Email/password; verify email; recover password by email; no default social login; no fake success |
| S02 Initial Brand Profile | Brand name, activity, audience required; logo optional; reuse supplied answers |
| S03 Brand DNA Setup | Prefill known facts; concise guided fields; optional sections skip/edit/save; Brand Voice, Visual Identity, Brand Assets; no Product Catalog |
| S04 Dashboard | Accessible brands, active brand, actual credits/usage where available, primary actions, real recent library items only |
| S05 Monthly Content | 8/12/16 posts; up to 3 goals (1 primary); up to 10 manual product photos; optional price per image and character; smart image/video distribution; no carousel/platform selection; actual quote; monthly video <=10 sec |
| S06 Template Review | Optional; show type, clearly illustrative reference, idea and copy/dialogue; only idea/copy editable; skip path available |
| S07 Progress | One progress indicator; completed/total; stages Planning, Content Preparation, Generation, Final Quality Check; derive from persisted task/item state |
| S08 Results | View/open/download only; completed outputs saved automatically; no publish/schedule/approve/ZIP/analytics |
| S09 Image Studio | P1–P4; one/five ideas; manual product image; optional price/character; Instagram Portrait/Landscape; internal style; quote before generation |
| S10 Image Ideas | Embedded interaction in Image Studio; distinguish suggestion from generation; no assumed charge |
| S11 Video Studio | V1–V4; one/five ideas; manual product image; optional character; 10/20/30 sec; Reels Portrait/Landscape; mandatory internal storyboard; no separate audio controls |
| S12 Storyboard Review | Optional; scene description and dialogue/text only; no exposed orchestration/technical controls |
| S13 Smart Editing | Simple task-based interface; only six approved tasks and supported motion categories; preserve source; no timeline editor |
| S14 Library | Image/video/monthly content; type/date filter; grid/open/preview/download; no projects/collections/approvals/ZIP |
| S15 Content Detail | Real asset and available metadata; authorized private preview/download |
| S16 Virtual Character | VARIOM questionnaire/Character Sheet; create/save/edit/reuse; version identity; capability-gated voice options |
| S17 Brand DNA Management | Edit approved DNA and Brand Assets; preserve versions; no Product Catalog |
| S18 Brand Management | Show/switch/manage only authorized brands; no inferred plan enforcement |
| S19 Settings | Language, account and supported preferences only; no nonfunctional billing/integration controls |

## 5. Form and validation principles
- Ask only for information required for the current task; reuse known account/brand facts.
- Clearly distinguish required, optional and conditionally required fields.
- Validate at the point of entry and again server-side.
- Preserve valid user input after recoverable errors.
- Do not force users to write professional prompts or marketing copy; use guided choices and internal intelligence.
- Product-level enum choices must exactly match V2.0. Provider-specific constraints are added only after evidence.

## 6. Content and status language
- Label reference images as illustrative references.
- Label preview/mock output explicitly; never style it as a real generated asset.
- Progress/success/failure messages reflect persisted backend states.
- Explain partial completion at item level; never mark failed items as complete.
- Show actual quote and applicable unit before confirmation; no placeholder price presented as live.
- Explain unavailable provider capability without implying user error.

## 7. Arabic/English and accessibility
- All user-facing flows support Arabic and English.
- Direction, layout order, icons, numeric treatment, mixed-language text and focus order must be checked in both directions.
- Provide semantic labels, visible focus, keyboard navigation, touch target usability, contrast and non-color status indicators.
- Error messages are associated with their fields and announced appropriately.
- Avoid embedding directional assumptions in icons or component ordering.

## 8. Owner-supplied visual inputs
The owner supplies the latest refined identity image and UI Design Prompt directly to Claude Code. This contract does not reconstruct either. Visual styling, tokens, component appearance and motifs must be taken from those owner inputs; conflicts with product behavior are resolved in favor of Documents 00/20.

## 9. Acceptance criteria
- All 19 screens follow the matrix without scope expansion.
- Required/optional fields and states are defined.
- Arabic/English RTL/LTR and accessibility are validated.
- No unsupported control, fake success, fake balance or fake output.
- Owner visual inputs are used as supplied and not replaced.
