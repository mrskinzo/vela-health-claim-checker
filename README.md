# Lumina Health Claim Checker

A portfolio project by **[Christi Akinwumi](https://christi.io)** · [github.com/mrskinzo](https://github.com/mrskinzo)

---

## What it is

A fictional but realistic AI-powered health misinformation claim checker, built as a UX/UI and content design portfolio piece. It simulates how a healthcare insurer's member portal might help patients evaluate health claims they've encountered online — with evidence-based ratings, plain-language explanations, and transparent AI sourcing.

**Lumina Health is a fictional company.** No real patient data is collected or used.

---

## Features

- **Evidence-based ratings** — claims scored against peer-reviewed literature (Strong Evidence → Limited → No Evidence → Potentially Harmful)
- **Claim journey tracker** — 3-step progress strip showing claim status
- **Plain-language labels** — field hints like "How well-studied is this claim?" alongside clinical labels
- **Inline AI transparency** — disclaimer surfaced directly on results, not hidden in an accordion
- **Persistent evidence legend** — color-coded rating scale always visible on the form
- **Member support contact** — phone number on results and error states (a finding from real healthcare UX research)
- **WCAG 2.1 AA accessible** — skip nav, `aria-live`, `aria-required`, `aria-describedby`, focus indicators, screen-reader markup
- **EN/ES bilingual** — full Spanish translation via a JavaScript i18n system
- **Print / Save PDF** — `@media print` styles with `window.print()`
- **Form validation** — inline error states with red border + message
- **5 demo claim codes** to explore every result type

---

## Demo codes

| Code | Topic | Rating |
|---|---|---|
| `LH-NO-EVIDENCE` | Celery juice liver detox | No Evidence |
| `LH-LIMITED-001` | Vitamin C megadose cold treatment | Limited Evidence |
| `LH-LIMITED-002` | Sugar and diabetes causation | Limited Evidence (context required) |
| `LH-LIMITED-003` | Turmeric vs. ibuprofen | Limited Evidence (overstated) |
| `LH-HARMFUL-001` | Hydrogen peroxide for ear infections | Potentially Harmful |

---

## UX/design decisions

This project incorporates findings from real healthcare UX research:

- **44% of users don't understand "EOB"** (MeasuringU) → plain-language glosses added under clinical labels
- **77% of users ranked support phone number as #1 portal feature** (Corporate Insight) → support line added to footer and error state
- **Users overtrust AI medical advice** (MIT Media Lab, 2025) → inline disclaimer on every result card, not just in an expandable panel
- **Step-trackers increase perceived utility** (UHC/Anthem BCBS pattern) → claim journey progress strip added
- **Color-coded rating keys reduce cognitive load** → persistent 4-item legend below the form

---

## Tech

Single-file HTML/CSS/JS — no build step, no backend, no dependencies except Google Fonts (Open Sans).

---

## Built with

Claude AI (Anthropic) · Designed & developed by Christi Akinwumi
