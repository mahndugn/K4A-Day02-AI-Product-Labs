# Day 02 - Individual Problem Scan & Top 3 Problem Cards

## Phase 1 — Individual Scan (10 Problems)

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại + Tốn thời gian | **Phân loại & điều phối Ticket/Bug (Triage)**: Nhận lỗi, đọc log, đoán service và gán thủ công cho team. | L2 Support / Tech Lead. | Mất 15-20p/ticket; gán nhầm 15% làm tăng thời gian xử lý sự cố. |
| 2 | Tốn thời gian + AI có thể làm tốt hơn | **Viết Release Notes/Changelog**: Dịch 50-100 commit kỹ thuật thành ngôn ngữ kinh doanh cho C-level & KH. | Product Manager. | Mất 3-4 tiếng cuối mỗi sprint; dễ sót tính năng nhỏ hoặc viết quá technical. |
| 3 | Lặp lại + Pain từ người khác | **Giải đáp FAQ nội bộ (Onboarding)**: Trả lời lặp đi lặp lại về bảo hiểm, ngày phép, remote working. | HR Generalist. | Mất 45p/ngày chỉ để copy-paste câu trả lời từ sổ tay nhân viên cho 10-15 câu hỏi. |
| 4 | Tốn thời gian + Lặp lại | **Sàng lọc hồ sơ (CV Screening)**: Tải file, đọc lướt kỹ năng/kinh nghiệm và đánh dấu Pass/Fail. | HR Recruiter. | Mất 3-5p/CV, cả buổi sáng cho 1 đợt tuyển; dễ sót người giỏi do mỏi mắt. |
| 5 | Lặp lại + Tốn thời gian | **Trích xuất thông tin hóa đơn (Reconciliation)**: Nhập tay mã số thuế, số tiền từ PDF vào phần mềm kế toán. | Kế toán thanh toán. | Mất 5-7p/hóa đơn; cuối tháng xử lý hàng trăm cái gây quá tải và sai sót. |
| 6 | Tốn thời gian + Lặp lại | **Tóm tắt cuộc gọi tư vấn & log CRM**: Phải nhớ và gõ lại nhu cầu, ngân sách, next steps sau khi cúp máy. | Sales / Account Executive. | Mất 15p sau mỗi cuộc gọi 45p; lười/quên nhập dẫn đến mất thông tin chăm sóc KH. |
| 7 | Tốn thời gian | **Phân tích Hồ sơ mời thầu (RFP/Tender)**: Đọc 50-100 trang, nhặt yêu cầu kỹ thuật/pháp lý vào ma trận. | Pre-sales / Solution Architect. | Mất 1-2 ngày đọc và nhặt điều khoản trước khi chốt có nộp thầu hay không. |
| 8 | Tốn thời gian + Lặp lại | **Tổng hợp báo cáo dự án đa kênh**: Gom số liệu từ Jira, Slack, Drive để viết báo cáo trạng thái dự án. | Project Manager. | Mất 1-2 tiếng chiều thứ 6; phải gõ tay từ nhiều tool khác nhau. |
| 9 | Tốn thời gian + AI có thể làm tốt hơn | **Viết Post-mortem Incident Report**: Thu thập log, đọc hàng trăm tin nhắn Slack để ráp lại timeline sự cố. | SRE / Lead Developer. | Tốn 3-4 tiếng/báo cáo; việc ráp timeline từ tin nhắn rất hỗn loạn và gây nản. |
| 10 | Lặp lại + AI có thể làm tốt hơn | **Phân loại phản hồi khảo sát (NPS)**: Đọc 500 dòng text tự do và gán nhãn thủ công (UI lỗi, Giá đắt,...). | CX Specialist / PO. | Mất 2 ngày/kỳ khảo sát; kết quả phân loại bị chủ quan, khó so sánh giữa các quý. |

---

## Phase 2 — Top 3 Problem Cards + Draft Workflow

### Chọn Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Phân loại & điều phối Ticket/Bug | Workflow rõ, đo được bằng số ticket và phút/ticket. Impact rất lớn với hệ thống. | AI có đủ bối cảnh (context) để phân loại đúng team không? |
| 2 | Trích xuất thông tin hóa đơn | Lặp lại rất nhiều, thao tác "đọc ảnh -> điền form" cực kì hợp để dùng AI. | Tỉ lệ OCR (đọc chữ) chính xác đối với các hóa đơn bị mờ, chụp tay là bao nhiêu? |
| 3 | Giải đáp FAQ nội bộ | Nỗi đau thực tế, nhân sự mất thời gian việc không tên. Dễ so sánh Agent/RAG. | Bot có giải quyết triệt để hay nhân viên vẫn muốn hỏi người thật cho chắc? |

---

### Problem Card #1: Phân loại & điều phối Ticket/Bug (Triage)

