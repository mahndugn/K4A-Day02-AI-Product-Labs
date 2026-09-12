# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: [Tên của bạn]
- Mã học viên: [Mã của bạn]
- Vai trò / bối cảnh (VD: sinh viên năm X, intern PM, ...): Kỹ sư phần mềm / Quản lý dự án
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem):
  - Hỗ trợ xử lý lỗi kĩ thuật (Triage bug/ticket)
  - Viết tài liệu release notes/changelog
  - Đọc hồ sơ thầu, trích xuất hóa đơn
  - Giải đáp thắc mắc nội bộ

---

## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | Lặp lại + Tốn thời gian | Phân loại & điều phối Ticket/Bug (Triage): Nhận lỗi, đọc log, đoán service và gán thủ công cho team. | L2 Support / Tech Lead. | Mất 15-20p/ticket; gán nhầm 15% làm tăng thời gian xử lý sự cố. |
| 2 | Tốn thời gian + AI có thể làm tốt hơn | Viết Release Notes/Changelog: Dịch 50-100 commit kỹ thuật thành ngôn ngữ kinh doanh cho C-level & KH. | Product Manager. | Mất 3-4 tiếng cuối mỗi sprint; dễ sót tính năng nhỏ hoặc viết quá technical. |
| 3 | Lặp lại + Pain từ người khác | Giải đáp FAQ nội bộ (Onboarding): Trả lời lặp đi lặp lại về bảo hiểm, ngày phép, remote working. | HR Generalist. | Mất 45p/ngày chỉ để copy-paste câu trả lời từ sổ tay nhân viên cho 10-15 câu hỏi. |
| 4 | Tốn thời gian + Lặp lại | Sàng lọc hồ sơ (CV Screening): Tải file, đọc lướt kỹ năng/kinh nghiệm và đánh dấu Pass/Fail. | HR Recruiter. | Mất 3-5p/CV, cả buổi sáng cho 1 đợt tuyển; dễ sót người giỏi do mỏi mắt. |
| 5 | Lặp lại + Tốn thời gian | Trích xuất thông tin hóa đơn (Reconciliation): Nhập tay mã số thuế, số tiền từ PDF vào phần mềm kế toán. | Kế toán thanh toán. | Mất 5-7p/hóa đơn; cuối tháng xử lý hàng trăm cái gây quá tải và sai sót. |
| 6 | Tốn thời gian + Lặp lại | Tóm tắt cuộc gọi tư vấn & log CRM: Phải nhớ và gõ lại nhu cầu, ngân sách, next steps sau khi cúp máy. | Sales / Account Executive. | Mất 15p sau mỗi cuộc gọi 45p; lười/quên nhập dẫn đến mất thông tin chăm sóc KH. |
| 7 | Tốn thời gian | Phân tích Hồ sơ mời thầu (RFP/Tender): Đọc 50-100 trang, nhặt yêu cầu kỹ thuật/pháp lý vào ma trận. | Pre-sales / Solution Architect. | Mất 1-2 ngày đọc và nhặt điều khoản trước khi chốt có nộp thầu hay không. |
| 8 | Tốn thời gian + Lặp lại | Tổng hợp báo cáo dự án đa kênh: Gom số liệu từ Jira, Slack, Drive để viết báo cáo trạng thái dự án. | Project Manager. | Mất 1-2 tiếng chiều thứ 6; phải gõ tay từ nhiều tool khác nhau. |
| 9 | Tốn thời gian + AI có thể làm tốt hơn | Viết Post-mortem Incident Report: Thu thập log, đọc hàng trăm tin nhắn Slack để ráp lại timeline sự cố. | SRE / Lead Developer. | Tốn 3-4 tiếng/báo cáo; việc ráp timeline từ tin nhắn rất hỗn loạn và gây nản. |
| 10 | Lặp lại + AI có thể làm tốt hơn | Phân loại phản hồi khảo sát (NPS): Đọc 500 dòng text tự do và gán nhãn thủ công (UI lỗi, Giá đắt,...). | CX Specialist / PO. | Mất 2 ngày/kỳ khảo sát; kết quả phân loại bị chủ quan, khó so sánh giữa các quý. |

> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi: Gợi ý các problem trong môi trường doanh nghiệp.
- Ý dùng được: Đủ các lĩnh vực HR, Sales, DevOps, Kế toán.
- Ý bỏ vì không phải pain thật: Không có (Các ý đều lấy từ bối cảnh thực tế đã lọc).

