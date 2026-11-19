# MAX — Claude Code Execution Rules

These rules apply to every task. The active task brief limits what may be changed; this file does not authorize work beyond that brief.

## Before editing
1. Read CLAUDE.md, docs/system-specification.md, docs/implementation-roadmap.md, docs/project-tracker.md, the active task brief, and relevant existing files.
2. Inspect the real repository state, current branch, uncommitted changes, package/tool configuration, and existing tests. Do not rely on stale tracker notes.
3. State a short plan and list likely files to change. Keep the plan within the task boundary.
4. Preserve useful existing work. Do not rewrite or reorganize unrelated files.

## Scope discipline
- Execute only the active task. Do not start the next phase early.
- Do not add features, dependencies, integrations, infrastructure, refactors, or design systems unless explicitly required.
- Do not choose an unresolved product, model, payment, hosting, database, or architecture decision without evidence and approval.
- If a material ambiguity or conflict blocks safe work, stop and report the precise question plus the smallest options needed. Continue independent, clearly authorized work.
- Prefer the smallest maintainable solution over speculative abstraction.
- Do not claim an external service works without a real supported test.

## Engineering and safety
- Never place secrets or credentials in source control. Use environment variables and a safe example file where appropriate.
- Follow existing conventions and compatible versions unless there is a demonstrated reason to change them.
- Validate user input and access boundaries where relevant.
- Handle loading, empty, error, retry, and partial-failure states for the feature being built.
- Keep provider-specific behavior isolated and expose only capabilities actually verified.
- Never fabricate brand/product facts, performance claims, source references, or test results.
- Avoid destructive commands and do not discard existing user changes.

## Verification
1. Run checks relevant to changed files; use existing scripts first.
2. Report each exact command and its actual result. Distinguish passed, failed, skipped, and not run.
3. Inspect the final diff for unrelated changes, secrets, generated noise, and incomplete implementation.
4. Do not mark work complete if acceptance criteria are unmet or a critical check has not run. Explain blockers.

## Required completion report
- **Outcome:** completed / partial / blocked.
- **Files changed:** paths and reason.
- **Acceptance criteria:** pass/fail with evidence.
- **Checks:** exact commands and results.
- **Risks/limitations:** concrete items only.
- **Tracker update:** proposed status and evidence.
- **Next action:** one next task only; do not execute it.

Update docs/project-tracker.md only with verified facts. Do not mark a task accepted on your own; acceptance is the reviewer's decision.

## Avoiding context drift
- Keep plans and reports concise.
- Re-read the active task after long investigations.
- Do not turn a future possibility into a requirement.
- Ask only the smallest necessary decision question when blocked.
- Never create duplicate source-of-truth documents; update the designated document instead.