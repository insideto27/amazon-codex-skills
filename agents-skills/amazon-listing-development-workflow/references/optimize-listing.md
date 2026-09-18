# Optimize Mode

Optimize by diagnosing the current constraint and making the smallest justified change. Do not rewrite everything by default.

## Workflow

1. Freeze the current live version with marketplace, ASIN/SKU, variant, and timestamp.
2. Identify the latest prior iteration separately from the live version.
3. Classify the requested change. A limited-field edit preserves the product function, positioning, core claims, and variation structure. Material restructuring changes those elements or substantially rewrites the listing. Use the actual change, not document version number or sales status alone.
4. Audit title, bullets, description, backend terms, attributes, images, A+, and variation structure as needed to identify the constraint and keep changed fields consistent.
5. Collect available search terms, PPC conversions, organic rank, indexing, CTR, CVR, reviews, returns, Q&A, and support feedback.
6. Compare against current competitor, keyword, and category evidence when it affects the proposed change.
7. Diagnose each issue as indexing, traffic, click-through, conversion, factual mismatch, or compliance.
8. Preserve proven wording, indexed terms, and converting concepts unless stronger evidence justifies change.
9. For a limited edit, check changed fields against verified product facts and obvious policy or claim risks without automatically running a full regulatory review. Invoke `amazon-listing-regulatory-review` before publish-ready output if the edit adds or changes a material claim, fitment, certification, safety statement, restricted function, or the user asks for a compliance audit.
10. For material restructuring, invoke the full regulatory review and obtain its publication decision before preparing publish-ready wording. Follow `PASS`, `CONDITIONAL PASS`, `HOLD`, or `BLOCK` delivery rules.
11. Draft only evidence-backed changes within the review result and maintain marketplace-appropriate natural language.
12. Record before/after changes, evidence level, review level and reason, expected effect, observation window, metric, and rollback condition.

## Incomplete-performance-data behavior

Optimization still proceeds. Classify each conclusion as:

- **Performance validated:** supported by own search, traffic, or conversion data.
- **Market evidenced:** supported by competitors, keyword research, VOC, or category data.
- **Structural inference:** supported by copy quality, indexing logic, or consistency analysis.

Small samples justify tests, not permanent conclusions. State the sample limit in the explanation table.

## Version discipline

Every change produces a new candidate document. Do not overwrite the live or prior iteration. Promotion to current-published status and movement of the displaced live version to history require explicit user direction or verified publication status.
