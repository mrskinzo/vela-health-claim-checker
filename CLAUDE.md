# CLAUDE.md — Vela Health Claim Checker

## Project Overview

A single-file portfolio project demonstrating healthcare UX/UI and content design for insurance claim verification. Built by [Christi Akinwumi](https://christi.io) (@mrskinzo). The app presents a side-by-side comparison of a legacy BCBS-style insurance portal versus a modern AI-powered chatbot interface.

**This is NOT a production application** — it is a demo/portfolio piece with hardcoded data and no backend.

## Architecture

```
vela-health-claim-checker/
├── CLAUDE.md                          # This file
├── README.md                          # Project documentation
└── vela-health-claim-checker.html     # Entire application (single file)
```

The entire application lives in `vela-health-claim-checker.html` (~1,864 lines):
- **Lines 1–9**: Meta tags and viewport
- **Lines 10–929**: Embedded CSS (~920 lines)
- **Lines 930–1111**: HTML markup
- **Lines 1112–1864**: Embedded JavaScript (~750 lines)

## Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — no frameworks, no build step, no dependencies
- **Google Fonts** (Inter, weights 300–700) — the only external resource
- Zero npm packages, no `package.json`, no bundler

## How to Run

Open `vela-health-claim-checker.html` directly in a browser. No server or build step required.

## Demo Data

Five hardcoded claim codes with paired DOBs for verification:

| Code | DOB | Status |
|------|-----|--------|
| `VH-PAID-001` | 01/14/1985 | Paid |
| `VH-DENIED-001` | 03/22/1979 | Denied |
| `VH-PENDING-001` | 07/08/1992 | In Review |
| `VH-PARTIAL-001` | 11/30/1987 | Partially Paid |
| `VH-PAID-002` | 05/17/1976 | Paid |

## Code Conventions

### CSS (embedded `<style>`)
- Organized in clearly commented sections: RESET, TOP BANNER, COMPARISON HEADER, SPLIT BODY, LEFT PANEL, RIGHT PANEL, MESSAGING & CHAT UI, COLOR STATUS PILLS, ANIMATIONS, WATERMARK
- Dark theme for the AI panel; light BCBS-branded theme for the legacy panel
- Status colors: green (Paid), red (Denied), amber (In Review), orange (Partial)
- Class-based selectors throughout (no IDs for styling)

### JavaScript (embedded `<script>`)
- 32 functions, all in the global scope (no modules)
- Organized in commented sections: CLAIM DATA, LEGACY LOGIC, BOT FACE, STATE MANAGEMENT, UTILITY FUNCTIONS, MESSAGING, INTENT HANDLERS, DOB VERIFICATION, CHAT RENDERING, LEGACY PANEL, INIT
- Key state variables: `awaitingDOB`, `currentClaimKey`, `chatStarted`, `dobAttempts`, `shownClaims`
- Fuzzy matching via Levenshtein distance for claim code detection
- HTML escaping via `escHtml()` — always use this for user-provided text

### HTML
- Semantic markup (`<button>`, `<textarea>`, `<table>`)
- Inline SVG for icons (robot avatar, send button, status dots)
- Class references only (IDs limited to form controls)

### Accessibility
- WCAG 2.1 AA compliant
- `aria-live="polite"` on chat messages
- `aria-label` on interactive elements
- Focus indicators on all buttons
- Keyboard support: Enter to send, Shift+Enter for newline

## Key Functions Reference

| Function | Purpose |
|----------|---------|
| `detectClaim(text)` | Parses claim codes from user input |
| `isClaimIntent(text)` | Detects claim-related natural language queries |
| `parseDOBKey(input)` | Validates and normalizes date-of-birth input |
| `levenshtein(a, b)` | Fuzzy string distance for claim code matching |
| `escHtml(str)` | Escapes HTML to prevent XSS — always use for user text |
| `addMsg(who, html)` | Appends a message bubble to the chat panel |
| `sendMessage()` | Main chat input handler and intent router |
| `renderBotCard(claim)` | Renders the full claim status card in the AI panel |
| `legacySubmit()` | Handles form submission on the legacy panel side |

## Guidelines for AI Assistants

1. **Single-file architecture**: All changes go into `vela-health-claim-checker.html`. Do not split into separate files unless explicitly asked.
2. **No build tools**: There is no package manager or build system. Do not introduce one without explicit instruction.
3. **No tests exist**: There is no test suite. If adding tests, discuss the approach first.
4. **Escape user input**: Always use `escHtml()` when rendering any user-provided text.
5. **Preserve accessibility**: Maintain WCAG 2.1 AA compliance — keep `aria-*` attributes, focus indicators, and keyboard navigation intact.
6. **Preserve the dual-panel layout**: The side-by-side legacy vs. AI comparison is the core UX concept.
7. **Keep demo data consistent**: If modifying claim data, ensure codes, DOBs, and statuses remain coherent across both panels.
8. **No external dependencies**: Avoid adding npm packages, CDN scripts, or frameworks. The zero-dependency design is intentional.
