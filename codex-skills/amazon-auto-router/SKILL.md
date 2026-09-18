---
name: amazon-auto-router
description: Automatically classify and route every Amazon seller question to the smallest relevant set of installed Amazon skills. Use whenever the user mentions Amazon, Seller Central, ASIN, SKU, FBA, FBM, PPC, ACoS, TACoS, BSR, listing, keywords, reviews, competitors, sales, profit, pricing, inventory, returns, variations, compliance, appeals, sourcing, shipping, tariffs, or any Amazon marketplace. Also use for Feishu/Lark files that contain Amazon operations data.
---

# Amazon Auto Router

Automatically select the relevant specialist skills before answering or acting on an Amazon task.

## Required workflow

1. Classify the request using the routing table below.
2. Select the minimum set of specialist skills that fully covers the task.
3. Read every selected `SKILL.md` completely before taking task actions.
4. If the task includes Feishu/Lark data, also select the matching `lark-*` skill for the file type.
5. Separate verified facts, model assumptions, estimates, and missing inputs.
6. Use current primary sources for fees, policies, laws, program rules, or other time-sensitive claims.
7. Complete the requested analysis or change, verify outputs, and state exact document/file locations.

Do not load every Amazon skill by default. Prefer one primary skill and add supporting skills only when they materially change the result. When `amazon-listing-development-workflow` or `amazon-negative-keyword-batch-review` is primary, let that workflow select its own specialists within the same run; do not start a competing full workflow.

## Routing table

| User need | Primary skill | Add when needed |
|---|---|---|
| Product research, niche, demand, category | `amazon-product-research` | `amazon-niche-finder`, `amazon-trending-products`, `amazon-sales-estimator` |
| Competitors, storefronts, reviews, monitoring | `amazon-competitor-analysis` | `amazon-review-analyzer`, `amazon-seller-analytics`, `amazon-competitor-monitoring` |
| On-demand MT002 negative-keyword review from the Feishu manual workbook, prepared incremental search-term workbook, or a user-provided search-term report folder/file | `amazon-negative-keyword-batch-review` | The workflow checks prepared increments before legacy report files, writes clear supported negatives to the single ledger as `待投放`, stages only unresolved terms with Chinese translations, and promotes a user's `确认否定` to the same ledger on a later run. Its horizontal sheet is display-only. Select `amazon-negative-keywords` only when strategy or performance judgment requires it; use `lark-drive` for source files and `lark-sheets` for the workbooks |
| Keywords and search terms | `amazon-keyword-research` | `amazon-search-optimization`, `amazon-backend-keywords`, `amazon-keyword-tracker` |
| Standalone negative-keyword strategy or search-term waste diagnosis outside the MT002 manual batch | `amazon-negative-keywords` | `amazon-ppc-campaign` when campaign structure, bids, or budgets are also requested |
| PPC campaign build or optimization | `amazon-ppc-campaign` | `amazon-advertising-strategy`, `amazon-negative-keywords`, `amazon-dayparting-strategy`, `amazon-display-ads` |
| End-to-end new listing, substantial or iterative listing optimization, or versioned Feishu listing delivery | `amazon-listing-development-workflow` | The workflow automatically selects relevant Amazon specialists from the evidence and requested fields |
| Standalone narrow listing copy or SEO audit without full development or versioned delivery | `amazon-listing-optimization` | `amazon-backend-keywords` or `amazon-search-optimization` only when the field or diagnosis requires it |
| Listing policy and claim review | `amazon-listing-regulatory-review` | `amazon-product-compliance`, `amazon-suspension-appeal` |
| Profit, break-even, fees, price | `amazon-profit-analyzer` | `amazon-fba-calculator`, `amazon-shipping-calculator`, `tariff-calculator-amazon`, `amazon-repricing-strategy` |
| Inventory, restock, FBA prep | `amazon-inventory-management` | `amazon-fba-prep`, `amazon-seasonal-planning`, `amazon-shipping-calculator` |
| Returns and review strategy | `amazon-return-reduction` | `amazon-review-strategy`, `amazon-vine-program`, `amazon-review-analyzer` |
| Variations, bundles, promotions | `amazon-variation-strategy` | `amazon-product-bundling`, `amazon-coupon-strategy`, `amazon-deal-finder` |
| Brand, Store, A+, global markets | `amazon-brand-registry` | `amazon-storefront-design`, `amazon-enhanced-brand-content`, `amazon-global-selling`, `amazon-international-listings` |
| Suspension, restricted categories, compliance | `amazon-suspension-appeal` | `amazon-category-ungating`, `amazon-product-compliance`, `amazon-listing-regulatory-review` |

## Mandatory combinations

- A new product link or material restructuring of an existing listing uses `amazon-listing-regulatory-review` and its publication-decision gate before publish-ready copy. For a limited edit to an already selling link, check the changed fields; invoke the full review if the user requests it or the change raises a material policy, product-function, safety, fitment, certification, or claim risk. Do not label a focused check as a full regulatory review.
- Every profit decision must include `amazon-profit-analyzer`; add `amazon-fba-calculator` when FBA fees or break-even price are involved.
- PPC work that includes search-term waste or negative targeting uses `amazon-negative-keywords` unless the MT002 manual batch workflow is primary; that workflow invokes the specialist only for its stated conditions and owns its review-field output.
- Every product opportunity estimate based on BSR must distinguish sales estimation from profit estimation. BSR alone cannot establish profit.
- Every Feishu spreadsheet task must use `lark-sheets`; every Feishu cloud document task must use `lark-doc`; file and folder organization must use `lark-drive`.

## Evidence and calculation rules

- Never fabricate Seller Central, competitor, fee, sales, conversion, or inventory data.
- Treat list price, strike-through price, coupon price, and realized selling price as different values.
- For advertising economics, state whether the percentage is ACoS or TACoS. Use TACoS for total product profitability unless the user explicitly requests advertising-attributed profit.
- For returns, do not multiply price by return rate without explaining the loss model. Prefer `return rate × net loss per returned order`.
- For competitor profit, require or estimate price, referral fee, FBA fee, landed-cost range, ad-rate range, and return provision. Present a range, not false precision.
- Mark every temporary zero-cost input that can understate profit costs, such as storage, inbound placement, coupon fees, removal/disposal, and overhead.
- Quote formulas or show a calculation table when a recommendation depends on break-even, target margin, or restock economics.

## Output standard

Lead with the decision. Then provide the supporting calculations, assumptions, risks, missing data, and the next action. When creating or updating a file, include the exact normalized title, folder path, and clickable URL or absolute local path.
