# VARIOM — MAX Creative Style ID Mapping (First-Pass Proposal)

**Date:** 2026-11-19  
**Status:** Proposed semantic mapping only — not owner-approved, not a production import manifest.  
**Source:** 144 MAX detailed records on branch creative-library-review-completion. This pass used each record's ID, bilingual name and short definition, together with the MAX quality/product-decision audit. It did not re-review every nested prompt, asset, reference and production field.

## 1. How to read this proposal

- **KEEP CONCEPT + ADAPT:** the creative idea is compatible with a VARIOM category, but its detailed record, terminology, UX use and constraints must be rewritten/revalidated.
- **RECLASSIFY:** the concept may be useful, but its current MAX category is not the right VARIOM home.
- **OWNER DECISION:** a known product-level conflict cannot be resolved by editorial judgment.
- **HOLD / CAPABILITY CHECK:** retain as a candidate, but do not expose or implement until technical feasibility, factual requirements or rights are verified.
- **DO NOT BULK IMPORT:** no source JSON record is production-approved; this is a migration rule applying to all 144 records.

VARIOM category meanings govern. MAX IDs may be retained only as historical aliases after a record is accepted. Do not preserve a MAX ID if its meaning changes; assign a new VARIOM ID and keep an explicit alias mapping.

## 2. P1 — MAX Product Photography → VARIOM P1 Product Showcase

**Category-level recommendation:** KEEP CONCEPT + ADAPT. These styles mostly describe ways to present a product and are broadly compatible with Product Showcase. They are not approved as-is.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| P1-001 | Clean Studio Product Photography | KEEP CONCEPT + ADAPT | Preserve accurate product appearance and clean presentation |
| P1-002 | Custom Color Background | KEEP CONCEPT + ADAPT | Brand/product color fidelity; avoid color shifts |
| P1-003 | Category-Relevant Background | ADAPT / POSSIBLE RECLASSIFICATION | Use only when background context remains subordinate to product; otherwise P4 |
| P1-004 | Dramatic Light and Shadow | KEEP CONCEPT + ADAPT | Do not lose important product details or imply material properties |
| P1-005 | Macro Detail Photography | KEEP CONCEPT + ADAPT | Detail must exist in supplied product reference |
| P1-006 | Styled Product Still Life | KEEP CONCEPT + ADAPT | Props must not imply unverified ingredients, benefits or use |
| P1-007 | Product Assortment | KEEP CONCEPT + ADAPT | Product set and variants must be confirmed; no catalog dependency |
| P1-008 | Product Variants | KEEP CONCEPT + ADAPT | Show only supplied/confirmed variants |
| P1-009 | Top-Down Product Photography | KEEP CONCEPT + ADAPT | Use when overhead angle explains form/layout |
| P1-010 | Side or Low-Angle Product Photography | KEEP CONCEPT + ADAPT | Preserve proportions and avoid misleading perspective |
| P1-011 | Material and Finish Detail | KEEP CONCEPT + ADAPT | Do not invent or alter material/finish |
| P1-012 | Scale and Size Context | HOLD / FACT CHECK | Requires verified dimensions or trustworthy scale reference |
| P1-013 | Packaged Product Photography | KEEP CONCEPT + ADAPT | Preserve actual package, label and required legal text |
| P1-014 | Ingredient or Component Layout | HOLD / FACT CHECK | Only verified ingredients/components; no inferred formulation |
| P1-015 | Dynamic Product Composition | KEEP CONCEPT + ADAPT | New composition; do not copy reference campaign |
| P1-016 | Premium Luxury Product Photography | KEEP CONCEPT + ADAPT | Visual tone only; never imply unverified quality/status |
| P1-017 | Minimal Negative-Space Product Shot | KEEP CONCEPT + ADAPT | Retain text-safe area for later composition |
| P1-018 | Composited Product Scene | HOLD / CAPABILITY CHECK | Require product fidelity, compositing feasibility and asset provenance |

## 3. P2 — MAX Static Advertising Creative → VARIOM P2 Static Ad

