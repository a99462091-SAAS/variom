# VARIOM — MAX Source Audit and Adoption Matrix

**Updated:** 2026-11-19  
**Status:** Read-only repository/source audit; first-pass adoption guidance. No product implementation or data import authorized.

## 1. Executive decision

MAX is a source of reusable product reasoning, engineering patterns and creative-style candidates—not a drop-in VARIOM specification.

- VARIOM Product Vision V2.0 remains the controlling product authority.
- VARIOM UX/Frontend V2.1 remains subordinate to V2.0.
- Reuse only compatible principles; rewrite MAX product/system/roadmap documents against VARIOM.
- Preserve MAX decisions, workbook and planning status as historical evidence, not current VARIOM authority.
- Treat all MAX creative styles as candidates until their semantics, factual claims, references, rights, schema and production feasibility are checked.
- Do not bulk-import or promote any MAX style record to production.

Detailed source inventory: [10 — MAX Source & Creative Asset Migration Inventory](10-max-source-and-creative-asset-migration-inventory.md).  
All 144 style-ID dispositions: [11 — Creative Style ID Mapping Proposal](11-creative-style-id-mapping-proposal.md).

## 2. Authority and conflict rules

1. VARIOM Product Vision V2.0 controls product scope and decisions.
2. VARIOM UX/Frontend Master Specification V2.1 controls screen behavior but cannot expand V2.0.
3. The separate owner-supplied UI Design Prompt and original identity image remain required for final visual acceptance.
4. Current repository code, APIs, schemas, tests and runtime evidence determine what is implemented.
5. MAX documents and data are historical/source material only unless an explicit bounded reuse is approved.
6. When MAX conflicts with VARIOM, VARIOM wins. Do not blend conflicting definitions silently.

## 3. MAX document adoption matrix

| Source document | Disposition | Reusable substance / action |
|---|---|---|
| VARIOM.md (root working transformation baseline) | KEEP AS WORKING CONTEXT + RECONCILE | Useful identity, preservation and audit context, but subordinate to the owner-approved V2.0/V2.1 source set. Resolve the explicit conflicts listed below before execution. Do not silently treat every statement in this working baseline as approved.
| README.md | HISTORICAL / ADAPT | Keep MAX history separate; use VARIOM documentation hub for current product |
| CLAUDE.md | ADAPT | Reuse execution discipline only after replacing MAX authority and scope rules with VARIOM rules |
| docs/approved-product-architecture.md | REBUILD | Reuse truthfulness, Brand DNA, selective execution, cost separation, idempotency, recovery, versioning, rights and isolation; rebuild product architecture as four logical VARIOM systems |
| docs/system-specification.md | REBUILD | Re-author from VARIOM V2.0/V2.1; do not inherit MAX workflows or capability assumptions |
| docs/implementation-roadmap.md | HISTORICAL + ADAPT | Reuse bounded gates and dependency discipline; do not import phases, percentages or statuses |
| docs/project-tracker.md | HISTORICAL ONLY | Do not inherit MAX tasks, status, percentages or acceptance |
| docs/library-design.md | ADAPT | Reuse category-vs-objective separation, selection principles, evidence, rights, prompt construction and quality gates |
| docs/claude-code-rules.md | ADAPT | Reuse scope control, pre-edit inspection, targeted checks and concise reporting |
| docs/claude-code-start-prompt.md | HISTORICAL ONLY | One-off MAX startup prompt; do not reuse |
| docs/creative-content-intelligence-library-source-needed.md | HISTORICAL EVIDENCE | Records missing verbatim 2026-10-28 source; this source remains unrecovered |
| docs/decision-id-reconciliation.md | HISTORICAL ONLY | MAX workbook decision IDs have no VARIOM authority |
| docs/p1-reference-audit.md | METHOD REUSE | Reuse reference/rights review method; recheck all source links and rights |
| docs/p1-visual-shot-analysis-pilot.md | METHOD REUSE | Reuse observation/analysis method only, not category decisions |
| docs/phase-0-repository-audit-task.md | HISTORICAL ONLY | Old repository findings are not current |
| docs/MAX_Planning_Update_Report.md | HISTORICAL ONLY | 2026-10-31 planning snapshot; no VARIOM status authority |
| docs/MAX_Workbook_Verify_Log.txt | HISTORICAL EVIDENCE | Verifies historical workbook only; not VARIOM software or project state |
| docs/MAX_Project_Execution_Tracker.xlsx | HISTORICAL ONLY | Remains on main; not present in this documentation branch and not duplicated into VARIOM |

