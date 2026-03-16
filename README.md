# cpa-skills

Practice-tested AI workflow skills for CPAs and bookkeepers.

Most AI tools in accounting are built by people who understand LLMs. These are built by someone who also does the month-end.

This repository is a collection of structured AI instruction workflows designed to handle the repeatable, data-heavy parts of accounting work so practitioners can focus on professional judgment.

---

## Current Build: `bookkeeping-review`

The current focus is a structured review of bookkeeping exports before CPA sign-off. This skill identifies accounting anomalies and classification errors that a human reviewer might miss during a high-volume month-end.

---

## What is a Skill?

A skill is a reusable instruction file that teaches an AI model how to perform a specific accounting task consistently.

Unlike a one-off prompt, a skill defines a fixed objective, required inputs, and a structured output format. It functions as a digital operational playbook for your AI workspace: load it at the start of a session and the same task runs consistently across multiple engagements without re-explaining the instructions each time.

---

## Workflow Pipeline

These skills mirror the actual flow of work inside a Canadian accounting practice.

```text
documents
   ↓
ingestion
(receipts, invoices → structured data)
   ↓
classification
(vendor mapping, tax treatment)
   ↓
reconciliation
(bank feeds → ledger entries)
   ↓
review
(anomaly detection, bookkeeping-review)
   ↓
communication
(client query generation)
   ↓
tax
(gsthst / t1 / t2)
```

Earlier skills prepare and structure accounting data. Later skills analyze the ledger and flag issues that require professional review. This reflects how accounting work actually happens: most of the effort is spent preparing and validating data before CPA judgment is applied.

---

## Skill Roadmap

| Category | Skill | Status |
|---|---|---|
| Review | `bookkeeping-review` | Active build |
| Ingestion | `document-processing` | Roadmap |
| Classification | `transaction-categorization` | Roadmap |
| Classification | `vendor-mapping` | Roadmap |
| Reconciliation | `bank-reconciliation` | Roadmap |
| Review | `ledger-anomaly-detection` | Roadmap |
| Communication | `client-query-generator` | Roadmap |
| Tax | `gsthst` | Roadmap |
| Tax | `t1` | Roadmap |
| Tax | `t2` | Roadmap |

---

## Repository Structure

```text
skills/
   ingestion/
      document-processing
   classification/
      transaction-categorization
      vendor-mapping
   reconciliation/
      bank-reconciliation
   review/
      ledger-anomaly-detection
      bookkeeping-review
   communication/
      client-query-generator
   tax/
      gsthst
      t1
      t2
```

---

## How to Use a Skill

Skills are designed to be loaded into an AI session before performing a task.

Typical workflow:

1. Start a new AI session.
2. Load the relevant skill file from the `skills/` directory.
3. Provide the required input data (for example a ledger export or bank statement).
4. The AI follows the structured instructions defined in the skill and produces a consistent output.

Example workflow for bookkeeping review:

```text
load skill → bookkeeping-review
input → ledger-export.csv
output → flagged transactions and review notes
```

Because the instructions are structured and reusable, the same accounting task runs consistently across multiple engagements.

---

## Example Data

The `examples/` directory contains sample datasets for testing skills without using real client data.

Example files may include:

```text
examples/

   ledger-export.csv
   bank-statement.csv
   receipts/
      sample-receipt-01.pdf
      sample-receipt-02.pdf
   tax-package/
      t1-sample-documents/
```

These files simulate typical accounting inputs such as bookkeeping exports, bank statements, receipts and invoices, and basic tax document packages.

---

## Project Principles

**Judgment over automation.** The goal is not a hands-off workflow. The goal is to surface the right information so the CPA can make a faster, better decision.

**Field tested.** Every skill in this repo is tested against real scenarios from two specific domains: Canadian self-employed professionals and e-commerce sellers.

**Iterative build.** This is an active log. As CRA interpretations change or new edge cases appear in practice, these skills are updated.

---

## Related Repositories

**[selfemployed-skills](https://github.com/alexteplovcpa/selfemployed-skills)**
Tax and bookkeeping workflows specifically for Canadian IT contractors, mortgage agents, trades, and real estate professionals.

**[ecommerce-skills](https://github.com/alexteplovcpa/ecommerce-skills)**
Specialized workflows for marketplace reconciliation, inventory, COGS treatment, and HST handling for Canadian e-commerce sellers.

---

## About

Built by [Alex Teplov, CPA](https://www.linkedin.com/in/alex-teplov/).

I run two specialized accounting practices in Canada and build these workflows to solve operational bottlenecks encountered in real accounting work.