**Category-level recommendation:** KEEP CONCEPT + ADAPT. The concepts are close to the VARIOM category. All claims, offers, comparisons and proof elements need validation.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| P2-001 | Single-Benefit Ad | KEEP CONCEPT + ADAPT | Benefit must be confirmed |
| P2-002 | Headline-Led Ad | KEEP CONCEPT + ADAPT | Approved copy and text composition |
| P2-003 | Problem-Solution Ad | KEEP CONCEPT + ADAPT | Do not promise unsupported outcomes |
| P2-004 | Price or Discount Offer | HOLD / FACT CHECK | Current price, discount and terms must be supplied/verified |
| P2-005 | Product Launch Creative | KEEP CONCEPT + ADAPT | Launch status and product facts must be true |
| P2-006 | Comparison Ad | HOLD / FACT CHECK | Fair, like-for-like, supportable comparison only |
| P2-007 | Feature List Ad | KEEP CONCEPT + ADAPT | Features must be confirmed |
| P2-008 | Differentiator-Led Ad | HOLD / FACT CHECK | Competitive difference needs evidence |
| P2-009 | Evidence-Led Ad | HOLD / SOURCE REQUIRED | Claims and cited evidence must be traceable |
| P2-010 | Verified Customer Testimonial Creative | HOLD / CONSENT REQUIRED | Real customer statement, permission and truthful context |
| P2-011 | Seasonal Promotional Ad | KEEP CONCEPT + ADAPT | Occasion and offer must be relevant/current |
| P2-012 | Justified Urgency Ad | HOLD / FACT CHECK | Real deadline/stock limitation only; no fabricated scarcity |
| P2-013 | Verified Guarantee or Service Ad | HOLD / FACT CHECK | Exact terms and exclusions must be confirmed |
| P2-014 | Product with Callouts | KEEP CONCEPT + ADAPT | Callouts identify only visible/verified features |
| P2-015 | Editorial Informational Ad | KEEP CONCEPT + ADAPT | Preserve hierarchy and concise information |
| P2-016 | Abstract Conceptual Ad | KEEP CONCEPT + ADAPT | Metaphor must remain understandable and non-misleading |
| P2-017 | Single-Element Minimal Ad | KEEP CONCEPT + ADAPT | Preserve legibility and brand/product identity |
| P2-018 | Multi-Product Offer Ad | HOLD / FACT CHECK | Confirm products, bundle, price and offer terms |

## 4. P3 — MAX Carousel Content → VARIOM P3 Carousel

**Category-level recommendation:** KEEP CONCEPT + ADAPT for Image Studio only. P3 is not allowed in Monthly Content. The six records P3-013 through P3-018 are an explicit OWNER DECISION because the historical record documents conflicting canonical mappings.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| P3-001 | Step-by-Step Carousel | KEEP CONCEPT + ADAPT | Ordered actionable steps |
| P3-002 | Multi-Angle Product Explainer | KEEP CONCEPT + ADAPT | Product facts and slide roles must be clear |
| P3-003 | Product Collection Carousel | KEEP CONCEPT + ADAPT | Collection must be supplied/confirmed |
| P3-004 | Options Comparison Carousel | HOLD / FACT CHECK | Comparable options and criteria |
| P3-005 | Practical Tips Carousel | KEEP CONCEPT + ADAPT | Advice must be accurate and useful |
| P3-006 | Problem-Solution Carousel | KEEP CONCEPT + ADAPT | Supported problem/solution claims |
| P3-007 | Sequential Story Carousel | KEEP CONCEPT + ADAPT | Coherent narrative continuity |
| P3-008 | Progressive Reveal Carousel | KEEP CONCEPT + ADAPT | Reveal must add meaningful information |
| P3-009 | Process Stages Carousel | KEEP CONCEPT + ADAPT | Accurate phases; distinguish from how-to steps |
| P3-010 | Verified Before-and-After Carousel | HOLD / EVIDENCE REQUIRED | Same conditions/context; substantiated and non-misleading |
| P3-011 | FAQ Carousel | KEEP CONCEPT + ADAPT | Answers grounded in verified brand/product info |
| P3-012 | Product Selection Guide Carousel | KEEP CONCEPT + ADAPT | Criteria must be accurate; no fake catalog |
| P3-013 | Benefits and Specifications Carousel | OWNER DECISION | Conflicts with prior approved mapping for this stable ID |
| P3-014 | Evidence-Based Case Study Carousel | OWNER DECISION | Conflicts with prior approved mapping for this stable ID |
| P3-015 | Sequential Conversion Carousel | OWNER DECISION | Conflicts with prior approved mapping for this stable ID |
| P3-016 | Myth and Fact Carousel | OWNER DECISION | Conflicts with prior approved mapping for this stable ID |
| P3-017 | Usage and Care Guide Carousel | OWNER DECISION | Conflicts with prior approved mapping for this stable ID |
| P3-018 | Brand Story or Behind-the-Scenes Carousel | OWNER DECISION | Conflicts with prior approved mapping for this stable ID |

