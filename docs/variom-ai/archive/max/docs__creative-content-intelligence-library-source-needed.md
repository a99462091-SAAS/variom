# MAX — Creative Content Intelligence Library: source material needed

**Date:** 2026-10-31
**Status:** Checklist only. It is not the specification and contains no reconstructed content.

## What is known

- **Module:** Creative Content Intelligence Library.
- **Arabic title:** نظام تصنيف واختيار الأساليب الإبداعية لمنصة إنشاء المحتوى بالذكاء الاصطناعي
- The user supplied a detailed specification in the project conversation on **2026-10-28**.
- The conversation is the **ChatGPT project conversation**. It is not accessible from the repository or the working environment, and no export, attachment or copy of the verbatim text exists in any of the 12 remote branches (searched twice, 2026-10-31, by module name, Arabic title and conversation references).
- `docs/creative-content-intelligence-library.md` was therefore **not created**. A summary is not presented as the approved specification (blocker B-012).
- `docs/approved-product-architecture.md` §4 is a summary. `data/taxonomy.json` is a data file. Neither replaces the full specification.

## Source material needed to create the standalone Markdown document

1. **The original specification text, verbatim**, from the 2026-10-28 conversation: every message that contains it, in order, with message dates. Do not paraphrase or summarize.
2. **Any attachments** sent with it (documents, tables, images, spreadsheets).
3. **Every later user amendment or approval** that changes it, with its date: corrections, additions, removals, and the approval status of each part (draft, ready for review, approved).
4. **The user's statement of which parts are approved** versus still proposals, so the document can mark each part correctly.
5. **Cited reference material or sources**, with rights and provenance where the text relies on them.
6. **The user's confirmation of the target path and name** for the new document, and whether it replaces or complements `docs/library-design.md`.

## Existing repository material to reconcile against (not the specification)

On `main`:
- `docs/approved-product-architecture.md` §4: hierarchy (Image/Video; P1–P4, V1–V4; internal detailed styles) and the style-record field list.
- `docs/library-design.md`: current library design.
- `data/taxonomy.json` (v1.0.0; identical on every branch), `data/style-inventory.json`, `data/styles.seed.json`, `data/styles.p1.json`.
- `schemas/creative-style.schema.json`, `schemas/p1-visual-shot-analysis.schema.json`.
- `docs/p1-reference-audit.md`, `docs/p1-visual-shot-analysis-pilot.md`, `data/p1-visual-reference-catalog.json`, `data/p1-visual-shot-analyses.json`.
- `README.md` (section "Creative Content Intelligence Library").

On other branches only (for example `creative-library-review-completion`):
- `CREATIVE_CONTENT_INTELLIGENCE_REVIEW.md`, `docs/creative-style-product-decisions.md`, `docs/creative-style-quality-audit.md`, `docs/creative-style-reference-audit.md`, `data/styles.p2.json` to `data/styles.p4.json`.

Before the transfer, the user should say whether any of these conflicts with the specification, and which one wins.

## Rules for the transfer

- Copy the approved text as supplied. Do not fill gaps, infer missing parts, or reconstruct from the taxonomy or the style records.
- Mark any part whose approval status is not stated as *status not stated — pending user confirmation*.
- Do not change `data/taxonomy.json`, the schemas or the style records as part of this transfer. Align them only under a separate, user-authorized task.
- Keep blocker B-012 open until the user accepts the standalone document.