**Self-check Phase 1:**
- [x] Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể
- [x] Dùng ít nhất 3/4 lăng kính
- [x] Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Phân loại & điều phối Ticket/Bug | Workflow rõ, đo được bằng số ticket và phút/ticket. Impact lớn. | AI có đủ context để phân loại đúng team không? |
| 2 | Giải đáp FAQ nội bộ | Nỗi đau thực tế lặp lại nhiều. Dễ build bot/RAG. | Nhân viên có muốn xài bot không hay thích hỏi người? |
| 3 | Trích xuất thông tin hóa đơn | Lặp lại lớn, OCR + AI trích xuất (Vision) rất phù hợp. | Tỉ lệ OCR đọc sai với ảnh mờ là bao nhiêu? |

### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

---

#### Problem Card #1 — Phân loại & điều phối Ticket/Bug (Triage)

```text
Problem 1 câu: L2 Support mất 15-20 phút cho mỗi ticket báo lỗi từ khách hàng chỉ để đọc log, đoán nguyên nhân và điều phối thủ công cho team dev phù hợp, dễ dẫn đến gán nhầm và tăng thời gian xử lý sự cố.

Actor: Kỹ sư hỗ trợ kỹ thuật (L2 Support) / Tech Lead trực on-call.

Thời điểm / bối cảnh: Hàng ngày, khi có ticket mới đẩy vào hệ thống (Jira/Zendesk) từ khách hàng.

Current workflow 3-7 bước:
1. Khách hàng/L1 tạo ticket báo lỗi trên hệ thống.
2. L2 Support mở ticket, đọc mô tả lỗi.
3. L2 Support tìm và phân tích log tương ứng.
4. Đoán lỗi thuộc service nào (Auth, Payment, Notification,...).
5. Gán ticket (assign) cho team/Dev phụ trách service đó.

Bottleneck: Bước 3 & 4 (Đọc log và đoán service) mất nhiều thời gian nhất do log dài và hệ thống microservice phức tạp.

Impact: Mất 15-20 phút/ticket, với 20-30 ticket/ngày tương đương 5-10 tiếng. Gán nhầm team chiếm 15% làm tăng thời gian gián đoạn của khách hàng.

Success metric: Giảm thời gian triage từ 15 phút xuống dưới 3 phút/ticket; độ chính xác khi gán team đạt > 90%.

Non-AI alternative: Tạo hệ thống dropdown chi tiết cho L1 bắt khách hàng tự chọn category, hoặc filter theo từ khóa cứng (Rule-based). Khách hàng thường chọn sai và keyword cứng không hiểu context.

AI hypothesis: AI tự động đọc mô tả ticket và log đính kèm, trích xuất mã lỗi và dự đoán service/team liên quan với độ tự tin nhất định. L2 duyệt nhanh và click "Assign".

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #1** (ASCII / Mermaid / ảnh đính kèm):

```text
CURRENT STATE — 20 phút/ticket