## 4. Important branch distinction in MAX creative assets

There are two different source states. They must not be conflated.

### MAX main branch

Read-only inspection found:
- data/taxonomy.json: v1.0.0, status approved_baseline (for MAX only).
- data/style-inventory.json: 144 candidate entries, 18 per category; all inventory_status=planned_for_full_record; only 19 rows report full_record_exists=true.
- data/styles.p1.json: 18 records, all status=draft.
- data/styles.seed.json: 2 draft seed examples.
- No P2–P4 or V1–V4 full style datasets were present on main at the inspected ref.
- Schemas, P1 visual-reference catalog, three P1 shot analyses, five P1 manual selection cases and validator are present.

### Historical branch creative-library-review-completion

A later review branch contains a substantially expanded dataset:
- 144 detailed records: 18 each in P1–P4 and V1–V4.
- All 144 detailed records remain status=review; inventory entries are draft_for_human_review.
- 144 detailed IDs are unique and align with the 144 inventory IDs; no missing or orphan IDs were found in the read-only cross-file check.
- The collaborative review record says P1–P4 style concepts completed review (72 concepts), but detailed cards remain in review and no production approval was granted.
- V1–V4 detailed records also remain in review; do not infer final product approval.
- P1 has 18 mapped references; the catalog contains 19 entries. Three direct visual analyses exist (P1-004, P1-015, P1-014).
- All references are link_only_reference; public availability is not permission to reuse.
- Evidence: 72 image records E3 (practice-level only), 72 video records unknown.
- The P1 manual selection file has five cases only, not a representative eight-category suite.
- The historical quality audit records a 144-record schema validation and 9 passing automated contract tests on commit 8182347561f75c9e08dac687538aa72bd72c351f. This was not rerun in the VARIOM documentation task.

The expanded review-branch datasets were inspected read-only and used for the provisional 144-ID mapping. They were not copied into VARIOM production paths.

## 5. Machine-readable asset disposition

| Asset | Disposition | Rule |
|---|---|---|
| data/taxonomy.json | UPDATE REQUIRED | MAX definitions do not automatically match VARIOM; reconcile names and meanings before using IDs |
| data/style-inventory.json | CANDIDATE INDEX | Main and review-branch versions differ; pin branch/commit before mapping |
| data/styles.p1.json | ADAPT / REVIEW | Main version has 18 draft cards; review branch has 18 status=review cards; do not mix versions |
| data/styles.p2.json–styles.p4.json | REVIEW-BRANCH CANDIDATES | 54 cards exist on review branch only; all status=review |
| data/styles.v1.json–styles.v4.json | REVIEW-BRANCH CANDIDATES | 72 cards exist on review branch only; all status=review |
| data/styles.seed.json | HISTORICAL SEED | Two examples only; not a complete source of truth |
| schemas/creative-style.schema.json | VERSIONED ADAPTATION | JSON Schema 2020-12, MAX-specific schema ID and category assumptions; create a VARIOM-owned schema only after field requirements are approved |
| schemas/p1-visual-shot-analysis.schema.json | CONDITIONAL ADAPTATION | Reuse only if VARIOM needs a distinct reference-shot analysis artifact |
| data/p1-visual-reference-catalog.json | RIGHTS-RESTRICTED REFERENCE | 19 entries; all link-only; retain source and rights metadata |
| data/p1-visual-shot-analyses.json | METHOD/REFERENCE ONLY | Three detailed analyses; use observed principles, not exact creative reproduction |
| tests/p1-selection-test-cases.json | ADAPT | Five P1 cases only; create VARIOM cases across all eight categories before trusting selection |
| scripts/validate_p1.py | ADAPT / VERIFY | Review dependencies and schema assumptions; do not treat as a VARIOM validator |
| docs/MAX_Project_Execution_Tracker.xlsx | HISTORICAL ONLY | Binary workbook remains on main; it is not in this branch's folder/archive |

## 6. Taxonomy conflicts that prohibit direct porting

| Category | MAX meaning | VARIOM meaning | Disposition |
|---|---|---|---|
| P1 | Product Photography | Product Showcase | Related; map each style by intent |
| P2 | Static Advertising Creative | Static Ad | Close; revalidate detailed records |
| P3 | Carousel Content | Carousel | Retain only for Image Studio; never Monthly Content |
| P4 | Lifestyle & Contextual Photography | Lifestyle | Related; revalidate context role |
| V1 | Creator-Led / UGC-Style Video | UGC | Preserve real vs paid/scripted/synthetic distinctions |
| V2 | Product Showcase / Demonstration | Product Demo | Close; verify style fit and capability |
| V3 | Motion Graphics / Animation | Motion Graphics | Close; verify production capability |
| V4 | Commercial / Advertising Video | Story / Testimonial | Material conflict; reclassify all 18 records individually |