**P3 owner-decision record:** previous mapping says P3-013 documented case study; P3-014 sequential sales; P3-015 new product/feature reveal; P3-016 educational awareness; P3-017 myth/fact; P3-018 usage/care guide. Current cards/inventory instead say benefits/specifications; case study; sequential conversion; myth/fact; usage/care; brand story. Do not change IDs or choose a side until the owner confirms.

## 5. P4 — MAX Lifestyle & Contextual Photography → VARIOM P4 Lifestyle

**Category-level recommendation:** KEEP CONCEPT + ADAPT. The context must materially support the idea; a person or attractive background alone is not enough.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| P4-001 | Natural Use Environment | KEEP CONCEPT + ADAPT | Context must be plausible and relevant |
| P4-002 | In-Use Lifestyle Photography | KEEP CONCEPT + ADAPT | Show correct use |
| P4-003 | Everyday Need Scenario | KEEP CONCEPT + ADAPT | Avoid fabricated problem/benefit claims |
| P4-004 | Indoor or Outdoor Context | KEEP CONCEPT + ADAPT | Environment must serve the message |
| P4-005 | Product-Related Lifestyle | KEEP CONCEPT + ADAPT | Avoid stereotypes or unsupported lifestyle claims |
| P4-006 | Product Impact in Context | HOLD / EVIDENCE REQUIRED | Only visible, supportable impact |
| P4-007 | Person with Product | KEEP CONCEPT + ADAPT | Accurate use and appropriate representation |
| P4-008 | Professional Use Context | KEEP CONCEPT + ADAPT | Do not imply credentials/endorsement |
| P4-009 | Home Environment | KEEP CONCEPT + ADAPT | Plausible product/home setting |
| P4-010 | Full Experience Context | KEEP CONCEPT + ADAPT | All depicted experience elements are grounded |
| P4-011 | Contextual Before-and-After | HOLD / EVIDENCE REQUIRED | Same context and conditions; no misleading transformation |
| P4-012 | Seasonal Lifestyle Context | KEEP CONCEPT + ADAPT | Real seasonal relevance |
| P4-013 | Audience-Relevant Context | KEEP CONCEPT + ADAPT | No unsupported demographic assumptions |
| P4-014 | Group Use Context | KEEP CONCEPT + ADAPT | Group usage must be plausible and accurate |
| P4-015 | Unboxing in Context | KEEP CONCEPT + ADAPT | Actual contents and packaging |
| P4-016 | Routine-in-Context | KEEP CONCEPT + ADAPT | Accurate sequence; distinguish from single use |
| P4-017 | Local Cultural Context | HOLD / HUMAN REVIEW | Avoid stereotypes; verify cultural details and locale |
| P4-018 | Workplace Context | KEEP CONCEPT + ADAPT | Keep distinct from professional task/expertise context |

## 6. V1 — MAX Creator-Led / UGC-Style Video → VARIOM V1 UGC

