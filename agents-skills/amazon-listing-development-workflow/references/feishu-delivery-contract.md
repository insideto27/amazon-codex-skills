# Feishu Delivery Contract

Use this contract whenever a listing candidate or review record is written to Feishu. It overrides specialist output templates. Select the document shape from the review level and actual publication decision; do not force publish-ready copy into a gated record.

## Document body

For a `PASS` full review, or a limited edit of an already selling listing that passed the focused changed-field check without triggering full review, the document contains at least three tables in this order. Metadata must state which review level was performed; a focused check must not be labeled `PASS` or described as a full regulatory review.

### Table 1: Copy-ready listing

Include only final target-market text that can be copied into Seller Central: title, each bullet, description, backend search terms, and user-requested listing fields.

Never include explanations, rationale, keyword markings, character counts, warnings, alternatives, Chinese translation, internal notes, or placeholders. Each field has one final candidate value.

If a claim is unsafe or unsupported, omit or safely rewrite it. Explain the decision only in Table 3. This table is unavailable when full review returns `CONDITIONAL PASS`, `HOLD`, or `BLOCK`.

### Table 2: Target language and Chinese

Use columns `Field`, `Target-language original`, and `Chinese translation`. Split bullets into separate rows. The target-language cells must match Table 1 exactly. Translation must not modify the original copy.

### Table 3: Version explanation

Keep every explanation here: version objective, source evidence, keyword allocation, changes from prior version, rationale, assumptions, review level and scope, compliance treatment, expected effect, validation metric, observation window, and rollback condition.

## Gated full-review decisions

- `CONDITIONAL PASS`: create a clearly marked pre-release record. Keep gated fields outside any ready-to-paste section, visibly mark the draft and exact fields that await verification, provide target-language/Chinese correspondence only for text actually drafted, and list the evidence and owner/action needed to release each gate. Do not present the document as publishable.
- `HOLD` or `BLOCK`: deliver the decision, reasons, checked sources, evidence checklist, and next action. Do not include a copy-ready listing or disguised replacement wording. A three-table listing is not required.

Record the exact marketplace, product/variant, review date, reviewed surfaces, unavailable surfaces, and decision for a full review. Check current authoritative sources during that review; do not reuse an old decision as current approval.

## Versioning

Any textual change creates a new document and version number. Never overwrite a prior version or append multiple listing versions to one document.

Recommended title:

`Amazon | <marketplace> | <SKU-or-ASIN> | Listing | <version-type> | Vx.y | YYYY-MM-DD`

- Use V1.0 for the first publishable version; a gated pre-release draft uses V0.x or an explicitly non-publishable review-record label.
- Increment the major version for a material positioning or structure change.
- Increment the minor version for keyword placement, localized copy, or limited field changes.
- The explanation or review record must identify the prior version; use `None` for the first version.

## Post-write verification

Re-fetch the Feishu document and verify:

1. For a ready-to-use version, at least three tables exist in the required order; Table 1 is free of diagnostic text and Table 2 target-language content equals Table 1.
2. For a gated record, no table or section is presented as copy-ready; the decision, blocked or conditional fields, and release evidence are visible.
3. The rationale, review level, prior-version reference, and version identifier match this exact candidate.
4. The version is unique and the document is in the verified existing destination folder.
5. A full regulatory review is recorded only when actually performed for this exact version; a focused changed-field check is labeled as such.
