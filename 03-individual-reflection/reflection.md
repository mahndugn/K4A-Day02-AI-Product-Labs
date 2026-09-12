# 03 — Individual Reflection

> Viết bằng lời của bạn (Phase 7 trong `01-worksheet.md`). Có thể dùng AI gợi ý câu hỏi tự soi, không dùng AI viết thay. 8-12 câu, có chuyện cụ thể.

## Thông tin cá nhân

- Họ và tên: [Tên của bạn]
- Mã học viên: [Mã của bạn]
- Nhóm: [Tên nhóm]
- Candidate problem nhóm chọn: Bác sĩ Vinmec gõ EMR thủ công

---

## 1. Tôi đã tham gia vào phần nào?

Ghi việc cụ thể + kết quả cụ thể. Không ghi chung chung kiểu "tham gia thảo luận".

| Hoạt động | Tôi đã làm gì? (việc cụ thể) | Kết quả / ảnh hưởng tới nhóm |
|---|---|---|
| Scan cá nhân | Tìm ra các vấn đề thực tế cá nhân (trong đó có bài toán EMR của Vinmec). | Đóng góp ý tưởng đầu vào để nhóm lựa chọn. |
| Chọn candidate problem | Vote đồng thuận chọn bài EMR Vinmec. | Chốt được đề tài có impact lớn nhất. |
| Validation / research | **(Phụ trách chính)** Tìm kiếm báo cáo y khoa, giải pháp (Nuance DAX) và đào sâu về rủi ro Ảo giác (Hallucination) & Bỏ sót (Omission). | Nhóm chốt được kiến trúc công nghệ và nhận diện được tử huyệt của AI y tế để không mù quáng tin vào tool. |
| Workflow nhóm | Cung cấp tài liệu rủi ro để hỗ trợ bạn khác vẽ workflow. | Giúp bản workflow của nhóm có thêm các chốt chặn an toàn (fallback) chặt chẽ. |
| Rule / Workflow / Agent | **(Phụ trách chính)** Lập luận vì sao bài y tế bắt buộc phải là Workflow (Human-in-the-loop). | Ngăn chặn tư duy "Solution-first" của nhóm khi muốn làm Agent tự kê đơn. |

**Dấu tay rõ nhất của tôi trong artifact cuối (1-2 câu):**

```text
Chính là mảng Research về rủi ro Ảo giác (Hallucination) và Bỏ sót (Omission) của AI trong y tế. Những tài liệu và cảnh báo của tôi là cơ sở gốc để cả nhóm quyết định phải xây dựng chốt chặn Human-in-the-loop (bắt buộc bác sĩ review) thay vì phó mặc cho Agent.
```

---

## 2. Bảng dùng AI (mỗi dòng 1 phase có dùng AI — 2 cột cuối bắt buộc)

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Nhờ gợi ý các pain point trong bệnh viện từ góc nhìn bác sĩ. | Gợi ý đúng điểm đau "Cognitive load" sau khi khám xong phải nhớ lại để gõ. | Đưa ra vài ý tưởng chung chung như "bác sĩ stress vì đông bệnh nhân". | Tôi gạn lọc và định lượng bằng con số cụ thể (8-12 phút gõ EMR). |
| Workflow | Nhờ AI phân tích các ca tử vong/kiện cáo do AI y tế sai sót. | Chỉ ra rất tốt rủi ro Omission khi AI nghe nhầm tiếng ồn thành triệu chứng bệnh. | Đề xuất giải pháp bằng cách "thêm prompt nhắc AI cẩn thận hơn" (rất hời hợt). | Tôi bỏ qua gợi ý prompt, mang tài liệu đó đi cảnh báo để nhóm vẽ thêm bước Human-in-the-loop. |
| Research | Tìm các tool AI y tế đã triển khai thành công. | Tổng hợp nhanh các tên tuổi như Suki, DeepScribe. | Giới thiệu các tool không hề hỗ trợ tiếng Việt. | Tự research thêm về PhoBERT (VinAI) để đảm bảo tính thực tiễn tại VN. |
| Rule / Workflow / Agent | Hỏi về các vụ kiện khi AI chẩn đoán sai để làm tư liệu phản biện. | Cung cấp góc nhìn về rủi ro pháp lý (Compliance/Liability). | | Chuyển hóa nó thành rào cản Boundary: Cấm dùng Agent. |

