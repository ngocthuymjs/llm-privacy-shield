# MULTI-AGENT.md — Prompts + task 1 tuần (copy-paste cho từng agent)

> Keep prompts short. Models are smart. Each step must pass tests before next.

## Agent 1 — Researcher B2B
Prompt: `Read RESEARCH/enterprise-insight.md + PRD.md. Output 1-page addendum: top 5 objections enterprise VN về LLM+PII kèm câu trả lời 1 dòng dùng cho FAQ. Informs BUILD landing.`
- T2 xong. Done = FAQ draft merged.

## Agent 2 — Copywriter + Designer
Prompt: `From PRD.md + BRAND.md + RESEARCH, generate 1 HTML file /tmp/spec.html with all 10 sections (HTML only, no JS). Dual CTA sticky. Mark every unverified claim with [PLACEHOLDER].`
- T3 xong. Done = anh duyệt bằng mắt trên HTML, sửa trực tiếp trong file.

## Agent 3 — Builder (Next.js + FastAPI)
Prompt: `Convert /tmp/spec.html to Next.js App Router + Tailwind. Routes: / /thank-you /paper-thank-you /privacy. Forms POST to backend. Mock only in app/api. E2E with playwright-cli: load, submit demo, submit paper.`
- T4 xong. Done = E2E pass + `POST /api/leads` lưu được.
Backend prompt: `FastAPI: POST /api/leads (block freemail), POST /api/paper-leads, GET /health. TDD: test_leads.py first. SQLite.`

## Agent 4 — Ads Planner
Prompt: `Read PLAN-ADS.md + BRAND.md. Output: 3 LinkedIn creatives (1200x627 text + headline) + 1 Document Ad teaser + 2 Google RSA sets + negative list 20 từ. No invented certs.`
- T3-T4 xong. Done = file ads-ready.

## Agent 5 — Ads Operator
Prompt: `Have domain + ad accounts + billing. Install GA4 + LinkedIn Insight + Google conversion (demo_submit, paper_download). UTM template. Create 1 LinkedIn campaign + 1 Google campaign PAUSED with budget split 4tr/2tr. Verify with test submit. Output screenshot checklist.`
- T4-T5 xong. Done = test conversion fires in all 3 platforms.
- T6 live 50% -> T7 report CPL/CTR/CVR.

## Orchestration
T2 research+PRD lock -> T3 HTML spec (anh duyệt) -> T4 build+E2E+ads paused -> T5 tracking verified -> T6 live test -> T7 SHIPLOG + Body-of-Work. Daily sync 15 phút: blocker duy nhất + metric duy nhất.
