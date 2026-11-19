# VARIOM — Creative Intelligence & Style Registry Contract

**Version:** 1.0 | **Status:** NORMATIVE DRAFT — registry governance | **Authority:** Documents 00, 19–29.

## 1. Purpose
Defines controlled taxonomies, creative-style governance and internal selection boundaries. It prevents MAX archives or candidate lists from becoming production-approved styles automatically.

## 2. Separate dimensions
The system MUST keep these concepts distinct:
- **Marketing objective:** one of the eight approved goals.
- **Content category:** Image P1–P4 or Video V1–V4.
- **Topic/idea:** subject and message of an individual content item.
- **Format:** approved product-level orientation/format.
- **Production method:** workflow/provider execution approach.
- **Copywriting approach:** narrative/text treatment.
- **Creative Style:** internal visual/creative direction applied to a task.

No dimension is inferred solely from another.

## 3. Approved product taxonomies
Marketing objectives: Brand Awareness, Product Awareness, Product Launch, Campaign Launch, Sales Growth, Engagement, Lead Generation, Trust Building.

Image categories: P1 Product Showcase; P2 Static Ad; P3 Carousel; P4 Lifestyle.
Video categories: V1 UGC; V2 Product Demo; V3 Motion Graphics; V4 Story/Testimonial.

P3 Carousel is an Image Studio category and MUST NOT create carousel items in Monthly Content.

## 4. Creative Style record
Each style record includes:
- stable identifier and version;
- concise name/description;
- modality and compatible category;
- visual/creative attributes in controlled vocabulary;
- source provenance (repository, branch, commit, path/section);
- status: candidate, under review, approved, deprecated, rejected;
- reviewer/approval evidence and date;
- known constraints and compatibility notes.

Only APPROVED active styles may be selected for production. Candidate or historical records remain unavailable.

## 5. Selection behavior
- Detailed style selection is internal; users do not navigate a long technical style menu.
- Selection considers task category, brief, Brand DNA, reference inputs and verified capability.
- Selection result and style version are recorded with the task for provenance.
- If no compatible approved style exists, use only an explicitly approved neutral fallback or block/ask for a valid option; do not invent an approved style.
- The system must not fabricate brand facts or imply a style is guaranteed to produce a particular output.

## 6. MAX source adoption
No blanket adoption of MAX's historical or candidate style inventory is authorized. For each candidate mapping, record exact source repo/branch/commit/path/section, original status, VARIOM adaptation and review status under Document 19. The existence of 144 candidate styles or other MAX records does not constitute VARIOM approval.

## 7. Versioning and retirement
- Changes to style meaning/attributes create a new version.
- Jobs pin selected style version.
- Deprecation blocks new selection but preserves historical references.
- Removal/rejection requires provenance and review record.
- Taxonomy code changes require compatibility review against requirement IDs and saved tasks.

## 8. Acceptance criteria
- Taxonomy dimensions remain distinct.
- P1–P4/V1–V4 and objectives match Product Vision.
- No unapproved candidate is production-selectable.
- Every selected style has provenance, approval and version.
- Selection remains internal and task-specific.
- Monthly Content cannot produce carousel items.
