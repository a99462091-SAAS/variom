# MAX — AI Marketing Content Platform

MAX is a Saudi/Gulf-first SaaS concept for businesses, brand owners, e-commerce businesses, and agencies managing multiple brands. It aims to make AI-assisted marketing content creation high-quality and simple, using brand context, a curated creative library, structured production workflows, and cost-aware execution.

## Current repository role

This repository contains the product specification baseline and the initial Creative Content Intelligence Library foundation. Product/architecture documentation is not evidence that application features have been implemented.

## Source-of-truth documents

- `docs/approved-product-architecture.md` — consolidated user-approved product and architecture decisions.
- `docs/system-specification.md` — product scope, boundaries, and system responsibilities.
- `docs/implementation-roadmap.md` — phased delivery order and acceptance gates.
- `docs/project-tracker.md` — current status, evidence, blockers, and next action.
- `CLAUDE.md` and `docs/claude-code-rules.md` — repository execution rules.

## Creative Content Intelligence Library

- `docs/library-design.md` — taxonomy, selection logic, evidence, rights, and maintenance rules.
- `schemas/creative-style.schema.json` — creative-style record contract.
- `data/taxonomy.json` — canonical content types and primary categories.
- `data/styles.seed.json` — illustrative seed examples, not a production import set.
- `data/styles.p1.json` — 18 detailed P1 draft records; human review required before production.
- `data/p1-visual-reference-catalog.json` — curated visual references with source and rights cautions.
- `data/p1-visual-shot-analyses.json` — image-specific visual analyses.
- `data/style-inventory.json` — candidate inventory.
- `tests/p1-selection-test-cases.json` — manual-review selection cases, not proof of an implemented selector.
- `scripts/validate_p1.py` — P1 schema and integrity validation.

## Product principles

- Maximum Quality, Minimum Overhead.
- Internal sophistication; simple user experience.
- Selective Skills and model calls; deterministic code where sufficient.
- Preserve brand/product facts and original references.
- Provider capabilities and prices must be verified, never assumed.
- Do not expand scope without an approved need.

## Current implementation status

The approved architecture is documented, but this README does not claim the SaaS workflows are implemented. See `docs/project-tracker.md` for the live phase, task, evidence, and next action.
