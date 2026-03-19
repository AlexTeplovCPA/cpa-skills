# cpa-skills

Practice-tested AI workflow skills for CPAs and bookkeepers.

Most AI tools in accounting are built by people who understand LLMs. These are built by someone who also does the month-end.

This repository is a collection of structured AI instruction workflows designed to handle the repeatable, data-heavy parts of accounting work so practitioners can focus on professional judgment.

## Current Build: bookkeeping-review

The current focus is a structured review of bookkeeping exports before CPA sign-off. This skill identifies accounting anomalies and classification errors that a human reviewer might miss during a high-volume month-end.

## What is a Skill?

A skill is a folder containing a SKILL.md file that teaches an AI agent how to perform a specific task consistently. The SKILL.md file includes a YAML frontmatter block with a name and description, followed by the full instructions in Markdown.

Unlike a one-off prompt, a skill defines a fixed objective, required inputs, and a structured output format. It functions as a reusable operational playbook: the agent discovers and loads it automatically when the task matches the skill's description, without re-explaining the instructions each time.

Skills follow the open Agent Skills standard and work identically across Claude, OpenAI Codex, and Google Gemini CLI.

## Workflow Pipeline

These skills mirror the actual flow of work inside a Canadian accounting practice.

```
documents
   ↓
01-ingestion
(receipts, invoices → structured data)
   ↓
02-classification
(vendor mapping, tax treatment)
   ↓
03-reconciliation
(bank feeds → ledger entries)
   ↓
04-review
(anomaly detection, bookkeeping-review)
   ↓
05-communication
(client query generation)
   ↓
06-tax
(gsthst / t1 / t2)
```

Earlier skills prepare and structure accounting data. Later skills analyze the ledger and flag issues that require professional review. This reflects how accounting work actually happens: most of the effort is spent preparing and validating data before CPA judgment is applied.

## Skill Roadmap

| Category | Skill | Status |
|---|---|---|
| 04-review | bookkeeping-review | Active build |
| 01-ingestion | document-processing | Roadmap |
| 02-classification | transaction-categorization | Roadmap |
| 02-classification | vendor-mapping | Roadmap |
| 03-reconciliation | bank-reconciliation | Roadmap |
| 04-review | ledger-anomaly-detection | Roadmap |
| 05-communication | client-query-generator | Roadmap |
| 06-tax | gsthst | Roadmap |
| 06-tax | t1 | Roadmap |
| 06-tax | t2 | Roadmap |

## Repository Structure

Each skill is a self-contained folder with a SKILL.md file. Optional `scripts/`, `references/`, and `assets/` subdirectories can be added inside a skill folder as needed.

```
01-ingestion/
   document-processing/
      SKILL.md

02-classification/
   transaction-categorization/
      SKILL.md
   vendor-mapping/
      SKILL.md

03-reconciliation/
   bank-reconciliation/
      SKILL.md

04-review/
   ledger-anomaly-detection/
      SKILL.md
   bookkeeping-review/
      SKILL.md
      references/
      scripts/

05-communication/
   client-query-generator/
      SKILL.md

06-tax/
   gsthst/
      SKILL.md
   t1/
      SKILL.md
   t2/
      SKILL.md

examples/
   ledger-export.csv
   bank-statement.csv
   receipts/
      sample-receipt-01.pdf
      sample-receipt-02.pdf
   tax-package/
      t1-sample-documents/
```

## Installation

**Claude (claude.ai):**

1. Download or clone this repository
2. Zip the skill folder you want to install (e.g. `bookkeeping-review.zip`)
3. Go to Settings > Capabilities > Skills > Upload skill

The agent discovers and loads the skill automatically when relevant.

**Claude Code:** Place the skill folder in `~/.claude/skills/`. Claude Code discovers skills automatically.

**OpenAI Codex:** Place the skill folder in `~/.agents/skills/`. Codex discovers skills automatically.

**Google Gemini CLI:** Place the skill folder in `~/.gemini/skills/` or `~/.agents/skills/`. Gemini CLI discovers skills automatically.

These skills follow the open Agent Skills standard and work across all compatible agents without modification.

## How to Use a Skill

Once installed, the agent discovers and loads the relevant skill automatically based on your request. You do not need to invoke it manually.

Example:

```
request  → "review this bookkeeping export before sign-off"
agent loads → bookkeeping-review
input    → ledger-export.csv
output   → flagged transactions and review notes
```

For explicit invocation in Claude Code or Codex CLI, reference the skill by name in your prompt.

## Project Principles

**Judgment over automation.** The goal is not a hands-off workflow. The goal is to surface the right information so the CPA can make a faster, better decision.

**Field tested.** Every skill in this repo is tested against real scenarios from two specific domains: Canadian self-employed professionals and e-commerce sellers.

**Iterative build.** This is an active log. As CRA interpretations change or new edge cases appear in practice, these skills are updated.

## Related Repositories

**selfemployed-skills** Tax and bookkeeping workflows specifically for Canadian IT contractors, mortgage agents, trades, and real estate professionals.

**ecommerce-skills** Specialized workflows for marketplace reconciliation, inventory, COGS treatment, and HST handling for Canadian e-commerce sellers.

## About

Built by [Alex Teplov, CPA](https://www.linkedin.com/in/alex-teplov/).

I run two specialized accounting practices in Canada and build these workflows to solve operational bottlenecks encountered in real accounting work.
