---
name: amazon-listing-development-workflow
description: "Develop or optimize a complete Amazon listing from product, competitor, keyword, VOC, and performance evidence, automatically invoking relevant Amazon specialist skills and delivering a versioned candidate. Use for end-to-end new listing development, substantial or iterative listing optimization, and Feishu listing delivery."
---

# Amazon Listing Development Workflow

Own the end-to-end listing decision and delivery. Invoke relevant specialist skills within this run; the user does not need to name them in separate messages. Specialist findings feed this workflow's evidence ledgers. This workflow determines the final wording, review level, version, and delivery format.

## Route the request

- **Create mode:** no published link exists, or the user asks to develop a new product link. Read [references/create-listing.md](references/create-listing.md).
- **Optimize mode:** a product link is already selling or a reliable published listing exists. Read [references/optimize-listing.md](references/optimize-listing.md). A prior draft alone does not prove a link is live.
- A new candidate version of an already selling link remains Optimize mode. Classify the change as limited-field optimization or material restructuring before choosing the review level.

Always read [references/evidence-model.md](references/evidence-model.md). If the deliverable goes to Feishu, also read [references/feishu-delivery-contract.md](references/feishu-delivery-contract.md) and [references/workspace-routing.md](references/workspace-routing.md).

## Automatically invoke specialist skills

After the initial product and review preflight, select and read the `SKILL.md` of each specialist whose condition applies. Run its relevant analysis in this same workflow; do not ask the user to invoke it separately. Reassess selection when new evidence changes the task. Use only the smallest useful set, and do not generate a separate full report for every specialist unless requested. A `HOLD` or `BLOCK` product decision stops marketing-copy development.

| Task condition | Specialist skill to invoke |
|---|---|
| New listing needs search vocabulary, or an existing listing has an evidenced keyword gap | `amazon-keyword-research` |
| New listing needs market positioning, or an optimization depends on competitor comparison | `amazon-competitor-analysis` |
| Reviews, returns, Q&A, or other customer feedback are available and materially shape the copy | `amazon-review-analyzer` |
| Backend search terms are being created or changed | `amazon-backend-keywords` |
| The diagnosed issue is indexing, organic rank, or search visibility | `amazon-search-optimization` |
| Parent-child structure or variant-specific copy is in scope | `amazon-variation-strategy` |
| The requested deliverable includes image text/strategy or A+ content | `amazon-listing-images` or `amazon-a-plus-content`, respectively |

For a new complete listing, keyword discovery, direct-competitor analysis, and backend-term preparation normally apply. If source access or data is insufficient, record the limit and continue with supported evidence. Do not use `amazon-listing-optimization` as a second end-to-end writer inside this workflow; it remains available for standalone narrow copy or SEO tasks. Specialist templates and fixed scores do not override product facts, current marketplace rules, the user's scope, or this workflow's delivery contract.

## Required operating sequence

1. Resolve marketplace, product/SKU/ASIN, variant scope, actual source folders, confirmed live version, latest prior candidate, and initial product facts. Do not confuse historical drafts with the live listing.
2. Choose Create or Optimize mode and classify the review level. For a new link or material restructuring, follow the mode's regulatory preflight before marketing-copy work. For a limited edit to an already selling link, check changed fields and supporting facts; invoke the full review if the user requests it or the change raises a material policy, product-function, safety, fitment, certification, or claim risk.
3. If development may proceed, inventory available evidence and invoke the matching specialists above. Reconcile findings using the evidence model; scores are not an admission gate.
4. Build or update three logical ledgers: product facts, claims/evidence, and normalized keywords. They may contain unknown values. Complete the remaining Create or Optimize steps within the review decision.
5. Draft the fields supported by the decision: title, bullets, description, backend search terms, and requested fields. Never turn a `HOLD` or `BLOCK` decision into publish-ready wording.
6. Verify factual consistency, keyword placement, current backend requirements when applicable, variant accuracy, and target-language/Chinese correspondence. Check current authoritative sources when a policy, limit, or law affects the decision.
7. If Feishu delivery is requested, use the product's verified existing directory and the status-specific delivery contract. Create a new version document only where a suitable existing destination is confirmed; never overwrite an earlier version.
8. Re-fetch any created document and verify its content, version, review record, and actual parent folder. Report the exact title, path, URL, and unresolved gates.

## Missing information policy

Missing specifications, competitor metrics, advertising data, reviews, or conversion data do not by themselves stop an evidence-supported draft. A material product-function or regulatory uncertainty may stop publish-ready output even when other evidence is strong.

- Record unknowns as assumptions, confidence limits, or future validation items in the explanation table or gated review record.
- Omit invented numerical specifications and unsupported claims.
- Prefer conservative wording when evidence is partial.
- If a specific wording claim creates risk, remove or narrow it and continue where the review decision allows. A restricted product function or unresolved material risk cannot be cured by word changes.
- Never place `TBD`, internal notes, caveats, or uncertainty markers in the copy-ready listing table.

## Authorization boundary

Analysis and candidate-document creation do not authorize editing Seller Central, replacing the live version, moving documents between status folders, creating Feishu folders, deleting history, or changing permissions. Do those actions only when explicitly requested. If no suitable existing Feishu destination is confirmed, deliver the candidate in chat or another authorized location and report the directory gap; do not create a folder to satisfy a template.

## Output contract

For chat-only work, lead with copy-ready text when the review level permits it, then bilingual content and analysis.

For Feishu, use the status-specific contract in [references/feishu-delivery-contract.md](references/feishu-delivery-contract.md). This workflow's final format takes precedence over specialist output templates.
