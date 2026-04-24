# cpa-skills

Practice-tested AI workflow skills for CPAs and bookkeepers.

This repository is a public, profession-facing library of structured AI workflows built around real accounting work. The focus is not generic prompting. It is repeatable workflow design for the parts of tax and bookkeeping work that are structured, reviewable, and worth standardizing.

Most AI tools in accounting are built by people who understand LLMs. These are built by someone who also does the month-end.

## Repository Purpose

This repository exists to explore what useful AI workflow design looks like inside a real accounting practice.

The goal is to build reusable skills that reflect how accounting work actually moves through a firm: collecting documents, organizing data, reconciling records, reviewing outputs, preparing follow-up, and supporting tax work. This is meant to be practical, iterative, and open to discussion.

This repository is practitioner-facing. It is separate from the client-facing repositories:

- [**it-contractors-skills**](https://github.com/alexteplovcpa/it-contractors-skills) — preparation workflows for Canadian IT contractors
- [**ecommerce-skills**](https://github.com/alexteplovcpa/ecommerce-skills) — accounting workflows for Canadian e-commerce sellers

## How This Repository Fits the Broader System

This repository is the practitioner-facing layer in a three-repository system:

- `cpa-skills` — practitioner-facing workflow library for CPAs, bookkeepers, and accountant-adjacent AI users
- `it-contractors-skills` — client-facing preparation workflows for Canadian IT contractors
- `ecommerce-skills` — client-facing preparation workflows for Canadian e-commerce sellers

The role of `cpa-skills` is to make the accounting workflow method visible. The client-facing repositories show how that method is applied to specific niches.

## Why This Repository Exists

There is a gap between deep technical accounting knowledge and consistent execution of repeatable work inside a practice.

A large share of accounting work is not pure judgment. It is preparing, organizing, spotting issues, following up, and reviewing. Those are the areas where structured AI workflows can help most, if they are built carefully and grounded in actual firm work.

This repository is an attempt to make that layer visible, testable, and reusable.

## What a Skill Is

A skill is a folder containing a `SKILL.md` file that teaches an AI agent how to perform a specific task consistently.

The `SKILL.md` file includes:

- YAML frontmatter with a `name` and `description`
- workflow instructions in Markdown
- optional supporting files such as `references/`, `scripts/`, and `assets/`

Unlike a one-off prompt, a skill is meant to be reusable. It defines a repeatable task, expected inputs, and a structured output pattern.

## Current Focus

The current flagship skill is `reviewing-bookkeeping`.

This skill is designed to review bookkeeping exports before CPA sign-off. It looks for anomalies, classification problems, and review points that can be missed in high-volume work when attention is limited and time is compressed.

The build is intentionally starting narrow. The goal is to make one workflow genuinely useful before expanding the library.

## Workflow Pipeline

These skills are organized around the actual flow of work inside a bookkeeping or tax practice.

```text
documents
   ↓
processing-documents
(receipts, invoices → structured data)
   ↓
categorizing-transactions
(vendor mapping, tax treatment)
   ↓
reconciling-records
(bank feeds → ledger entries)
   ↓
reviewing-bookkeeping
(anomaly detection, review workflow)
   ↓
generating-client-queries
(client follow-up and clarification)
   ↓
preparing-tax-files
(gst-hst / t1 / t2)
```

Earlier skills prepare and structure accounting data. Later skills review that data, surface issues, and support practitioner decision-making. The point is not to automate judgment away. The point is to improve the quality and consistency of the workflow before judgment is applied.

## Current and Planned Skills

| Category | Skill | Status | Notes |
|---|---|---|---|
| reviewing | reviewing-bookkeeping | Active | Current flagship build |
| reviewing | detecting-ledger-anomalies | In progress | Adjacent review workflow |
| generating | generating-client-queries | In progress | Follow-up support after review |
| researching | researching-tax-questions | Active | T1, GST/HST, payroll — federal sources, quoted extracts, confidence assessment |
| processing | processing-documents | Planned | Intake and extraction support |
| categorizing | categorizing-transactions | Planned | Early-stage transaction workflow |
| mapping | mapping-vendors | Planned | Reusable vendor treatment patterns |
| reconciling | reconciling-bank-accounts | Planned | Reconciliation support |
| preparing | preparing-gst-hst-files | Planned | GST/HST workflow support |
| preparing | preparing-t1-files | Planned | T1 workflow support |
| preparing | preparing-t2-files | Planned | T2 workflow support |

## Repository Structure

Each skill is a self-contained folder with a `SKILL.md` file. Optional `references/`, `scripts/`, and `assets/` folders can be added inside a skill when needed.

```text
skills/
  processing-documents/
    SKILL.md

  categorizing-transactions/
    SKILL.md

  mapping-vendors/
    SKILL.md

  reconciling-bank-accounts/
    SKILL.md

  detecting-ledger-anomalies/
    SKILL.md

  reviewing-bookkeeping/
    SKILL.md
    references/
    scripts/

  generating-client-queries/
    SKILL.md

  preparing-gst-hst-files/
    SKILL.md

  preparing-t1-files/
    SKILL.md

  preparing-t2-files/
    SKILL.md

docs/
  repo-scope.md
  writing-rules.md

examples/
  ledger-export.csv
  bank-statement.csv
  receipts/
    sample-receipt-01.pdf
    sample-receipt-02.pdf
  tax-package/
    t1-sample-documents/
```

## Professional Boundary

These skills are designed to support practitioner work, not replace professional judgment.

Outputs should still be reviewed by a CPA or qualified bookkeeper before they are relied on for client communication, financial reporting, or filing. These workflows are meant to improve consistency and reduce friction in repeatable work, not to bypass review.

## Installation

### Claude (claude.ai)

1. Download or clone this repository
2. Zip the skill folder you want to install
3. Go to **Settings → Capabilities → Skills**
4. Upload the skill ZIP

The agent should discover and load the skill automatically when relevant.

### Claude Code

Place the skill folder in:

```text
~/.claude/skills/
```

### OpenAI Codex

Place the skill folder in:

```text
~/.agents/skills/
```

### Google Gemini CLI

Place the skill folder in one of:

```text
~/.gemini/skills/
~/.agents/skills/
```

These skills follow a shared agent-skill style structure and are being developed primarily around Claude-style workflows. Behavior may vary across tools.

## How to Use a Skill

Once installed, the agent should discover and load the relevant skill based on the task.

Example:

```text
request: review this bookkeeping export before sign-off
skill loaded: reviewing-bookkeeping
input: ledger-export.csv
output: flagged transactions and review notes
```

For explicit invocation in CLI-based tools, reference the skill by name in your prompt.

## Collaboration and Discussion

This repository is intended to be public and iterative.

The goal is not just to publish finished skills. It is to make workflow design visible enough that other CPAs, bookkeepers, and accounting-technology builders can react to it, challenge it, improve it, and help build better versions.

Useful contributions include:

- workflow suggestions
- edge cases
- failure examples
- structure improvements
- missing review logic
- better output patterns
- practitioner feedback from real use

The standard for inclusion is simple: the workflow should reflect real accounting work and improve repeatability without pretending that judgment no longer matters.

## Project Principles

**Judging over automating**  
The goal is not a hands-off system. The goal is to surface the right information so a practitioner can make a faster, better decision.

**Testing in practice over theorizing**  
This repository is built from real accounting environments, especially self-employed and e-commerce files, rather than generic AI demos.

**Reusing over improvising**  
A good skill should capture a repeatable pattern that is worth using again.

**Iterating in public**  
This is a build-in-public project. The workflows should improve as they encounter more edge cases and better criticism.

## Related Repositories

- [**it-contractors-skills**](https://github.com/alexteplovcpa/it-contractors-skills) — Client-facing preparation workflows for Canadian IT contractors.
- [**ecommerce-skills**](https://github.com/alexteplovcpa/ecommerce-skills) — Client-facing preparation workflows for Canadian e-commerce sellers.

## About

Built by [Alex Teplov, CPA](https://www.linkedin.com/in/alex-teplov/).

This repository is part of a broader effort to build practical, profession-grounded AI workflow libraries for accounting work in Canada, with separate repositories for practitioner-facing workflows and client-facing preparation workflows.
