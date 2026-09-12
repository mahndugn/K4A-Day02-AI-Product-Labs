# 02 — Group Problem Statement (Bản nộp nhóm)

> Làm chung 1 bản, mỗi thành viên copy vào repo cá nhân. Đi theo Phase 3 → 6 trong `01-worksheet.md`. Nhóm chỉ chọn **candidate problem** ở Phase 3, viết Problem Statement sau khi validate + vẽ workflow.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm (VD: facilitator, workflow, research, writer) |
|-----|-----------|-------------|---------------------------------------------------------------|
| 1   | Từ Hoàng Giang | 2A202602363 | Leader, Facilitator, Workflow |
| 2   | Trần Nguyễn Thái Duy | 2A202602991 | Slide (chính), Writer |
| 3   | Phạm Thành Trung | 2A202602949 | Research, Workflow |
| 4   | Đinh Mạnh Dũng | 2A202602975 | Facilitator, Writer |
| 5   | Nguyễn Hồng Phi | 2A202602750 | Research, Writer |

**Candidate problem nhóm chọn (1 câu):**

Bác sĩ lâm sàng Vinmec mất 30-40% thời gian làm việc để tự gõ hồ sơ bệnh án (EMR) sau mỗi lượt khám, trong khi AI voice-to-text kết hợp NLP y tế có thể tự động điền phần lớn nội dung, để bác sĩ chỉ cần review và ký số.

---

## Phase 3 — Group Convergence: từ 9-12 candidates về 1

### 3.1. Trình bày top 3 mỗi người (mỗi candidate 1-2 phút)

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh của nhóm |
|---|---|---|---|---|---|
| 1 | Phạm Thành Trung | Bác sĩ Vinmec tự gõ hồ sơ bệnh án (EMR) sau mỗi lượt khám — mất 8-12 phút/lượt, chiếm 30-40% thời gian làm việc | Bác sĩ lâm sàng Vinmec (3.000+ bác sĩ) | Gõ narrative (Chief Complaint + HPI) và tra mã ICD-10 chiếm 5-7 phút/lượt — lặp lại 20-30 lần/ngày, không tạo giá trị lâm sàng | Đánh giá cao nhất. Pain được 4 nghiên cứu peer-reviewed xác nhận. Workflow rõ, bottleneck cô lập được, boundary pháp lý tự nhiên (bác sĩ ký số). Ứng cử viên số 1. |
| 2 | Phạm Thành Trung | Tài xế Xanh SM báo hết pin, điều phối viên tra cứu thủ công trạm sạc — mất 12-15 phút/lần, gây gián đoạn dịch vụ | Tài xế Xanh SM + Điều phối viên CSKH GSM | Tra bản đồ thủ công (5-7') + xác nhận slot sạc trống (3-5') — 8-10 phút bị lãng phí mỗi lần xử lý | Pain real-time rõ, nhưng cần API nội bộ Xanh SM — không thể prototype trong lab. Xếp thứ 2. |
| 3 | Phạm Thành Trung | CSKH Vinhomes phân loại và định tuyến ticket khiếu nại thủ công — SLA 30 ngày thường xuyên trễ | Nhân viên CSKH + BQL tòa nhà Vinhomes | Phân loại danh mục (5') + tìm bộ phận phụ trách (3-5') — sai ~20%, phải forward lại từ đầu | Bài toán đúng nhưng Zendesk AI, Freshdesk đã giải quyết tốt. Khoảng trống sáng tạo hẹp. |
| 4 | Đinh Mạnh Dũng | Trợ lý AI ghi bệnh án cho bác sĩ Vinmec (Ambient Voice AI) — AI ghi âm ngầm cuộc hội thoại, tự động tóm tắt thành SOAP form và gợi ý mã bệnh | Bác sĩ lâm sàng Vinmec | Bác sĩ mất 8-12 phút gõ EMR + tra mã ICD sau mỗi ca khám, lặp 20-30 lần/ngày | Đánh giá cao nhất. Trùng hoàn toàn với #1 — xác nhận pain thật. Đinh Mạnh Dũng cũng đề xuất đây là bài chốt. Tín hiệu hội tụ mạnh trong nhóm. |
| 5 | Đinh Mạnh Dũng | AI điều phối trạm sạc cho tài xế Xanh SM — khi pin dưới ngưỡng, hệ thống tự động quét vị trí, tính toán khoảng cách và số trụ trống | Tài xế xe điện Xanh SM | Tài xế vừa lái vừa tự tra app gây mất tập trung, nguy hiểm; phải tìm trạm không lòng vòng | Trùng với #2 — cùng nhận ra rủi ro: cần API real-time nội bộ, khó prototype trong lab. |
| 6 | Đinh Mạnh Dũng | Tự động phân loại ticket khiếu nại cư dân Vinhomes — AI đọc hiểu nội dung, gắn tag/chủ đề, route thẳng về đúng bộ phận | Ban quản lý tòa nhà Vinhomes | Đọc thủ công từng ticket text dài để gán team Kỹ thuật / Lễ tân / An ninh — chậm và dễ gán nhầm | Trùng với #3. Bài cũ và phổ biến — khó tạo điểm nhấn khi chấm điểm. |
| 7 | Nguyễn Hồng Phi | Viết báo cáo Pentest (Reporting & PoC Documentation) — AI hỗ trợ tạo bản nháp từ notes thô: ảnh PoC, steps-to-reproduce, CVSS, remediation | Pentester / Security Analyst | Chuyển notes thô và bằng chứng scan thành report đúng template mất đến 3 ngày/lần kiểm thử | Pain rõ, workflow cụ thể, baseline thời gian đo được. Domain hẹp (security) nhưng có thể mở rộng sang technical writing nói chung. |
| 8 | Nguyễn Hồng Phi | Lọc False Positive từ công cụ scan bảo mật tự động — Rule lọc mẫu rõ kết hợp Workflow review của pentester | Pentester / Security Analyst | Phải mở và kiểm tra thủ công từng cảnh báo để phân biệt true/false positive — input vượt 500 issues/lần scan | Khối lượng lớn, false-positive rate đo được. Kết hợp Rule + Workflow là hướng đúng. Domain chuyên biệt, cần chuyên môn security để đánh giá sâu. |
| 9 | Nguyễn Hồng Phi | Phân bổ tài nguyên container Kubernetes bị lãng phí (Over-provisioning) — AI gợi ý requests/limits tối ưu dựa trên usage thực tế | DevOps / SRE / Platform Engineer | CPU/RAM được đặt quá cao trước khi có đủ feedback — usage thực chỉ 15-20% nhưng cluster thiếu chỗ, chi phí cloud tăng gấp đôi | Impact tài chính rõ ràng, metric kiểm chứng được. Cần validate baseline cost và ngưỡng an toàn. Phù hợp nếu nhóm có background DevOps. |
| 10 | Từ Hoàng Giang | Xác thực chuyến hủy thủ công — Xanh SM: kiểm tra hàng loạt thông tin (lý do hủy, vị trí tài xế, thời gian chờ, lịch sử liên hệ, ảnh bằng chứng) | Nhân viên vận hành / CSKH Xanh SM | Phải đối chiếu thủ công nhiều nguồn dữ liệu rời rạc cho mỗi ca hủy chuyến — công việc lặp lại liên tục dưới áp lực thời gian | Pain lặp lại rõ ràng, nhiều bằng chứng cần tổng hợp, phù hợp Workflow AI. Cần access vào log hệ thống Xanh SM để prototype. |
| 11 | Từ Hoàng Giang | Tra cứu tài liệu sửa chữa xe thủ công — VinFast: kỹ thuật viên mất 20-30 phút lật tìm sơ đồ, hướng dẫn tháo lắp, mã lỗi trong PDF hàng nghìn trang | Kỹ thuật viên xưởng dịch vụ VinFast | Tra cứu thủ công trong tài liệu kỹ thuật dày đặc — thiếu search thông minh theo ngữ cảnh lỗi thực tế | Pain đo được (20-30 phút/lần tra), ảnh hưởng trực tiếp thời gian xe nằm xưởng. RAG trên tài liệu kỹ thuật là giải pháp đã proven. Tiềm năng cao. |
| 12 | Từ Hoàng Giang | Quản lý sự cố MEP bị động — Vinhomes: thiếu cơ chế dự báo bảo trì thông minh dẫn đến hỏng hóc đột xuất (thang máy, PCCC, máy bơm) | Đội ngũ vận hành tòa nhà Vinhomes | Không có hệ thống cảnh báo sớm — hỏng hóc xảy ra đột ngột, chi phí sửa khẩn cấp cao, ảnh hưởng cư dân | Rủi ro vận hành cao nhưng bài toán predictive maintenance phức tạp — cần IoT sensor data và training data lịch sử dài. Khó prototype trong thời gian lab ngắn. |
| 13 | Trần Nguyễn Thái Duy | Trích xuất Action Items, người phụ trách và deadline từ 100+ tin nhắn Discord/Zalo sau họp nhóm | Trưởng nhóm + thành viên nhóm đồ án CNTT | Lội ngược và đọc thủ công 100+ tin nhắn lộn xộn mất 15-20 phút, dễ bỏ sót task hoặc nhầm người phụ trách | Pain thật với môi trường tech/đồ án, nhưng phạm vi hẹp và một phần giải quyết được bằng bot checklist/rule đơn giản. Thiếu business impact lớn. |
| 14 | Trần Nguyễn Thái Duy | Gợi ý và sinh danh sách edge cases / boundary test cases cho hàm xử lý logic nghiệp vụ trước khi viết unit test | Backend Developer + Tester trong nhóm đồ án | Vắt óc suy nghĩ kịch bản biên mất 20-25 phút/hàm — dev hay bị thiên kiến chỉ test happy path | Ý tưởng kỹ thuật tốt, giá trị chuyên môn cao. Khó đo business impact trực quan cho người nghe ngoài chuyên ngành. |
| 15 | Trần Nguyễn Thái Duy | Tự động tổng hợp changelog và release notes mỗi cuối tuần từ 10-15 Pull Request trên GitHub | Tech Lead nhóm đồ án kiêm người review PR | Đọc raw git diff từng PR mất 25-30 phút do thành viên để trống hoặc ghi description quá sơ sài | Quy trình rõ ràng, dễ đo thời gian. Tuy nhiên đã có nhiều GitHub Actions template và tooling hỗ trợ sẵn — khoảng trống sáng tạo hẹp. |