**Problem 1 câu:** L2 Support mất 15-20 phút cho mỗi ticket báo lỗi từ khách hàng chỉ để đọc log, đoán nguyên nhân và điều phối thủ công cho team dev phù hợp, dễ dẫn đến gán nhầm và tăng thời gian xử lý sự cố.

**Actor:** Kỹ sư hỗ trợ kỹ thuật (L2 Support) / Tech Lead trực on-call.

**Thời điểm / bối cảnh:** Hàng ngày, khi có ticket mới đẩy vào hệ thống (Jira/Zendesk) từ khách hàng.

**Current workflow 3-7 bước:**
1. Khách hàng/L1 tạo ticket báo lỗi trên hệ thống.
2. L2 Support mở ticket, đọc mô tả lỗi.
3. L2 Support tìm và phân tích log tương ứng.
4. Đoán lỗi thuộc service nào (Auth, Payment, Notification,...).
5. Gán ticket (assign) cho team/Dev phụ trách service đó.

**Bottleneck:** Bước 3 & 4 (Đọc log và đoán service) mất nhiều thời gian nhất do log dài và hệ thống có nhiều microservices phức tạp.

**Impact:** Mất 15-20 phút/ticket, với 20-30 ticket/ngày tương đương 5-10 tiếng. Gán nhầm team chiếm 15% làm tăng thời gian gián đoạn của khách hàng.

**Success metric:** Giảm thời gian triage từ 15 phút xuống dưới 3 phút/ticket; độ chính xác khi gán team đạt > 90%.

**Non-AI alternative:** Tạo hệ thống dropdown chi tiết cho L1 bắt khách hàng tự chọn category, hoặc filter theo từ khóa cứng (Rule-based). Tuy nhiên khách hàng thường chọn sai và từ khóa cứng không hiểu ngữ cảnh (context).

**AI hypothesis:** AI tự động đọc mô tả ticket và log đính kèm, trích xuất mã lỗi và dự đoán service/team liên quan với độ tự tin nhất định. L2 duyệt nhanh và click "Assign".

**Quick gut:**
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

**Draft Workflow #1:**
```text
CURRENT STATE — 20 phút/ticket
[1 Nhận ticket: 1']
→ [2 Đọc mô tả: 2']
→ [3 Tìm & phân tích log: 10'] <-- bottleneck
→ [4 Đoán service: 5'] <-- bottleneck
→ [5 Gán cho Dev: 2']

FUTURE STATE — 3 phút/ticket
[1 Auto-trigger khi có ticket: 0']
→ [2 AI phân tích text + log & dự đoán team: 1']
→ [3 L2 Review dự đoán của AI: 1'] <-- human boundary
→ [4 L2 Gán cho Dev hoặc sửa lại: 1']

Fallback: Nếu tự tin của AI thấp (<70%), L2 tự đọc log và đoán như quy trình cũ.
```

---

### Problem Card #2: Trích xuất thông tin hóa đơn (Reconciliation)

**Problem 1 câu:** Kế toán thanh toán mất rất nhiều thời gian gõ tay các thông tin từ file PDF/ảnh hóa đơn vào phần mềm, dễ gây quá tải và sai lệch số liệu vào dịp cuối tháng.

**Actor:** Kế toán thanh toán (Accountant).

**Thời điểm / bối cảnh:** Hàng ngày và đặc biệt căng thẳng vào cuối tháng khi có nhiều hóa đơn từ nhà cung cấp gửi về.

**Current workflow 3-7 bước:**
1. Kế toán tải PDF/ảnh hóa đơn từ email.
2. Mở file hóa đơn trên một màn hình, phần mềm kế toán trên màn hình khác.
3. Đọc và gõ tay mã số thuế, số hóa đơn, ngày, số tiền.
4. Đối chiếu thông tin với lệnh chuyển khoản.
5. Lưu bản ghi vào hệ thống phần mềm.

**Bottleneck:** Bước 3 (Đọc và gõ tay dữ liệu từ file không có định dạng chuẩn) rất chậm và mỏi mắt.

**Impact:** Mất 5-7 phút/hóa đơn. Xử lý hàng trăm hóa đơn mỗi tháng gây tốn hàng chục giờ đồng hồ, nguy cơ sai sót cao dẫn đến hậu quả tài chính.

**Success metric:** Thời gian xử lý 1 hóa đơn giảm xuống < 1 phút. 100% không có sai sót (accuracy) trong việc nhập liệu sau đối chiếu.

**Non-AI alternative:** Yêu cầu nhà cung cấp gửi định dạng chuẩn (XML hóa đơn điện tử) thay vì PDF/ảnh. Hoặc dùng OCR truyền thống theo template (tuy nhiên mỗi nhà cung cấp có template hóa đơn khác nhau sẽ làm OCR vỡ form).

**AI hypothesis:** Dùng AI (Vision/Document Intelligence) tự động trích xuất các trường thông tin quan trọng từ hóa đơn (bất kể định dạng layout) và điền sẵn vào form. Kế toán chỉ việc nhìn lại và bấm Approve.

