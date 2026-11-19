# P1 visual reference audit

Status: working review, 2026-10-28

## Changes in this pass

- Replaced the weak editorial/model-and-horse reference for `P1-013` (Packaged Product Photography) with the Sadan Perfumes product-photography portfolio. The page describes a product photography set for a perfume company based in Saudi Arabia and Libya; direct inspection of individual images is still required before claiming it demonstrates packaging views.
- Assigned `P1-009` (Top-Down Product Photography) to Klaud9's NIVEA flat-lay case study, whose page explicitly describes a flat-lay shoot and overhead-style product compositions.
- Assigned `P1-014` (Ingredient or Component Layout) to dpix's Iylah cosmetic photography case study, which describes ingredient-led fragrance flat lays.
- Assigned `P1-018` (Composited Product Scene) to the Ibrahim Al Qurashi CGI perfume project rather than a generic promotional-image portfolio page.
- Retained link-only rights status. A publicly accessible page does not grant permission to reuse its images or reproduce its distinctive design.
- Added five representative P1 selection fixtures. They are human-review test cases, not proof that a ranking engine exists or that a style will perform commercially.

## Sources

- Sadan Perfumes Product Photography — https://www.feels.digital/photography/sadan-perfumes-product-photography/
- NIVEA Flat Lay Product Photography Case Study — https://klaud9.com/case-studies/nivea-skin-care
- Iylah Cosmetic Product Photography — https://dpix.co.uk/case-studies/case-study-iylah/
- Ibrahim Al Qurashi CGI Perfume Animation — https://www.behance.net/gallery/154266699/CGI-Perfume-Animation-Ibrahim-Al-Qurashi

## Remaining review items

- Open each source and inspect the actual frames before accepting style-to-reference fit.
- Verify source credits and whether each page is a client campaign, portfolio concept, or technical exercise.
- Confirm each visual principle is visible in the linked work; keep performance evidence separate.
- Run a formal JSON Schema validator in CI before production import. The prior lightweight local check is not equivalent to a dedicated standards-compliant validator.
- Keep `data/styles.seed.json` as schema/example material; do not concatenate it blindly into the P1 import dataset because it contains a duplicate `P1-001` identifier.