### 3.2. Gom trùng / cluster (gom 9-12 ý thành 3-4 cụm)

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A | #1 (Trung), #4 (Dũng) | Bác sĩ mất thời gian gõ hồ sơ thủ công sau khám bệnh; AI ambient voice có thể tự điền SOAP form | Hội tụ mạnh nhất — 2/5 thành viên độc lập chọn cùng bài. Technology stack proven (Nuance DAX, Suki AI, PhoBERT). Boundary pháp lý rõ ràng. |
| B | #2 (Trung), #5 (Dũng), #10 (Giang) | Vận hành xe điện Xanh SM gặp vấn đề real-time: hết pin, điều phối tra thủ công, xác thực chuyến hủy | Cùng hệ sinh thái GSM/Xanh SM. Pain thật nhưng phụ thuộc API nội bộ — prototype khó. Cần data access đặc biệt. |
| C | #3 (Trung), #6 (Dũng), #12 (Giang) | Vinhomes: phân loại ticket khiếu nại, quản lý MEP bị động — vấn đề vận hành tòa nhà thiếu automation | Ticket classification đã có SaaS. MEP predictive maintenance phức tạp, cần sensor data. Cụm này thiếu khoảng trống sáng tạo. |
| D | #7, #8, #9 (Phi), #11 (Giang), #13, #14, #15 (Duy) | Các bài toán xử lý tài liệu kỹ thuật, tổng hợp thông tin, automation trong môi trường dev/security/infra | Đa dạng domain. #11 (VinFast RAG) nổi bật nhất trong cụm — impact đo được và fit với Vingroup. Các bài còn lại scope hẹp hoặc tooling đã có sẵn. |

### 3.3. Shortlist (giữ 2-3 bài trả lời được 7 câu hỏi worksheet)

