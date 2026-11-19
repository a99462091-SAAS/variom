# VARIOM — MAX Source & Creative Asset Migration Inventory

**Date:** 2026-11-19  
**Status:** Evidence-based first-pass classification; not an import authorization.

## 1. Classification legend
- **KEEP AS-IS (REFERENCE):** reusable principle/method; not VARIOM authority.
- **ADAPT:** preserve substance but rewrite scope, terminology or workflow.
- **REBUILD:** use as background only; create a VARIOM-native document.
- **HISTORICAL ONLY:** preserve for traceability; not current requirements/status.
- **EXCLUDE FROM VARIOM V1:** do not expose or implement unless re-approved.
- **HOLD — SOURCE/VALIDATION REQUIRED:** semantic mapping, rights, schema or evidence incomplete.

## 2. MAX document-by-document classification

| MAX source | Classification | Reusable content | Required VARIOM treatment |
|---|---|---|---|
| README.md | ADAPT | Product summary; specification vs implementation distinction | VARIOM README is new entry point; do not carry MAX market positioning or imply implementation |
| CLAUDE.md | ADAPT | Repository safety and execution discipline | Review root instructions before changes; VARIOM authority/exclusions prevail |
| docs/approved-product-architecture.md | REBUILD | Brand context, truthfulness, selective orchestration, idempotency, recovery, cost separation, rights and isolation | Four logical VARIOM systems replace mandatory six-Skill topology; only V2.0 workflows survive |
| docs/system-specification.md | REBUILD | Responsibility boundaries, contracts, operational principles, capability verification | Re-author against VARIOM V2.0; remove MAX-only assumptions and conflicting formats/durations |
| docs/implementation-roadmap.md | HISTORICAL + selective ADAPT | Stage gates, bounded tasks, evidence-first acceptance | Use VARIOM roadmap; inherit no MAX phases, statuses, percentages or dependencies |
| docs/project-tracker.md | HISTORICAL ONLY | Historical status and decision evidence | VARIOM tracker independent; copy no MAX status or acceptance |
| docs/library-design.md | ADAPT | Taxonomy boundaries, style record concepts, evidence/rights, selection, prompts, quality gates | VARIOM category definitions and actual records prevail; styles require reconciliation |
| docs/claude-code-rules.md | ADAPT | Scope control, evidence, secret safety, bounded execution/reporting | Apply VARIOM source hierarchy and active owner-approved task |
| docs/claude-code-start-prompt.md | HISTORICAL ONLY | Old task setup record | Do not reuse as active prompt; write new VARIOM task command when authorized |
| docs/creative-content-intelligence-library-source-needed.md | KEEP AS-IS (EVIDENCE) | Provenance: detailed 2026-10-28 library specification was not recovered verbatim in repo | Keep limitation visible; obtain original before claiming exact migration |
| docs/decision-id-reconciliation.md | HISTORICAL ONLY | Explains why workbook IDs are not current decisions | Do not import MAX IDs into VARIOM decision records |
| docs/p1-reference-audit.md | HOLD — SOURCE/VALIDATION REQUIRED | Reference-review method, provenance and rights cautions | Recheck each reference for availability, rights and fit to current P1 |
| docs/p1-visual-shot-analysis-pilot.md | ADAPT | Visual-analysis method and structured observations | Reuse method only; reclassify examples and verify P1 fit |
| docs/phase-0-repository-audit-task.md | HISTORICAL ONLY | Audit approach and evidence discipline | Old findings are not current repository facts |
| docs/MAX_Planning_Update_Report.md | HISTORICAL ONLY | Past planning/workbook verification | No VARIOM status or approval authority |
| docs/MAX_Workbook_Verify_Log.txt | HISTORICAL ONLY | Historical workbook validation evidence | Does not validate VARIOM docs, app or current workbook |
| docs/MAX_Project_Execution_Tracker.xlsx | HISTORICAL ONLY | Old planning structure and decision aliases | Retain original; copy no IDs, status or percentages |

## 3. Creative-library source assets — migration decision

The MAX README and source-needed record identify these assets. They remain at original repository paths; this documentation branch has not copied or modified them.

| MAX asset | Classification | Migration rule |
|---|---|---|
| data/taxonomy.json | HOLD — SEMANTIC RECONCILIATION | Compare every type/category ID and definition to VARIOM V2.0. Preserve exact matches only; explicitly map changed meanings. |
| data/style-inventory.json | HOLD — SEMANTIC RECONCILIATION | Candidate inventory, not approved catalog. Deduplicate, classify and map each record. |
| data/styles.seed.json | HOLD — SEED ONLY | Illustrative examples are not production-approved. Keep isolated from production import. |
| data/styles.p1.json | HOLD — RECORD-BY-RECORD REVIEW | 18 historical P1 drafts require category-fit, factual, rights, quality and schema checks. Never bulk-import. |
| data/styles.p2.json through styles.p4.json | HOLD — BRANCH/PROVENANCE CHECK | Reported on a historical review branch, not established as current production records. Verify branch, content, approval and provenance. |
| schemas/creative-style.schema.json | ADAPT / VERSION | Reuse structural concepts only after comparing fields with VARIOM requirements. Do not silently replace MAX schema. |
| schemas/p1-visual-shot-analysis.schema.json | ADAPT / OPTIONAL | Reuse only if VARIOM needs a distinct shot-analysis artifact; avoid unnecessary schema overhead. |
| data/p1-visual-reference-catalog.json | HOLD — RIGHTS + CATEGORY REVIEW | Validate source, creator, license/permission, date, usage rights and fit to VARIOM P1. Public access is not reuse permission. |
| data/p1-visual-shot-analyses.json | HOLD — SOURCE + SEMANTIC REVIEW | Keep analysis separate from source image/style record; verify observations and P1 fit. |
| tests/p1-selection-test-cases.json | ADAPT | Convert relevant cases into VARIOM tests after definitions and selection behavior are finalized. Historical cases are not passing tests. |
| scripts/validate_p1.py | ADAPT / VERIFY | Inspect dependencies/schema assumptions; reuse only if it validates selected VARIOM schema without mutating source data. |
| CREATIVE_CONTENT_INTELLIGENCE_REVIEW.md and review/audit documents | HISTORICAL + EVIDENCE | Use as review evidence, not approval; verify source branch, date and decision status. |

