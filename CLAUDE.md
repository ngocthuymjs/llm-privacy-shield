# CLAUDE.md — llm-privacy-shield

Inherits `../CLAUDE.md` (Studio/BUILD: code workspace).

## Stack
- Frontend: Next.js (App Router) + Tailwind. Static landing, 1 long page + /thank-you + /paper-thank-you + /privacy.
- Backend: FastAPI (Python) in `backend/`. Endpoints: `POST /api/leads`, `POST /api/paper-leads`, `GET /health`.
- DB: SQLite for test week (migrate Postgres later).

## Build / Test (mandatory)
- Web E2E via `playwright-cli` skill. No feature done until E2E passes:
  1. Open `/`, assert hero + 2 CTA visible.
  2. Submit demo form with work email -> `/thank-you`, lead saved in backend.
  3. Submit paper form -> `/paper-thank-you`, conversion events fire.
- TDD for backend: test first (`test_leads.py`), then code. Code before test will be deleted.
- Mock rule: mock data only in `frontend/app/api/*` or `backend/` stubs. Never mock in React UI.
- Privacy: demo redaction widget is client-side only. Backend blocks freemail (gmail/yahoo) for demo, allows for paper.

## Constraints
- No cross-product edits. No commit/push unless asked.
- Copy claims must match evidence level. No invented ISO/SOC2 certs — use "Designed to support" for PLACEHOLDERs.
- Ads approval needs `/privacy`, footer company info (MST, address) before going live.
