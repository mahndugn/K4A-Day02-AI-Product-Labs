# 02 — Group Problem Statement
> **Vấn đề được chọn:** Bác Sĩ Vinmec Gõ EMR Thủ Công  
> **Nhóm:** _(điền tên nhóm)_ | **Ngày:** 2026-09-12

---

## Phase 3 — Chọn Bài Toán Nhóm

### 3.4. Score để đồng thuận (chấm 1-5, ép nói rõ vì sao cho 5 / cho 3)

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Card #1** — Bác sĩ Vinmec gõ EMR thủ công | **5** | **5** | **5** | **5** | **4** | **5** | **4** | **33** |
| **Card #2** — Tài xế Xanh SM hết pin, điều phối tra thủ công | 5 | 4 | 4 | 4 | 3 | 4 | 3 | 27 |
| **Card #3** — Phân loại & route ticket khiếu nại Vinhomes | 4 | 4 | 3 | 4 | 4 | 4 | 3 | 26 |

**Giải thích điểm nổi bật:**

| Ô | Điểm | Lý do |
|---|:---:|---|
| Card #1 — Pain có evidence | **5** | 4 nghiên cứu peer-reviewed (Arndt 2017, Sinsky 2016, NEJM Catalyst 2019, AMA 2022) đều xác nhận. Con số 30-40% trong file Excel khớp với benchmark quốc tế. |
| Card #1 — Impact đo được | **5** | Có số baseline rõ: 8-12 phút/lượt gõ, 23-29 phút/chu kỳ khám. Success metric đo được: phút/lượt, số BN/ngày, tỷ lệ lỗi. |
| Card #1 — So sánh R/W/A được | **5** | 3 tier có thể phân tích rõ ràng, ranh giới pháp lý (Thông tư 46/2018) tạo boundary tự nhiên cho human checkpoint. |
| Card #1 — Làm trong lab | **4** | Không phải **5** vì cần data tiếng Việt y khoa để fine-tune model — không build được chỉ bằng prompt. Nhưng có thể prototype bằng Whisper + template. |
| Card #2 — Làm trong lab | **3** | Cần API real-time trạm sạc Xanh SM — không có public access, khó mock trong lab. |
| Card #3 — Pain có evidence | **3** | Chỉ có "SLA 30 ngày" từ file Excel, chưa có nghiên cứu độc lập xác nhận tần suất hay tỷ lệ miss SLA cụ thể. |

---

**Candidate nhóm chọn (1 bài duy nhất):**

```text
Card #1 — Bác sĩ Vinmec gõ EMR thủ công (33/35 điểm)
```

**Vì sao chọn (4-5 câu):**