**Quick gut:**
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

**Draft Workflow #2:**
```text
CURRENT STATE — 6 phút/hóa đơn
[1 Tải hóa đơn từ email: 1']
→ [2 Mở song song file & phần mềm: 1']
→ [3 Gõ tay số liệu: 3'] <-- bottleneck
→ [4 Đối chiếu lệnh CK thủ công: 1']

FUTURE STATE — 1 phút/hóa đơn
[1 Tải hóa đơn & upload vào tool: 0.5']
→ [2 AI Vision tự động trích xuất & điền form: 0']
→ [3 Kế toán đối chiếu form đã điền với ảnh hóa đơn: 0.5'] <-- human boundary
→ [4 Approve & Lưu: 0']

Fallback: Nếu OCR/AI đọc sai do ảnh mờ, Kế toán sẽ sửa lại trường dữ liệu bị sai thủ công.
```

---

### Problem Card #3: Giải đáp FAQ nội bộ (Onboarding)

**Problem 1 câu:** HR Generalist mất nhiều thời gian mỗi ngày để trả lời lặp đi lặp lại những câu hỏi cơ bản của nhân viên mới về chính sách bảo hiểm, ngày phép, remote working.

**Actor:** Chuyên viên nhân sự (HR Generalist).

**Thời điểm / bối cảnh:** Hàng ngày, đặc biệt là các tuần có đợt tuyển dụng, onboarding nhân sự mới.

**Current workflow 3-7 bước:**
1. Nhân viên mới nhắn tin hỏi trên Slack/Teams.
2. HR đọc tin nhắn và xác định chủ đề cần giải đáp.
3. HR mở sổ tay nhân viên hoặc file nội bộ (PDF/Excel) để tìm kiếm.
4. HR copy/paste nội dung hoặc gõ lại cho phù hợp câu hỏi.
5. HR gửi câu trả lời và link tài liệu đính kèm cho nhân viên.

**Bottleneck:** Bước 3 & 4 (Tra cứu tài liệu và soạn câu trả lời) lặp đi lặp lại rất nhàm chán và làm ngắt quãng công việc chính.

**Impact:** 1 HR trả lời 10-15 câu hỏi/ngày mất khoảng 45 phút. Quá trình này gây gián đoạn luồng suy nghĩ (context switching), làm giảm năng suất làm các việc chiến lược hơn.

**Success metric:** Giảm 80% số lượng tin nhắn nhân viên phải hỏi trực tiếp HR về các quy định cơ bản. Thời gian HR dùng để trả lời FAQ giảm xuống dưới 10 phút/ngày.

**Non-AI alternative:** Tạo file FAQ tổng hợp hoặc thiết lập wiki/Confluence để nhân viên tự search. Tuy nhiên nhân viên lười search hoặc search keyword không chuẩn.

**AI hypothesis:** Một Bot AI (tích hợp trên Slack/Teams) tự động trả lời các câu hỏi FAQ dựa trên knowledge base (sổ tay nhân viên). Nếu Bot không biết, nó sẽ tự động tag HR vào trả lời.

**Quick gut:**
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết

**Draft Workflow #3:**
```text
CURRENT STATE — 5 phút/câu hỏi
[1 NV nhắn Slack hỏi quy định: 1']
→ [2 HR đọc tin: 1']
→ [3 HR tra tài liệu: 2'] <-- bottleneck
→ [4 HR soạn trả lời & gửi: 1']

FUTURE STATE — 0 phút/câu hỏi (cho HR)
[1 NV nhắn cho Bot/Slack channel: 1']
→ [2 Bot Agent tự động tra cứu RAG & trả lời: 0']
→ [3 NV đánh giá hữu ích / bấm tag HR nếu chưa rõ: 1'] <-- boundary

Fallback: Bot không tự tin hoặc câu hỏi nằm ngoài tài liệu, Bot báo "Tôi chưa rõ, xin phép tag @HR_Name vào hỗ trợ".
```

---

### Card tôi muốn pitch nhất

**Card tôi muốn pitch nhất:** 
Problem #1: Phân loại & điều phối Ticket/Bug (Triage).

**Vì sao:** 
Bởi vì đây là một bài toán có impact dây chuyền cực lớn. Việc giảm thời gian triage từ 15 phút xuống 3 phút không chỉ tiết kiệm sức cho team Support, mà còn giảm thời gian chết (downtime) của khách hàng, đẩy nhanh quá trình fix bug của team Dev. Metric rất rõ ràng và dễ đo lường.

**Câu hỏi tôi muốn nhóm challenge:** 
Liệu L2 Support có đủ tin tưởng AI để click Assign ngay, hay cuối cùng họ vẫn sẽ phải đi đọc lại toàn bộ log từ đầu (như vậy thì không tiết kiệm được thời gian)? 
