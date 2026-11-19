# VARIOM — Execution Charter & Authority Map

**Version:** 1.0  
**Status:** Initial governance baseline; owner confirmation required only where explicitly marked OPEN.  
**Last updated:** 2026-11-19

## 1. Purpose

This charter establishes the sole execution boundary for VARIOM documentation and future implementation. It prevents MAX repository instructions, historical MAX decisions, candidate research and unverified provider capabilities from being treated as VARIOM authority.

## 2. Authorized repository and branch

- **VARIOM repository:** `a99462091-SAAS/variom`
- **Documentation working branch:** `work/variom-documentation-readiness`
- **Default branch:** `main`
- **Current scope:** documentation readiness work only.
- **Implementation status:** NOT AUTHORIZED by this charter.
- **MAX source repository:** `a99462091-SAAS/ai-content-creation-platform-max`; source/reference only.

The owner established the new VARIOM repository and directed migration of the complete `docs/variom-ai/` package. The migrated source package was compared by path and Git blob SHA: 40 entries, 38 files, no missing, extra or content-mismatched entries.

## 3. Authority hierarchy

Apply this order when sources conflict:

1. Explicit, latest owner decision recorded in the VARIOM Product Decisions Register.
2. `00-product-vision-simplified-ux-v2.md` — highest product authority, unless a later explicit owner decision supersedes a specific clause.
3. `04-ux-frontend-interface-master-spec-v2.1.md` — subordinate UX and screen authority; it cannot expand product scope.
4. This Execution Charter for repository, source and execution governance.
5. Approved normative VARIOM specifications, each with a defined scope and status.
6. Current VARIOM implementation, schemas, tests and runtime evidence — implementation truth, but not authority to silently change product requirements.
7. Explicitly adopted MAX planning sources, only for the exact sections and purposes recorded in the source-adoption register.
8. MAX archive and other historical/candidate sources — context only; never automatic approval.

If two sources at the same authority level conflict, stop the affected work and request owner resolution. Do not silently choose one.

## 4. MAX source-use policy

MAX is a planning-source foundation, not an implementation parent or a blanket product authority.

Every adopted MAX source must record:
- exact repository;
- branch and commit SHA;
- path and section;
- source status (approved in MAX, candidate, historical, superseded or unresolved);
- VARIOM adoption status (adopted, adapted, rejected, reference-only or pending);
- VARIOM decision ID and any required owner approval.

Archived copies under `docs/variom-ai/archive/max/` are preserved for provenance. They do not become current requirements by being present in this repository.

## 5. Claude Code operating rules

- The root `CLAUDE.md` in this repository is the VARIOM execution entry point. MAX root instructions must never be imported or followed as repository instructions.
- Before a task, read root `CLAUDE.md`, this charter, the Product Decisions Register, product vision, relevant normative specifications and tracker.
- Execute only a clearly bounded, owner-authorized task.
- Do not invent product behavior, commercial rules, provider/model capability, price, retention, consent wording, visual inputs or acceptance thresholds.
- Separate owner decisions from engineering choices. Engineering choices must preserve the product contract and be documented with rationale where material.
- Stop on unresolved product conflicts, destructive changes, schema/data migrations, security boundary changes, provider activation, billing changes, paid generation, external publication or deployment.
- Do not use mocks or local rendering as evidence of real provider capability or production generation.
- Preserve existing work; no broad refactors, opportunistic features or unrelated dependency upgrades.
- Report exact changed paths, commands, evidence, failures, skipped checks and remaining risks. Owner acceptance is separate from implementation completion.

## 6. Approval boundaries

| Activity | Authorization |
|---|---|
| Read/review VARIOM docs and MAX source material | Allowed for scoped documentation work |
| Create/update VARIOM planning and governance docs | Allowed within this documentation-readiness task |
| Record a confirmed owner decision with source evidence | Allowed |
| Resolve an unresolved product/commercial/visual/legal decision | Owner decision required |
| Create or modify application code | Separate explicit authorization required |
| Add/change database schema or migrate data | Separate explicit authorization required |
| Activate providers, run paid generation or incur usage charges | Separate explicit authorization required |
| Configure billing, payments, subscriptions or credits in production | Separate explicit authorization required |
| Deploy, publish externally or claim production readiness | Separate explicit authorization required |

## 7. Current phase and exit gates

**Phase:** Documentation Readiness.

- **Gate A — Authority and owner decisions:** establish repository authority; record owner decisions; resolve conflicts or explicitly defer them with implementation gates.
- **Gate B — Normative contracts:** requirements and acceptance, domain/data, workflows/state machines, APIs/schemas, credits/commercial, security/privacy, provider capability, UX, storyboard, editing, character, creative library and tests.
- **Gate C — Evidence and readiness audit:** verify source provenance, cross-document consistency, requirement-to-test traceability and implementation entry-point safety.

Do not label the package READY FOR IMPLEMENTATION until the objective criteria in document 18 are met. Stage-specific work may remain explicitly blocked where provider, legal, hosting or account evidence is unavailable.

## 8. Confirmed and open governance facts

**Confirmed**
- The implementation/documentation home is the separate `a99462091-SAAS/variom` repository.
- The MAX repository remains a source/reference repository.
- Product Vision V2.0 remains the controlling product baseline; UX V2.1 is subordinate.
- This phase is documentation-only.

**Open or deferred**
- Whether this documentation working branch is to be merged into `main` after documentation acceptance.
- Exact first launch market under VAR-OD-007; pricing, subscriptions, payment, tax and enforceable entitlements remain deferred.
- Provider/model selection, region, capabilities, costs, rights and data terms pending evidence and separate approval.
- Provider-specific output dimensions/formats/quality and exact voice/dialect catalogue pending capability verification.
- Retention periods, legal wording and jurisdiction-specific obligations pending legal review.
- Hosting, database, object storage, KMS and backup topology pending technical/cost/security review.
- Owner-supplied identity image and UI Design Prompt must be provided directly to Claude Code before visual implementation; neither may be reconstructed or replaced.
- Separate application implementation repository/branch and implementation authorization are not established by the documentation repository.

