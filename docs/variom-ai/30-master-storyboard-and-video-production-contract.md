# VARIOM — Master Storyboard & Video Production Contract

**Version:** 1.0 | **Status:** NORMATIVE DRAFT | **Authority:** Documents 00, 19–29.

## 1. Purpose
Defines the internal storyboard contract for coherent video production. The Master Storyboard is mandatory before video-generation dispatch; it is not a user-facing professional editor or an optional bypass.

## 2. Inputs and bounds
Inputs may include:
- approved video category V1–V4;
- requested duration: exactly 10, 20 or 30 seconds in Video Studio;
- Reels Portrait or Reels Landscape Video;
- Creative Brief and selected Idea/Copy;
- pinned Brand DNA version;
- optional pinned Virtual Character Sheet version;
- manually uploaded product reference image(s) for this task;
- approved Creative Style and verified provider capability.
Monthly Content video is separately limited to 10 seconds maximum.

No 4K or unapproved ratio/format is inferred. Provider-specific dimensions/codecs remain evidence-gated.

## 3. Logical storyboard structure
A Storyboard has:
- stable ID, version, parent task and requested total duration;
- language and approved voice/dialect direction where supported;
- pinned brand, character, product-reference and style context;
- ordered Scenes;
- continuity constraints;
- validation status and provenance.

Each Scene has:
- stable scene ID and sequence index;
- concise visual/action description;
- dialogue/on-screen text where applicable;
- intended duration allocation;
- optional transition description;
- optional start/end visual reference when useful and supported;
- validation status.

The exact provider payload is not the canonical storyboard. It is a derived adapter and must not overwrite the source storyboard.

## 4. Continuity invariants
Across scenes preserve, as applicable:
- character identity and locked traits;
- product appearance and reference consistency;
- visual style and brand identity;
- language and approved voice direction;
- scene order, action progression and narrative intent;
- timing and transitions.
Any continuity requirement unsupported by the chosen provider must be flagged; do not promise it as guaranteed.

Segmenting is an internal orchestration detail. Segments must reconstruct one coherent story and must not fragment narrative continuity. Start/end references are used only when supported by verified capability.

## 5. Duration and validation
- Sum of scene allocations must equal requested duration within a documented tolerance selected after provider evidence and implementation test; do not invent a universal tolerance now.
- Reject missing/negative durations, empty required descriptions, duplicate sequence indices and incompatible total durations.
- Validate category, format, duration, language and capability before quote/confirmation.
- Scene review is optional. When exposed, user may edit only scene description and dialogue/text; hidden orchestration fields remain system-controlled.
- No separate audio control surface is exposed in Video Studio.

## 6. Production flow
1. Build brief from known brand context and task inputs.
2. Draft storyboard and ordered scenes.
3. Run structural, policy, continuity and capability validation.
4. Optional user review of allowed fields.
5. Freeze a versioned storyboard snapshot for the confirmed job.
6. Obtain quote and explicit confirmation; reserve credits.
7. Derive provider-specific execution payload from frozen snapshot.
8. Execute/monitor/reconcile segments or provider operation.
9. Validate resulting media metadata and content.
10. Persist output and library entry; mark success only after durable linkage.

Any user edit after confirmation creates a new storyboard version and requires revalidation and, if cost changes, a fresh quote/confirmation.

## 7. Failure handling
- Invalid storyboard: return to editable draft; no reservation/provider call.
- Capability unavailable: block dispatch and explain unavailable capability.
- Provider timeout/unknown result: RECONCILING; no blind duplicate request.
- Segment failure: retry only if provider evidence confirms safe idempotency/retry; otherwise reconcile and expose partial/failure.
- Continuity failure: do not label output accepted; use only approved repair path and within approved repair limit if one is later established.
- Persistence failure: preserve recovery state; do not mark success.
- Cancellation: reconcile actual provider usage before release/settlement.

## 8. Acceptance criteria
- No video provider call without a validated, versioned storyboard.
- Storyboard records exact context versions used.
- User review remains optional and limited to approved fields.
- Continuity is preserved where supported and limitations are explicit.
- Duration, category and format match product requirements.
- Provider-specific payloads are derived and traceable.
- Output is validated and saved to Content Library before success.