Additional unresolved decisions:
- P3-013…P3-018 have conflicting historical canonical mappings.
- V2-016 Voice-Over Product Demo and V2-017 On-Screen Annotation Demo may be production modifiers rather than standalone styles.
- P1-012 scale, P1-014 components, P2 offers/comparisons/guarantees/testimonials, and multiple before/after styles require verified facts/evidence/consent.
- Advanced 3D, simulation, complex animation, camera movement and compositing require real capability and cost verification.

See the 144-ID proposal in document 11 for candidate-level disposition. That proposal is not owner approval.

## 7. VARIOM scope differences and root-baseline conflicts

Do not import MAX assumptions about:
- Six Skills and a mandatory Orchestrator topology.
- MAX market positioning or target-market order.
- MAX video durations, aspect ratios, storyboard approval or audio controls.
- MAX montage/editing task list where it differs from the VARIOM repository-approved list.
- MAX monthly-planning exclusion; VARIOM monthly content is approved but has its own strict scope and limits.
- Product Catalog, publishing/scheduling, analytics, teams, professional timeline editing, or other excluded features.
- MAX billing, subscription, pricing, provider or credit assumptions.

VARIOM V2.0/V2.1 controls all product scope.

The root VARIOM.md is a working transformation baseline, not a substitute for the controlling V2.0 source. It contains the following conflicts or stale statements that must not be carried forward uncritically:
- It describes a 9-primary-tools + 15-More-Tools navigation as already approved. The later owner clarification says that this navigation proposal is not a final approved decision. Keep the exact tool mapping open; do not implement the 9+15 structure.
- It says the P1–P4 and V1–V4 definitions must not be renamed or invented because they are not supplied. The current V2.0 source baseline now defines the VARIOM categories; use those definitions, not the older unresolved wording.
- It records a 10/20/30/40 vs 10/20/30 duration discrepancy and defers resolution. The current VARIOM V2.0/V2.1 baseline sets Video Studio to 10/20/30 seconds and monthly video to a maximum of 10 seconds.
- It records future plan names Starter/Pro/Agency. The latest owner decision names Basic (1 brand), Pro (3 brands), and Agency (up to 8 brands); plan information remains hidden in the current interface and this does not authorize billing/subscription implementation.
- Its CREWZO repository audit and test/provider findings are dated working observations, not current implementation evidence. Recheck the live local checkout before making implementation claims.

## 8. Archive and branch preservation status

- Text copies of the historical MAX planning documents are in docs/variom-ai/archive/max/.
- Original MAX text documents and source JSON/schema files have been restored at their original paths on work/variom-ai-documentation, alongside the VARIOM documentation.
- The binary docs/MAX_Project_Execution_Tracker.xlsx is still present on main but is absent from work/variom-ai-documentation. The branch must not be merged until this binary-preservation gap is resolved or the owner explicitly accepts leaving it on main only.
- The source review branch creative-library-review-completion remains a separate historical source; its P2–P4/V1–V4 detailed datasets are not copied into the VARIOM branch.

## 9. Next steps

1. Resolve the P3-013…P3-018 owner decision.
2. Resolve V2-016/V2-017 style-vs-modifier decision.
3. Review the V4 reclassification proposal.
4. Confirm the minimum VARIOM style set required for V1; do not attempt to complete all 144 merely because MAX has them.
5. After owner decisions, perform field-level QA on retained records, finalize VARIOM schema and build representative tests.
6. Resolve the missing binary workbook in the documentation branch before any merge.

## 10. Audit boundary

This is a read-only source/documentation audit. It did not inspect the binary workbook contents, recheck external rights with rights holders, run validation in the user's local checkout, or verify live provider capability. Historical CI results are attributed to their source audit documents, not claimed as rerun here.


## 11. Detailed creative-card audit
The 144-card structural/editorial risk review is documented in [12 — Creative Style Field-Level Audit](12-creative-style-field-level-audit.md). It confirms structural consistency and valid alternative IDs, while identifying weak video family metadata, unmeasured video feasibility/cost, reference/evidence gaps and owner decisions. It authorizes no production import.
