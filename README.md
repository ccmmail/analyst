# Equity Analyst

A source-backed equity research repo organized around reusable Codex skills.

This repo is for producing actual investing work: company memos, supporting analysis, saved source material, and public-market name generation from higher-level hypotheses. The goal is not to summarize companies, but to produce decision-useful views with clear evidence, explicit assumptions, and traceable sources.

## How it works now

The workflow has been refactored from a single agent prompt into task-specific skills under `.agents/skills/`.

- `AGENTS.md` defines the analyst behavior, sourcing standards, and repo conventions.
- `.agents/skills/create-investment-memo/SKILL.md` defines the company memo workflow.
- `.agents/skills/generate-names-from-hypotheses/SKILL.md` defines the hypothesis-to-names workflow.

## Skills

### `create-investment-memo`

Use this skill to build a company investment memo.

- Output: `notes/<company>/report_<company>_<date>.md`
- Purpose: produce a full writeup covering summary, company overview, revenue and margin decomposition, financials, management and investors, valuation, recent developments, catalysts, and sources
- Inputs: company research conducted by the agent plus any reference materials you add to the repo

### `generate-names`

Use this skill to turn active hypotheses into investable public-market expressions.

- Input: `notes/synthesized_implications.md`
- Scope: reads the `Active hypotheses` section only
- Output: `notes/names.md`
- Purpose: generate candidate `Long`, `Short`, and `Underweight/Avoid` names with explicit transmission mechanisms and company-specific rationale

## Typical workflow

1. Maintain top-down views in `notes/synthesized_implications.md`.
2. Run `generate-names` to convert active hypotheses into candidate public-market names in `notes/names.md`.
3. Pick a target company and run `create-investment-memo`.
4. Save any models, charts, scripts, or source documents alongside the company note.

## Repo structure

```text
.agents/
  skills/
    create-investment-memo/
    generate-names-from-hypotheses/
notes/
  synthesized_implications.md
  names.md
  <company>/
    report_<company>_<date>.md
    supporting_analysis/
    reference_materials/
```

### Folder guidance

#### `notes/<company>/report_<company>_<date>.md`

The main investment memo for a company.

#### `notes/<company>/supporting_analysis/`

Artifacts created during the work, for example:

- spreadsheets or valuation models
- Python scripts
- charts
- decomposition tables
- sensitivity analyses

#### `notes/<company>/reference_materials/`

Input documents used during analysis, for example:

- 10-Ks / 10-Qs / annual reports
- earnings decks
- transcripts
- investor presentations
- industry reports
- press releases

## Research standards

Work in this repo should be:

- **source-backed**: major claims should trace to filings, disclosures, reputable industry sources, or clearly labeled assumptions
- **numerically consistent**: tables, forecasts, and valuation outputs should reconcile
- **decision-useful**: the writeup should help an investor decide what to do
- **clear about uncertainty**: reported facts, estimates, and judgment should stay distinct

Practical rules:

- prefer primary sources when possible
- label internally estimated figures clearly
- explain estimation methods when disclosures are incomplete
- avoid false precision
- separate structural changes from short-term noise

## Output expectations

A standard investment memo should cover:

- summary recommendation
- simple business overview
- detailed company and industry overview
- revenue and gross margin decomposition
- historical and forecast financials
- management team and investor base
- valuation versus peers
- recent developments from the last 180 days
- top price catalysts
- footnotes and sources

The detailed memo structure and behavior live in `AGENTS.md` and the individual skill definitions.