**Category-level recommendation:** KEEP CONCEPT + ADAPT. Truthful disclosure is a hard requirement. Real testimonial, paid creator, actor and synthetic performance must never be conflated.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| V1-001 | First-Person Product Experience | HOLD / TRUTH CHECK | Genuine first-person experience only when represented as real |
| V1-002 | Product Review | KEEP CONCEPT + ADAPT | Disclose basis/source of review; do not fabricate user experience |
| V1-003 | Verified User Testimonial | HOLD / CONSENT REQUIRED | Actual user, original statement, explicit permission |
| V1-004 | Paid Creator Content | KEEP CONCEPT + ADAPT | Clear paid/sponsored disclosure as required |
| V1-005 | Unboxing and First Impression | KEEP CONCEPT + ADAPT | Real contents; do not fake spontaneity as genuine |
| V1-006 | FAQ Creator Answer | KEEP CONCEPT + ADAPT | Verified answer, not invented authority |
| V1-007 | Objection Response | KEEP CONCEPT + ADAPT | Address a real objection with substantiated information |
| V1-008 | Creator-Led Product Use | KEEP CONCEPT + ADAPT | Clearly label scripted/synthetic performance when needed |
| V1-009 | Day-in-the-Life Scenario | KEEP CONCEPT + ADAPT | Do not imply actual customer routine if staged |
| V1-010 | Direct-to-Camera Talk | KEEP CONCEPT + ADAPT | Accurate presenter identity and claims |
| V1-011 | First-Person POV Narrative | KEEP CONCEPT + ADAPT | Distinguish fictional POV from real testimony |
| V1-012 | Reasons or Benefits List | KEEP CONCEPT + ADAPT | Every reason/benefit grounded |
| V1-013 | Question-and-Answer Video | KEEP CONCEPT + ADAPT | Answers grounded in approved information |
| V1-014 | Creator-Led Comparison | HOLD / FACT CHECK | Fair, consistent comparison |
| V1-015 | Naturalistic Skit | KEEP CONCEPT + ADAPT | Clearly a scenario/acting, not a customer testimonial |
| V1-016 | User-POV Scenario | KEEP CONCEPT + ADAPT | Fictional/user POV must not imply a real user |
| V1-017 | Staff or Expert Explainer | HOLD / CREDENTIAL CHECK | Confirm role/credentials; no fabricated expertise |
| V1-018 | Verifiable Reaction | HOLD / CONSENT REQUIRED | Real reaction, provenance and permission |

## 7. V2 — MAX Product Showcase / Demonstration → VARIOM V2 Product Demo

**Category-level recommendation:** KEEP CONCEPT + ADAPT. These concepts align closely with product demonstration. Provider capability, product fidelity and duration constraints must be rechecked.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| V2-001 | Multi-Angle Product Showcase | KEEP CONCEPT + ADAPT | Real product views and continuity |
| V2-002 | Product Detail Close-Ups | KEEP CONCEPT + ADAPT | Preserve details from references |
| V2-003 | How-to Demonstration | KEEP CONCEPT + ADAPT | Correct instructions and sequence |
| V2-004 | Product in Operation | HOLD / CAPABILITY CHECK | Show only operation that can be accurately represented |
| V2-005 | Installation Steps | HOLD / FACT CHECK | Manufacturer-approved steps and safety |
| V2-006 | Single-Feature Demonstration | KEEP CONCEPT + ADAPT | Feature must be observable and confirmed |
| V2-007 | Multiple-Feature Showcase | KEEP CONCEPT + ADAPT | Prioritize; avoid feature overload |
| V2-008 | Practical Comparison Demo | HOLD / FACT CHECK | Fair test and comparable conditions |
| V2-009 | Before-and-After Demonstration | HOLD / EVIDENCE REQUIRED | Genuine transformation, consistent conditions |
| V2-010 | Unboxing and Contents | KEEP CONCEPT + ADAPT | Contents match actual package |
| V2-011 | Product Range Showcase | KEEP CONCEPT + ADAPT | Variants supplied/confirmed |
| V2-012 | Product Use Context | KEEP CONCEPT + ADAPT | Keep product operation central; if context dominates, assess V1/V4 |
| V2-013 | Scale and Dimensions Demo | HOLD / FACT CHECK | Verified measurements/reference scale |
| V2-014 | Materials and Finish Showcase | KEEP CONCEPT + ADAPT | Do not invent materials/finish |
| V2-015 | Planned Camera-Movement Showcase | HOLD / CAPABILITY CHECK | Actual model supports the required camera movement |
| V2-016 | Voice-Over Product Demo | OWNER DECISION | Could be a production modifier, not a standalone style |
| V2-017 | On-Screen Annotation Demo | OWNER DECISION | Could be a production modifier, not a standalone style |
| V2-018 | Rapid Product Detail Reel | KEEP CONCEPT + ADAPT | Pacing must remain legible and fit VARIOM duration limits |

