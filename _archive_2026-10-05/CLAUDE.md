# CLAUDE.md — llm-privacy-shield

Inherits `../../CLAUDE.md` + `../CLAUDE.md` + `../../../CLAUDE.md`.

## Stack
- Frontend: Next.js (App Router) + Tailwind. Static landing, 1 page long + /thank-you + /paper-thank-you.
- Backend: FastAPI (Python) separate `backend/`. Endpoints: `POST /api/leads`, `POST /api/paper-leads`, `GET /api/health`.
- DB: SQLite for test week (migrate Postgres later). No PII logging beyond lead fields.

## Build / Test (mandatory)
- Web E2E via `playwright-cli` skill. No feature done until E2E passes:
  1. Open `/`, assert hero + 2 CTA visible.
  2. Submit demo form with work email -> redirect `/thank-you`, lead in backend.
  3. Submit paper form -> redirect `/paper-thank-you`, PDF download starts, conversion event fires.
- TDD for backend: write test first (`test_leads.py`), then code. Code before test will be deleted.
- Mock rule: mock data only in `frontend/app/api/*` or `backend/` stubs. Never mock in React UI components.
- Privacy: frontend redaction demo widget is client-side only, never send raw PII to LLM API in demo. Backend validates work email (block gmail/yahoo for demo, allow for paper).

## Constraints
- No cross-product edits. No commit/push unless asked.
- Copy claims must match BRAND.md evidence level. Do not invent ISO/SOC2 certs — use "Designed to support" if PLACEHOLDER.
- Ads approval: must have `/privacy`, `/terms`, footer company info (MST, address) before going live.
