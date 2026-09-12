# 02 — Group Problem Statement (Bản nộp nhóm)

> Làm chung 1 bản, mỗi thành viên copy vào repo cá nhân. Đi theo Phase 3 → 6 trong `01-worksheet.md`. Nhóm chỉ chọn **candidate problem** ở Phase 3, viết Problem Statement sau khi validate + vẽ workflow.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm (VD: facilitator, workflow, research, writer) |
|-----|-----------|-------------|---------------------------------------------------------------|
| 1   | [Tên của bạn] | [Mã HV]    | Facilitator & Workflow |
| 2   | Nguyễn Văn A  | ...         | Research & Validation |
| 3   | Trần Thị B    | ...         | Writer & Metrics |

**Candidate problem nhóm chọn (1 câu):**
Bác sĩ Vinmec mất 30-40% thời gian làm việc để tự gõ hồ sơ bệnh án (EMR) sau mỗi lượt khám, làm giảm năng suất khám và tăng tỷ lệ sai sót.

---

## Phase 3 — Group Convergence: từ 9-12 candidates về 1

### 3.1. Trình bày top 3 mỗi người (mỗi candidate 1-2 phút)

*(Ví dụ minh họa rút gọn)*
| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh của nhóm |
|---|---|---|---|---|---|
| 1 | Bạn | Bác sĩ gõ EMR thủ công sau mỗi lượt khám | Bác sĩ Vinmec | Mất 8-12p/lượt chỉ để gõ text | Pain rất thật, scale lớn. |
| 2 | A | Kế toán nhập tay hóa đơn PDF | Kế toán thanh toán | Gõ tay số tiền, ngày tháng | Đau, nhưng đã có tool OCR. |
| 3 | B | HR trả lời FAQ lặp đi lặp lại | Chuyên viên HR | Tra tài liệu và gõ lại trả lời | Hợp làm chatbot nhưng impact không bằng y tế. |
| ... | ... | ... | ... | ... | ... |

### 3.2. Gom trùng / cluster (gom 9-12 ý thành 3-4 cụm)

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A | Bác sĩ gõ EMR, Kế toán nhập hóa đơn | Chuyển dữ liệu phi cấu trúc (giọng nói, PDF) vào hệ thống có cấu trúc. | AI làm rất tốt khâu này. |
| B | HR trả lời FAQ, IT Helpdesk support | Giải đáp thông tin từ Knowledge Base. | Hướng làm Bot/Agent. |
| C | Viết Release Notes, Họp lấy Meeting notes | Tóm tắt và phân loại nội dung dài thành text ngắn gọn. | Có thể dùng LLM cơ bản. |

### 3.3. Shortlist (giữ 2-3 bài trả lời được 7 câu hỏi worksheet)

| Candidate | Vì sao vào shortlist (2-3 ý) | Rủi ro / điều chưa rõ |
|---|---|---|
| Bác sĩ gõ EMR | Impact cực lớn (3000+ bác sĩ). Workflow quá rõ ràng (1 lượt khám). | AI nhận diện tiếng Việt y khoa có chính xác không? |
| Kế toán nhập hóa đơn | Dễ đo lường ROI (thời gian/hóa đơn). Có data hóa đơn thực tế. | Khó xin data thật vì bảo mật tài chính. |

### 3.4. Score để đồng thuận (chấm 1-5, ép nói rõ vì sao cho 5 / cho 3)

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bác sĩ EMR | 5 | 5 | 5 | 5 | 5 | 5 | 4 | 34 |
| Kế toán HĐ | 5 | 5 | 4 | 4 | 4 | 5 | 4 | 31 |

**Candidate nhóm chọn (1 bài duy nhất):**

```text
Bác sĩ Vinmec Gõ EMR Thủ Công
```

**Vì sao chọn (4-5 câu):**

```text
Bài toán có quy mô cực lớn (hơn 3.000 bác sĩ) và ảnh hưởng trực tiếp đến doanh thu phòng khám lẫn trải nghiệm bệnh nhân. Workflow rất gọn gàng và khép kín trong 1 lượt khám 25-30 phút. Nút thắt rõ ràng nằm ở khâu "chuyển lời nói/suy nghĩ thành text trên máy tính". Dễ dàng đo lường bằng việc bấm giờ (time-motion) trước và sau khi có AI.
```

**Vì sao KHÔNG chọn các candidate còn lại (mỗi bài 2-3 câu):**

```text
Không chọn bài "Kế toán nhập hóa đơn" vì bài này hiện tại trên thị trường đã có các giải pháp OCR trưởng thành, không cần thiết kế một luồng AI gen quá phức tạp. Bài HR FAQ thì giá trị kinh tế mang lại không thể so sánh với việc giải phóng sức lao động cho bác sĩ lâm sàng.
```

