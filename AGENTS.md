# AGENTS.md — 4 vai phối hợp (PO / Design / Dev / QC)

> Single source for task division. Keep prompts short. No next step until QC passes or PO approves visually.

## 1. PO
- Owns PRD.md + acceptance criteria + budget 6tr (LinkedIn 4tr / Google 2tr) + dual conversion (book demo + paper).
- Prompt: `Read PRD.md. Output 5 acceptance lines for HTML spec + 5 for E2E. Block scope creep.`
- Done: criteria locked, anh OK.

## 2. Design
- Input: PRD.md + PO criteria. Output: 1 file `/tmp/spec.html` (HTML only, no JS), 10 sections, 2 CTA sticky, mark unverified claims [PLACEHOLDER].
- Prompt: `From PRD.md generate /tmp/spec.html, all sections in one file. No JS.`
- Done: anh duyet bang mat tren HTML.

## 3. Dev Fullstack
- Input: approved spec.html. Stack: Next.js (routes /, /thank-you, /paper-thank-you, /privacy) + FastAPI (`POST /api/leads` block freemail, `POST /api/paper-leads`, `GET /health`).
- Rules: mock only in `app/api` or backend stubs, never in UI. TDD backend, E2E via `playwright-cli`.
- Prompt: `Convert spec.html to Next.js + FastAPI per CLAUDE.md. E2E: load, submit demo, submit paper.`
- Done: E2E passes + leads saved.

## 4. QC (independent gate)
- Checklist: hero + 2 CTA visible; demo blocks gmail/yahoo, paper allows; `demo_submit` + `paper_download` fire in GA4 + LinkedIn + Google; `/privacy` exists for ads approval.
- Prompt: `Run E2E + conversion check. FAIL if any item missing. No auto-fix, return log.`
- Done: PASS log, else send back to Dev/Design.

## Handoff
PO lock -> Design HTML -> anh visual OK -> Dev build -> QC gate -> mới tới ads. Daily: 1 blocker + 1 metric.
