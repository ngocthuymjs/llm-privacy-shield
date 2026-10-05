# PLAN-ADS.md — 6tr / 1 tuần, LinkedIn + Google, dual conversion

## 0. Budget split (6.000.000 VND)
- LinkedIn: 4.000.000 (~570k/ngày x 7 ngày). Lý do: đúng CISO/CTO/DPO nhưng CPC 180k-350k => chỉ ~12-22 clicks. Mục tiêu: 2-4 demo leads chất lượng.
- Google Search: 2.000.000 (~285k/ngày). CPC 15k-40k => ~50-120 clicks. Mục tiêu: 4-8 paper leads + 1-2 demo.
- Dự phòng: nếu LinkedIn CPL > 1.5tr sau 3 ngày, chuyển 1.5tr sang Google + retargeting.

KPI pass/fail tuần test:
- CTR LinkedIn >= 0.8%, Google >= 3%. CVR landing demo >= 3%, paper >= 8%.
- CPL demo <= 1.2tr, CPL paper <= 250k. Không đạt => fix message/landing, không scale.

## 1. Tracking (Operator dựng trước khi live, bắt buộc)
- GA4 + Google Tag: `demo_submit`, `paper_download`.
- LinkedIn Insight Tag + conversion 2 events tương ứng.
- UTM: `utm_source=linkedin|google&utm_medium=cpc&utm_campaign=shield_{angle}_{date}`.
- Landing: `/`, `/thank-you`, `/paper-thank-you`, `/privacy`, `/terms`. Verify domain đã có.

## 2. Targeting
### LinkedIn (1 campaign, 3 ad sets theo angle, mỗi ad set 1 creative để khỏi loãng với budget nhỏ)
- Geo: Vietnam. Company size: 500+. Industries: Banking, Insurance, Telco, IT Services, Retail.
- Titles: CISO, CTO, CIO, Head of Security, DPO, Head of Legal/Compliance, Head of Customer Service, Head of Digital.
- Exclude: sinh viên, HR tuyển dụng, agency nhỏ. Frequency cap chặt.
- Format: Single image + Document Ad (teaser whitepaper 3 trang đầu).

### Google Search (1 campaign, 2 ad groups)
- Group VN: [che dữ liệu nhạy cảm AI], [bảo mật chatgpt doanh nghiệp], [dlp cho llm], [pdpl sử dụng AI] + broad modifier.
- Group EN (người nước ngoài ở VN + corp): [pii redaction llm], [llm data loss prevention], [ai compliance vietnam pdpl].
- Negative: free, crack, tuyển dụng, khóa học. Giờ chạy: T2-T6 8h-18h.

## 3. Angles + copy draft (dùng luôn)
**A1 — Fear (cho CISO):**
- H1 ads: "Nhân viên paste CCCD/STK vào AI public mỗi ngày?"
- Body: "ShieldGate che PII trước khi qua LLM + audit log PDPL. Book demo 30 phút."
- CTA: Book demo.

**A2 — Compliance (cho DPO/Pháp chế):**
- H1: "Checklist 12 điểm PDPL khi dùng LLM"
- Body: "Tải whitepaper 8 trang + xem deploy on-prem/VPC, không train lại model."
- CTA: Tải paper.

**A3 — Ops (cho Head CS):**
- H1: "Cho tổng đài xài AI mà không lộ data khách"
- Body: "Proxy <100ms, thử widget che CCCD/SĐT ngay trên landing."
- CTA: Book demo.

Google RSA ví dụ (A1): Headlines: {Khử PII trước khi qua LLM}, {Book Demo 30 Phút}, {Đạt chuẩn PDPL}; Desc: {Detect CCCD/SĐT/STK tiếng Việt. Proxy/on-prem, audit đầy đủ.}.

## 4. Lịch 1 tuần
- T2: gắn tag + verify conversion (test submit thật).
- T3: duyệt creative + copy, campaign ở PAUSED.
- T4 10h: bật 50% bid, check search term + LinkedIn demo report sau 6h.
- T5-T6: kill angle CPL cao nhất, dồn tiền angle tốt nhất. Thêm 5 negative keywords/ngày.
- T7: chốt report CPL/CTR/CVR + 3 insight message thắng => sửa landing v1.1.

## 5. Rủi ro với 6tr
- LinkedIn quá ít click để kết luận thống kê — coi là qualitative (ai click, title gì) chứ không tối ưu sâu.
- Enterprise cần sales follow-up trong 24h — nếu không gọi ngay, lead nguội. Cần owner sales + kịch bản + mail paper day-2.
- Không public giá + claim cert lố sẽ bị reject — đã dùng chữ "Designed to support" trong BRAND.md.