> Nếu phase nào không dùng AI, ghi `Không dùng` và vì sao tự làm.

---

## 3. Reflection câu hỏi mở

Chọn 3-4 câu trong 6 câu dưới để viết thành đoạn 8-12 câu (không trả lời bullet 1 dòng):
- Tôi học được gì khi nghe top 3 problems của các bạn khác?
- Nhóm có lúc nào bị solution-first, đòi làm Agent cho ngầu không?
- Tôi có thay đổi ý kiến sau khi bị challenge không, vì sao đổi?
- Tôi đóng góp gì thật sự vào artifact cuối, phần nào có dấu tay của tôi?
- Điều khó nhất khi viết Problem Statement là gì, metric hay boundary?
- Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

**Reflection:**

```text
Trong dự án này, dấu ấn lớn nhất của tôi nằm ở khâu Research giải pháp và Cảnh báo rủi ro hệ thống. Ban đầu, khi nhóm chốt làm bài EMR, một vài thành viên khá phấn khích và rơi vào bẫy "solution-first", muốn tích hợp luôn một Agent tự động tra cứu hồ sơ và kê đơn thuốc tự động cho "ngầu". Tuy nhiên, qua quá trình đào sâu nghiên cứu các giải pháp trên thị trường và đọc các tài liệu về rủi ro AI, tôi nhận ra tử huyệt của AI y tế nằm ở "Ảo giác" (Hallucination) và "Bỏ sót" (Omission). Một lỗi bỏ sót tiền sử dị ứng thuốc do AI nghe nhầm có thể phải đánh đổi bằng tính mạng bệnh nhân. Vì vậy, tôi đã cung cấp các tài liệu này để kéo nhóm trở lại mặt đất, kiên quyết yêu cầu nhóm phải thiết kế cơ chế Human-in-the-loop (bắt buộc bác sĩ review) thay vì bấm "Approve All" mù quáng. Điều này giúp bản thiết kế của nhóm thực sự khả thi về mặt pháp lý và tuân thủ chặt chẽ Thông tư 46 của Bộ Y tế. Nếu được làm lại, tôi sẽ challenge nhóm mạnh hơn ở phần đo lường Baseline. Việc sử dụng số liệu proxy từ nghiên cứu AMA của Mỹ dù uy tín nhưng chưa sát thực tiễn Việt Nam. Tôi sẽ yêu cầu nhóm tìm cách liên hệ bác sĩ thực tế để bấm giờ (time-motion) một vài ca khám, từ đó chứng minh bài toán thuyết phục và "đời" hơn nữa.
```

---

## 4. Tự kiểm cuối bài (check trước khi nộp repo)

- [x] [12đ] Cá nhân có 5+ problems + top 3 Problem Cards
- [x] [12đ] Tôi đã pitch rõ + challenge nhóm đúng trọng tâm (ghi ở bảng mục 1)
- [x] Nhóm có nhật ký hội tụ từ candidates về 1 bài
- [x] [15đ] Nhóm có workflow trước/sau
- [x] [20đ] Nhóm có PS v0/v1 với metric + boundary rõ
- [x] [15đ] Nhóm có so sánh No AI / Rule / Workflow / Agent
- [x] [10đ] Nhóm có Go / Not Yet / No-Go + lý do rõ
- [x] [10đ] Reflection này có vai trò thật + AI giúp/sai ở đâu + điều học được + nếu làm lại đổi gì
- [x] [6đ] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp AI