| Candidate | Vì sao vào shortlist (2-3 ý) | Rủi ro / điều chưa rõ |
|---|---|---|
| Cluster A — Bác sĩ Vinmec gõ EMR thủ công (#1 + #4) | 1. Hội tụ cao nhất: 2/5 thành viên độc lập chọn cùng bài — pain thật sự được nhiều người nhận ra.<br>2. Evidence học thuật mạnh: 4 nghiên cứu peer-reviewed (Arndt 2017, Sinsky 2016, AMA 2022, NEJM 2019) xác nhận 30-50% thời gian bác sĩ mất cho EHR.<br>3. Workflow 6 bước vẽ được đầy đủ, bottleneck cô lập tại bước 4-5, boundary pháp lý tự nhiên (bác sĩ bắt buộc ký số theo TT 46/2018). | Accuracy tiếng Việt y khoa của STT chưa được đo thực tế. Baseline Vinmec cụ thể (phút/lượt) chưa có — đang dùng proxy quốc tế. Cần phỏng vấn tối thiểu 2 bác sĩ Vinmec để xác nhận. |
| Cluster D — KTV VinFast tra cứu tài liệu sửa chữa xe thủ công (#11) | 1. Pain đo được rõ ràng: 20-30 phút/lần tra trong PDF hàng nghìn trang — ảnh hưởng trực tiếp thời gian xe nằm xưởng và chi phí.<br>2. RAG (Retrieval-Augmented Generation) trên tài liệu kỹ thuật là pattern đã proven — nhiều case study automotive đã làm.<br>3. Dữ liệu đầu vào (tài liệu kỹ thuật VinFast) là tài liệu nội bộ có thể tiếp cận, không cần API real-time phức tạp như Cluster B. | Tài liệu kỹ thuật VinFast có thể là tài sản độc quyền — cần confirm có thể dùng cho prototype. Chưa có số liệu về volume (bao nhiêu KTV, bao nhiêu lần tra/ngày). |
| Cluster B — Xác thực chuyến hủy Xanh SM thủ công (#10) | 1. Bài toán lặp lại rõ ràng với nhiều nguồn dữ liệu cần tổng hợp — phù hợp Workflow AI.<br>2. Actor cụ thể (nhân viên CSKH Xanh SM), bối cảnh thời gian thực dưới áp lực xử lý nhanh.<br>3. Khác với #2/#5 (cần API trạm sạc), bài này có thể prototype từ log và form hủy chuyến có cấu trúc hơn. | Vẫn cần access vào hệ thống nội bộ Xanh SM. Chưa rõ volume: bao nhiêu ca hủy/ngày cần xác thực thủ công. Cần 1 buổi shadow CSKH để đo baseline. |

### 3.4. Score để đồng thuận (chấm 1-5, ép nói rõ vì sao cho 5 / cho 3)

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Card #1 — Bác sĩ Vinmec gõ EMR thủ công | **5** | **5** | **5** | **5** | **4** | **5** | **4** | **33** |
| Card #2 — Tài xế Xanh SM hết pin, điều phối tra thủ công | 5 | 4 | 4 | 4 | 3 | 4 | 3 | 27 |
| Card #3 — Phân loại & route ticket khiếu nại Vinhomes | 4 | 4 | 3 | 4 | 4 | 4 | 3 | 26 |

**Giải thích điểm nổi bật:**

| Ô | Điểm | Lý do |
|---|:---:|---|
| Card #1 — Pain có evidence | **5** | 4 nghiên cứu peer-reviewed (Arndt 2017, Sinsky 2016, NEJM Catalyst 2019, AMA 2022) đều xác nhận. Con số 30-40% trong file Excel khớp với benchmark quốc tế. |
| Card #1 — Impact đo được | **5** | Có số baseline rõ: 8-12 phút/lượt gõ, 23-29 phút/chu kỳ khám. Success metric đo được: phút/lượt, số BN/ngày, tỷ lệ lỗi. |
| Card #1 — So sánh R/W/A được | **5** | 3 tier có thể phân tích rõ ràng, ranh giới pháp lý (Thông tư 46/2018) tạo boundary tự nhiên cho human checkpoint. |
| Card #1 — Làm trong lab | **4** | Không phải 5 vì cần data tiếng Việt y khoa để fine-tune model — không build được chỉ bằng prompt. Nhưng có thể prototype bằng Whisper + template. |
| Card #2 — Làm trong lab | **3** | Cần API real-time trạm sạc Xanh SM — không có public access, khó mock trong lab. |
| Card #3 — Pain có evidence | **3** | Chỉ có "SLA 30 ngày" từ file Excel, chưa có nghiên cứu độc lập xác nhận tần suất hay tỷ lệ miss SLA cụ thể. |

**Candidate nhóm chọn (1 bài duy nhất):**

```text
Card #1 — Bác sĩ Vinmec gõ EMR thủ công (33/35 điểm)
```

**Vì sao chọn (4-5 câu):**

```text
Đây là bài toán duy nhất trong 3 card có evidence từ nghiên cứu học thuật
peer-reviewed: Arndt et al. (2017, n=142) và Sinsky et al. (2016, n=57) xác nhận
bác sĩ mất 30-50% thời gian cho EHR documentation — khớp hoàn toàn với con số
quan sát được trong môi trường Vinmec. Workflow hiện tại vẽ được 5-6 bước rõ ràng,
bottleneck nằm đúng tại bước gõ narrative và tra mã ICD — cô lập được để AI can
thiệp mà không đụng các bước khác. Technology stack (Whisper STT + PhoBERT NER)
đã tồn tại, có thể prototype trong lab mà không cần API kín của bên thứ ba. Quan
trọng nhất, boundary pháp lý từ Thông tư 46/2018/TT-BYT tạo ra human checkpoint
tự nhiên (bác sĩ phải ký số) — giúp solution vừa safe vừa compliant ngay từ
thiết kế.
```

**Vì sao KHÔNG chọn các candidate còn lại (mỗi bài 2-3 câu):**

```text
Card #2 — Xanh SM hết pin:
Pain là thật nhưng dependency vào API real-time của hệ thống quản lý trạm sạc
nội bộ Xanh SM khiến nhóm không thể prototype trong lab — không có dữ liệu mock
đủ thực tế. Domain knowledge về fleet management và EV routing cũng đòi hỏi
chuyên môn sâu mà nhóm chưa có để đánh giá đúng rủi ro.

Card #3 — Ticket khiếu nại Vinhomes:
NLP ticket classification là bài toán đã rất mature (tooling sẵn có: Zendesk AI,
Intercom, nhiều SaaS giải quyết rồi) — không có khoảng trống để nhóm tạo ra giá
trị mới. Pain evidence chỉ dừng ở "SLA 30 ngày thường trễ" mà không có log ticket
thực tế hay tỷ lệ cụ thể, làm baseline yếu khi cần đo impact sau triển khai.
```

**Disagreement (nếu có — ai lo gì, chốt ra sao):**

```text
Lo ngại chính: Một thành viên cho rằng Card #1 có rào cản pháp lý quá lớn
(Thông tư 46/2018) và accuracy tiếng Việt y khoa chưa đủ để deploy thực tế.

Chốt: Nhóm đồng ý đây là rủi ro thật, nhưng đây là bài tập lab — mục tiêu là
prototype và validate concept, không phải production deployment. Boundary pháp lý
đã được thiết kế vào workflow (bác sĩ review + ký số) nên không block prototype.
Accuracy là thách thức kỹ thuật cần đo, không phải lý do loại bài.
```

---

## Phase 4 — Quick Validation + Research

### 4.1. Quick validation (ít nhất 1 cách: interview 2-3 người hoặc survey 5-10 người)

| Nguồn | Số người / mẫu | Tín hiệu xác nhận (kèm quote nguyên văn) | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Academic study (Arndt et al., *Annals of Family Medicine*, 2017) | 142 bác sĩ gia đình, theo dõi 3 năm | *"Clinicians spent 355 minutes (5.9 hours) of an 11.4-hour workday in the EHR... Clerical and administrative tasks including documentation accounted for nearly one-half of EHR time (44.2%)"* | Nghiên cứu tại Mỹ, hệ thống Epic — có thể không map hoàn toàn sang VN | Dùng làm proxy benchmark; cần điều chỉnh với pilot thực địa Vinmec |
| Academic study (Sinsky et al., *Annals of Internal Medicine*, 2016) | 57 bác sĩ, 4 chuyên khoa, time-motion study | *"For every hour of direct patient care, physicians spend nearly 2 additional hours on EHR and desk work"* | Chuyên khoa khác nhau có tỷ lệ khác nhau — nội khoa cao hơn, ngoại khoa thấp hơn | Scope bài toán vào nội khoa / đa khoa Vinmec trước |
| Survey (AMA, 2022) | Hàng nghìn bác sĩ Mỹ | *"62% of physicians say EHR contributes to burnout"; ">80% want AI to reduce documentation burden"* | Mỹ có EHR phức tạp hơn VN; burnout context khác | Dùng 80% muốn AI hỗ trợ như social proof khi thuyết phục stakeholder |
| Product report (Nuance DAX, 2023) | 550+ bệnh viện triển khai tại Mỹ | *"Reduces documentation time by 50%; physicians gain back 3+ hours per day"* | Internal study của vendor — có thể bias; chưa có RCT độc lập | Xem là upper bound; dùng conservative estimate 30-40% cho pitch |
| Expert observation (NEJM Catalyst, 2019) | Survey executives & clinicians | *"Physicians spend 15-17 minutes per encounter on EHR documentation — nearly equal to face-time with patient"* | Survey, không phải time-motion — có thể over-report | Dùng 15-17 phút làm baseline documentation time trong workflow table |

**Insight sau validation (1-2 câu — pain thật nằm ở đâu):**

```text
Pain thật không nằm ở việc "gõ chậm" mà nằm ở "cognitive context switch" — bác sĩ
phải chuyển từ tư duy lâm sàng (quan sát bệnh nhân) sang tư duy hành chính (nhập
form) ngay sau khám, gây mệt mỏi tích lũy và lỗi nhập liệu vào cuối ngày. Đây là
lý do pajama time (gõ EMR sau khi về nhà) xuất hiện ở >40% bác sĩ theo AMA 2022.
```

Bằng chứng đính kèm (nếu có): `02-group-problem-statement-survey.png`, `...-interview-notes.md`

### 4.2. Research giải pháp đã có (ít nhất 2-3 tools/patterns + 1-2 link kiểm được)

| Nguồn / tool / case | Link | Họ giải quyết bước nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Nuance DAX Copilot (Microsoft) | https://www.microsoft.com/en-us/health-solutions | Ambient listening → GPT-4 clinical note → bác sĩ review → EHR sync | Tích hợp sẵn Epic/Cerner; đã triển khai 550+ bệnh viện; giảm 50% thời gian ghi chú | Chỉ tiếng Anh; giá enterprise; không hỗ trợ HIS VN | Validate architecture: ambient → NLP → structured note là pattern đúng. Copy kiến trúc, không copy sản phẩm. |
| Suki AI | https://www.suki.ai | Voice command + ambient AI → SOAP notes | Giảm 72% thời gian; 90% retention sau 30 ngày; EHR-agnostic API | Không có tiếng Việt; subscription per-doctor model đắt cho VN | Human boundary: bác sĩ vẫn review trước khi sign — áp dụng nguyên mẫu |
| DeepScribe | https://www.deepscribe.ai | AI-generated SOAP notes từ conversation recording | 90% bác sĩ tiếp tục dùng sau 30 ngày; specialty-specific models | US-only; không mở API; no Vietnamese support | Specialty-specific training data là key insight — Vinmec cần fine-tune theo từng khoa |
| Abridge | https://www.abridge.com | Summarize patient-doctor conversation → structured summary cho bác sĩ và bệnh nhân | Partnership với UPMC (150+ bệnh viện); bệnh nhân cũng nhận tóm tắt | Enterprise-only; tiếng Anh | Dual output (cho bác sĩ + bệnh nhân) là use case mở rộng thú vị cho giai đoạn 2 |
| PhoBERT (VinAI Research) | https://github.com/VinAIResearch/PhoBERT | Pre-trained BERT cho tiếng Việt; state-of-the-art NLP VN | Miễn phí, open-source; tốt nhất cho tiếng Việt hiện tại; trong hệ sinh thái Vingroup | Chưa có medical domain fine-tuning; cần corpus y khoa VN | Fine-tune PhoBERT với dữ liệu EMR Vinmec là path khả thi nhất cho tiếng Việt |
| Whisper (OpenAI) | https://openai.com/research/whisper | Speech-to-text đa ngôn ngữ, bao gồm tiếng Việt | Open-source; WER tiếng Việt ~8-12% (tốt); chạy on-premise được | WER tăng với thuật ngữ y khoa hiếm; latency nếu run real-time | Dùng Whisper làm STT layer; accept imperfect transcription vì có human review |

**Research takeaway (2-3 câu — nên build gì / không build gì):**

```text
Không nên build lại từ đầu những gì Nuance DAX đã làm — nên copy kiến trúc
(ambient → STT → NLP → structured note → human review) và thay bằng open-source
stack phù hợp tiếng Việt: Whisper (STT) + PhoBERT fine-tuned (NER) + Vinmec
SOAP template engine. Lợi thế cạnh tranh duy nhất và thực tế là VinAI (cùng hệ
sinh thái Vingroup) đã có PhoBERT — đây là điểm khởi đầu không bệnh viện VN nào
khác có. Không build tính năng "tự order thuốc" hay "tự schedule tái khám" ở phase
1 — đây là Agent territory, quá rủi ro và không cần thiết để giải quyết bottleneck
chính.
```

> Lưu ý: không dùng số liệu AI đưa nếu không verify được link chính thức. Ghi rõ giả định chưa chắc.

---

## Phase 5 — Workflow + Problem Statement

### 5.1. Current workflow bản nhóm

Dán workflow hoặc link file: `02-group-problem-statement-workflow.png/pdf/md`

```text
[1 Tiếp nhận BN: 1-2' - Bác sĩ] → [2 Hỏi bệnh sử + khám: 8-10' - Bác sĩ]
→ [3 BN ra ngoài: 0' - transition] → [4 Gõ CC + HPI: 3-4' - Bác sĩ | BOTTLENECK 1]
→ [5 Tra mã ICD-10: 2-3' - Bác sĩ | BOTTLENECK 2] → [6 Gõ đơn thuốc: 2-3' - Bác sĩ | BOTTLENECK 3]
→ [7 Ghi kế hoạch + tái khám: 1-2' - Bác sĩ] → [8 Ký số & submit HIS: 1' - Bác sĩ]
TỔNG: 18-25 phút/bệnh nhân | Gõ EMR = 8-12 phút = 44-48%
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú (handoff? bottleneck?) |
|---|---|---|---|---|---|
| 1. Tiếp nhận bệnh nhân | Bác sĩ + Bệnh nhân | Lịch hẹn, thẻ BHYT | Bệnh nhân ngồi khám | 1-2 phút / mỗi lượt khám | HIS auto-pull thông tin cơ bản |
| 2. Hỏi bệnh sử & khám lâm sàng | Bác sĩ (chủ động), Bệnh nhân (trả lời) | Triệu chứng BN kể, kết quả khám thực thể | Mental model chẩn đoán trong đầu bác sĩ | 8-10 phút / lượt | Thông tin tập trung ở đây — chưa được ghi lại |
| 3. Bệnh nhân ra ngoài | Bệnh nhân | — | — | 0 phút | Context switch bắt đầu |
| 4. Gõ CC + HPI vào EMR | Bác sĩ | Mental model từ bước 2 | Text trong form EMR | 3-4 phút / lượt | **BOTTLENECK 1** — narrative tự do, không có autocomplete |
| 5. Tra & chọn mã ICD-10 | Bác sĩ | Chẩn đoán trong đầu | Mã ICD được chọn trong dropdown | 2-3 phút / lượt | **BOTTLENECK 2** — dropdown 10.000+ mã, search kém |
| 6. Gõ đơn thuốc | Bác sĩ | Phác đồ điều trị | Đơn thuốc trong HIS | 2-3 phút / lượt | **BOTTLENECK 3** — gõ tên thuốc, liều, tần suất |
| 7. Ghi kế hoạch điều trị | Bác sĩ | Quyết định lâm sàng | Text kế hoạch, lịch tái khám | 1-2 phút / lượt | Thường copy template cũ rồi sửa |
| 8. Ký số & submit | Bác sĩ | EMR đã điền đủ | Hồ sơ hợp lệ trong HIS | 1 phút / lượt | Không thể bỏ — yêu cầu pháp lý theo TT 46/2018 |

**Bottleneck chính (2-3 câu):**

```text
Ba bước 4-5-6 chiếm 7-10 phút (44-48% tổng chu kỳ) nhưng không tạo ra giá trị
lâm sàng mới — chúng chỉ chuyển thông tin từ đầu bác sĩ vào form máy tính.
Bottleneck không phải là tốc độ gõ mà là cognitive overhead: bác sĩ phải dừng
tư duy lâm sàng, chuyển sang tư duy hành chính, tra cứu mã số trong hệ thống
phân loại 10.000+ mục — đây là nguồn gốc của lỗi nhập liệu và burnout tích lũy.
```

### 5.2. Future workflow bản nhóm

Phải nhìn ra 5 thứ: bước nào máy (Rule), bước nào AI, bước nào người, boundary ở đâu, fallback khi AI sai.

```text
[1 Tiếp nhận BN + bật AI ambient: 1-2' - Bác sĩ]
→ [2 Hỏi bệnh sử + khám / AI ghi âm ngầm: 8-10' - Bác sĩ chủ đạo, AI thu thập]
→ [3 AI processing: transcribe → NER → draft SOAP + gợi ý ICD top-3: 30-60s - AI tự động]
→ [4 Bác sĩ review draft + sửa nếu sai + confirm ICD: 1-2' - Bác sĩ / HUMAN BOUNDARY]
→ [5 Ký số & submit: 1' - Bác sĩ]
TỔNG: 12-15 phút/bệnh nhân | Tiết kiệm: 10-13 phút/lượt (~48%)

Fallback: AI confidence < 70% → blank form + flag đỏ → bác sĩ nhập tay như cũ
          AI gợi ý sai thuốc có tương tác → hard block + cảnh báo bắt buộc confirm
          Ghi âm lỗi (môi trường ồn) → fallback về template SOAP trống + manual
```

**Before/after impact:**

| Metric | Trước | Sau kỳ vọng | Cách đo |
|---|---:|---:|---|
| Tổng thời gian | 18-25 phút | 12-15 phút | Bấm giờ thực tế (stopwatch) |
| Số bước | 8 bước | 5 bước | Đếm từ workflow diagram |
| Số bước thủ công | 6 bước (3-8) | 2 bước (4, 5) | Đếm trực tiếp từ workflow |
| Bottleneck chính | Gõ narrative + tra ICD: 5-7' | Review draft AI: 1-2' | Log timestamp từng bước |
| Risk mới | 0% (manual) | Có — quản lý bằng human review step | Theo dõi số lần bác sĩ sửa draft/tuần |

### 5.3. Problem Statement v0 (mỗi field 2-3 câu)

| Field | Nội dung |
|---|---|
| **Actor** | Bác sĩ lâm sàng tại Vinmec (ước tính 1.500-3.000+ bác sĩ toàn hệ thống), đặc biệt khoa Nội, Nhi, Đa khoa — nơi volume bệnh nhân cao và documentation nặng nhất. |
| **Workflow** | Sau mỗi lượt khám (5-15 phút), bác sĩ phải tự gõ toàn bộ hồ sơ bệnh án vào HIS: Chief Complaint, HPI, chẩn đoán (tra mã ICD), đơn thuốc, kế hoạch điều trị — mất 8-12 phút/lượt, chiếm 44-48% tổng chu kỳ khám. |
| **Bottleneck** | Bước gõ narrative (CC + HPI) và tra mã ICD-10 chiếm 5-7 phút trong số 8-12 phút — không tạo giá trị lâm sàng mới, chỉ chuyển thông tin từ đầu bác sĩ sang form máy tính. |
| **Impact** | Bác sĩ khám được ít hơn 30-40% số bệnh nhân so với tiềm năng; lỗi nhập liệu tăng vào cuối ngày khi mệt; >40% bác sĩ tiếp tục gõ EMR sau giờ làm (AMA 2022); dẫn đến burnout và giảm chất lượng chăm sóc. |
| **Success Metric** | Thời gian gõ EMR/lượt: 8-12 phút → ≤2 phút; số BN/ngày/bác sĩ tăng ≥20%; tỷ lệ pajama time giảm từ 40% xuống <10%; tỷ lệ lỗi nhập liệu giảm ≥40%. |
| **Boundary** | AI có thể làm: ghi âm, transcribe, NER, điền draft SOAP, gợi ý ICD top-3, gợi ý thuốc theo protocol. AI KHÔNG làm: ký số, quyết định chẩn đoán cuối, order thuốc không qua confirm của bác sĩ. |

**Câu hỏi AI phản biện v0 (nếu có):**
- Field nào mơ hồ: "Impact" nêu nhiều hậu quả nhưng chưa có baseline Vinmec thực tế — con số AMA 2022 là của Mỹ.
- Tôi sửa gì: Thêm ghi chú "(proxy từ AMA 2022 — cần validate tại Vinmec)" vào Impact; thêm cột "Cách đo baseline" vào Success Metric.

---

## Phase 6 — Rule / Workflow / Agent + Decision

### 6.0. Ma trận độ phù hợp (suy nghĩ nhanh, không thay quyết định cuối)

- Độ mơ hồ: [x] Thấp (có đúng/sai rõ) / [ ] Cao (nhiều cách trả lời vẫn OK) — Vì sao: Output EMR có cấu trúc chuẩn (SOAP), có đúng/sai có thể verify bằng bác sĩ review. Không phải bài "nhiều đáp án đều OK".
- Độ phức tạp: [ ] Thấp (1-2 bước) / [x] Cao (3+ bước/nguồn, phụ thuộc nhau) — Vì sao: AI phải chain 3 bước: STT → NLP NER → structured mapping. Mỗi bước có error rate riêng, lỗi bước trước ảnh hưởng bước sau.

**Bài toán nhóm nằm ở ô nào:**

```text
Ô: Độ mơ hồ THẤP × Độ phức tạp CAO
→ Đây là vùng Workflow — cần AI xử lý nhiều bước phức tạp,
  nhưng output có thể verify rõ ràng bởi con người.
```

**Vì sao (2-3 câu):**

```text
Narrative y tế có cấu trúc (SOAP: Subjective → Objective → Assessment → Plan) —
đây là output có thể đúng/sai, bác sĩ có thể verify trong 60 giây. Nhưng để tạo
ra draft đó, AI phải chain STT → NER → template mapping — đủ phức tạp để cần ML,
không đủ phức tạp để cần Agent tự lập kế hoạch. Đây là sweet spot của Workflow.
```

### 6.1. So sánh Rule / Workflow / Agent (so trên cùng 1 bài)

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? (Dùng cho bước nào?) |
|---|---|---|---|---|
| **Rule** | Auto-fill tên BN, ngày, bác sĩ từ lịch hẹn. Template SOAP theo chuyên khoa. Search ICD cải tiến (fuzzy search). | Nếu bottleneck chỉ là thiếu template — nhưng pain thật là narrative phải gõ tay, Rule không đụng được. | Không giải quyết bottleneck chính. Đã có trong HIS, nếu đủ thì vấn đề đã giải quyết từ lâu. | Dùng làm pre-fill layer kết hợp Workflow, không dùng độc lập. |
| **Workflow** | AI ambient ghi âm ngầm → Whisper STT → PhoBERT NER → điền SOAP draft → gợi ý ICD top-3 → bác sĩ review + ký số. | Khi AI giải quyết được bước nặng nhất (narrative), human vẫn giữ quyết định cuối. Đây đúng là trường hợp này. | STT accuracy với thuật ngữ y khoa VN ~88-92% (chưa perfect). Bác sĩ phải tin AI đủ để không đọc lại từng chữ. | LỰA CHỌN CHÍNH — giải quyết 70-80% bottleneck, comply pháp lý, có thể pilot. |
| **Agent** | AI tự nghe → điền EMR → order thuốc → schedule tái khám → gửi summary → không cần bác sĩ duyệt từng bước. | Chỉ khi accuracy >99.5% VÀ pháp lý cho phép VÀ bác sĩ tin tưởng hoàn toàn — cả 3 điều kiện chưa thoả. | Sai 1 bước → hậu quả y tế nghiêm trọng. Thông tư 46/2018 chặn hoàn toàn ở khâu ký. Trust gap với bác sĩ VN hiện tại. | Không chọn — roadmap 3-5 năm, bắt đầu từng scope nhỏ sau khi Workflow proven. |

**5 câu hỏi chốt (trả lời câu đầy đủ):**

1. Rule có giải được 70-80% case không?
```
Không. Rule giải được ~20-30%: auto-fill trường cố định (tên, ngày, bác sĩ),
template theo chuyên khoa. Nhưng 70-80% còn lại là narrative tự do (HPI, chẩn
đoán tự viết, kế hoạch điều trị) — Rule không xử lý được ngôn ngữ tự nhiên.
Bằng chứng: HIS đã có auto-fill cơ bản, nhưng pain vẫn tồn tại → Rule không đủ.
```

2. Các bước có đi thẳng một đường không hay phải rẽ nhánh?
```
Rẽ nhánh ở 2 điểm: (1) Nếu AI confidence <70% → blank form thay vì điền sai.
(2) Nếu thuốc gợi ý có tương tác nguy hiểm → hard block, không cho submit.
Hai nhánh này cần logic điều kiện → đây là lý do cần Workflow (có conditional
routing) thay vì Rule đơn thuần (chỉ có một đường thực thi).
```

3. Có thật sự cần Agent tự lập kế hoạch + gọi tool không?
```
Không. Bài này không cần Agent vì: (a) Không có "planning" — chuỗi bước đã cố
định (ghi âm → STT → NER → template). (b) Không có "tool calling" động — AI không
cần tự quyết dùng tool nào. (c) Không có multi-step reasoning về mục tiêu dài hạn.
Đây là pipeline tuyến tính có conditional — đặc trưng của Workflow, không phải Agent.
```

4. Nếu AI sai, ai phát hiện đầu tiên và sửa trong bao lâu?
```
Bác sĩ phát hiện tại bước review (bước 4 trong future workflow) — ngay lập tức,
trong cùng lượt khám. Thời gian sửa: ước tính 30-60 giây nếu chỉ sửa vài chỗ.
Nếu AI sai nhiều (confidence thấp) → blank form → bác sĩ nhập tay trong 8-12 phút
như cũ. Không có hậu quả delay — fallback về current state ngay lập tức.
```

5. Có hạ được từ Agent → Workflow → Rule không?
```
Có và đã quyết định hạ xuống Workflow. Test: Rule đã thử (HIS có auto-fill),
không đủ. Agent quá rủi ro và không comply pháp lý. Workflow là điểm cân bằng
đúng: AI xử lý bước nặng nhất, human giữ review + ký. Đây là thiết kế conscious
chứ không phải "chọn giữa" — Rule layer vẫn hoạt động bên dưới Workflow.
```

**Mức chọn:**

```text
Workflow — với Rule làm pre-fill foundation bên dưới
```

**Vì sao chọn (3-4 câu):**

```text
Workflow giải quyết đúng bottleneck chính (7-10 phút narrative + ICD lookup) mà
Rule không đụng được, đồng thời giữ human boundary bắt buộc theo Thông tư
46/2018/TT-BYT (bác sĩ review + ký số) mà Agent vi phạm. Technology stack tồn tại
và đã proven: Nuance DAX (Mỹ) và Suki AI đã làm được, VinAI/PhoBERT cung cấp path
khả thi cho tiếng Việt trong hệ sinh thái Vingroup. Fallback logic rõ ràng (AI
confidence <70% → blank form) đảm bảo sai thì sửa được ngay, không có hậu quả trễ.
```

**Vì sao không chọn mức đơn giản hơn (2-3 câu):**

```text
Rule đã có trong HIS và pain vẫn tồn tại — đây là bằng chứng mạnh nhất rằng Rule
không đủ. Template, auto-fill, dropdown cải thiện chỉ giải quyết structured fields
(~20% effort) nhưng không đụng được narrative tự do (Chief Complaint, HPI) — đây
là phần chiếm nhiều thời gian và cognitive load nhất.
```

### 6.2. Problem Statement v1 (v0 sửa chặt hơn + 3 field cuối)

| Field | Nội dung |
|---|---|
| **Actor** | Bác sĩ lâm sàng tại Vinmec — ưu tiên khoa Nội & Nhi (volume cao nhất); ước tính 1.500-3.000+ bác sĩ toàn hệ thống *(con số chưa verify chính thức — proxy từ quy mô 43+ cơ sở Vinmec)*. |
| **Workflow** | Sau mỗi lượt khám 8-10 phút, bác sĩ gõ thủ công 6 trường EMR vào HIS: CC → HPI → chẩn đoán (tra ICD-10) → đơn thuốc → kế hoạch → ký số; tổng 8-12 phút/lượt; lặp lại 20-30 lượt/ngày/bác sĩ. |
| **Bottleneck** | Bước gõ CC+HPI (3-4') và tra mã ICD-10 (2-3') chiếm 5-7 phút — đây là bước chuyển thông tin từ đầu bác sĩ sang form, không tạo giá trị lâm sàng, nhưng xảy ra sau mỗi cuộc khám mà không có công cụ hỗ trợ. |
| **Impact** | Proxy từ Sinsky et al. 2016 & AMA 2022 (chưa đo tại Vinmec): giảm capacity khám 30-40%; burnout tích lũy; lỗi nhập liệu vào cuối ca; pajama time (gõ sau giờ làm) ảnh hưởng work-life balance. |
| **Success Metric** | ① Thời gian gõ EMR/lượt: 8-12' → ≤2' ② Số BN/ngày/bác sĩ: tăng ≥20% ③ Pajama time: từ >40% bác sĩ → <10% bác sĩ ④ First-pass accuracy của AI draft: ≥85% (bác sĩ không cần sửa major). |
| **Boundary** (làm / không làm) | Làm: Ghi âm ngầm, STT, NER entities y tế, điền draft SOAP, gợi ý ICD top-3, gợi ý thuốc theo protocol Vinmec. Không làm: Ký số thay bác sĩ, quyết định chẩn đoán cuối, order thuốc không qua confirm, chia sẻ dữ liệu ra ngoài HIS. |
| **AI intervention point** (can thiệp sau bước nào, trước bước nào) | Can thiệp sau bước 2 (kết thúc khám — bác sĩ đã có mental model). Kết thúc trước bước 4 (bác sĩ review và ký số). AI hoạt động trong cửa sổ 30-60 giây giữa BN ra ngoài và bác sĩ nhìn vào màn hình. |
| **Mức chọn** (Rule / Workflow / Agent + 1 câu vì sao) | Workflow — AI xử lý bước nặng nhất (narrative + ICD lookup), human giữ review + ký số; Rule làm foundation pre-fill; Agent không dùng vì vi phạm pháp lý y tế VN. |
| **Rủi ro & người thật kiểm tra** (rủi ro lớn nhất + ai kiểm tra bằng cách nào) | Rủi ro lớn nhất: AI transcribe sai thuật ngữ y khoa hiếm → bác sĩ không chú ý → lỗi vào hồ sơ. Người kiểm tra: Bác sĩ senior (1 người/khoa) audit 5% hồ sơ AI-assisted/tuần trong 3 tháng đầu; so sánh draft AI vs. version bác sĩ sửa. |

### 6.3. Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú (câu đầy đủ) |
|---|---|---|
| Actor + workflow rõ chưa? | Yes | Bác sĩ lâm sàng Vinmec + 8-bước workflow đã vẽ được đầy đủ với thời gian từng bước. |
| Baseline + metric đo được chưa? | Not Yet | Metric định nghĩa rõ, nhưng baseline Vinmec chưa đo — đang dùng proxy từ nghiên cứu quốc tế. Cần bấm giờ 10-20 lượt khám thực. |
| Data/input đủ dùng chưa? | Not Yet | Cần corpus ghi âm cuộc khám tiếng Việt để fine-tune Whisper và PhoBERT. Hiện chưa có. Prototype có thể chạy với script mô phỏng. |
| AI sai, hậu quả chấp nhận được không? | Yes | Có human review step trước khi lưu. Fallback về blank form nếu confidence thấp. Không có auto-submit. Worst case = bác sĩ nhập tay như cũ. |
| Có người review/owner không? | Not Yet | Cần xác định bác sĩ champion (early adopter) tại 1 khoa. Chưa có cam kết từ Vinmec IT/Medical Director. |
| Có cách non-AI đơn giản hơn không? | Yes — nhưng đã thử | Thuê y tá hành chính gõ hộ (giải pháp ở một số bệnh viện). Nhưng chi phí cao, vẫn có delay, không scale. Template/Rule đã có trong HIS và không đủ. |

**Decision:**

```text
Not Yet — nhưng Go cho Pilot nhỏ
```

**Lý do (3-4 câu dựa trên bằng chứng):**

```text
Pain thật sự và có evidence học thuật (4 nghiên cứu peer-reviewed xác nhận bác sĩ
mất 30-50% thời gian cho EHR documentation). Technology stack khả thi và đã proven
ở thị trường Mỹ (Nuance DAX -50%, Suki AI -72%). Tuy nhiên 2 điều kiện chưa thoả:
(1) baseline Vinmec chưa đo — không thể claim impact mà không có số thực; (2) chưa
có bác sĩ champion và chưa có corpus data tiếng Việt y khoa. "Not Yet" ở đây có
nghĩa là Go for Pilot — không phải dừng lại, mà là bắt đầu đúng thứ tự.
```

**Nếu Go — pilot nhỏ nhất (data nào, chạy tay ra sao, đo 3 số nào):**

```text
SCOPE: 3 bác sĩ nội khoa tại 1 cơ sở Vinmec trong 2 tuần.

DATA: Bấm giờ 30 lượt khám (10 lượt/bác sĩ) bằng stopwatch: [open EMR form] →
[submit]. Ghi lại: tổng thời gian gõ, số lần phải tra ICD, số lần sửa lại.

CHẠY TAY: Mô phỏng "future state" bằng cách bác sĩ nói to quyết định lâm sàng
sau khám (10 giây) → người quan sát ghi ra → so sánh với EMR cuối cùng. Không
cần AI thật — chỉ cần xác nhận content quality.

ĐO 3 SỐ:
① Thời gian gõ EMR/lượt (baseline thực của Vinmec — chưa có)
② Tỷ lệ content trùng khớp: lời nói ngay sau khám vs. EMR cuối (AI có thể capture được bao nhiêu?)
③ Số lần bác sĩ tra ICD/lượt (để ưu tiên improve bước này trước)
```

**Nếu Not Yet — cần validate gì trước:**

```text
① Phỏng vấn 2-3 bác sĩ Vinmec, bấm giờ thực tế để có baseline số phút/lượt gõ EMR
② Xác nhận 1 bác sĩ champion tại 1 khoa sẵn sàng tham gia pilot
③ Kiểm tra Vinmec IT có thể cung cấp sample EMR data (ẩn danh) để test NER không
```

**Nếu No-Go — làm gì thay AI:**

```text
Không áp dụng trong trường hợp này — nhóm đã xác định "Not Yet / Go for Pilot".
Nếu pilot thất bại: quay về recommendation thuê thêm y tá hành chính chuyên gõ
hộ, kết hợp cải thiện UX HIS (fuzzy search ICD, template thông minh hơn).
```

**Exit / rollback (khi nào dừng AI, quay về cách cũ):**

```text
DỪNG AI KHI:
① First-pass accuracy của draft <70% sau 4 tuần pilot (bác sĩ phải sửa nhiều hơn
  là review → không tiết kiệm thời gian)
② Xảy ra ≥2 incident: AI điền sai thông tin thuốc/liều lượng mà bác sĩ không bắt
  được trong review
③ Bộ Y tế ban hành thông tư mới cấm AI participation trong hồ sơ bệnh án

ROLLBACK: Tắt AI layer, giữ nguyên HIS hiện tại. Không có data loss vì EMR chỉ
được lưu sau khi bác sĩ review + ký — draft AI không bao giờ được lưu tự động.
Thời gian rollback: < 1 ngày (tắt feature flag).
```

---

### Self-check nộp phần 02 (nhóm)
- [x] Có nhật ký hội tụ 9-12 → 1 (cluster + shortlist + score)
- [x] Có validation (quote thật) + research (link kiểm được)
- [x] Có workflow trước/sau đủ thời gian, handoff, bottleneck, boundary, fallback
- [x] Có PS v0 → v1, metric có trước/sau + cách đo, boundary có làm/không làm
- [x] Có so sánh Rule/Workflow/Agent + Decision Go/Not Yet/No-Go có lý do

---

*Tài liệu tổng hợp từ research thực: Arndt et al. 2017, Sinsky et al. 2016, AMA 2022, NEJM Catalyst 2019, Nuance DAX, Suki AI, DeepScribe, PhoBERT (VinAI). Các con số chưa verify tại Vinmec được đánh dấu rõ.*
