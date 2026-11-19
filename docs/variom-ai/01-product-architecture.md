# VARIOM — Product & System Architecture

**Status:** Reconciled working architecture based on VARIOM V2.0 and reusable MAX architecture principles.  
**Authority:** Subordinate to `00-product-vision-simplified-ux-v2.md`.

## 1. Principles
Maximum useful quality with minimum user and operational overhead. Preserve verified foundations; prefer deterministic code where sufficient; use AI only where it adds demonstrated value; execute only required components; keep providers replaceable; treat unknown capability, price and quality as unknown.

## 2. Four logical systems
### A. Brand Intelligence
Brand Profile, Brand DNA, Brand Voice, Visual Identity, Brand Assets, active-brand context and optional Virtual Character references. Reuse known information and distinguish confirmed facts from inferred suggestions. Product photos remain task uploads; no Product Catalog.

### B. Marketing & Creative Intelligence
Marketing strategy/objective interpretation, idea generation, copywriting, content taxonomy, internal style selection and prompt engineering. Produce structured briefs. Never invent product claims, testimonials, certifications, prices or results.

### C. Content Production
Monthly Content orchestration, image/video generation, internal Master Storyboard, Simple Smart Editing, job lifecycle, media processing and output validation.

### D. Content Library
Persistence and retrieval of generated images, videos, editing outputs and monthly content. Enforce account/brand ownership. Not a project-management or approval system.

These are logical boundaries, not a requirement for four microservices or agents.

## 3. Internal contracts
Use structured contracts where workflows cross meaningful boundaries: brand context; marketing brief/idea/copy; creative direction/style; storyboard/scenes; generation request/capability requirements; editing task plan; final asset metadata/library persistence. Include stable identifiers, brand/task references, approved decisions, version/fingerprint, status, output and structured errors. Do not create one agent/model call per conceptual subcomponent.

## 4. Workflow controls
Validate before reserving credits. Use idempotent operations. Reserve before paid work. Execute only necessary steps. Persist successful partial results. Retry only failed/dependent work. Settle actual consumption and return unused reservations. Preserve provenance and versions. Enforce account/brand isolation.

## 5. Production constraints
Only P1–P4 and V1–V4. Detailed styles are internal. Product image uploaded manually where relevant. Video uses internal Master Storyboard. Monthly video <=10 seconds; Video Studio durations 10/20/30 seconds. Smart Editing is limited to the repository-approved Simple Smart Editing list.

## 6. Providers and cost
Maintain a capability registry only for accessible, verified providers/models. Record modality, reference behavior, duration, aspect ratio, resolution, audio, cost, latency, limits and failure modes when known. Unknowns remain unknown. Route using verified capabilities. Preserve spend controls and kill switches.

## 7. Data and asset integrity
Isolate account, brand, job and asset ownership. Preserve original uploads. Store outputs separately. Maintain stable asset identity and provenance. Bind approvals to exact versions where applicable. Prevent duplicate jobs/settlements. Isolate preview/mock data from production jobs, assets and credits.

## 8. Reuse from MAX
Reuse structured handoffs, idempotency, partial recovery, version/fingerprint controls, provider verification, cost separation, asset isolation, rights/evidence tracking and simple task-based editing. MAX's six Skills are not a mandatory VARIOM architecture. Map useful functions into the four VARIOM systems without unnecessary agents/services.

## 9. Not required
No Product Catalog, monthly publishing calendar, social publishing/scheduling, agency roles, professional timeline, speculative agents/microservices or unverified provider integrations.
\n\n## 10. Normative contract links and implementation boundary\nThis architecture is the high-level logical view, not a technology or deployment topology. Its normative requirements, domain model, workflows, APIs, credit invariants, security, provider evidence, UX, storyboard, editing, character, creative registry, verification and operations are defined in Documents 22–35. Gate B and Gate C review outcomes are recorded in Documents 36–37. No separate services, agents, database, queue, provider or cloud topology is mandated by the four logical systems. Application implementation remains unauthorized until a separate application target and owner authorization are recorded in the Project Tracker.\n\n\n## 10. Normative contract links and implementation boundary\nThis architecture is the high-level logical view, not a technology or deployment topology. Its normative requirements, domain model, workflows, APIs, credit invariants, security, provider evidence, UX, storyboard, editing, character, creative registry, verification and operations are defined in Documents 22–35. Gate B and Gate C review outcomes are recorded in Documents 36–37. No separate services, agents, database, queue, provider or cloud topology is mandated by the four logical systems. Application implementation remains unauthorized until a separate application target and owner authorization are recorded in the Project Tracker.\n