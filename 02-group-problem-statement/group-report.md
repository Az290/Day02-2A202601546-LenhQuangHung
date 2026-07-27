## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1   | Phan Văn Tình | 2A202601430 | Nhóm trưởng |
| 2   | Nguyễn Tiến Đạt | 2A202601678 | Thành viên |
| 3   | Nguyễn Mai Hoàng Anh | 2A202601118 | Thành viên |
| 4   | Nguyễn Đức Dũng | 2A202601096 | Thành viên |
| 5   | Lệnh Quang Hưng | 2A202601546 | Thành viên |
| 6   | Hồ Quang Minh | 2A202601906 | Thành viên |

---

# Phase 3 — Nhật ký hội tụ

## Bước 3.1 — Các candidate đã trình bày

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh |
|---:|---|---|---|---|---|
| 1 | Nguyễn Đức Dũng | Mất nhiều thời gian đọc và tóm tắt hồ sơ học bổng. | Người xét/đọc hồ sơ; ứng viên. | Đọc tài liệu dài, rút thông tin và đối chiếu điều kiện. | Nhiều dữ liệu cá nhân; cần tiêu chí xét rõ. |
| 2 | Nguyễn Tiến Đạt | Giáo viên tổng hợp tài liệu để soạn giáo án. | Giáo viên; gián tiếp là học sinh. | Tìm, đọc và đánh giá tài liệu từ nhiều nguồn. | Workflow lặp lại, có thể giới hạn nguồn và có người duyệt. |
| 3 | Hồ Quang Minh | Đối soát giao dịch ngân hàng với hóa đơn mất nhiều thời gian. | Kế toán/thu ngân. | Ghép giao dịch với hóa đơn, xử lý chênh lệch. | Impact tài chính rõ nhưng dữ liệu và sai sót có rủi ro cao. |
| 4 | Lệnh Quang Hưng | Bệnh nhân chờ khám bệnh quá lâu. | Bệnh nhân, nhân viên tiếp nhận, bác sĩ. | Điều phối lịch hẹn, thứ tự ưu tiên và năng lực khám. | Tác động lớn nhưng quá rộng, cần dữ liệu vận hành bệnh viện. |
| 5 | Phan Văn Tình | Học sinh chờ giáo viên chấm bài quá lâu. | Học sinh, giáo viên. | Giáo viên chấm, nhận xét và tổng hợp lỗi thủ công. | Có tiềm năng nhưng cần kiểm soát chất lượng phản hồi. |
| 6 | Nguyễn Mai Hoàng Anh | HR đọc thủ công toàn bộ CV để đánh giá mức độ phù hợp với JD. | HR, hiring manager, ứng viên. | Trích thông tin từ CV và so khớp với JD. | Có dữ liệu cá nhân và rủi ro thiên lệch trong tuyển dụng. |

## Bước 3.2 — Gom trùng / cluster

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A — Đọc, chọn lọc và tổng hợp tài liệu | Hồ sơ học bổng; giáo án; CV | Đọc nhiều tài liệu rời rạc rồi đối chiếu với tiêu chí. | Hai bài toán hồ sơ có dữ liệu cá nhân và quyết định có tác động cao hơn. |
| B — Đối soát nghiệp vụ | Giao dịch ngân hàng và hóa đơn | Ghép hai nguồn dữ liệu để tìm chênh lệch. | Cần quyền truy cập dữ liệu tài chính và quy tắc nghiệp vụ chính xác. |
| C — Điều phối dịch vụ | Bệnh nhân chờ khám | Phân bổ người/thời gian/tài nguyên theo hàng đợi. | Scope lớn; không phù hợp để kiểm chứng trong một lab. |
| D — Phản hồi học tập | Chờ chấm bài | Đọc bài làm rồi tạo phản hồi cho người học. | Chất lượng phản hồi và tính công bằng phải được giáo viên kiểm tra. |

## Bước 3.3 — Shortlist

