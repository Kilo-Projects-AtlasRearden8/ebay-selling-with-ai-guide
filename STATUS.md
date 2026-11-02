# STATUS

## What was built

A beginner manual and static HTML site on using **free AI** to sell on eBay, produced by **Asdale Dynamics, LLC** (Indiana, formed October 2026). Credit appears in the README and site footer; the LICENSE copyright line is exactly `Copyright (c) 2026 Asdale Dynamics, LLC`.

**docs/** — beginner manual in Markdown (9 files + overview):
- `00-overview.md` — manual orientation and contents
- `01-free-ai-tools.md` — free AI tools (Google AI Studio, Bing Copilot, Poe, Ollama/local AI), no paid tools
- `02-writing-titles.md` — AI prompts for eBay titles (<=80 chars)
- `03-writing-descriptions.md` — AI prompts for honest, trust-building descriptions
- `04-photos.md` — planning photo lists, free shooting/editing, privacy
- `05-pricing.md` — researching sold prices and setting price with AI
- `06-shipping-policies.md` — AI prompts for shipping and return policies
- `07-buyer-messages.md` — AI prompts for replies to common buyer situations
- `08-privacy.md` — privacy rules: what never to share with AI
- `09-printable-worksheet.md` — one-page printable listing worksheet

**site/** — polished static HTML version (shared `styles.css`):
- `index.html` — landing page with contents and links
- `manual.html` — full manual, table of contents, all sections, prompts, examples, tips
- `worksheet.html` — printable listing worksheet (print via Ctrl+P/Cmd+P)
- `styles.css` — shared responsive styles with print media query

**Root files:**
- `LICENSE` — MIT License, exact copyright line `Copyright (c) 2026 Asdale Dynamics, LLC`
- `README.md` — overview, credits Asdale Dynamics, LLC, no-secrets notice
- `STATUS.md` — this file

## How to run

No installation or build step required. It is a static site of Markdown and HTML files.

- Read the manual: open any file in `docs/`, or browse `site/manual.html`.
- Land on the site: open `site/index.html` in a browser.
- Print the worksheet: open `site/worksheet.html` and use your browser's print command (Ctrl+P / Cmd+P).
- To preview locally as a served site: `python3 -m http.server` inside `site/` (or the repo root) and open `http://localhost:8000`.

No accounts, API keys, or paid tools are required beyond the free AI tools you choose to try.

## Verification results

All checks passed:

- Internal links: every `href` across `index.html`, `manual.html`, `worksheet.html` resolves to an existing file; no broken links (including fragment links like `manual.html#free-ai-tools`).
- Tag balance: all HTML tags properly opened and closed in all three HTML files (a `div`-vs-`</p>` mismatch in `manual.html` was found and fixed).
- CSS present: `site/styles.css` referenced by all pages.
- LICENSE: exact copyright line `Copyright (c) 2026 Asdale Dynamics, LLC` confirmed present.
- README: credits `Asdale Dynamics, LLC`.
- Live smoke test: served `site/` via `python3 -m http.server` on `127.0.0.1:18080`; `index.html`, `manual.html`, `worksheet.html`, and `styles.css` all returned HTTP 200. Test server stopped afterward.
- Git: initialized, all 16 files committed in one root commit on branch `master` using the existing git identity (Dylan Asdale / dylanasdale@users.noreply.github.com). Plain commit message, no `Co-authored-by` trailers. Not pushed, no remote created.

## Known gaps

- The manual is Markdown in `docs/` and HTML in `site/`; the two are hand-maintained and not auto-synced (edits to one are not reflected in the other).
- No automated test suite or CI (no `.github/workflows`, per requirements); verification was manual via a Python link/balance checker and a local HTTP smoke test.
- The HTML validator check was structural (tag balance + link resolution), not a formal W3C validation.
- Pricing guidance notes that free AI tools cannot reliably look up live eBay sold prices; the user must check sold listings themselves.
- Examples use made-up/placeholder items only; no real personal data, API keys, or secrets are present.
