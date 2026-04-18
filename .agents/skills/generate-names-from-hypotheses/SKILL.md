---
name: generate-names
description: Generate candidate public-market long, short, and underweight names from the active hypotheses in synthesized_implications.md.
---

Read:
`equity-analyst/notes/synthesized_implications.md`

Task:
Read `equity-analyst/notes/synthesized_implications.md` and generate candidate public-market investment ideas from the hypotheses in the **Active hypotheses** section only.

Ignore all hypotheses in **Candidate hypotheses not yet promoted**.

Your job is not to produce a loose thematic watchlist. Your job is to identify the cleanest potential market expressions of each active hypothesis.

Process:
1. For each active hypothesis:
   - Restate the hypothesis in 1 sentence for yourself.
   - Identify 2-4 concrete transmission mechanisms that connect the hypothesis to company-level outcomes.
   - Use those mechanisms to generate candidate public-company names.
2. For each active hypothesis, generate:
   - 3-5 potential longs
   - 3-5 potential shorts or underweights
3. For each company, decide whether it is better framed as:
   - `Long`
   - `Short`
   - `Underweight/Avoid`

Selection rules:
- Do not simply repeat the illustrative public proxies named in `synthesized_implications.md`.
- You may include overlap with those names, but only if they still appear to be among the best expressions after independent reasoning.
- Prefer clean expressions over thematic adjacency.
- Penalize weak proxy names.
- It is acceptable to produce fewer than 5 names if there are not enough good candidates.
- It is acceptable to produce no clean short for a hypothesis if the short expression is weak.
- In cases where the downside thesis is real but the short expression is weak, label the name `Underweight/Avoid` instead of `Short`.
- Avoid duplicate names across hypotheses unless the company fits multiple hypotheses for clearly different reasons.

Rationale rules:
- Each rationale must be specific to the company.
- Do not use vague wording like “AI beneficiary” or “AI loser” without explaining the mechanism.
- Tie the rationale back to the actual business model, distribution advantage, product surface, workflow ownership, customer base, cost structure, pricing model, competitive position, or valuation setup.
- Where relevant, explain the effect through one or more of the following:
  - TAM expansion through new use cases or new customer segments
  - TAM expansion through budget share shift or market structure change
  - pricing power
  - distribution advantage
  - customer switching friction
  - capital intensity
  - multiple expansion
  - multiple compression
- Do not include a company unless the rationale can point to at least one concrete mechanism by which the hypothesis should matter economically.

Output:
Write the results to:
`equity-analyst/notes/names.md`

Organize the output by hypothesis, with one markdown table per hypothesis.

Use this exact format:

# Public-market expressions from active hypotheses

## <Hypothesis title>

| Company | Ticker | View | Exposure Type | Transmission Mechanism | Rationale | Confidence | Time Horizon | Related Hypothesis |
|---|---|---|---|---|---|---|---|---|
| <Company> | <Ticker> | Long / Short / Underweight/Avoid | Direct / Indirect / Proxy | <specific mechanism that links the hypothesis to this company> | <brief company-specific rationale> | High / Medium / Low | Near-term / Medium-term / Long-term | <concise hypothesis title> |

Definitions:
- `View` must be one of:
  - `Long`
  - `Short`
  - `Underweight/Avoid`
- `Exposure Type` must be one of:
  - `Direct`
  - `Indirect`
  - `Proxy`
- `Confidence` must be one of:
  - `High`
  - `Medium`
  - `Low`
- `Time Horizon` refers to when the business impact from the hypothesis is most likely to become economically meaningful for the company, not when the stock price is expected to move.
- `Time Horizon` must be one of:
  - `Near-term` = next 180 days
  - `Medium-term` = 180 days to 2 years
  - `Long-term` = more than 2 years

Additional guidance:
- `Direct` means the company is tightly exposed to the mechanism of the hypothesis.
- `Indirect` means the company benefits or suffers through a second-order effect.
- `Proxy` means the company is only a partial or imperfect market expression.
- `Transmission Mechanism` should be concrete and specific, not generic. Examples: `owns enterprise workflow distribution`, `benefits from AI data-center cooling demand`, `faces feature-speed moat compression`, `depends on flat-rate monetization for heavy AI usage`, `exposed to labor-arbitrage margin pressure`, `could see multiple expansion as the market re-rates scarce infrastructure exposure`.
- `Confidence` should reflect how clean and well-supported the expression is, not general confidence that the stock will outperform.
- Keep the rationale concise enough to fit cleanly into a table that will later be imported into Google Sheets.
- Be conservative.
- Fewer high-quality rows are better than many weak ones.
- Do not force symmetry between long and short ideas if the hypothesis produces cleaner expressions on one side.