| Candidate | Vì sao vào shortlist | Rủi ro / điều chưa rõ |
|---|---|---|
| Giáo viên tổng hợp tài liệu để soạn giáo án | Có thành viên hiểu bối cảnh; workflow có thể giới hạn vào bước tìm/chọn tài liệu; dễ thiết kế human review. | Chưa có baseline thời gian và chưa biết nguồn nào được phép dùng. |
| Đối soát giao dịch ngân hàng với hóa đơn | Actor, input/output và metric chênh lệch khá rõ. | Dữ liệu tài chính nhạy cảm; sai kết quả có thể gây hậu quả lớn; nhóm chưa có quyền truy cập workflow thật. |
| HR sàng lọc CV theo JD | Có workflow đọc/tóm tắt/so khớp rõ. | Rủi ro thiên lệch, dữ liệu cá nhân và quyết định tuyển dụng; nhóm chưa có domain owner để kiểm chứng. |

## Bước 3.4 — Chấm nhanh và đồng thuận

> Điểm dưới đây là điểm tự chấm của nhóm để so sánh candidate, không phải bằng chứng validation.

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Giáo viên tổng hợp tài liệu để soạn giáo án | 4 | 4 | 2 | 3 | 5 | 4 | 5 | 27 |
| Đối soát giao dịch ngân hàng với hóa đơn | 4 | 4 | 2 | 4 | 3 | 4 | 2 | 23 |
| HR sàng lọc CV theo JD | 4 | 4 | 2 | 4 | 3 | 3 | 2 | 22 |

**Candidate nhóm chọn:**  
Giáo viên tổng hợp tài liệu để soạn giáo án, tập trung vào bước tìm và đánh giá học liệu trước khi giáo viên viết giáo án.

**Vì sao chọn:**  
Candidate có workflow đủ hẹp cho lab, có thành viên hiểu bối cảnh và cho phép đặt boundary rõ: AI chỉ hỗ trợ trên nguồn học liệu được giáo viên duyệt, còn giáo viên giữ quyền lựa chọn, kiểm tra và phê duyệt giáo án.

**Vì sao không chọn các candidate còn lại:**  
Đối soát giao dịch và sàng lọc CV có impact rõ nhưng nhóm chưa có quyền truy cập dữ liệu, domain owner hoặc quy trình kiểm chứng. Vấn đề chờ khám quá rộng; đọc hồ sơ học bổng và chấm bài cần thêm tiêu chí đánh giá chất lượng trước khi có thể thử an toàn.

**Nếu có disagreement, nhóm xử lý thế nào:**  
Nhóm so sánh theo bảng điểm, ưu tiên candidate mà nhóm hiểu workflow hơn và có thể thử trong phạm vi hẹp. Các candidate còn lại được giữ làm phương án dự phòng, không bị loại vì “ít AI hơn”.

---

# Phase 4 — Quick Validation + Research giải pháp

## Bước 4.1 — Quick validation

> Nhóm chưa cung cấp kết quả phỏng vấn, survey hoặc log thực tế. Vì vậy không ghi số liệu giả định là dữ liệu thật; đây là phần cần thực hiện trước khi Go.

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Interview giáo viên | Chưa thực hiện | Cần hỏi thời gian soạn 3 giáo án gần nhất, nguồn dùng và bước nghẽn. | Có thể giáo viên đã có thư viện học liệu đủ tốt, khi đó AI không phải ưu tiên. | Thu hẹp hoặc dừng AI nếu pain chủ yếu là thiếu quy trình/chia sẻ tài liệu. |
| Nhật ký thời gian | Chưa thu thập | Cần đo từng bước: tìm, đọc/đánh giá, chọn và viết giáo án. | Bottleneck có thể nằm ở thiết kế hoạt động thay vì tìm tài liệu. | Đặt intervention đúng bước có thời gian lớn nhất. |
| Survey / poll | Chưa thực hiện | Có thể hỏi tần suất, nguồn, mức đáng giải quyết và nhu cầu review. | Nhu cầu có thể khác nhau giữa môn học/cấp lớp. | Chọn một môn và một cấp lớp cho pilot. |

**Kế hoạch validation tối thiểu trước pilot:**

1. Phỏng vấn 2–3 giáo viên cùng môn/cấp học.
2. Mỗi người ghi thời gian cho 3 giáo án gần nhất, tách riêng bước tìm và đánh giá tài liệu.
3. Chỉ giữ hypothesis AI nếu ít nhất hai người xác nhận bước tìm/đánh giá là bottleneck đáng kể và sẵn sàng review bản nháp.