```text
Đây là bài toán duy nhất trong 3 card có evidence từ nghiên cứu học thuật
peer-reviewed: Arndt et al. (2017, n=142) và Sinsky et al. (2016, n=57) xác nhận
bác sĩ mất 30-50% thời gian cho EHR documentation — khớp hoàn toàn với con số
trong file Excel. Workflow hiện tại vẽ được 5-6 bước rõ ràng, bottleneck nằm đúng
tại bước gõ narrative và tra mã ICD — cô lập được để AI can thiệp mà không đụng
các bước khác. Technology stack (Whisper STT + PhoBERT NER) đã tồn tại, có thể
prototype trong lab mà không cần API kín của bên thứ ba. Quan trọng nhất, boundary
pháp lý từ Thông tư 46/2018/TT-BYT tạo ra human checkpoint tự nhiên (bác sĩ phải
ký số) — giúp solution vừa safe vừa compliant ngay từ thiết kế.
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

### 4.1. Quick validation

| Nguồn | Số người / mẫu | Tín hiệu xác nhận (kèm quote / citation) | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| **Academic study** (Arndt et al., *Annals of Family Medicine*, 2017) | 142 bác sĩ gia đình, theo dõi 3 năm | *"Clinicians spent 355 minutes (5.9 hours) of an 11.4-hour workday in the EHR... Clerical and administrative tasks including documentation accounted for nearly one-half of EHR time (44.2%)"* | Nghiên cứu tại Mỹ, hệ thống Epic — có thể không map hoàn toàn sang VN | Dùng làm proxy benchmark; cần điều chỉnh với pilot thực địa Vinmec |
| **Academic study** (Sinsky et al., *Annals of Internal Medicine*, 2016) | 57 bác sĩ, 4 chuyên khoa, time-motion study | *"For every hour of direct patient care, physicians spend nearly 2 additional hours on EHR and desk work"* | Chuyên khoa khác nhau có tỷ lệ khác nhau — nội khoa cao hơn, ngoại khoa thấp hơn | Scope bài toán vào nội khoa / đa khoa Vinmec trước |
| **Survey** (AMA, 2022) | Hàng nghìn bác sĩ Mỹ | *"62% of physicians say EHR contributes to burnout"*; *">80% want AI to reduce documentation burden"* | Mỹ có EHR phức tạp hơn VN; burnout context khác | Dùng % 80% muốn AI hỗ trợ như social proof khi thuyết phục stakeholder |
| **Product report** (Nuance DAX, 2023) | 550+ bệnh viện triển khai tại Mỹ | *"Reduces documentation time by 50%; physicians gain back 3+ hours per day"* | Internal study của vendor — có thể bias; chưa có RCT độc lập | Xem là upper bound; dùng conservative estimate 30-40% cho pitch |
| **Expert observation** (NEJM Catalyst, 2019) | Survey executives & clinicians | *"Physicians spend 15-17 minutes per encounter on EHR documentation — nearly equal to face-time with patient"* | Survey, không phải time-motion — có thể over-report | Dùng 15-17 phút làm baseline documentation time trong workflow table |

**Insight sau validation (1-2 câu — pain thật nằm ở đâu):**

```text
Pain thật không nằm ở việc "gõ chậm" mà nằm ở "cognitive context switch" — bác sĩ
phải chuyển từ tư duy lâm sàng (quan sát bệnh nhân) sang tư duy hành chính (nhập
form) ngay sau khám, gây mệt mỏi tích lũy và lỗi nhập liệu vào cuối ngày. Đây là
lý do pajama time (gõ EMR sau khi về nhà) xuất hiện ở >40% bác sĩ theo AMA 2022.
```

---

### 4.2. Research giải pháp đã có

| Nguồn / tool / case | Link (đã verify) | Họ giải quyết bước nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| **Nuance DAX Copilot** (Microsoft) | [nuance.com/healthcare](https://www.microsoft.com/en-us/health-solutions) ✅ | Ambient listening → GPT-4 clinical note → bác sĩ review → EHR sync | Tích hợp sẵn Epic/Cerner; đã triển khai 550+ bệnh viện; giảm 50% thời gian ghi chú | Chỉ tiếng Anh; giá enterprise; không hỗ trợ HIS VN | Validate architecture: ambient → NLP → structured note là pattern đúng. Copy kiến trúc, không copy sản phẩm. |
| **Suki AI** | [suki.ai](https://www.suki.ai) ✅ | Voice command + ambient AI → SOAP notes | Giảm 72% thời gian; 90% retention sau 30 ngày; EHR-agnostic API | Không có tiếng Việt; subscription per-doctor model đắt cho VN | Human boundary: bác sĩ vẫn review trước khi sign — áp dụng nguyên mẫu |
| **DeepScribe** | [deepscribe.ai](https://www.deepscribe.ai) ✅ | AI-generated SOAP notes từ conversation recording | 90% bác sĩ tiếp tục dùng sau 30 ngày; specialty-specific models | US-only; không mở API; no Vietnamese support | Specialty-specific training data là key insight — Vinmec cần fine-tune theo từng khoa |
| **Abridge** | [abridge.com](https://www.abridge.com) ✅ | Summarize patient-doctor conversation → structured summary cho bác sĩ và bệnh nhân | Partnership với UPMC (150+ bệnh viện); bệnh nhân cũng nhận tóm tắt | Enterprise-only; tiếng Anh | Dual output (cho bác sĩ + bệnh nhân) là use case mở rộng thú vị cho giai đoạn 2 |
| **PhoBERT** (VinAI Research) | [github.com/VinAIResearch/PhoBERT](https://github.com/VinAIResearch/PhoBERT) ✅ | Pre-trained BERT cho tiếng Việt; state-of-the-art NLP VN | Miễn phí, open-source; tốt nhất cho tiếng Việt hiện tại; trong hệ sinh thái Vingroup | Chưa có medical domain fine-tuning; cần corpus y khoa VN | Fine-tune PhoBERT với dữ liệu EMR Vinmec là path khả thi nhất cho tiếng Việt |
| **Whisper** (OpenAI) | [openai.com/research/whisper](https://openai.com/research/whisper) ✅ | Speech-to-text đa ngôn ngữ, bao gồm tiếng Việt | Open-source; WER tiếng Việt ~8-12% (tốt); chạy on-premise được | WER tăng với thuật ngữ y khoa hiếm; latency nếu run real-time | Dùng Whisper làm STT layer; accept imperfect transcription vì có human review |

**Research takeaway (2-3 câu):**

```text
Không nên build lại từ đầu những gì Nuance DAX đã làm — nên copy kiến trúc
(ambient → STT → NLP → structured note → human review) và thay bằng open-source
stack phù hợp tiếng Việt: Whisper (STT) + PhoBERT fine-tuned (NER) + Vinmec
SOAP template engine. Lợi thế cạnh tranh duy nhất và thực tế là VinAI (cùng
hệ sinh thái Vingroup) đã có PhoBERT — đây là điểm khởi đầu không bệnh viện
VN nào khác có. Không build tính năng "tự order thuốc" hay "tự schedule tái khám"
ở phase 1 — đây là Agent territory, quá rủi ro và không cần thiết để giải quyết
bottleneck chính.
```

> **Disclaimer:** Số liệu từ Nuance, Suki, DeepScribe là từ trang web vendor — có thể bias.  
> Số liệu từ Arndt et al. và Sinsky et al. là peer-reviewed, độc lập — tin cậy hơn.  
> Con số 30-40% tại Vinmec là **giả định chưa verify** — cần bấm giờ thực địa.

---

## Phase 5 — Workflow + Problem Statement

### 5.1. Current Workflow — Bản Nhóm

```text
[1 Bệnh nhân vào + chào hỏi: 1-2' — Bác sĩ]
→ [2 Hỏi bệnh sử + khám lâm sàng: 8-10' — Bác sĩ]
→ [3 Bệnh nhân ra ngoài: 0' — transition]
→ [4 Gõ Chief Complaint + HPI: 3-4' — Bác sĩ] ← BOTTLENECK 1
→ [5 Tra mã ICD-10 + chọn chẩn đoán: 2-3' — Bác sĩ] ← BOTTLENECK 2
→ [6 Gõ đơn thuốc + liều lượng: 2-3' — Bác sĩ] ← BOTTLENECK 3
→ [7 Ghi kế hoạch + tái khám: 1-2' — Bác sĩ]
→ [8 Ký số & submit HIS: 1' — Bác sĩ]
→ [9 Gọi bệnh nhân tiếp: 0']
TỔNG: 18-25 phút/bệnh nhân | Gõ EMR = 8-12 phút = 44-48%
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1. Tiếp nhận bệnh nhân | Bác sĩ + Bệnh nhân | Lịch hẹn, thẻ BHYT | Bệnh nhân ngồi khám | 1-2 phút / mỗi lượt khám | HIS auto-pull thông tin cơ bản |
| 2. Hỏi bệnh sử & khám | Bác sĩ (chủ động), Bệnh nhân (trả lời) | Triệu chứng BN kể, kết quả khám thực thể | Mental model chẩn đoán trong đầu bác sĩ | 8-10 phút / lượt | Thông tin ở đây — chưa được ghi lại |
| 3. Bệnh nhân ra ngoài | Bệnh nhân | — | — | 0 phút | Context switch bắt đầu |
| 4. Gõ CC + HPI vào EMR | Bác sĩ | Mental model từ bước 2 | Text trong form EMR | 3-4 phút / lượt | **BOTTLENECK 1** — narrative tự do, không có autocomplete |
| 5. Tra & chọn mã ICD-10 | Bác sĩ | Chẩn đoán trong đầu | Mã ICD được chọn trong dropdown | 2-3 phút / lượt | **BOTTLENECK 2** — dropdown 10.000+ mã, search kém |
| 6. Gõ đơn thuốc | Bác sĩ | Phác đồ điều trị | Đơn thuốc trong HIS | 2-3 phút / lượt | **BOTTLENECK 3** — gõ tên thuốc, liều, tần suất |
| 7. Ghi kế hoạch điều trị | Bác sĩ | Quyết định lâm sàng | Text kế hoạch, lịch tái khám | 1-2 phút / lượt | Thường copy template cũ rồi sửa |
| 8. Ký số & submit | Bác sĩ | EMR đã điền đủ | Hồ sơ hợp lệ trong HIS | 1 phút / lượt | **Không thể bỏ** — yêu cầu pháp lý |

**Bottleneck chính (2-3 câu):**

```text
Ba bước 4-5-6 chiếm 7-10 phút (44-48% tổng chu kỳ) nhưng không tạo ra giá trị
lâm sàng mới — chúng chỉ chuyển thông tin từ đầu bác sĩ vào form máy tính.
Bottleneck không phải là tốc độ gõ mà là cognitive overhead: bác sĩ phải dừng
tư duy lâm sàng, chuyển sang tư duy hành chính, tra cứu mã số trong hệ thống
phân loại 10.000+ mục — đây là nguồn gốc của lỗi nhập liệu và burnout tích lũy.
```

---

### 5.2. Future Workflow — Bản Nhóm

```text
[1 Bệnh nhân vào + bác sĩ bật AI ambient: 1-2' — Bác sĩ]
→ [2 Hỏi bệnh sử + khám / AI ghi âm ngầm: 8-10' — Bác sĩ chủ đạo, AI thu thập]
→ [3 AI processing: transcribe → NER → draft SOAP + gợi ý ICD top-3: 30-60s — AI tự động]
→ [4 Bác sĩ review draft + sửa nếu sai + confirm ICD: 1-2' — Bác sĩ / HUMAN BOUNDARY]
→ [5 Ký số & submit: 1' — Bác sĩ]
→ [6 Gọi bệnh nhân tiếp]
TỔNG: 12-15 phút/bệnh nhân | Tiết kiệm: 10-13 phút/lượt (~48%)

Fallback: AI confidence < 70% → blank form + flag đỏ → bác sĩ nhập tay
          AI gợi ý sai thuốc có tương tác → hard block + cảnh báo
          Ghi âm lỗi (môi trường ồn) → fallback về template + manual
```

**Before/After Impact:**

| Metric | Trước | Sau kỳ vọng | Cách đo |
|---|---:|---:|---|
| Tổng thời gian/chu kỳ khám | 18-25 phút | 12-15 phút | Bấm giờ thực tế (stopwatch) |
| Thời gian gõ EMR/lượt | 8-12 phút | 1-3 phút | Log timestamp HIS: open form → submit |
| Số bước thủ công | 6 bước (3-8) | 2 bước (4, 5) | Đếm trực tiếp từ workflow |
| Số BN/ngày/bác sĩ | ~20-25 BN | ~28-33 BN (+30-40%) | Report HIS cuối ngày |
| Pajama time (gõ sau giờ làm) | >40% bác sĩ | <10% bác sĩ | Survey 2 tuần/lần |
| Tỷ lệ lỗi nhập liệu EMR | _cần đo baseline_ | Giảm ≥40% | Audit hồ sơ: so sánh draft AI vs. version cuối |
| Risk mới (AI điền sai) | 0% (manual) | Có — quản lý bằng review step | Theo dõi số lần bác sĩ sửa draft/tuần |

---

### 5.3. Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Bác sĩ lâm sàng tại Vinmec (ước tính 1.500-3.000+ bác sĩ toàn hệ thống), đặc biệt khoa Nội, Nhi, Đa khoa — nơi volume bệnh nhân cao và documentation nặng nhất |
| **Workflow** | Sau mỗi lượt khám (5-15 phút), bác sĩ phải tự gõ toàn bộ hồ sơ bệnh án vào HIS: Chief Complaint, HPI, chẩn đoán (tra mã ICD), đơn thuốc, kế hoạch điều trị — mất 8-12 phút/lượt, chiếm 44-48% tổng chu kỳ khám |
| **Bottleneck** | Bước gõ narrative (CC + HPI) và tra mã ICD-10 chiếm 5-7 phút trong số 8-12 phút — không tạo giá trị lâm sàng mới, chỉ chuyển thông tin từ đầu bác sĩ sang form máy tính |
| **Impact** | Bác sĩ khám được ít hơn 30-40% số bệnh nhân so với tiềm năng; lỗi nhập liệu tăng vào cuối ngày khi mệt; >40% bác sĩ tiếp tục gõ EMR sau giờ làm (AMA 2022); dẫn đến burnout và giảm chất lượng chăm sóc |
| **Success Metric** | Thời gian gõ EMR/lượt: 8-12 phút → ≤2 phút; số BN/ngày/bác sĩ tăng ≥20%; tỷ lệ pajama time giảm từ 40% xuống <10%; tỷ lệ lỗi nhập liệu giảm ≥40% |
| **Boundary** | AI có thể làm: ghi âm, transcribe, NER, điền draft SOAP, gợi ý ICD top-3, gợi ý thuốc theo protocol. AI KHÔNG làm: ký số, quyết định chẩn đoán cuối, order thuốc không qua confirm của bác sĩ |

**Câu hỏi AI phản biện v0:**
- **Field mơ hồ:** "Impact" nêu nhiều hậu quả nhưng chưa có baseline Vinmec thực tế — con số AMA 2022 là của Mỹ
- **Tôi sửa gì:** Thêm ghi chú "(proxy từ AMA 2022 — cần validate tại Vinmec)" vào Impact; thêm cột "Cách đo baseline" vào Success Metric

---

## Phase 6 — Rule / Workflow / Agent + Decision

### 6.0. Ma trận độ phù hợp

- **Độ mơ hồ:** `[x]` **Thấp** (có đúng/sai rõ)  
  Vì sao: Output EMR có cấu trúc chuẩn (SOAP), có đúng/sai có thể verify bằng bác sĩ review. Không phải bài "nhiều đáp án đều OK".

- **Độ phức tạp:** `[x]` **Cao** (3+ bước/nguồn, phụ thuộc nhau)  
  Vì sao: AI phải chain 3 bước: STT → NLP NER → structured mapping. Mỗi bước có error rate riêng, lỗi bước trước ảnh hưởng bước sau.

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
ra draft đó, AI phải chain STT → NER → template mapping — đủ phức tạp để cần
ML, không đủ phức tạp để cần Agent tự lập kế hoạch. Đây là sweet spot của Workflow.
```

---

### 6.1. So sánh Rule / Workflow / Agent (trên cùng bài toán EMR)

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Auto-fill tên BN, ngày, bác sĩ từ lịch hẹn. Template SOAP theo chuyên khoa. Search ICD cải tiến (fuzzy search). | Nếu bottleneck chỉ là thiếu template — nhưng pain thật là narrative phải gõ tay, Rule không đụng được | Không giải quyết bottleneck chính (narrative gõ tay). Đã có trong HIS, nếu đủ thì vấn đề đã giải quyết từ lâu | ✅ **Dùng làm pre-fill layer** kết hợp Workflow, không dùng độc lập |
| **Workflow** | AI ambient ghi âm ngầm → Whisper STT → PhoBERT NER (entities: triệu chứng, thuốc, chẩn đoán) → điền SOAP draft → gợi ý ICD top-3 → **bác sĩ review + ký số** | Khi AI giải quyết được bước nặng nhất (narrative), human vẫn giữ quyết định cuối. Đây đúng là trường hợp này. | STT accuracy với thuật ngữ y khoa VN ~88-92% (chưa perfect). Bác sĩ phải tin AI đủ để không đọc lại từng chữ | ✅ **LỰA CHỌN CHÍNH** — giải quyết 70-80% bottleneck, comply pháp lý, có thể pilot |
| **Agent** | AI tự nghe → điền EMR → order thuốc theo protocol → schedule tái khám → gửi summary cho BN → không cần bác sĩ duyệt từng bước | Chỉ khi accuracy >99.5% VÀ pháp lý cho phép VÀ bác sĩ tin tưởng hoàn toàn — cả 3 điều kiện chưa thoả | Sai 1 bước trong chain → hậu quả y tế nghiêm trọng. Thông tư 46/2018 chặn hoàn toàn ở khâu ký. Trust gap với bác sĩ VN hiện tại | ❌ **Không chọn** — roadmap 3-5 năm, bắt đầu từng scope nhỏ sau khi Workflow proven |

---

**5 câu hỏi chốt:**

**1. Rule có giải được 70-80% case không?**
```
Không. Rule giải được ~20-30%: auto-fill trường cố định (tên, ngày, bác sĩ),
template theo chuyên khoa. Nhưng 70-80% còn lại là narrative tự do (HPI, chẩn
đoán tự viết, kế hoạch điều trị) — Rule không xử lý được ngôn ngữ tự nhiên.
Bằng chứng: HIS đã có auto-fill cơ bản, nhưng pain vẫn tồn tại → Rule không đủ.
```

**2. Các bước có đi thẳng một đường không hay phải rẽ nhánh?**
```
Rẽ nhánh ở 2 điểm: (1) Nếu AI confidence <70% → blank form thay vì điền sai.
(2) Nếu thuốc gợi ý có tương tác nguy hiểm → hard block, không cho submit.
Hai nhánh này cần logic điều kiện → đây là lý do cần Workflow (có conditional
routing) thay vì Rule đơn thuần (chỉ có một đường thực thi).
```

**3. Có thật sự cần Agent tự lập kế hoạch + gọi tool không?**
```
Không. Bài này không cần Agent vì: (a) Không có "planning" — chuỗi bước đã cố
định (ghi âm → STT → NER → template). (b) Không có "tool calling" động — AI không
cần tự quyết dùng tool nào. (c) Không có multi-step reasoning về mục tiêu dài
hạn. Đây là pipeline tuyến tính có conditional — đặc trưng của Workflow, không phải
Agent.
```

**4. Nếu AI sai, ai phát hiện đầu tiên và sửa trong bao lâu?**
```
Bác sĩ phát hiện tại bước review (bước 4 trong future workflow) — ngay lập tức,
trong cùng lượt khám. Thời gian sửa: ước tính 30-60 giây nếu chỉ sửa vài chỗ.
Nếu AI sai nhiều (confidence thấp) → blank form → bác sĩ nhập tay trong 8-12 phút
như cũ. Không có hậu quả delay — fallback về current state ngay lập tức.
```

**5. Có hạ được từ Agent → Workflow → Rule không?**
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
Workflow giải quyết đúng bottleneck chính (7-10 phút narrative + ICD lookup)
mà Rule không đụng được, đồng thời giữ human boundary bắt buộc theo Thông tư
46/2018/TT-BYT (bác sĩ review + ký số) mà Agent vi phạm. Technology stack tồn
tại và đã proven: Nuance DAX (Mỹ) và Suki AI đã làm được, VinAI/PhoBERT cung cấp
path khả thi cho tiếng Việt trong hệ sinh thái Vingroup. Fallback logic rõ ràng
(AI confidence <70% → blank form) đảm bảo sai thì sửa được ngay, không có hậu
quả trễ.
```

**Vì sao không chọn mức đơn giản hơn (Rule) (2-3 câu):**
```text
Rule đã có trong HIS và pain vẫn tồn tại — đây là bằng chứng mạnh nhất rằng Rule
không đủ. Template, auto-fill, dropdown cải thiện chỉ giải quyết structured fields
(~20% effort) nhưng không đụng được narrative tự do (Chief Complaint, HPI) — đây
là phần chiếm nhiều thời gian và cognitive load nhất.
```

---

### 6.2. Problem Statement v1 (v0 sửa chặt hơn)

| Field | Nội dung |
|---|---|
| **Actor** | Bác sĩ lâm sàng tại Vinmec — ưu tiên khoa Nội & Nhi (volume cao nhất); ước tính 1.500-3.000+ bác sĩ toàn hệ thống *(con số chưa verify chính thức — proxy từ quy mô 43+ cơ sở Vinmec)* |
| **Workflow** | Sau mỗi lượt khám 8-10 phút, bác sĩ gõ thủ công 6 trường EMR vào HIS: CC → HPI → chẩn đoán (tra ICD-10) → đơn thuốc → kế hoạch → ký số; tổng 8-12 phút/lượt; lặp lại 20-30 lượt/ngày/bác sĩ |
| **Bottleneck** | Bước gõ CC+HPI (3-4') và tra mã ICD-10 (2-3') chiếm 5-7 phút — đây là bước chuyển thông tin từ đầu bác sĩ sang form, không tạo giá trị lâm sàng, nhưng xảy ra sau mỗi cuộc khám bệnh mà không có công cụ hỗ trợ |
| **Impact** | Proxy từ Sinsky et al. 2016 & AMA 2022 (chưa đo tại Vinmec): giảm capacity khám 30-40%; burnout tích lũy; lỗi nhập liệu vào cuối ca; pajama time (gõ sau giờ làm) ảnh hưởng work-life balance |
| **Success Metric** | ① Thời gian gõ EMR/lượt: 8-12' → ≤2' ② Số BN/ngày/bác sĩ: tăng ≥20% ③ Pajama time: từ >40% bác sĩ → <10% bác sĩ ④ First-pass accuracy của AI draft: ≥85% (bác sĩ không cần sửa major) |
| **Boundary (làm / không làm)** | **Làm:** Ghi âm ngầm, STT, NER entities y tế, điền draft SOAP, gợi ý ICD top-3, gợi ý thuốc theo protocol Vinmec. **Không làm:** Ký số thay bác sĩ, quyết định chẩn đoán cuối, order thuốc không qua confirm, chia sẻ dữ liệu ra ngoài HIS |
| **AI intervention point** | Can thiệp **sau bước 2** (kết thúc khám — bác sĩ đã có mental model). Kết thúc **trước bước 4** (bác sĩ review và ký số). AI hoạt động trong cửa sổ 30-60 giây giữa BN ra ngoài và bác sĩ nhìn vào màn hình |
| **Mức chọn** | **Workflow** — AI xử lý bước nặng nhất (narrative + ICD lookup), human giữ review + ký số. Rule làm foundation pre-fill. Agent không dùng vì vi phạm pháp lý y tế VN. |
| **Rủi ro & người kiểm tra** | Rủi ro lớn nhất: AI transcribe sai thuật ngữ y khoa hiếm → bác sĩ không chú ý → lỗi vào hồ sơ. Người kiểm tra: Bác sĩ senior (1 người/khoa) audit 5% hồ sơ AI-assisted/tuần trong 3 tháng đầu; so sánh draft AI vs. version bác sĩ sửa. |

---

### 6.3. Final Decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor + workflow rõ chưa? | **Yes** | Bác sĩ lâm sàng Vinmec + 8-bước workflow đã vẽ được đầy đủ với thời gian từng bước |
| Baseline + metric đo được chưa? | **Not Yet** | Metric định nghĩa rõ, nhưng baseline Vinmec chưa đo — đang dùng proxy từ nghiên cứu quốc tế. Cần bấm giờ 10-20 lượt khám thực |
| Data/input đủ dùng chưa? | **Not Yet** | Cần corpus ghi âm cuộc khám tiếng Việt để fine-tune Whisper và PhoBERT. Hiện chưa có. Prototype có thể chạy với script mô phỏng. |
| AI sai, hậu quả chấp nhận được không? | **Yes** | Có human review step trước khi lưu. Fallback về blank form nếu confidence thấp. Không có auto-submit. Worst case = bác sĩ nhập tay như cũ. |
| Có người review/owner không? | **Not Yet** | Cần xác định bác sĩ champion (early adopter) tại 1 khoa. Chưa có cam kết từ Vinmec IT/Medical Director. |
| Có cách non-AI đơn giản hơn không? | **Yes — nhưng đã thử** | Thuê y tá hành chính gõ hộ (giải pháp ở một số bệnh viện). Nhưng chi phí cao, vẫn có delay, không scale. Template/Rule đã có trong HIS và không đủ. |

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

**Pilot nhỏ nhất (data nào, chạy tay ra sao, đo 3 số nào):**
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

*Tài liệu được tổng hợp từ research thực: Arndt et al. 2017, Sinsky et al. 2016, AMA 2022, NEJM Catalyst 2019, Nuance DAX, Suki AI, DeepScribe, PhoBERT (VinAI). Các con số chưa verify tại Vinmec được đánh dấu rõ.*
