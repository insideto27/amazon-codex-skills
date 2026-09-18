# Evidence Model

Use evidence scores to resolve conflicts and allocate confidence. Scores do not decide whether work may start.

## Weighted scoring

- Product relevance: 30%
- Factual reliability: 25%
- Recency: 15%
- Buyer-intent evidence: 15%
- Sample coverage: 10%
- Traceability: 5%

Reject wrong-marketplace, wrong-variant, obsolete, or demonstrably inapplicable sources regardless of score.

## Source hierarchy

| Source | Default score | Primary use |
|---|---:|---|
| Verified specifications, factory data, tests | 10.0 | Product truth |
| Fitment matrix and explicit exclusions | 10.0 | Compatibility boundaries |
| Certifications and claim substantiation | 10.0 | Performance, safety, and compliance claims |
| Actual package contents, dimensions, weight, materials | 9.8 | Physical accuracy |
| Actual sellable variation and configuration | 9.5 | Variant-specific copy |
| Own search-term and conversion data | 9.2 | Buyer intent and proven vocabulary |
| Brand Analytics or SQP | 9.2 | Search, click, and purchase evidence |
| Own reviews, returns, support, Q&A | 9.0 | Objections and conversion barriers |
| Current live listing and backend terms | 8.8 | Optimization baseline |
| Competitor keyword reverse-search data | 8.5 | Keyword demand and gaps |
| Competitor reviews and VOC | 8.5 | Pain points and customer language |
| Browse node, attributes, and category rules | 8.5 | Indexing and policy context |
| Competitor titles | 7.8 | Vocabulary, structure, positioning |
| Competitor bullets | 7.5 | Benefits, scenarios, objections |
| Competitor descriptions, A+, images, video | 7.2 | Content and visual coverage |
| Competitor price, rating, review count, BSR | 7.0 | Market positioning |
| Amazon autocomplete, Alexa, public Q&A | 6.8 | Long-tail and natural-language demand |
| Historical listing versions | 5.5 | Version archaeology only |
| Supplier marketing copy | 5.0 | Leads requiring verification |
| Generic keyword tools with unclear methodology | 4.5 | Supplemental discovery |
| Prior AI drafts | 4.0 | Version reference, never factual proof |

## Required logical ledgers

Maintain these in analysis, even when not materialized as separate files:

1. **Product facts:** field, value, source, date, variant, confidence, conflict.
2. **Claims:** claim, evidence, allowed wording, prohibited wording, status (`verified`, `conditional`, `hypothesis`, `prohibited`).
3. **Keywords:** normalized term, source, metric, relevance, intent, factual fit, competition, placement, coverage.

Unknown cells remain empty or explicitly unknown in analysis. They do not block drafting.

## Conflict handling

Prefer evidence closer to the physical product, more traceable, more recent, and more variant-specific. For ordinary uncertainty, use conservative copy and document the assumption. For safety, fitment, regulatory, certification, quantified-performance, warranty, or material-deception conflicts, do not choose silently; omit or narrow the claim and surface the issue in the explanation table.