---

## Phase 4 — Quick Validation + Research

### 4.1. Quick validation (ít nhất 1 cách: interview 2-3 người hoặc survey 5-10 người)

| Nguồn | Số người / mẫu | Tín hiệu xác nhận (kèm quote nguyên văn) | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Interview | 2 bác sĩ | "Khám bệnh 5 phút mà ngồi gõ máy tính 10 phút, cực kỳ mỏi mắt vào cuối ngày." | "Bệnh nhân VN hay nói lan man, ghi âm cả cục chưa chắc xài được." | Thu hẹp: AI chỉ nghe, lọc ý chính và điền form, bác sĩ phải duyệt. |

**Insight sau validation (1-2 câu — pain thật nằm ở đâu):**

```text
Pain không chỉ là việc gõ phím, mà là sự mệt mỏi về nhận thức (cognitive load) khi phải nhớ lại chi tiết cuộc khám và chuyển nó thành ngôn ngữ mã hóa ICD/y khoa chuẩn mực vào cuối ngày.
```

### 4.2. Research giải pháp đã có (ít nhất 2-3 tools/patterns + 1-2 link kiểm được)

| Nguồn / tool / case | Link | Họ giải quyết bước nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Nuance Dragon Medical (Microsoft) | nuance.com | Voice-to-text chuyên ngành y tế. | Độ chính xác y khoa cao, tích hợp sâu EMR. | Chủ yếu tiếng Anh, chi phí cực đắt. | Pattern: Ambient listening (nghe nền) tốt hơn là cầm mic đọc từng chữ. |
| Nabla Copilot | nabla.com | Tự tạo SOAP note từ cuộc nói chuyện. | Thiết kế UI/UX tuyệt vời, review dễ. | Tiếng Việt chưa hỗ trợ tốt. | AI draft -> Human review là luồng chuẩn mực. |
| AWS HealthScribe | aws.amazon.com | API tạo notes và mã hóa y tế. | Trích xuất entity y tế tốt. | Chỉ là API, phải tự xây app. | Cần phải tách bạch NLP y khoa với ghi âm thường. |

**Research takeaway (2-3 câu — nên build gì / không build gì):**

```text
Thị trường đã chứng minh giải pháp Ambient Clinical Voice (AI nghe lén và ghi chép) là tương lai. Chúng ta không build agent tự động chẩn đoán bệnh, mà build Workflow "Trợ lý ghi chép" (Scribe) nghe thụ động, điền form và bắt buộc bác sĩ review trước khi ký.
```

---

## Phase 5 — Workflow + Problem Statement

### 5.1. Current workflow bản nhóm

```text
CURRENT STATE — 23-29 phút/bệnh nhân

[1 Khám BN, giao tiếp: 10'] 
→ [2 Bác sĩ gõ EMR thủ công: 8-12']  <-- bottleneck 
→ [3 Tra cứu mã ICD/thuốc: 3-5']  <-- bottleneck 
→ [4 Ký số & lưu hệ thống: 2']
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú (handoff? bottleneck?) |
|---|---|---|---|---|---|
| 1 | Bác sĩ & BN | Lời nói, triệu chứng | Nhận định lâm sàng | 10' / lượt | Tương tác người - người |
| 2 | Bác sĩ | Trí nhớ của bác sĩ | Text bệnh án (SOAP) | 8-12' / lượt | Bottleneck: Mỏi tay, mỏi mắt, dễ quên |
| 3 | Bác sĩ | Tên bệnh, tên thuốc | Mã ICD-10, mã thuốc | 3-5' / lượt | Bottleneck: Mất công search dropdown EMR |
| 4 | Bác sĩ | Bản nháp EMR hoàn thiện | Hồ sơ được ký số | 2' / lượt | Bắt buộc pháp lý |

**Bottleneck chính (2-3 câu):**

```text
Bước 2 và 3 chiếm tới gần 50% thời gian của một chu kỳ khám. Bác sĩ phải đóng vai trò "người nhập liệu" và "tra cứu danh mục" thay vì tập trung chuyên môn, dẫn đến năng suất khám không thể tăng thêm.
```

### 5.2. Future workflow bản nhóm

```text
FUTURE STATE — 13-15 phút/bệnh nhân