## 4. Category semantic conflicts to resolve before import

Identical P1–P4 / V1–V4 labels do not guarantee identical product meaning.

| Category | MAX documented meaning | VARIOM current baseline | Decision |
|---|---|---|---|
| P1 | Product Photography | Product Showcase | Related, not automatically equivalent; map by actual style intent |
| P2 | Static Advertising Creative | Static Ad | Likely close; verify each record |
| P3 | Carousel Content | Carousel | Broad concept matches; VARIOM restricts it to Image Studio, never Monthly Content |
| P4 | Lifestyle & Contextual Photography | Lifestyle | Related; verify contextual meaning |
| V1 | Creator-Led / UGC-Style Video | UGC | Distinguish genuine testimonial, scripted actor and synthetic character |
| V2 | Product Showcase / Demonstration | Product Demo | Likely close; verify each record |
| V3 | Motion Graphics / Animation | Motion Graphics | Likely close; verify feasibility |
| V4 | Commercial / Advertising Video | Story / Testimonial | **Material conflict.** No mapping without individual review. |

Any record depending on old durations, aspect ratios, storyboard approvals, audio controls, platform assumptions or old UI must be updated or excluded from the relevant VARIOM workflow.

## 5. Reusable methods vs. non-transferable assumptions

### Reusable methods (subject to fit)
- Keep category, detailed style, objective, subject/message, publishing format, production method and copywriting approach separate.
- Select detailed styles internally rather than exposing a long technical taxonomy.
- Reuse Brand DNA and supplied assets; ask only for missing material facts.
- Separate product-fact confidence, style-match confidence and evidence strength.
- Preserve source provenance, rights, evidence date and limitations.
- Use stable IDs/versions; do not recycle retired IDs for new meanings.
- Separate seed/example records from production-approved records.
- Assemble prompts from confirmed facts, objective, style, brand rules, assets, format and constraints.
- Prefer a reserved text area plus programmatic composition when generated Arabic text is unreliable.
- Validate records and selection behavior with representative test cases.

### Not transferable without explicit VARIOM approval
- MAX's six Skills and Orchestrator as mandatory runtime topology.
- MAX market positioning, target-market sequence or customer segments.
- MAX video durations, aspect ratios, scene limits or audio controls.
- Mandatory full-storyboard user approval.
- MAX editing task list if it differs from the repository-approved VARIOM list.
- MAX project/collection concepts, monthly calendar or publishing planner.
- MAX workbook decision IDs, percentages, completion states or acceptance claims.
- Any provider, price, licensing, model or API capability not re-verified for VARIOM.

## 6. Minimum record-level migration workflow

For each candidate taxonomy/style/reference/test record:
1. Record original path, stable ID, version, branch/commit and provenance.
2. Classify: exact match, compatible with edits, conflicting, duplicate, obsolete, unsupported or unknown.
3. Map intended meaning to a VARIOM category using VARIOM definitions, not the old label alone.
4. Check required assets, claims, rights, AI feasibility and human-review needs.
5. Validate against the selected VARIOM schema; record unknowns without inventing values.
6. Assign a VARIOM ID only after semantic acceptance; retain old ID as traceable alias.
7. Keep candidate/seed/review records isolated from production-approved records.
8. Test selection against representative VARIOM briefs before enabling the record.

## 7. Evidence limitations and next work
- This inventory uses archived MAX Markdown sources and source asset names/relationships documented by the MAX README and source-needed record.
- Underlying JSON files, schemas, workbook and visual assets were not fetched or parsed in this documentation-only pass. Their contents, hashes and current branch availability are **not verified here**.
- The detailed 2026-10-28 owner-supplied creative-library specification was not recovered verbatim. This inventory is not a replacement for it.
- The original separate UI Design Prompt and visual identity image remain required for final visual acceptance.

**Next bounded task:** read-only inventory of listed JSON/schema/test assets and relevant review-branch files; produce record-level mapping. Do not edit, import, delete, rename or migrate assets during that audit.


## 8. Record-level mapping proposal
The first-pass semantic disposition for all 144 IDs is now documented in [11 — Creative Style ID Mapping Proposal](11-creative-style-id-mapping-proposal.md). That proposal does not approve an import or replace detailed record-level QA.
