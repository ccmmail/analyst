# Equity Analyst

A research agent for building rigorous, source-backed equity investment memos.

This repo is designed for company deep dives that combine business analysis, financial modeling, valuation, and recent-development tracking into a single investment view. The goal is not just to summarize a company, but to produce an actual opinion that is useful for an investor.

## What this repo is for

Use this repo when you want to:
- evaluate a public or private company as a potential investment
- refresh a thesis after earnings, news, or strategic changes
- compare a company against key competitors
- build a structured memo with supporting analysis and source materials

The expected output is a written investment report plus whatever supporting work is needed to justify it, such as models, charts, decomposition tables, and saved reference documents.

## What the agent is expected to do

The agent should behave like a strong equity analyst:
- form a clear buy / sell / neutral view
- support conclusions with evidence
- be explicit about assumptions and uncertainty
- compare the view against consensus when relevant
- be willing to make a contrarian call if the facts support it

The detailed behavioral and output specification lives in `AGENTS.md`.

## Typical workflow

1. Pick a target company and define the core investment question.
2. The agent will do its own research, but also reference additional materials such as industry research that you provide it. 
3. Run agent to get an investment memo

## Repo structure

```text
analyst/
  <investment_name>/
    report_<investment>_<date>.md
    supporting_analysis/
    reference_materials/
```

### Folder guidance

#### `report_<investment>_<date>.md`
The main investment memo.

#### `supporting_analysis/`
Anything created during analysis, for example:
- spreadsheets or models
- Python scripts
- charts
- decomposition tables
- sensitivity analyses

#### `reference_materials/`
Documents used as inputs, for example:
- 10-Ks / 10-Qs / annual reports
- earnings decks
- transcripts
- investor presentations
- industry reports
- press releases

## Output expectations

A standard report should cover:
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

The exact required section structure is defined in `AGENTS.md`.

## Research standards

A good report in this repo should be:
- **source-backed**: major claims should trace to filings, disclosures, reputable industry sources, or clearly labeled assumptions
- **numerically consistent**: tables, forecasts, and valuation outputs should reconcile
- **decision-useful**: the writeup should help an investor decide what to do
- **clear about uncertainty**: separate reported facts from estimates and judgment

A few practical rules:
- prefer primary sources when possible
- label internally estimated figures clearly
- explain estimation methods when company disclosures are incomplete
- avoid false precision
- separate structural changes from short-term noise

