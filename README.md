# Vela Health Claim Checker

A portfolio project by **[Christi Akinwumi](https://christi.io)** · [github.com/mrskinzo](https://github.com/mrskinzo)

---

## What it is

A fictional but realistic AI-powered health insurance claim checker, built as a UX/UI and content design portfolio piece. It simulates how a healthcare insurer's member portal might help patients check claim status — with evidence-based ratings, plain-language explanations, and a side-by-side comparison of legacy vs. AI-powered UX.

**Vela Health is a fictional company.** No real patient data is collected or used.

---

## Features

- **Evidence-based ratings** — claims scored across four tiers: Covered · Limited · Not Covered · Excluded
- **Side-by-side UX comparison** — legacy insurance portal (BCBS-style) vs. modern AI chatbot
- **Plain-language labels** — clear, jargon-free explanations on every result
- **Inline AI transparency** — disclaimer surfaced directly on results, not hidden in an accordion
- **Ambient glow AI panel** — polished dark UI with color-coded status cards
- **WCAG 2.1 AA accessible** — skip nav, `aria-live`, `aria-required`, `aria-describedby`, focus indicators
- **5 demo claim codes** to explore every result type

---

## Demo codes

| Code | Topic | Status |
|---|---|---|
| `VH-NO-EVIDENCE` | No supporting evidence | Excluded |
| `VH-LIMITED-001` | Physical therapy | Limited Coverage |
| `VH-LIMITED-002` | Mental health services | Limited Network |
| `VH-LIMITED-003` | Specialist referral | Pending Authorization |
| `VH-HARMFUL-001` | Experimental treatment | Not Covered |

---

## UX/design decisions

This project incorporates findings from real healthcare UX research:

- **44% of users don't understand "EOB"** (MeasuringU) → plain-language glosses added under clinical labels
- **77% of users ranked support phone number as #1 portal feature** (Corporate Insight) → support line added to footer and error state
- **Users overtrust AI medical advice** (MIT Media Lab, 2025) → inline disclaimer on every result card, not just in an expandable panel
- **Step-trackers increase perceived utility** (UHC/Anthem BCBS pattern) → claim journey progress strip added
- **Color-coded rating keys reduce cognitive load** → persistent legend always visible

---

## Tech

Single-file HTML/CSS/JS — no build step, no backend, no dependencies except Google Fonts (Inter).

---

## Built with

Claude AI (Anthropic) · Designed & developed by Christi Akinwumi
