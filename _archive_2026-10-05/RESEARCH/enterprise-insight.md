# RESEARCH — Enterprise insight

> Informs: Studio/BUILD/llm-privacy-shield (landing copy + ad angles + FAQ). Research without consumer = archive (Studio rule).

## Persona (VN large enterprise)
1. **CISO/CTO:** Fear = leak lên model public, mất việc. Wants = proxy/on-prem, audit log, latency thấp. Objection = "thêm hop là chậm + false positive che sai".
2. **DPO/Pháp chế:** Fear = phạt PDPL NĐ 13/2023 + trách nhiệm giải trình. Wants = DPIA, consent log, data residency VN. Objection = "vendor có lưu prompt không?".
3. **Head CS/Ops:** Fear = team xài shadow AI không kiểm soát. Wants = cho xài AI nhưng an toàn, report được. Objection = "có khó dùng không?".

## Message house (dùng cho hero + ads)
- Roof: "Dùng LLM mà không lộ dữ liệu khách hàng."
- Pillar 1 (Fear): Paste là lộ — model nhớ, log third-party giữ.
- Pillar 2 (How): Detect VN-PII (CCCD, SĐT, STK, biển số, địa chỉ) -> mask/tokenize -> proxy -> audit.
- Pillar 3 (Trust): Deploy trong VPC/on-prem, không train lại, log phục vụ kiểm toán.

## Competitors (để khỏi nói sai)
- Nightfall, Private AI, Microsoft Purview, Skyhigh — mạnh EN-PII, yếu VN-PII (CCCD/STK). Góc thắng: VN-PII + PDPL + deploy on-prem nhanh + pilot 2 tuần.
- Đừng claim "duy nhất", chỉ claim "tối ưu cho PDPL + tiếng Việt".

## Implications for BUILD
- Hero phải có 2 CTA (demo + paper) vì DPO thích đọc trước, CISO thích demo.
- FAQ bắt buộc: dữ liệu đi đâu? có train không? ở đâu? latency? false positive xử sao?
- Form demo chặn freemail để tăng lead quality; form paper cho freemail để tăng volume nuôi.
