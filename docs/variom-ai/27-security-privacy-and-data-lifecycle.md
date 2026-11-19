# VARIOM — Security, Privacy & Data Lifecycle

**Version:** 1.0 | **Status:** NORMATIVE DRAFT — security baseline; legal details deferred | **Authority:** Documents 19–26; VAR-OD-008–010.

## 1. Purpose
Defines minimum security, privacy and lifecycle controls for future design and implementation. It is not legal advice and does not determine jurisdiction-specific retention periods or consent wording. Those require legal review before launch.

## 2. Security objectives
- Enforce account and brand tenant isolation on every server operation.
- Protect credentials, sessions, prompts, Brand DNA, uploaded media, generated outputs and financial records.
- Prevent unauthorized media access, cross-tenant disclosure, unsafe uploads, prompt injection and provider-secret leakage.
- Preserve ledger integrity and traceability.
- Make deletion reliable across primary storage, derived records, processors and backups.

## 3. Authentication and session controls
- First release: email/password, email verification and email password recovery.
- Store only appropriately salted password hashes through a reviewed authentication mechanism; never log passwords, recovery tokens or session secrets.
- Apply rate limits and abuse detection to registration, login, verification and recovery.
- Recovery tokens are single-use, short-lived and invalidated after use or credential change.
- Sessions have explicit expiry, revocation and rotation rules; sensitive account actions require renewed authentication where risk warrants.
- Avoid account enumeration in authentication/recovery responses.
- Social login is excluded by default.

## 4. Authorization and tenant isolation
- Deny by default; authorize every read, write, list, preview, download, delete and job-state operation server-side.
- Derive account context from authenticated identity, not request body.
- Verify that every brand, task, character, asset, job and library entry belongs to that account and that related records form a valid ownership chain.
- Never trust client-supplied storage paths or provider IDs.
- Prevent insecure direct object reference, cross-account enumeration and cross-brand leakage.
- Background workers must carry a verified account/brand scope and enforce it when reading/writing.
- No team/member/shared-account permissions are implied.

## 5. Data classification and handling
| Data class | Examples | Minimum controls |
|---|---|---|
| Authentication secrets | Password hash, session/recovery tokens | Restricted access, secure hashing/storage, never log |
| Account personal data | Email, preferences | Minimize, access-controlled |
| Brand confidential data | Brand DNA, strategy, prompts, copy | Private, account/brand-scoped, restricted provider transfer |
| Uploaded media | Product photos, logos, source videos, character references | Private quarantine, type/size/content validation, malware scanning where applicable |
| Generated media | Images, videos, text, storyboard | Private by default, authorized preview/download |
| Financial/security records | Credit ledger, settlement, security events | Integrity, auditability, restricted access, separate retention |
| Provider evidence/operations | Model, region, cost, correlation IDs | No secrets; minimize user payloads and access |
| Controlled reference data | Taxonomies/styles | Versioned, provenance and approval status |

## 6. Upload and media security
- Validate actual file content, not only extension or client MIME.
- Apply size, duration, dimension and file-count limits once verified and documented.
- Quarantine uploads until validation completes.
- Reject malformed, executable or unsupported files; prevent path traversal and parser abuse.
- Strip or control sensitive metadata where appropriate; preserve only metadata needed for product behavior.
- Store private media outside public web roots or equivalent protected storage.
- Use short-lived authorized preview/download access; never expose permanent public URLs by default.
- Apply malware scanning and safe transcoding where supported by chosen infrastructure.
- Keep original editing source immutable; generated/edited outputs are separate assets.

## 7. Prompt injection and AI-specific risks
- Treat user text, uploaded image/video metadata, retrieved documents and provider outputs as untrusted data, not instructions.
- System and owner-approved product policy cannot be overridden by prompt content.
- Prevent prompts from requesting secrets, cross-account data or hidden instructions.
- Minimize data sent to providers; send only task-required context.
- Validate provider outputs and metadata before persistence/display.
- Record provider/model/version and evidence references without storing unnecessary sensitive request payloads.
- Never claim real-person likeness/voice rights based only on user assertion when policy requires evidence.

## 8. Provider data boundary
Before any provider is used with real user data, verify and record:
- provider identity and account/region availability;
- data processing terms, retention, training use, deletion and subprocessors;
- rights to submitted inputs and generated outputs;
- permitted use cases and safety controls;
- security/authentication method and secret handling;
- supported capabilities, limits, pricing and failure semantics.
No provider activation or paid generation is authorized by this document. If required terms are unknown, use no real user data with that provider.

## 9. Logging, audit and secrets
- Never log passwords, tokens, API keys, private signed URLs or full sensitive media/prompt payloads by default.
- Use structured logs with correlation IDs and minimal identifiers.
- Audit security-sensitive actions, account/brand changes, deletion, credit mutations and provider operation outcomes.
- Restrict log access and define retention with legal/operational review.
- Keep secrets outside source control and client bundles; production secret management requires a managed secret/KMS decision.
- Rotate and revoke compromised credentials; document incident response in B-14.

## 10. Data lifecycle and deletion
Deletion is a workflow, not a single row delete:
1. Authenticate/reauthenticate and verify ownership.
2. Record deletion request and scope.
3. Prevent new use of the targeted resource where required.
4. Identify dependent records, assets, jobs, derived outputs and provider copies.
5. Delete or de-identify user content across primary stores and processors according to verified capability.
6. Include backup expiry/purge process; backups must not silently reintroduce deleted data.
7. Retain only minimized financial/security records where a documented legal basis requires it.
8. Record completion, exceptions and unresolved processor/backup actions.

Separate controls are required for output deletion, Brand deletion and Account deletion. Removing a library entry must not accidentally destroy a shared media object still referenced by another authorized record. Conversely, a deletion request must not leave orphaned private content indefinitely.

**Deferred:** exact retention periods, statutory exceptions, legal basis, user-facing legal text, backup purge windows and processor deletion SLAs require the first-market decision and legal/provider evidence. Do not invent durations.

## 11. Privacy principles
- Data minimization and purpose limitation.
- Private by default.
- Transparent provider transfer and user control.
- Separate content from financial/security retention.
- No sale or unrelated reuse of user content.
- Do not use real-person likeness/voice without applicable rights and consent.
- Support Arabic/English privacy-facing UX after legal copy is approved.

## 12. Incident and vulnerability handling
B-14 must define severity, triage, containment, evidence preservation, notification/legal assessment, recovery and post-incident review. Security findings affecting tenant isolation, credential exposure, private media or ledger integrity are release blockers.

## 13. Acceptance criteria
- Cross-account and cross-brand negative tests pass.
- Every resource operation has server-side authorization.
- Upload and download paths are private and validated.
- Secrets and sensitive payloads are absent from logs.
- Provider data handling is evidence-backed before real user data is sent.
- Deletion covers primary data, dependencies, processors and backup semantics.
- Legal/retention unknowns remain explicit launch blockers.
