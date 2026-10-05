# LLM Privacy Shield — Landing + Ads for Enterprise

> Solution khử dữ liệu nhạy cảm (PII redaction / DLP proxy) khi doanh nghiệp làm việc với LLM. Target: doanh nghiệp lớn (bank, insurance, telco, retail chain).

## What it is
- Landing page 1 trang (Next.js static) + form dual conversion:
  1. Primary: Book demo (name, work email, phone, company, company size, use-case)
  2. Secondary: Download whitepaper "Checklist PDPL + AI compliance" (name, work email, company)
- Backend FastAPI tách riêng: `POST /api/leads` (demo), `POST /api/paper-leads` (paper), lưu DB + gửi mail nội bộ.
- Ads: LinkedIn + Google Search, budget 6tr/tuần test, đã có domain + ad account + billing.

## How to run (dev)
- `frontend/`: Next.js — `npm install && npm run dev` (port 3000)
- `backend/`: FastAPI — `pip install -r requirements.txt && uvicorn main:app --reload --port 8000`
- Contract: frontend gọi backend qua `NEXT_PUBLIC_API_URL`, không mock trong UI. Mock chỉ trong `frontend/app/api/*` lúc chưa có backend, sau đó chuyển hết sang backend.

## 7 selection questions (root README)
1. Build? Có — ra landing chạy được + thu lead thật.
2. Create? Có — message + gu B2B riêng, không sao chép template.
3. Research? Có — insight CISO/DPO giúp copy đúng (xem RESEARCH/).
4. Compounding? Có — mẫu landing B2B + setup ads tái dùng.
5. Challenge? Có — vượt comfort: copy enterprise, tracking, ads approval.
6. Artifact? Có — URL live + 2 conversion events bắn được.
7. North Star? Có — dám bán cho enterprise, lớn hơn nỗi sợ bị từ chối.

## Map file
- `PRD.md` — spec 10 phút (giả định đã chốt với chủ product).
- `BRAND.md` — brand + bằng chứng giả định (đánh dấu PLACEHOLDER cần thay trước khi chạy ads thật).
- `RESEARCH/enterprise-insight.md` — insight, `Informs: Studio/BUILD/llm-privacy-shield`.
- `PLAN-ADS.md` — plan 6tr LinkedIn + Google, KPI, angle, ad copy draft.
- `MULTI-AGENT.md` — prompt chia việc cho 5 agent + task 1 tuần.
- `SHIPLOG.md` — chưa ship = chưa xong.

## Status
- [ ] HTML spec v1.0
- [ ] Next.js + E2E pass
- [ ] Backend /api/leads chạy
- [ ] GA4 + LinkedIn Tag + Google conversion verified
- [ ] 2 campaign live (paused -> live test)