[1 Nhận ticket: 1'] → [2 Đọc mô tả: 2'] → [3 Đọc log: 10'] → [4 Đoán team: 5']  <-- bottleneck → [5 Gán: 2']

FUTURE STATE — 3 phút/ticket

[1 Auto trigger: 0'] → [2 AI đọc log & đoán team: 1'] → [3 L2 review & Gán: 2']  <-- human boundary

Fallback: nếu AI sai (hoặc tự tin < 70%) thì L2 tự đọc log và đoán như cũ.
```

---

#### Problem Card #2 — Giải đáp FAQ nội bộ (Onboarding)

```text
Problem 1 câu: HR Generalist mất nhiều thời gian mỗi ngày để trả lời lặp đi lặp lại những câu hỏi cơ bản của nhân viên mới về chính sách bảo hiểm, ngày phép, remote working.

Actor: Chuyên viên nhân sự (HR Generalist).

Thời điểm / bối cảnh: Hàng ngày, đặc biệt là các tuần có đợt tuyển dụng/onboarding nhân sự mới.

Current workflow 3-7 bước:
1. Nhân viên mới nhắn tin hỏi trên Slack/Teams.
2. HR đọc tin nhắn và xác định chủ đề.
3. HR mở sổ tay nhân viên hoặc tài liệu nội bộ để tìm kiếm.
4. HR copy/paste nội dung hoặc gõ lại cho phù hợp.
5. HR gửi câu trả lời và link tài liệu cho nhân viên.

Bottleneck: Bước 3 & 4 (Tra cứu tài liệu và soạn câu trả lời) lặp đi lặp lại và ngắt quãng luồng công việc.

Impact: 1 HR trả lời 10-15 câu hỏi/ngày mất khoảng 45 phút. Context switching liên tục làm giảm năng suất làm các việc khác.

Success metric: Giảm 80% số lượng tin nhắn hỏi trực tiếp HR về FAQ cơ bản. Thời gian HR dùng để trả lời FAQ giảm xuống dưới 10 phút/ngày.

Non-AI alternative: Tạo file FAQ tổng hợp, Wiki/Confluence để nhân viên tự đọc. Nhân viên lười đọc hoặc search keyword không ra.

AI hypothesis: Bot AI (trên Slack/Teams) tự động tra cứu Knowledge Base (Sổ tay NV) bằng RAG và trả lời. Nếu không biết sẽ tự động tag HR.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết
```

**Draft workflow Card #2:**

```text
CURRENT STATE — 5 phút/câu

[1 NV nhắn: 1'] → [2 HR tra tài liệu: 2'] <-- bottleneck → [3 HR soạn trả lời & gửi: 2']

FUTURE STATE — 0 phút (cho HR)

[1 NV hỏi Bot: 1'] → [2 Bot trả lời & NV check: 1']  <-- human boundary

Fallback: Nếu NV thấy chưa thoả mãn hoặc Bot không biết, Bot tag @HR vào trả lời.
```

---

#### Problem Card #3 — Trích xuất thông tin hóa đơn (Reconciliation)

```text
Problem 1 câu: Kế toán thanh toán mất rất nhiều thời gian gõ tay các thông tin từ file PDF/ảnh hóa đơn vào phần mềm, dễ gây quá tải và sai sót lệch số liệu vào dịp cuối tháng.

Actor: Kế toán thanh toán (Accountant).

Thời điểm / bối cảnh: Hàng ngày/cuối tháng khi nhận nhiều hóa đơn từ nhà cung cấp.

Current workflow 3-7 bước:
1. Kế toán tải PDF/ảnh hóa đơn từ email.
2. Mở file hóa đơn 1 bên, phần mềm kế toán 1 bên.
3. Đọc và gõ tay mã số thuế, số hóa đơn, ngày, số tiền.
4. Đối chiếu thông tin với lệnh chuyển khoản.
5. Lưu bản ghi vào hệ thống.

Bottleneck: Bước 3 (Đọc và gõ tay dữ liệu từ file không chuẩn form) rất chậm.

Impact: Mất 5-7 phút/hóa đơn. Xử lý hàng trăm hóa đơn mỗi tháng gây tốn chục tiếng đồng hồ, nguy cơ sai sót cao.

Success metric: Thời gian xử lý hóa đơn giảm xuống < 1 phút/cái. 100% không có lỗi sai (accuracy).

Non-AI alternative: Yêu cầu nhà cung cấp gửi định dạng chuẩn (XML) hoặc OCR cứng theo template. OCR cứng dễ vỡ form khi đổi nhà cung cấp.

AI hypothesis: Dùng AI Vision tự trích xuất thông tin từ hóa đơn các form khác nhau và điền sẵn, Kế toán chỉ review và duyệt.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #3:**

```text
CURRENT STATE — 6 phút/hóa đơn

[1 Tải file: 1'] → [2 Gõ tay số liệu: 3']  <-- bottleneck → [3 Đối chiếu tay & Lưu: 2']

FUTURE STATE — 1 phút/hóa đơn

[1 Tải & Upload: 0.5'] → [2 AI điền form: 0'] → [3 Kế toán review & Lưu: 0.5']  <-- human boundary

Fallback: Nếu AI OCR sai (ảnh mờ), kế toán gõ lại trường dữ liệu đó.
```

---

### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```text
Problem #1: Phân loại & điều phối Ticket/Bug (Triage).
```

**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```text
Quy trình Triage hiện tại nghẽn ở khâu đọc log, ngốn 15-20 phút cho mỗi ticket. Nếu dùng AI phân tích log và tự đoán team phụ trách, thời gian giảm xuống còn 3 phút. Impact dây chuyền cực lớn vì nó giúp giảm thời gian chờ của khách hàng, tăng tốc độ xử lý sự cố.
```

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

```text
Liệu các L2 Support có đủ tin tưởng AI để bấm Assign ngay không, hay họ vẫn phải đi đọc lại toàn bộ log từ đầu cho chắc chắn? (Nếu đọc lại thì sẽ không tiết kiệm được thời gian).
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra: AI có thể gán sai team nếu log mơ hồ hoặc không chứa đủ nguyên nhân lỗi thực tế.
- Tôi sửa gì: Thêm Fallback rất rõ (Nếu tự tin <70% thì L2 tự xử lý) và Boundary là L2 Review chứ không cho AI tự gán luôn.

### Self-check nộp phần 01
- [x] Có 5+ problems + top 3 Cards đủ field
- [x] Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- [x] Đã chọn 1 card pitch + câu hỏi challenge