## 8. V3 — MAX Motion Graphics / Animation → VARIOM V3 Motion Graphics

**Category-level recommendation:** KEEP CONCEPT + ADAPT, with selective HOLD for advanced production requirements. Do not promise 3D, simulation, or complex animation until a real provider/tool path is verified.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| V3-001 | Animated Typography | KEEP CONCEPT + ADAPT | Arabic/English text rendered accurately |
| V3-002 | Animated Infographic | KEEP CONCEPT + ADAPT | Data and labels verified |
| V3-003 | Animated Illustrations | KEEP CONCEPT + ADAPT | Illustration supports a clear explanation |
| V3-004 | Animated Icons | KEEP CONCEPT + ADAPT | Consistent icon style and legibility |
| V3-005 | 2D Animation | HOLD / CAPABILITY CHECK | Verify achievable quality, complexity and cost |
| V3-006 | 3D Animation | HOLD / CAPABILITY CHECK | Do not assume 3D production support |
| V3-007 | 3D Product Visualization | HOLD / CAPABILITY + ASSET CHECK | Requires accurate 3D model or validated product reference |
| V3-008 | Mechanism Simulation | HOLD / TECHNICAL FACT CHECK | Simulation must not misrepresent actual mechanism |
| V3-009 | Data Story Motion Graphics | KEEP CONCEPT + ADAPT | Source, context and figures must be traceable |
| V3-010 | Animated Step-by-Step Explainer | KEEP CONCEPT + ADAPT | Accurate steps; avoid duplication with V2 how-to |
| V3-011 | Motion from Still Images | HOLD / CAPABILITY CHECK | No false claim that generated motion is real footage |
| V3-012 | Live Action with Motion Overlays | KEEP CONCEPT + ADAPT | Separate real footage from overlays; protect subject legibility |
| V3-013 | Product-Shape Transitions | HOLD / CAPABILITY CHECK | Product silhouette and continuity must remain accurate |
| V3-014 | Animated Comparison | HOLD / FACT CHECK | Consistent scale, data and fair comparison |
| V3-015 | Graphic Explainer Video | KEEP CONCEPT + ADAPT | Keep information hierarchy simple |
| V3-016 | Kinetic Typography | KEEP CONCEPT + ADAPT | Arabic shaping/RTL and timing verified |
| V3-017 | Complex-Concept Animation | HOLD / CAPABILITY CHECK | Limit scope to feasible, factually correct explanation |
| V3-018 | Message-Led Abstract Motion | KEEP CONCEPT + ADAPT | Abstract motion must clarify rather than obscure the message |

## 9. V4 — MAX Commercial / Advertising Video → VARIOM V4 Story / Testimonial

**Category-level recommendation:** RECLASSIFY ALL 18 RECORDS BEFORE MIGRATION. MAX V4 is an advertising/commercial category; VARIOM V4 is story/testimonial. A sales objective or commercial finish does not make a concept a story or testimonial.