[1 Khám BN + AI ghi âm nền: 10'] 
→ [2 AI auto-draft EMR & mapping ICD: 1-2'] 
→ [3 Bác sĩ review & ký số: 2-3']  <-- human boundary

Fallback: Nếu AI nghe sai (tiếng lóng/thuật ngữ mới), bác sĩ sửa tay trực tiếp trên bản draft; log correction gửi về train model.
```

**Before/after impact:**

| Metric | Trước | Sau kỳ vọng | Cách đo |
|---|---:|---:|---|
| Tổng thời gian chu kỳ | 23-29 phút | 13-15 phút | Bấm giờ time-motion thực tế |
| Thời gian gõ & tra mã | 11-17 phút | 1-2 phút (do AI) | Hệ thống log thời gian |
| Thời gian review thủ công | 0 phút | 2-3 phút | Bác sĩ thao tác trên màn hình |
| Năng suất bệnh nhân/ca | ~15 BN/ca | ~25 BN/ca | Số lượng ticket khám hoàn thành |
| Risk mới | Không có | Lỗi hallucination của AI | Đo tỉ lệ % text bị bác sĩ sửa lại |

### 5.3. Problem Statement v0 (mỗi field 2-3 câu)

| Field | Nội dung |
|---|---|
| **Actor** | Bác sĩ lâm sàng tại hệ thống Vinmec (ngoại trú). |
| **Workflow** | Khám -> Bệnh nhân ra ngoài -> Bác sĩ gõ bệnh án -> Tra mã ICD -> Ký số. |
| **Bottleneck** | Bước gõ bệnh án và tra mã ICD chiếm 11-17 phút, gây mệt mỏi và tốn thời gian. |
| **Impact** | Bác sĩ mất 30-40% thời gian làm việc để nhập liệu, giới hạn số lượng bệnh nhân khám được mỗi ngày và gây kiệt sức (burnout). |
| **Success Metric** | Giảm thời gian nhập liệu EMR từ ~10 phút xuống < 2 phút/lượt. Tăng 20% lượng bệnh nhân khám được/ngày. |
| **Boundary** | AI chỉ đóng vai trò thư ký ghi chép (scribe), KHÔNG đưa ra quyết định lâm sàng, KHÔNG kê đơn thuốc. |

---

## Phase 6 — Rule / Workflow / Agent + Decision

### 6.0. Ma trận độ phù hợp (suy nghĩ nhanh, không thay quyết định cuối)

- Độ mơ hồ: [x] Cao (nhiều cách trả lời vẫn OK) — Vì sao: Lời nói bệnh nhân rất lan man, không có format chuẩn, ngôn ngữ tự nhiên nhiều tiếng lóng.
- Độ phức tạp: [x] Thấp (1-2 bước) — Vì sao: Luồng xử lý chỉ là Audio -> Text -> Structured Data. Đường đi thẳng tắp.

**Bài toán nhóm nằm ở ô nào:**

```text
Mơ hồ cao - Phức tạp thấp.
```

**Vì sao (2-3 câu):**

```text
Dữ liệu đầu vào (giọng nói) cực kỳ nhiễu và mơ hồ, cần LLM để tóm tắt và hiểu ngữ cảnh y khoa. Tuy nhiên, quy trình (process) lại rất tuyến tính: nghe -> tóm tắt -> điền form, không cần AI phải tự quyết định bước đi tiếp theo.
```

### 6.1. So sánh Rule / Workflow / Agent (so trên cùng 1 bài)

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? (Dùng cho bước nào?) |
|---|---|---|---|---|
| **Rule** | Dùng template gõ tắt trên EMR. | Chỉ đủ cho các ca khám sức khỏe định kỳ giống hệt nhau. | Không cover được các ca bệnh phức tạp có diễn biến riêng. | Không chọn. |
| **Workflow** | App thu âm -> AI Speech-to-text -> LLM tóm tắt SOAP -> Bác sĩ duyệt. | Đủ để xử lý thông tin phi cấu trúc thành form chuẩn mực. | AI draft sai (hallucination), bác sĩ lười review mà bấm ký luôn. | Chọn (Làm toàn bộ). |
| **Agent** | AI lắng nghe, tự tra cứu lịch sử bệnh án, tự đề xuất phác đồ điều trị và đặt lịch hẹn. | Chỉ dùng khi muốn AI làm bác sĩ ảo. | Rủi ro pháp lý và an toàn tính mạng cực lớn. Không thể vượt rào y tế. | Không chọn. |

**5 câu hỏi chốt (trả lời câu đầy đủ):**
1. Rule có giải được 70-80% case không? Không, ngôn ngữ khám bệnh rất đa dạng, rule/template chỉ xử lý được 20%.
2. Các bước có đi thẳng một đường không hay phải rẽ nhánh? Đi thẳng 1 đường: Audio -> Text -> Form.
3. Có thật sự cần Agent tự lập kế hoạch + gọi tool không? Tuyệt đối không. Bác sĩ mới là người ra quyết định y khoa.
4. Nếu AI sai, ai phát hiện đầu tiên và sửa trong bao lâu? Bác sĩ là người phát hiện khi review bản draft, sửa mất 30s.
5. Có hạ được từ Agent → Workflow → Rule không? Đã chọn Workflow. Không thể hạ xuống Rule.

**Mức chọn:**

```text
Workflow
```

**Vì sao chọn (3-4 câu):**

```text
Vì bài toán cần sức mạnh NLP/LLM để xử lý ngôn ngữ y khoa mơ hồ, nhưng quy trình lại phải được kiểm soát nghiêm ngặt 100%. Workflow cho phép chèn "Human-in-the-loop" (Bác sĩ review) làm chốt chặn cuối cùng. Vừa giải phóng sức lao động, vừa đảm bảo tuân thủ pháp lý y tế.
```

### 6.2. Problem Statement v1 (v0 sửa chặt hơn + 3 field cuối)

| Field | Nội dung |
|---|---|
| **Actor** | Bác sĩ lâm sàng ngoại trú tại Vinmec. |
| **Workflow** | Khám (ghi âm nền) -> AI auto-draft EMR -> Bác sĩ review form -> Ký số. |
| **Bottleneck** | Bước gõ bệnh án và tra mã ICD thủ công ngốn 11-17 phút/lượt. |
| **Impact** | Tốn 30-40% quỹ thời gian của bác sĩ cho việc hành chính, gây kiệt sức và kìm hãm công suất bệnh viện. |
| **Success Metric** | Thời gian gõ EMR giảm xuống < 2 phút. Tỷ lệ text AI draft bị sửa < 15%. |
| **Boundary** (làm / không làm) | AI chỉ tóm tắt SOAP và điền form. Tuyệt đối không đưa ra chẩn đoán hay thay đổi quyết định dùng thuốc của bác sĩ. |
| **AI intervention point** | Chen vào giữa khâu kết thúc nói chuyện với bệnh nhân và khâu bác sĩ lưu hồ sơ. |
| **Mức chọn** | Workflow. Vì cần xử lý ngôn ngữ tự nhiên nhưng phải có luồng kiểm soát review bắt buộc. |
| **Rủi ro & người thật kiểm tra** | Rủi ro: AI nhận diện nhầm "có u" thành "không u" (hallucination). Kiểm soát: Bác sĩ bắt buộc phải đọc màn hình review và ký số xác nhận pháp lý. |

### 6.3. Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú (câu đầy đủ) |
|---|---|---|
| Actor + workflow rõ chưa? | Yes | Workflow khép kín trong 1 phiên khám bệnh. |
| Baseline + metric đo được chưa? | Yes | Có thể đo ngay bằng đồng hồ bấm giờ (time-motion). |
| Data/input đủ dùng chưa? | Not Yet | Cần thu thập audio khám bệnh thực tế để test độ nhạy tiếng Việt. |
| AI sai, hậu quả chấp nhận được không? | Yes | Chấp nhận được NẾU bác sĩ làm đúng quy trình review trước khi ký. |
| Có người review/owner không? | Yes | Bác sĩ là người chịu trách nhiệm pháp lý cao nhất. |
| Có cách non-AI đơn giản hơn không? | No | Đã tối ưu EMR UI/UX nhưng vẫn chạm ngưỡng giới hạn sức người. |

**Decision:**

```text
Go
```

**Lý do (3-4 câu dựa trên bằng chứng):**

```text
Vấn đề có tính sống còn với trải nghiệm bác sĩ và năng suất bệnh viện. Nút thắt hoàn toàn có thể được gỡ bỏ bằng công nghệ LLM và Speech-to-Text hiện tại. Các rủi ro y tế được rào lại an toàn bằng chốt chặn "Bác sĩ review & ký số".
```

**Nếu Go — pilot nhỏ nhất (data nào, chạy tay ra sao, đo 3 số nào):**

```text
Thu âm bằng điện thoại 20 ca khám của 1 bác sĩ quen (đã xin phép bệnh nhân). Dùng OpenAI Whisper để dịch audio -> text, dùng Claude để tóm tắt ra form SOAP. Cho bác sĩ đọc lại bản draft và bấm giờ xem thời gian đọc/sửa có dưới 2 phút không.
```

**Exit / rollback (khi nào dừng AI, quay về cách cũ):**

```text
Nếu bác sĩ phải sửa tay lại quá 30% nội dung bản draft trong 3 ngày thử nghiệm liên tiếp (AI làm mất thời gian hơn cả tự gõ) -> Rollback về gõ tay.
```

---

### Self-check nộp phần 02 (nhóm)
- [x] Có nhật ký hội tụ 9-12 → 1 (cluster + shortlist + score)
- [x] Có validation (quote thật) + research (link kiểm được)
- [x] Có workflow trước/sau đủ thời gian, handoff, bottleneck, boundary, fallback
- [x] Có PS v0 → v1, metric có trước/sau + cách đo, boundary có làm/không làm
- [x] Có so sánh Rule/Workflow/Agent + Decision Go/Not Yet/No-Go có lý do
