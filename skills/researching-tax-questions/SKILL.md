---
name: researching-tax-questions
description: Research Canadian federal tax questions for T1, GST/HST, and payroll using authoritative government sources. Returns a direct answer, quoted source extracts, and a confidence assessment.
metadata:
    author: Teplov CPA
    version: 1.0
    updated: 2026-04-18
---

# Researching Tax Questions

Answer Canadian federal tax questions by locating and quoting authoritative source text. This skill covers T1 personal income tax, GST/HST, and payroll (CPP, EI, source deductions). It does not cover T2 corporate income tax or provincial tax administration.

## Core Rules

- Never paraphrase legislation. Quote verbatim or do not quote.
- Always include the section reference alongside the quote.
- Always include the source URL alongside the quote.
- If a source cannot be located, state that explicitly rather than filling the gap with inference.
- Do not cite the year a folio or bulletin was last updated as evidence it reflects current law. Check whether the underlying legislation has changed.
- Do not answer T2 questions. If the question is corporate, say so and stop.
- Do not offer tax planning advice or opinions on optimal structuring.
- Do not cite secondary sources, tax blogs, or paraphrased summaries.

## Inputs

Accept any of:

- a plain-language question ("Is this expense deductible?")
- a transaction or fact scenario ("Client sold their principal residence but rented part of it for two years")
- a specific section reference ("ITA s. 18(1)(h)")
- any combination of the above

If the question is ambiguous, ask one clarifying question before proceeding.

## Authoritative Sources

| Source | Type | URL |
|---|---|---|
| Income Tax Act (R.S.C. 1985, c. 1 (5th Supp.)) | Legislation | https://laws-lois.justice.gc.ca/eng/acts/I-3.3/ |
| Income Tax Regulations | Legislation | https://laws-lois.justice.gc.ca/eng/regulations/C.R.C.,_c._945/ |
| Excise Tax Act (GST/HST) | Legislation | https://laws-lois.justice.gc.ca/eng/acts/E-15/ |
| Canada Pension Plan Act | Legislation | https://laws-lois.justice.gc.ca/eng/acts/C-8/ |
| Employment Insurance Act | Legislation | https://laws-lois.justice.gc.ca/eng/acts/E-5.6/ |
| CRA Income Tax Folios | CRA administrative | https://www.canada.ca/en/revenue-agency/services/tax/technical-information/income-tax/income-tax-folios-index.html |
| CRA Interpretation Bulletins (archived) | CRA administrative | https://www.canada.ca/en/revenue-agency/services/tax/technical-information/income-tax/interpretation-bulletins-index-topic.html |
| CRA GST/HST Memoranda | CRA administrative | https://www.canada.ca/en/revenue-agency/services/forms-publications/publications/technical-notes-gst-hst.html |
| CRA GST/HST Policy Statements | CRA administrative | https://www.canada.ca/en/revenue-agency/services/forms-publications/publications/policy-statements.html |
| CRA T4001 Payroll Deductions Guide | CRA administrative | https://www.canada.ca/en/revenue-agency/services/forms-publications/publications/t4001.html |
| CRA T4032 Payroll Deductions Tables | CRA administrative | https://www.canada.ca/en/revenue-agency/services/forms-publications/payroll/t4032-payroll-deductions-tables.html |
| Tax Court of Canada decisions (CanLII) | Case law | https://www.canlii.org/en/ca/tcc/ |
| Federal Court of Appeal decisions (CanLII) | Case law | https://www.canlii.org/en/ca/fca/ |

## Workflow

1. **Identify the governing area.** T1, GST/HST, or payroll. If unclear, state the assumption.
2. **Locate the primary legislation.** Find the relevant ITA, ETA, CPP, or EI Act section. Quote the operative text verbatim.
3. **Locate the CRA administrative position.** Find the relevant folio, bulletin, memorandum, or guide section. Quote the relevant passage verbatim.
4. **Check for divergence.** If the legislation and CRA position conflict, or if there is known litigation on the point, flag it explicitly.
5. **Check for provincial dimension.** If the question has a Quebec or significant provincial component, apply the provincial flag.
6. **Compose the output** using the structure below.

## Output

### Answer

One clear sentence that directly answers the question. No hedging unless the answer is genuinely unsettled.

### Legal Basis

Quoted text from the governing legislation. Format:

> "[exact quoted text]"
>
> -- *[Act name]*, [section reference] -- [URL]

### CRA Position

Quoted text from the relevant CRA folio, bulletin, memorandum, or guide. Format:

> "[exact quoted text]"
>
> -- *[Document name and number]*, [paragraph or section reference] -- [URL]

If no CRA administrative position exists on the point, state: "No CRA administrative guidance identified on this specific point."

### Confidence

One of three levels:

- **Confirmed** -- legislation and CRA position are consistent and the point is not under active dispute
- **Administrative** -- answer rests on CRA administrative guidance with no explicit statutory basis, or CRA guidance goes beyond what the legislation says
- **Unsettled** -- known CRA vs. taxpayer disagreement, active or recent litigation, or silence in both legislation and guidance

### Provincial Flag

Include only when triggered. Use this language:

> **Provincial note:** This question may have a [Quebec / provincial] dimension. The answer above covers federal rules only. Check [Revenu Quebec / the relevant provincial tax authority] separately before advising.

## Boundaries

- Covers T1 personal income tax (Income Tax Act, CRA Income Tax Folios, Interpretation Bulletins).
- Covers GST/HST (Excise Tax Act, CRA GST/HST Memoranda, Policy Statements).
- Covers payroll (CPP Act, EI Act, CRA T4001 Payroll Deductions Guide, T4032).
- Does not cover T2 corporate income tax.
- Does not cover provincial income tax administration (except flagging Quebec dimension).
- Does not cover tax planning or opinion work.

## Example

**Input:** Is a home office deduction available to an employee who works from home?

**Answer**

An employee may deduct home office expenses if their employer requires them to work from home and the workspace is used exclusively and regularly for employment duties, subject to specific conditions in the ITA.

**Legal Basis**

> "An amount... is deductible... as... workspace in the home... only if the workspace is where the individual principally performs the duties of the office or employment, or the workspace is used exclusively during the period in respect of which the amount relates for the purpose of earning income from the office or employment and is used on a regular and continuous basis for meeting customers or other persons in the ordinary course of performing the duties of the office or employment."
>
> -- *Income Tax Act*, s. 8(13) -- https://laws-lois.justice.gc.ca/eng/acts/I-3.3/page-5.html

**CRA Position**

> "You can claim the employment use of a work space in your home if you meet one of the following conditions: the home office is where you principally (more than 50% of the time) perform your employment duties, or you use the home office only to earn employment income and you use it on a regular and continuous basis to meet clients or customers."
>
> -- *Income Tax Folio S1-F2-C2*, paragraph 2.6 -- https://www.canada.ca/en/revenue-agency/services/tax/technical-information/income-tax/income-tax-folios-series-1-individuals/folio-2-students/income-tax-folio-s1-f2-c2-tuition-tax-credit.html

**Confidence**

Confirmed -- legislation and CRA administrative position are consistent on the core conditions.

**Provincial Flag**

> **Provincial note:** This question may have a Quebec dimension. Quebec employees file separately with Revenu Quebec. Check Revenu Quebec guidance separately before advising a Quebec-resident employee.
