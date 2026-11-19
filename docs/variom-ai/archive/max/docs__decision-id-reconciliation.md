# MAX — Decision ID Reconciliation (workbook ↔ Markdown)

**Date:** 2026-10-31
**Status:** Reconciliation record. It approves nothing and renumbers nothing.

## Rules (user decision, 2026-10-31)

- **Canonical IDs are the IDs in `docs/project-tracker.md`** (D-01..D-24), which record the user-approved decisions in `docs/approved-product-architecture.md`.
- The workbook's historical IDs (`docs/MAX_Project_Execution_Tracker.xlsx`, sheet *Decisions*) are kept as **aliases** for traceability. The workbook ID column was not changed, because the same ID means different things in the two systems (for example D-13, D-14, D-23, D-24). Each workbook row's Notes column starts with `[ID MAP 2026-10-31] Canonical ID (main): … | Workbook alias: … | Class: …`.
- A parenthetical such as "D-12 (part: PostgreSQL)" names the part of one canonical decision that a workbook row covers. It is a label, not a new ID.
- No canonical ID is shared by decisions with different meanings. A record with no confirmed mapping is **UNASSIGNED** and **pending user review**; none is deleted.
- Classes: **User-approved** (recorded in the main decision log or the approved architecture); **User-approved initial choice** (initial approval, not verified, no programming authorization); **Open item**; **Rejected**; **Pending user review** (no claim of user approval).

## Mapping: workbook alias → canonical ID

| Workbook alias | Canonical ID | Meaning | Class |
|---|---|---|---|
| D-01 … D-11 | D-01 … D-11 | The eleven original decisions (SaaS in verified phases; unified entry; segments; Claude as reasoning layer; replaceable provider; credits; billing early, payment later; Arabic and English; gradual video/audio; Claude Code executes written tasks only; simplicity) | User-approved |
| D-14 | D-12 (part: Next.js + TypeScript + simple background jobs) | Application framework and background jobs | User-approved initial choice (2026-10-29) |
| D-15 | D-12 (part: PostgreSQL) | Database | User-approved initial choice (2026-10-29) |
| D-17 | D-12 (part: private object storage) | File/asset storage | User-approved initial choice (2026-10-29) |
| D-16 | D-12 (part: authentication) | Authentication approach | Open item |
| D-18 | D-12 (part: hosting provider) | Hosting/region | Open item |
| D-19 | D-12 (part: generation provider/model/API; D-05 approves evaluating Google models first) | Exact model and API | Open item |
| D-20 | D-12 (part: payment provider) | Payment provider | Open item |
| D-25 | D-13 | One Orchestrator + six Skills | User-approved |
| D-30 | D-15 | Taxonomy P1–P4, V1–V4; automatic internal style selection | User-approved |
| D-29 | D-16 (part: calendar exclusion) | Monthly content calendar / publishing planner | Rejected |
| D-31 | D-19 | Unified Master Storyboard for all video | User-approved |
| D-32 | D-21 (part: the six items) | Smart Editing: Auto Captions, Audio Enhancement, Silence Removal, Music & Rhythm, Motion Graphics, Additional Instructions | User-approved |
| D-34 | D-21 (part: Logo Overlay excluded) | No seventh "Logo Overlay" task (restated by the user 2026-10-31) | Rejected |
| D-35 | D-21 (part: professional editing excluded) | No professional timeline/frame editor, story reconstruction or complex VFX | Rejected |
| D-33 | D-22 (part: no preview) | No preview before final export | Rejected |
| D-27 | D-23 (also D-03, D-08) | Maximum Quality, Minimum Overhead; Arabic/English; multi-brand account | User-approved |
| D-36 | D-23 (partly D-14; architecture §14) | Cost and execution architecture principles | User-approved |
| D-37 | D-24 | 52 design acceptance cases and 3 end-to-end scenarios (design baseline, not executed tests) | User-approved |

## Unresolved workbook-only records (UNASSIGNED — pending user review)

All eight are kept with their content and historical IDs. None is claimed as user-approved by this record.

| Workbook alias | Description | Why the canonical mapping is unresolved |
|---|---|---|
| D-13 | No complex staff roles or permissions initially | The content appears in `docs/approved-product-architecture.md` §1/§2, but main's decision log has no entry for it, and main's D-13 (Orchestrator + six Skills) already uses that ID |
| D-21 | Real generation cost and final pricing (open) | Architecture §16 lists pricing and credit conversion as open, but main's D-12 does not cover pricing and the log has no entry |
| D-22 | Qualified Saudi legal review, data transfer and privacy (open) | Architecture §16 lists legal/privacy/rights as open; the log has no entry |
| D-23 | Formal approval of the documentation baseline (older-lineage record; pending) | Main's D-23 means Maximum Quality, Minimum Overhead; main records the approved product/architecture baseline rather than a documentation-baseline approval, and the user has not recorded a formal approval |
| D-24 | Application implementation authorization (not authorized) | Consistent with `CLAUDE.md` and this tracker, but main's D-24 is the 52-case suite, so the ID is taken and the log has no authorization entry |
| D-26 | Initial markets: Saudi Arabia first, then UAE, Kuwait, Oman, Egypt | Content appears in architecture §1, but the log has no entry |
| D-28 | No initial external social-media publishing integrations | Only partly supported: architecture §2 says "no unnecessary external integrations"; an explicit ban is not in the approved record. Workbook status kept as *under evaluation* |
| D-38 | 50% planning / 50% programming weighting | A temporary proposal with no counterpart; changing it needs the user's approval |

## Canonical decisions with no workbook row

Their IDs collide with workbook rows that mean something else, so they were not added to the workbook.

| Canonical ID | Meaning |
|---|---|
| D-14 | Skill contracts, workflow routing, version/dependency control, asset identity, approval binding, operation recovery, timeline, concurrency, account/brand isolation |
| D-16 (marketing part) | Marketing Ideas and 12-part Copywriting Intelligence (the workbook has only the calendar rejection) |
| D-17 | Explicit Dialect Lock and brand-specific dialect learning |
| D-18 | Typography library, user brand fonts, automatic layout, programmatic text composition |
| D-20 | Prompt Engineering & Generation Intelligence: eight coordinated systems |
| D-22 (cost part) | Montage shows per-task and total cost before execution |

## Technology stack record (D-12)

- Initially approved by the user on 2026-10-29 as architectural choices: Next.js, TypeScript, PostgreSQL, private object storage, simple background jobs. This is not a verified production decision and does not authorize programming.
- Open: hosting provider, authentication, generation provider/model/API, payment provider, final infrastructure/service providers; pricing, availability and suitability must be verified first.
- Alignment (2026-10-31): `docs/approved-product-architecture.md` §16 now lists these five choices as initially approved, separates what requires verification and what is open, and states that programming authorization is NOT granted. `docs/system-specification.md` §15 and `docs/implementation-roadmap.md` §6 carry the same wording.
