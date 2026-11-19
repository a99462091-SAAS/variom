# Task MAX-P0-01 — Live Repository Audit and Phase 1 Readiness

**Phase:** 0 — Project control and documentation  
**Status:** Ready to run; not yet executed or accepted  
**Objective:** inspect the actual checkout and reconcile the planning baseline with the repository before implementation begins.

## Scope
1. Read root instructions and current planning/library documentation.
2. Inspect the tracked file tree, git status/branch, recent commits, app/tooling files.
3. Identify whether this repository contains only the creative library or also an application skeleton.
4. Record confirmed stack/tooling evidence from manifests, lockfiles, configuration, tests, and CI. Do not infer a stack from convention or preference.
5. Run safe, already-defined validation commands that do not require secrets or paid services.
6. Compare live facts against the system specification, roadmap, and tracker.
7. Make only necessary evidence-backed corrections to the tracker and, if needed, add a concise docs/repository-audit.md.
8. Recommend the smallest Phase 1 foundation task based on the actual state.

## Explicit exclusions
- Do not implement product features.
- Do not write the Generation Prompt Engine.
- Do not add or upgrade dependencies.
- Do not choose a framework, database, authentication provider, hosting service, generation API, or payment provider.
- Do not perform broad refactoring, rename existing files, delete data, or modify creative-library datasets.
- Do not commit secrets or access paid/external services.

## Acceptance criteria
- [ ] Current branch, clean/dirty state, recent commit, and tracked top-level structure are reported.
- [ ] Existing app vs. library-only state is supported by file evidence.
- [ ] Existing validation/test commands and actual outcomes are reported; unrun checks are labeled.
- [ ] Discrepancies with planning docs are listed; only factual, non-material corrections are made.
- [ ] One recommended next task is stated, with scope, exclusions, affected files, tests, and acceptance criteria.
- [ ] No product code or creative-library data was changed.
- [ ] Final diff contains only authorized documentation updates, if any.

## Required report
Use the completion-report format in docs/claude-code-rules.md. If a command cannot run, explain why; never substitute an assumed result.

## Next step after review
The reviewer checks the evidence and approves or requests corrections. Only then prepare the separate Phase 1 implementation task.