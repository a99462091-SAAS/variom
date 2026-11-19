# VARIOM — Claude Code Execution Rules

These rules apply to all tasks. The active owner-approved task defines the permitted changes.

## Source hierarchy
1. `00-product-vision-simplified-ux-v2.md` — highest product authority.
2. `04-ux-frontend-interface-master-spec-v2.1.md` — screen implementation, subordinate to product vision.
3. Owner-supplied UI Design Prompt and visual identity image — visual styling.
4. Current code, schemas, tests and runtime evidence — implementation truth.
5. VARIOM architecture, system, library, roadmap and tracker documents.
6. MAX archive — historical context only.

## Before editing
Read root CLAUDE.md, this rules file, product vision, relevant architecture/system docs, tracker and active task. Inspect actual branch, working tree, diffs, relevant code, schemas and tests. State a concise bounded plan and likely changed paths. Preserve existing work.

## Scope discipline
Execute only the active task. Do not invent product decisions, content types, formats, durations, prices, providers or capabilities. Do not introduce Product Catalog, monthly publishing calendar, scheduling, publishing, analytics, approvals, teams, ZIP, professional timeline editor or excluded scope. Do not assume legacy MAX features remain approved because code/docs exist. Do not remove legacy code/data without explicit authorization. No opportunistic refactors or broad upgrades. Stop on material ambiguity, destructive changes, migrations, provider activation, billing changes or external publication.

## Engineering and safety
Never commit secrets, credentials, real customer data or local environment files. Keep live AI providers disarmed unless separately authorized. Isolate preview/mock assets from production jobs/assets/credits. Enforce account/brand authorization and private asset access. Keep credit reservation/settlement/refund tied to actual backend state. Preserve idempotency, partial recovery and bounded retries. Never call a mock/local render real AI generation.

## Verification and report
Run relevant existing checks. Report exact commands and outcomes; separate passed/failed/skipped/not run. Inspect final diff for unrelated changes, secrets and generated noise. Do not mark work accepted; owner acceptance is required.

Completion report: outcome; changed files; acceptance criteria; exact checks/results; risks/limitations; tracker update proposal; one next action.
