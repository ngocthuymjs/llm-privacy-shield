# PRD.md — LLM Privacy Shield (10-min voice spec, assumed locked)

> FORBIDDEN: Do not polish this text. Fix the HTML spec instead (development-guideline).

## 1. One-liner
Nhân viên paste dữ liệu khách hàng vào ChatGPT/LLM là rò rỉ. Shield ngồi giữa: detect PII -> redact/mask -> mới cho qua LLM -> audit log đầy đủ.

## 2. Who (enterprise VN, 500+ nhân sự)
- CISO / CTO: sợ leak, cần on-prem/proxy, audit.
- DPO / Pháp chế: sợ phạt PDPL (Nghị định 13/2023), cần bằng chứng compliance.
- Head CS / Ops: muốn xài AI cho tổng đài, tóm tắt ticket, nhưng không dám đưa data thật.

## 3. Screens (single long landing, 10 sections in 1 HTML file)
1. Hero: H1 "Dùng LLM mà không lộ dữ liệu khách hàng." Sub: proxy khử PII real-time. 2 CTA: [Book demo] [Tải whitepaper PDPL+AI].
2. Problem: 3 stats (paste PII vào LLM, phạt PDPL, nhân viên dùng shadow AI). PLACEHOLDER stats cần source.
3. How it works (4 bước): Detect (CCCD, SĐT, STK, email, địa chỉ) -> Redact/Mask/Tokenize -> Proxy to LLM -> Audit log + policy.
4. Live widget: ô nhập thử "Tôi là Nguyễn Văn A, CCCD 001..., SĐT 09..." -> hiện bản đã che. Client-side only.
5. Compliance strip: "Designed to support PDPL / GDPR / ISO 27001 / SOC 2" — chưa claim đạt nếu chưa có cert.
6. Deployment: Cloud proxy / On-prem / VPC. Latency < 100ms (cần bench thật).
7. Use-cases: tổng đài, tóm tắt hồ sơ tín dụng, HR, code assistant.
8. Pricing hint: Pilot 2 tuần + Enterprise contact. Không public giá.
9. Proof: 2 logo khách pilot (PLACEHOLDER), 1 quote CISO (PLACEHOLDER).
10. Dual form + FAQ (data có train lại LLM không? Không. Dữ liệu đi đâu? Log ở đâu?) + footer MST/địa chỉ/privacy.

## 4. Conversions
- Primary `/thank-you`: book demo. Fields: name, work email, phone, company, size (500-1000/1000+), use-case. Block freemail for demo.
- Secondary `/paper-thank-you`: download paper. Fields: name, work email, company. Freemail allowed.

## 5. Non-goals (week 1)
- No real redaction engine in landing (widget is regex demo only).
- No pricing page, no signup tự phục vụ, no EN version.