| MAX ID | Style | Proposed treatment | Main condition |
|---|---|---|---|
| V4-001 | Problem-Solution Commercial | RECLASSIFY | Likely V2/V1 or narrative only if a real story is central |
| V4-002 | Hero Benefit Commercial | RECLASSIFY | Usually message/creative direction, not automatically story/testimonial |
| V4-003 | Cinematic Commercial | RECLASSIFY / HOLD | Cinematic treatment is a production modifier unless narrative is central |
| V4-004 | Offer-Led Commercial | RECLASSIFY | Offer-led creative is not automatically V4 Story/Testimonial |
| V4-005 | Product Launch Film | RECLASSIFY | Could fit V2 or narrative depending on actual structure |
| V4-006 | Transformation Commercial | HOLD / RECLASSIFY | Requires substantiated transformation; narrative fit must be assessed |
| V4-007 | Comparative Commercial | RECLASSIFY | Comparison structure, not automatically a story |
| V4-008 | Emotional Story Commercial | CANDIDATE V4 — ADAPT | Story-led structure may fit; remove generic commercial assumption |
| V4-009 | Reveal-Based Commercial | RECLASSIFY / HOLD | Reveal is a narrative device, not necessarily a story |
| V4-010 | Single-Scene Commercial | RECLASSIFY / HOLD | Single scene alone does not establish story/testimonial |
| V4-011 | Short Narrative Commercial | CANDIDATE V4 — ADAPT | Narrative is central; validate whether testimonial is involved |
| V4-012 | Differentiator-Led Commercial | RECLASSIFY | A differentiator-led message may fit V2/P2 concepts, not automatically V4 |
| V4-013 | Craft and Detail Commercial | RECLASSIFY | Usually product demonstration/detail, likely V2 |
| V4-014 | Signature Visual Concept Commercial | RECLASSIFY / HOLD | Visual signature is a treatment, not story content |
| V4-015 | Seasonal Commercial | RECLASSIFY | Seasonal is an objective/context modifier, not a story category |
| V4-016 | Live Action and Motion Hybrid | RECLASSIFY | Likely V3 production treatment unless story is central |
| V4-017 | Multi-Scene Commercial | CANDIDATE V4 — ADAPT | May fit when scenes form a coherent story arc |
| V4-018 | Offer/CTA-Ending Commercial | RECLASSIFY | CTA ending is a copy/structure modifier, not a story style |

Only V4-008, V4-011 and V4-017 are preliminary candidates for V4 Story; none is approved by this mapping. No MAX V4 record is a testimonial unless a genuine, verified testimonial is actually present and consented to.

## 10. Overall migration disposition

| MAX category | Records | First-pass disposition |
|---|---:|---|
| P1 | 18 | Retain concepts; adapt to Product Showcase and verify product fidelity |
| P2 | 18 | Retain concepts; adapt claims, offers, evidence and text layout |
| P3 | 18 | Retain as Image Studio Carousel candidates only; six IDs need owner decision |
| P4 | 18 | Retain concepts; adapt context and factual/representation constraints |
| V1 | 18 | Retain concepts; enforce real vs scripted/synthetic/paid distinctions |
| V2 | 18 | Retain concepts; two IDs need owner decision on style vs modifier |
| V3 | 18 | Retain concepts selectively; verify advanced production capability |
| V4 | 18 | No direct category carry-over; reclassify by actual narrative/content role |
| **Total** | **144** | **0 production imports authorized** |

## 11. Required decisions and checks before an import manifest

1. Owner resolves P3-013…P3-018 canonical meanings.
2. Owner decides whether V2-016 and V2-017 are styles or production modifiers.
3. VARIOM V4 definition is treated as authoritative; each MAX V4 candidate is reclassified individually.
4. Approve the final VARIOM creative-style schema and stable-ID/alias policy.
5. Review detailed records, source references, rights and feasibility; the mapping above is not a substitute for field-level QA.
6. Build representative VARIOM selection cases for all eight categories; the historical file contains only five P1 manual cases.
7. Keep all imported records in candidate/review state until owner acceptance.

**No source JSON was changed, no data was copied into application paths, and no production record was approved by this proposal.**
