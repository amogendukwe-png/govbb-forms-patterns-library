# GovTech Barbados — Forms Pattern Library

Reusable form patterns, field definitions, and design standards for GovTech Barbados digital services — spanning NISSS, CAIPO, and future MDAs.

---

## What this is

This library documents every reusable pattern identified across the paper and legacy digital forms of Barbados government departments. A **pattern** is a named, reusable form block — a set of fields, labels, validation rules, and conditional logic that solves a recurring design problem (e.g. "how do we ask for a Barbadian address?" or "how do we capture company identity on a filing form?").

The library is used by the GovTech Barbados forms prototyping team when:
- Analysing a new form before building a spec
- Building a form spec (reference patterns by ID instead of re-describing fields from scratch)
- Preparing for MDA workshops (use the Open Questions table to surface what needs answering)
- Logging design decisions (tag decisions in the Decision Log with the Pattern ID)

---

## Viewing the library

Open `Patterns/pattern-library.html` in any browser. No build step, no server required — it is a single self-contained file.

The library is filterable by **MDA**, **status**, and **category**, and fully searchable. Each pattern card expands to show field definitions, validation rules, design notes, and a link to related decisions in the Decision Log.

---

## Repository structure

```
Forms/
  NISSS Forms/        # NIS Social Security forms — PDFs and form specs (.docx)
  CAIPO Forms/        # Corporate Affairs and Intellectual Property forms — PDFs
Patterns/
  pattern-library.html  # The pattern library (open in browser)
Principles/
  Form Categorisation.pdf
  Form Specification.pdf
  Service Patterns Definitions and Examples.pdf
```

---

## MDAs covered

| MDA | Forms | Patterns |
|-----|-------|----------|
| NISSS | 11 forms (Termination, Unemployment, DP-10, Direct Deposit, Educational Status, Employee Online, Employer Online, Life Certificate, Old Age Pension, Pensioner Declaration, Self-Employment Registration) | P-01 to P-24 |
| CAIPO | 15 forms (IBC Application, Company Declarations, Name Reservation, Registered Agents, Articles of Reincorporation, Notice of Cancellation, URL Declaration, CSME Complaints, and others) | P-25 to P-37 |

Four patterns appear across both MDAs: **P-01** Name Block, **P-04** Contact Block, **P-05** Declaration Block, **P-14** Official Use Block.

---

## Pattern lifecycle

Every pattern has a status that reflects how many times it has been observed across real forms.

| Status | Meaning | Threshold |
|--------|---------|-----------|
| 🔴 New | Observed in one form only. Fields and rules are provisional. | 1 form |
| 🟡 Emerging | Observed in two or more forms. Pattern is stabilising. | 2+ forms |
| 🟢 Standard | Observed in three or more forms. Use this pattern as the default. Do not deviate without a logged decision. | 3+ forms |

---

## Adding a new form

1. **Run a pattern check.** Before writing a new form spec, search the library for fields that look similar. If a section has a name, address, or contact block — reference P-01, P-02, P-04 by ID rather than re-describing them.

2. **Use this prompt** to generate a pattern delta. Paste it into Claude with the form attached:

```
You are a service designer working on the GovTech Barbados forms prototyping team.

Analyse the attached form against the GovTech Barbados Pattern Registry (P-01 to P-37).

The registry covers two MDAs: NISSS (P-01 to P-24) and CAIPO (P-25 to P-37).
Note the MDA context of the form you are analysing — NISSS patterns may appear
in CAIPO forms and vice versa.

For each section of the form, output:
1. MATCHED — pattern ID + name (e.g. "P-02 Barbados Address Block") + note if cross-MDA
2. VARIANT — pattern ID + how this instance differs from the standard
3. NEW — a proposed pattern name, description, and field list

Then output a FORM COMPLEXITY ASSESSMENT (Simple / Medium / Complex).
Finally, list any OPEN QUESTIONS for the MDA question log.
```

3. **Update the library** for each new or changed pattern:
   - **NEW pattern found** → add a card to `pattern-library.html` with status 🔴 New. Assign the next available P-number.
   - **Existing pattern gains an occurrence** → update the occurrence pill and forms list on the card.
   - **Pattern reaches 2 occurrences** → update status from 🔴 New to 🟡 Emerging.
   - **Pattern reaches 3 occurrences** → update status from 🟡 Emerging to 🟢 Standard.

---

## Connecting to the Decision Log

Every pattern card links to the [Decision Log](https://amogendukwe-png.github.io/forms-decision-log/) pre-filtered by that pattern's ID.

To keep the connection live:
- When you log a design decision that affects a pattern, add the **Pattern ID** as a tag (e.g. `P-06`).
- When a question from the Open Questions table is resolved, add the **Question ID** as a tag (e.g. `Q-11`).
- The "View decisions" link on each pattern card will then surface all related decisions automatically.

---

## Principles documents

The `Principles/` folder contains three reference documents agreed with MDAs:

- **Form Categorisation** — criteria for classifying a form as Simple, Medium, or Complex
- **Form Specification** — the standard template for documenting a digital form spec
- **Service Patterns Definitions and Examples** — the 9 service pattern pages (Start, Eligibility, Applicant Details, Criteria & Entitlement, Evidence Upload, Check Your Answers, Payment & Submit, Confirmation) with worked examples

---

## Design system

The pattern library HTML is built on the [alpha.gov.bb design system](https://alpha.gov.bb) — Figtree typeface, `bb-` prefixed colour tokens, and the standard Government of Barbados page chrome (top bar, yellow header with trident wordmark, alpha banner, blue footer).

---

## Contact

GovTech Barbados — Forms Prototyping Team
[alpha.gov.bb](https://alpha.gov.bb)
