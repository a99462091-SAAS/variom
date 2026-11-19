# VARIOM — Decisions, Open Items & MAX Document Reconciliation

**Date:** 2026-11-19. **Status:** Initial reconciliation baseline.

## 1. Approved VARIOM constraints
V2.0 controls: four product systems; no Product Catalog; eight monthly goals; up to three goals (one primary, two supporting); 8/12/16 monthly posts; monthly images/videos only; no monthly carousel/platform selection; monthly video <=10 seconds; Video Studio 10/20/30 seconds; P1–P4 and V1–V4; Arabic/English RTL/LTR; real cost before execution; real credit lifecycle; automatic library save; repository-approved Simple Smart Editing only.

## 2. MAX document treatment
| MAX source | VARIOM action |
|---|---|
| approved-product-architecture.md | Rebuild as VARIOM architecture; preserve original |
| system-specification.md | Rebuild aligned to V2.0; preserve original |
| implementation-roadmap.md | Rebuild from actual VARIOM baseline; no old phases/status |
| project-tracker.md | New tracker; do not inherit MAX statuses/percentages |
| library-design.md | Reconcile taxonomy/records; old category meanings are not authoritative |
| claude-code-rules.md | Adapt to VARIOM source hierarchy and exclusions |
| CLAUDE.md / README.md | Root updates deferred until documentation branch review |
| p1-reference-audit.md | Historical evidence; recheck mapping/rights |
| p1-visual-shot-analysis-pilot.md | Reusable review method; historical examples |
| creative-content-intelligence-library-source-needed.md | Preserve evidence of missing verbatim MAX library source |
| decision-id-reconciliation.md | Historical only |
| phase-0-repository-audit-task.md | Historical task, not a VARIOM task |
| claude-code-start-prompt.md | Historical MAX prompt |
| MAX planning report/workbook verify log | Historical only |
| MAX execution workbook (.xlsx) | Remains on main; missing from this documentation branch pending binary-preservation resolution |

## 3. Product conflicts
- MAX excluded monthly content calendar; VARIOM approves monthly content generation, not a calendar/scheduler.
- MAX P1/P4 and V4 definitions differ; use VARIOM definitions.
- MAX historical 40-second duration is not valid for VARIOM Video Studio.
- Monthly video is capped at 10 seconds.
- Do not impose mandatory user storyboard approval; Master Storyboard is internal and scene review is optional.
- MAX projects/collections do not authorize VARIOM collections/projects.
- MAX subscription/payment assumptions do not authorize billing UI or invented prices.
- Earlier suggestion of 9 primary + 15 More Tools is not a final navigation decision.

## 4. Legacy capability mapping
| Legacy feature | Candidate VARIOM mapping | Constraint |
|---|---|---|
| Static Ads | P2 Static Ad | Verify actual output |
| Carousel | P3 Carousel | Image Studio only, not Monthly Content |
| Product Photoshoot | P1/P4 | Map by semantics |
| Ad Scripts | Copywriting Intelligence | Internal capability |
| UGC | V1 | Distinguish scripted/synthetic from genuine testimony |
| Motion Graphics | V3 | Verify behavior |
| Video Studio | Video Production | No AI claims without real AI video provider |
| Video Editor | Smart Editing | Only approved repository task list |
| Logo tool | Brand Assets | Not a standalone primary tool by default |
| Lead Magnet, Trend Finder, Reels Planner, Swap, Speech Edit | Deferred/legacy | Preserve code; no VARIOM V1 UX assumption |

## 5. Open items
- Verify exact approved Simple Smart Editing list in the current local repository.
- Obtain/locate separate final UI Design Prompt and original visual identity image.
- Obtain approved Virtual Character questionnaire and Character Sheet.
- Map existing routes/tools to VARIOM workflows.
- Reconcile creative JSON/schema records with VARIOM categories.
- Verify real provider states and AI capabilities.
- Reconcile documentation against Claude's current local audit.
- Review whether root CLAUDE.md and README.md should be updated.

## 6. Authority
This reconciliation does not authorize provider activation, billing, migrations, destructive cleanup, deployment, or implementation of the 19-screen UX. Owner review is required before merge or execution.


## 7. Detailed migration inventory
The document-by-document classification and creative-asset migration rules are maintained in [10 — MAX Source & Creative Asset Migration Inventory](10-max-source-and-creative-asset-migration-inventory.md). It is the detailed companion to this summary.

Important distinctions:
- The MAX P1–P4 and V1–V4 labels do not prove semantic equivalence. In particular MAX V4 (Commercial / Advertising Video) materially differs from VARIOM V4 (Story / Testimonial).
- MAX P1 Product Photography and VARIOM P1 Product Showcase are related but require record-level mapping.
- Existing JSON, schemas, visual references and tests remain at their original paths and are not approved for bulk import.
- The historical MAX workbook and its decision IDs/statuses are not VARIOM planning truth.
- The detailed owner-supplied creative-library specification from 2026-10-28 remains a missing verbatim source; the current VARIOM library document is not a verbatim replacement.

## 8. Scope of this audit
This documentation pass reviewed archived Markdown sources and their documented asset inventory. It did not parse the underlying JSON/schema/workbook/visual files or execute repository tests. Their contents, hashes, current branch availability and runtime behavior remain unverified. A separate read-only asset inventory is required before any migration.


## 9. Creative-style ID mapping proposal
A first-pass mapping for all 144 MAX style IDs is documented in [11 — Creative Style ID Mapping Proposal](11-creative-style-id-mapping-proposal.md). It is a semantic proposal based on names/short definitions and historical audits, not an owner-approved import manifest. It explicitly flags the P3-013…P3-018 and V2-016/V2-017 owner decisions and rejects direct MAX V4 → VARIOM V4 carry-over.


## 10. Root VARIOM.md reconciliation
The root VARIOM.md is a working transformation baseline and useful context, but it is not a substitute for the controlling V2.0/V2.1 source documents. The updated [10 — MAX Source Audit and Adoption Matrix](10-max-source-audit-and-adoption-matrix.md) records its conflicts: the 9+15 navigation proposal, unresolved category definitions, old video-duration discrepancy, older plan naming, and dated CREWZO implementation observations. Do not implement those statements without reconciliation against current owner-approved decisions.