## Bước 4.2 — Research giải pháp đã có

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Microsoft 365 Copilot — Teach / Lesson Plan | [Microsoft Support](https://support.microsoft.com/en-us/education/teach-in-the-microsoft-365-copilot-app) | Tạo lesson plan, quiz/rubric và điều chỉnh theo tiêu chuẩn, trình độ hoặc độ khó. | Luồng tạo bản nháp có hướng dẫn cho giáo viên. | Phụ thuộc license và dữ liệu/truy cập của tổ chức; bản nháp vẫn cần kiểm tra sư phạm. | Dùng form đầu vào rõ: môn, lớp, mục tiêu, thời lượng và nguồn được phép. |
| MagicSchool | [MagicSchool](https://www.magicschool.ai/) | Tạo lesson plan theo chủ đề/mục tiêu và các học liệu liên quan. | Sản phẩm chuyên cho giáo viên; cho thấy use case tạo giáo án đã phổ biến. | Không thay thế việc kiểm chứng nội dung, chương trình hoặc quyền sử dụng học liệu. | Chỉ xem AI là công cụ tạo/gom bản nháp, không phải tác giả hoặc người phê duyệt giáo án. |
| UNESCO — Guidance for Generative AI in Education and Research | [UNESCO](https://www.unesco.org/en/articles/guidance-generative-ai-education-and-research?hub=84636) | Đưa ra định hướng áp dụng GenAI trong giáo dục. | Nhấn mạnh cách tiếp cận lấy con người làm trung tâm, bảo vệ quyền riêng tư và kiểm chứng sư phạm. | Không phải một công cụ triển khai; cần chuyển thành quy tắc vận hành cụ thể. | Đặt human review, giới hạn nguồn/dữ liệu và tiêu chí dừng khi AI sai ngay từ workflow. |

**Kết luận research:**  
Các công cụ hiện có cho thấy việc tạo bản nháp giáo án và điều chỉnh học liệu là khả thi. Tuy nhiên research không chứng minh pain, baseline hay mức cải thiện của bối cảnh nhóm; các yếu tố đó vẫn phải được validate bằng giáo viên thực tế.

---

# Phase 5 — Workflow + Problem Statement

## Bước 5.1 — Current workflow bản nhóm

```text
[Giáo viên xác định bài học và mục tiêu]
→ [Mở sách giáo khoa, tài liệu tham khảo và nền tảng quen thuộc]
→ [Tìm, đọc và đánh giá tài liệu]  <-- bottleneck cần đo
→ [Chọn nội dung/hoạt động]
→ [Viết, rà soát và hoàn thiện giáo án]
```

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | Giáo viên | Chương trình, bài học sắp dạy | Mục tiêu bài học | Mỗi bài; cần đo | Có thể khác theo môn/cấp lớp. |
| 2 | Giáo viên | Danh sách sách, kho học liệu, website | Tập nguồn tham khảo | Mỗi bài; cần đo | Chỉ dùng nguồn có quyền sử dụng. |
| 3 | Giáo viên | Các tài liệu tìm được | Danh sách tài liệu phù hợp/không phù hợp | Mỗi bài; cần đo | Bottleneck giả định, phải kiểm chứng. |
| 4 | Giáo viên | Tài liệu đã chọn, mục tiêu | Nội dung/hoạt động dự kiến | Mỗi bài; cần đo | Cần cân nhắc trình độ lớp. |
| 5 | Giáo viên | Nội dung và mẫu giáo án | Giáo án sẵn sàng dạy | Mỗi bài; cần đo | Giáo viên chịu trách nhiệm cuối. |

**Bottleneck chính:**  
Tìm, đọc và đánh giá mức phù hợp của tài liệu từ nhiều nguồn với mục tiêu bài học. Đây là hypothesis cho đến khi có nhật ký thời gian.

## Bước 5.2 — Future workflow bản nhóm

```text
[Giáo viên nhập môn/lớp/bài học/mục tiêu + chọn nguồn được phép]
→ [Rule lọc nguồn ngoài phạm vi]
→ [AI tìm, tóm tắt và gắn thẻ tài liệu theo mục tiêu]
→ [Giáo viên mở nguồn, kiểm tra độ đúng và chọn hoạt động]  <-- human boundary
→ [Giáo viên hoàn thiện và phê duyệt giáo án]

Fallback: AI không tìm thấy nguồn phù hợp, dẫn sai nguồn hoặc nội dung không đúng → giáo viên quay lại tìm/chọn thủ công theo workflow hiện tại.
```

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Số bước | 5 | 5 | Bớt thao tác tìm/đọc thủ công, không bỏ bước phê duyệt. |
| Tổng thời gian | Chưa có baseline | Mục tiêu giảm ≥30% sau pilot | Chỉ đặt metric chính thức sau khi đo baseline. |
| Số bước thủ công | 5 | 2 | Giáo viên nhập mục tiêu và kiểm tra/phê duyệt. |
| Bottleneck chính | Tìm + đánh giá tài liệu | Kiểm tra tính đúng và phù hợp | Rủi ro chuyển từ thời gian sang chất lượng/nguồn. |
| Risk mới | Chưa có AI | Sai kiến thức, sai nguồn, bản nháp chung chung | Mitigation: giới hạn nguồn, dẫn nguồn, giáo viên review. |

## Bước 5.3 — Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Giáo viên phải tự chuẩn bị giáo án trước buổi dạy. |
| **Workflow** | Xác định bài → tìm tài liệu → đọc/đánh giá → chọn nội dung → viết và rà soát giáo án. |
| **Bottleneck** | Tìm và đánh giá học liệu từ nhiều nguồn. |
| **Impact** | Có thể làm giáo viên mất nhiều thời gian chuẩn bị; mức độ tác động chưa được đo. |
| **Success Metric** | Giảm thời gian chuẩn bị giáo án mà vẫn đảm bảo nội dung phù hợp. |
| **Boundary** | AI chỉ hỗ trợ chuẩn bị; giáo viên quyết định giáo án cuối. |

---

# Phase 6 — Rule / Workflow / Agent + Decision

## Bước 6.0 — Vị trí trên ma trận độ phù hợp với AI

**Bài toán nằm ở:** Độ phức tạp trung bình–cao, độ mơ hồ trung bình–cao → **Workflow có AI hỗ trợ một số bước**.

**Vì sao:**  
Bài toán có nhiều bước và nhiều nguồn, nhưng AI không cần tự quyết định mục tiêu, nội dung cuối hay hành động tiếp theo. Độ phù hợp của tài liệu phụ thuộc vào ngữ cảnh lớp học nên giáo viên phải kiểm tra.

## Bước 6.1 — So sánh Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Thư viện học liệu có gắn thẻ, template giáo án, checklist nguồn. | Đủ nếu vấn đề chủ yếu là tài liệu phân tán/chưa chuẩn hóa. | Không xử lý tốt tìm kiếm theo ngữ cảnh hoặc tóm tắt nhiều nguồn. | Cần triển khai trước hoặc song song. |
| **Workflow** | Giáo viên nhập mục tiêu → AI tìm/tóm tắt trong nguồn được duyệt → giáo viên kiểm tra/chọn → hoàn thiện giáo án. | Phù hợp nếu nguồn và mục tiêu được xác định rõ. | Nội dung sai, nguồn không phù hợp, phụ thuộc bản nháp AI. | **Có điều kiện** |
| **Agent** | AI tự tìm nguồn rộng, tự chọn hoạt động và tự xuất bản giáo án. | Không cần cho pilot này. | Sai kiến thức, vượt nguồn được duyệt, mất quyền kiểm soát sư phạm. | Không chọn. |

**Mức chọn:**  
Workflow có AI hỗ trợ, với Rule để giới hạn nguồn và cấu trúc đầu vào.

**Vì sao chọn:**  
Workflow giải quyết đúng bước tìm/tóm tắt nhưng vẫn giữ giáo viên ở điểm quyết định sư phạm. Agent không tạo thêm giá trị tương xứng với rủi ro.

**Vì sao không chọn mức đơn giản hơn:**  
Rule/template có thể giảm thời gian định dạng và chia sẻ tài liệu, nhưng chưa chắc hỗ trợ được việc tìm và đối chiếu nội dung từ nhiều nguồn theo một mục tiêu bài học. Điều này phải được xác nhận trong pilot.

## Bước 6.2 — Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Giáo viên của một môn và cấp/lớp cụ thể, tự nguyện tham gia pilot. |
| **Workflow** | Nhập bài học/mục tiêu và nguồn được duyệt → AI tìm/tóm tắt/gắn thẻ → giáo viên mở nguồn, kiểm tra và chọn → hoàn thiện giáo án. |
| **Bottleneck** | Thời gian tìm, đọc và đánh giá tài liệu phù hợp trong các nguồn được phép. |
| **Impact** | Nếu hypothesis được xác nhận, giáo viên có thêm thời gian cho thiết kế hoạt động và điều chỉnh theo lớp học. |
| **Success Metric** | Đo baseline trên 3 giáo án; trong pilot 5 giáo án, mục tiêu giảm ít nhất 30% thời gian ở bước tìm/đánh giá, không có lỗi kiến thức hoặc nguồn không kiểm chứng trong bản giáo án được duyệt. |
| **Boundary** | Không dùng dữ liệu cá nhân của học sinh; chỉ xử lý nguồn giáo viên có quyền dùng; không tự xuất bản/gửi giáo án; không thay giáo viên quyết định nội dung hay đánh giá học sinh. |
| **AI intervention point** | Tìm, tóm tắt, gắn thẻ và gợi ý liên kết giữa mục tiêu bài học với tài liệu trong phạm vi nguồn được duyệt. |
| **Mức chọn** | Workflow có AI hỗ trợ + Rule giới hạn nguồn. |
| **Rủi ro & người thật kiểm tra** | Giáo viên kiểm tra nguồn, độ chính xác, độ phù hợp với chương trình/lớp và phê duyệt bản cuối; nếu AI sai, quay về workflow thủ công. |

## Bước 6.3 — Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Cần chốt cụ thể môn và cấp/lớp trước pilot. |
| Baseline và success metric đã đo được chưa? | Not Yet | Chưa có nhật ký thời gian của giáo viên. |
| Có data/input đủ dùng chưa? | Not Yet | Chưa xác định nguồn được phép và quyền sử dụng học liệu. |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes, có điều kiện | Giáo viên review; AI không tự xuất bản hay dùng dữ liệu học sinh. |
| Có người review/owner vận hành không? | Yes, có điều kiện | Giáo viên pilot là owner và người phê duyệt. |
| Có cách non-AI đơn giản hơn không? | Yes | Thư viện học liệu + template phải được thử/so sánh. |

**Decision:**  
**Not Yet**

**Lý do:**  
Workflow và boundary đã đủ rõ để thiết kế pilot, nhưng nhóm chưa có evidence về mức độ pain, baseline thời gian hoặc quyền sử dụng dữ liệu/nguồn. Chọn Go ở thời điểm này sẽ biến giả định thành kết luận.

**Nếu Go, pilot nhỏ nhất là:**  
Sau validation, thử với 1 giáo viên, 1 môn/cấp lớp, 1 danh mục nguồn được duyệt và 5 giáo án; so sánh thời gian tìm/đánh giá tài liệu trước–sau, đồng thời giáo viên chấm đạt/không đạt về độ đúng và độ phù hợp.

**Nếu Not Yet, cần validate gì trước:**

1. Phỏng vấn 2–3 giáo viên và đo baseline trên ít nhất 3 giáo án/người.
2. Chốt danh mục nguồn có quyền sử dụng, quy định không đưa dữ liệu học sinh vào hệ thống.
3. Thử non-AI alternative (template + thư viện có gắn thẻ) để biết AI có thực sự cần thiết.
4. Xác định rubric review: đúng chương trình, đúng nguồn, phù hợp thời lượng và phù hợp lớp học.

**Nếu No-Go, nên làm gì thay AI:**  
Chuẩn hóa template giáo án, xây thư viện học liệu dùng chung có gắn thẻ và checklist kiểm tra nguồn/nội dung trước giờ dạy.

