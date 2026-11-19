# Library design and operating rules

Version: 1.0.0  
Status: Initial design baseline

## 1. Purpose

The library stores actionable creative execution styles and the decision rules needed to select them. It is not a generic mood-board collection and is not a guarantee of advertising performance.

## 2. Concept boundaries

Keep these dimensions separate:

- **Content type:** image or video.
- **Primary category:** P1–P4 for images; V1–V4 for videos.
- **Creative execution style:** the internal execution approach.
- **Marketing objective:** awareness, engagement, leads, sales, inquiries, retention, or another stated goal.
- **Content subject/message:** the product, service, offer, need, or claim being communicated.
- **Publishing format:** dimensions, aspect ratio, duration, number of carousel slides, platform placement.
- **Production method:** generated image, generated video, live-action, compositing, motion graphics, or hybrid production.
- **Copywriting approach:** educational, problem–solution, comparison, narrative, direct response, and related approaches.

A short vertical educational video about a product is a combination of category, execution style, objective, duration, and aspect ratio—not a new primary category.

## 3. Canonical primary categories

### Image
- **P1 — Product Photography:** the product's appearance, attributes, material, shape, or arrangement is the primary subject.
- **P2 — Static Advertising Creative:** a designed advertising message and its visual hierarchy are central.
- **P3 — Carousel Content:** a multi-panel publishing structure organizes a sequence or set of messages. Carousel is a publishing structure with multiple possible creative approaches, not one visual style.
- **P4 — Lifestyle & Contextual Photography:** the usage context materially contributes to the idea or message; a person or attractive location alone is not enough.

### Video
- **V1 — Creator-Led / UGC-Style Video:** a person, presenter, or creator-led narrative is the main communication vehicle. Clearly distinguish real testimony from scripted or synthetic performance.
- **V2 — Product Showcase / Demonstration:** the product and its observable features, operation, contents, or usage are the main focus.
- **V3 — Motion Graphics / Animation:** animated typography, illustration, data, diagrams, or motion-led visual explanation carries the message.
- **V4 — Commercial / Advertising Video:** a deliberately directed advertising concept, scene structure, and visual treatment shape the message. A video is not V4 solely because it sells something.

## 4. Style record contract

Every production-ready style should have:
- Stable ID, bilingual name, version, type, and category.
- Short and full definitions.
- Actionable visual or narrative execution instructions.
- Hook/opening and beginning–middle–end guidance where relevant.
- Composition, camera, lighting, color, background, movement, pacing, product/brand visibility, text-safe area, and avoidances as applicable.
- Fit and poor-fit conditions, required assets, complexity/cost estimates only when responsibly assessed, AI suitability, and human-review requirements.
- Selection signals, exclusion signals, alternatives, and combination rules.
- Copywriting guidance separated by text placement: image text, on-screen text, voice-over, dialogue, caption, and CTA.
- Reference metadata and evidence metadata with source, context, date, limitations, and rights status.
- Production requirements and quality checks.

Fields that do not apply should be represented as an explicit not-applicable state where the schema permits it; unavailable facts should be unknown/null rather than invented.

## 5. Selection engine

The engine must first parse the brief and use relevant existing Brand DNA and supplied assets. It should not ask for information already available.

Extract, where available:
- Product/service and confirmed facts.
- Business sector, audience, objective, message, need/problem, supported benefit, evidence, and CTA.
- User-selected content type and primary category.
- Publishing platform/format, source assets, tone, constraints, budget/quality preference, and production capabilities.

Respect the selected type and category. Search styles inside that category first. If the request appears incompatible, explain the conflict and suggest a suitable alternative rather than silently changing the category.

A preliminary ranking model may score:
- Objective fit: 25
- Message/idea fit: 20
- Product/service fit: 15
- Audience fit: 10
- Available assets: 10
- Platform/format fit: 10
- Production feasibility and constraints: 5
- Copywriting fit: 5

These are **initial design weights, not empirically validated weights**. Score each criterion from 0–5, normalize to its weighted contribution, and calibrate through tests. Do not display the score as a probability of success.

Usually select one primary style. Add a secondary style only if the combination has a clear purpose and compatible instructions. When options score similarly, prefer simpler and more feasible execution.

Track separately:
- Style-match confidence.
- Evidence strength.
- Confidence in product/brief facts.

## 6. Evidence levels

- **E1 — Contextual campaign results:** published results with identifiable objective, audience, platform, period, metric, and limitations.
- **E2 — Research or study:** a traceable study with method, sample/context, findings, and limitations.
- **E3 — Established production practice:** a common execution practice without sufficient evidence to claim commercial superiority.
- **E4 — Creative hypothesis:** plausible idea requiring testing.

Several articles repeating one unsupported claim do not automatically increase evidence strength. One successful campaign does not prove universal effectiveness. Keep source dates and last-reviewed dates.

## 7. Reference and intellectual-property policy

For each reference, store its original URL or internal asset ID, creator/brand/campaign if known, description of the relevant principle, reason it is useful, review date, rights status, and allowed use. Never fabricate a source or imply that inspiration grants reproduction rights. Extract general principles such as composition, lighting, pacing, or hierarchy; do not instruct the model to reproduce a protected campaign or distinctive artwork exactly unless rights and permission are established.

## 8. Product truth and testimonials

- Confirmed product facts take precedence over speculative visual references.
- Do not invent dimensions, ingredients, certifications, discounts, guarantees, results, or availability.
- Never present actors, generated characters, or scripted performances as genuine customers.
- Label paid, scripted, or synthetic creator content appropriately when required.
- Before/after claims, health claims, financial claims, and measurable performance claims require substantiation and human review.
- If accurate product appearance is important, identify which product/logo/reference assets must be preserved and what may be changed.

## 9. Prompt assembly

Do not send an empty template to a generation model. Assemble a coherent, conflict-checked prompt from the brief, chosen style, brand rules, asset instructions, format, text/copy plan, and safety/truth constraints.

### Image prompt components
Task; confirmed product facts; objective/message; selected style; composition; camera/viewpoint; lighting/color/materials/background; product and brand fidelity; text or reserved text area; aspect ratio; constraints; success criteria.

### Video prompt components
Task; product/objective; selected style; hook and beat sequence; shot/scenes; camera and movement; lighting/color; product and brand fidelity; duration/aspect ratio; dialogue/voice-over/on-screen text/caption/CTA separated; audio requirements; constraints; success criteria.

If Arabic text rendering is unreliable in the image generator, request a clean reserved text area and add approved text in a separate design step.

## 10. Quality gates

Before a style is production-ready, check:
- Category fit and distinction from similar styles.
- Instructions are actionable rather than adjectives alone.
- No internal contradictions or unsupported claims.
- Product/logo fidelity and asset roles are clear.
- Text placement, tone, and CTA match the objective.
- Platform format and production capabilities are feasible.
- Human review is required where facts, rights, testimonials, regulated claims, or material product accuracy demand it.
- Schema validation passes and source/evidence status is explicit.

## 11. Maintenance and versioning

- Use stable style IDs; do not reuse a retired ID for a different concept.
- Add new styles only when meaningfully distinct; use aliases or modifiers for minor variations.
- Keep an audit trail of version changes and why they were made.
- Review references for availability, rights, relevance, and accuracy.
- Do not change a style's evidence level based on one weak test or one engagement spike.
- Test selection on a representative brief set before changing ranking weights.
- Keep seed/examples separate from approved production records.
