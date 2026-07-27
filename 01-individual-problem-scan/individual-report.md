# 01 — Individual Problem Scan

---

## Phase 1 — Bảng scan (8 problems)

| # | Lăng kính | Vấn đề | Actor | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tốn thời gian | Xếp hàng chờ khám bệnh quá lâu | Bệnh nhân | Chờ 1–3 giờ mới đến lượt |
| 2 | Tốn thời gian | Mất thời gian tìm chỗ đỗ xe | Người lái xe | Đi nhiều vòng mới tìm được chỗ |
| 3 | Lặp lại | Quên uống thuốc đúng giờ | Người bệnh | Bỏ lỡ nhiều liều thuốc |
| 4 | Lặp lại + tốn thời gian | Quản lý chi tiêu cá nhân khó | Người đi làm, sinh viên | Cuối tháng không biết tiền đã tiêu vào đâu |
| 5 | Tốn thời gian + AI có thể tốt hơn | Khó tìm tài liệu học phù hợp | Sinh viên | Mất nhiều giờ tìm kiếm |
| 6 | Lặp lại | Quên deadline công việc hoặc bài tập | Sinh viên, nhân viên | Nộp muộn hoặc bỏ sót việc |
| 7 | Pain từ người khác + AI có thể tốt hơn | Thông tin trong nhóm chat bị trôi | Thành viên nhóm | Hỏi lại cùng một nội dung nhiều lần |
| 8 | Lặp lại + AI có thể tốt hơn | Phân loại email quan trọng mất thời gian | Nhân viên văn phòng | Bỏ sót email cần xử lý |

8 vấn đề chia thành 2 nhóm: nghẽn ở hàng đợi hoặc ở việc nhắc đúng lúc (#1, #2, #3, #6), và thông tin đã tồn tại nhưng người phải tự đọc, tự chọn lọc (#4, #5, #7, #8).

---

## Phase 2 — Top 3 Problem Cards

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | #1 — Bệnh nhân chờ khám bệnh quá lâu | Impact rộng nhất; baseline và target là số đo được rõ ràng | Có tiếp cận được dữ liệu lượt khám và quyền đổi quy trình tiếp nhận không |
| 2 | #4 — Khó khăn trong quản lý chi tiêu cá nhân | Lặp lại hằng ngày, tôi là actor nên nắm workflow thật | "Chính xác theo danh mục" đến mức nào là đủ để ra quyết định cắt chi |
| 3 | #5 — Khó tìm tài liệu học phù hợp | Bottleneck rõ; đo được bằng thời gian và số nguồn phải đọc | "Phù hợp" phụ thuộc trình độ từng người nên metric hài lòng còn chủ quan |

Vì sao 5 vấn đề còn lại không vào top 3:

- **#2 Đỗ xe** — cần dữ liệu chỗ trống theo thời gian thực, không có dữ liệu thì không có gì để xử lý.
- **#3 Uống thuốc** và **#6 Deadline** — nhắc theo giờ cố định đã giải gần trọn, Rule là đủ.
- **#7 Chat bị trôi** — phải cho AI đọc toàn bộ lịch sử chat nên vướng quyền riêng tư của cả nhóm.
- **#8 Email** — tôi không phải nhân viên văn phòng nên không nắm workflow thật; quy tắc lọc theo người gửi đã giải phần lớn.

---

### Problem Card #1 — Bệnh nhân chờ khám bệnh quá lâu

**Problem 1 câu:** Bệnh nhân mất 2–3 giờ chờ để gặp bác sĩ trong vài phút, vì tất cả cùng đến vào buổi sáng và không có khung giờ hẹn, trong khi số bác sĩ mỗi ca là cố định.

**Actor:** Bệnh nhân khám ngoại trú, nặng nhất với người ở xa và người cao tuổi.

**Thời điểm:** Buổi sáng các ngày trong tuần, khi lượng bệnh nhân dồn cao nhất.

**Current workflow:**

```text
1. Đến sớm, lấy số thứ tự và đăng ký (không có khung giờ hẹn)
2. Chờ vào tiếp nhận: đo sinh hiệu, khai thông tin
3. Chờ đến lượt vào phòng bác sĩ              <-- nghẽn
4. Bác sĩ hỏi lại thông tin, khám
5. Chỉ định xét nghiệm, chờ lấy mẫu và chờ kết quả
6. Chờ gặp bác sĩ lần hai để đọc kết quả, kê thuốc
```

**Bottleneck:** Bước 3. Bệnh nhân dồn hết vào đầu buổi vì ai cũng muốn lấy số sớm, trong khi công suất bác sĩ mỗi giờ là cố định. Bước 5–6 khiến cùng một bệnh nhân phải xếp hàng hai lượt.

**Impact:** Chờ trung bình 120–180 phút, 30% chờ trên 3 giờ; bệnh nhân phải nghỉ cả buổi làm. Phía bệnh viện thì tải dồn cục đầu buổi rồi vắng cuối buổi.

**Success metric:**

| | Baseline | Target | Cách đo |
|---|---|---|---|
| Thời gian chờ trung bình | 120–180 phút | Dưới 90 phút | Thời gian từ đăng ký đến khi gặp bác sĩ |
| Tỷ lệ chờ quá lâu | 30% chờ trên 3 giờ | Dưới 10% chờ trên 2 giờ | Phân bố thời gian chờ theo lượt khám |
| Khám đúng khung giờ | Không có khung giờ để đối chiếu | Phần lớn lượt khám trong khung đã hẹn | Tỷ lệ gặp bác sĩ trong khung giờ đăng ký |

**Non-AI alternative:** Đặt hẹn online theo khung giờ 30 phút, số thứ tự online, phân luồng khám mới và khám tái, nhắn tin khi gần tới lượt. Đây là thay đổi quy trình và đã giải phần lớn bài toán rải tải.

**AI hypothesis:** Dự báo lượng bệnh nhân theo giờ từ dữ liệu lịch sử để mở đúng số khung hẹn và bố trí bác sĩ theo tải thực tế; chuẩn hoá thông tin bệnh nhân khai trước ở nhà thành bản tóm tắt cho bác sĩ.

**Quick gut:** `[x] Rule` — không rải tải thì thêm AI cũng không làm hàng đợi ngắn lại.

```text
CURRENT STATE — chờ 120-180 phút, 30% chờ trên 3 giờ

[1 Lấy số + đăng ký: 15']
→ [2 Chờ tiếp nhận: 20-40']
→ [3 Chờ đến lượt bác sĩ: 60-120']     <-- bottleneck
→ [4 Bác sĩ hỏi lại + khám: 5-10']
→ [5 Chờ xét nghiệm và kết quả: 30-60']
→ [6 Chờ gặp bác sĩ lần hai: 20-40']   <-- xếp hàng lần thứ hai

FUTURE STATE — chờ dưới 90 phút, dưới 10% chờ trên 2 giờ

[1 Đặt hẹn online, chọn khung giờ 30': 2']        -- Rule: rải tải theo giờ
→ [2 Khai triệu chứng trước tại nhà: 5']          -- Form cố định, AI chuẩn hoá
→ [3 Đến trước hẹn 15', tiếp nhận: 10']
→ [4 Gặp bác sĩ trong khung đã hẹn: chờ dưới 30'] <-- mục tiêu chính
→ [5 Xét nghiệm, nhận kết quả qua app]
→ [6 Đọc kết quả theo lịch hẹn lại, không xếp hàng lần hai]

Số khung hẹn mỗi giờ tính từ dự báo tải:
[Dữ liệu lượt khám lịch sử] → [AI dự báo theo giờ] → [Bệnh viện chốt số khung + số bác sĩ]

Boundary:
- AI KHÔNG chẩn đoán, KHÔNG xếp ưu tiên theo mức độ nặng — đó là quyết định y khoa,
  do điều dưỡng và bác sĩ xác nhận.
- AI chỉ chuẩn hoá thông tin bệnh nhân tự khai, không thêm thông tin bệnh nhân không nói.

Fallback:
- Giữ quầy lấy số tại chỗ và một phần suất khám cho người không đặt hẹn online,
  để cải tiến không đẩy người cao tuổi ra ngoài. Bệnh nhân cấp cứu không qua hàng đợi hẹn.
- Dự báo sai → số khung hẹn vẫn có giới hạn trên theo số bác sĩ thực tế trong ca.
```

---

### Problem Card #2 — Khó khăn trong quản lý chi tiêu cá nhân

**Problem 1 câu:** Tiền tiêu rải rác qua tiền mặt, chuyển khoản và ví điện tử nhưng chỉ khoảng 30% khoản chi được ghi nhận, nên cuối tháng không xác định được khoản chi lớn nằm ở đâu.

**Actor:** Người đi làm và sinh viên tự quản lý tiền của mình.

**Thời điểm:** Lúc vừa tiêu tiền (đang ở ngoài nên không ghi) và cuối tháng (muốn biết đã tiêu vào đâu nhưng dữ liệu đã thiếu).

**Current workflow:**

```text
1. Tiêu tiền (tiền mặt / chuyển khoản / ví điện tử)
2. Định ghi lại nhưng đang ở ngoài nên bỏ qua   <-- nghẽn
3. Cuối tháng mở lịch sử giao dịch từng ứng dụng
4. Tự nhớ và tự phân loại từng giao dịch vào danh mục
5. Nhìn con số cuối cùng nhưng không tin, vì tiền mặt đã mất dấu
```

**Bottleneck:** Bước 2 — thời điểm nhập liệu. Nghẽn không nằm ở tính toán mà ở chỗ dữ liệu không bao giờ được ghi đủ. Bước 4 tốn công nhưng chỉ là hệ quả: phân loại kỹ trên 30% dữ liệu thì kết quả vẫn không dùng được.

**Impact:** Không xác định được khoản chi lớn nên không có căn cứ cắt khoản nào, tháng sau lặp lại y hệt.

**Success metric:**

| | Baseline | Target | Cách đo |
|---|---|---|---|
| Tỷ lệ khoản chi được ghi nhận | Khoảng 30% | Trên 90% giao dịch | Đối chiếu số đã ghi với biến động số dư tài khoản và ví |
| Chính xác theo danh mục | Cuối tháng khó xác định khoản chi lớn | Báo cáo chính xác theo từng danh mục | Rà từng danh mục cuối tháng, đếm giao dịch xếp sai |
| Giữ ngân sách đã đặt | Chưa theo dõi được | Số tháng chi trong ngân sách tăng dần | Đếm số tháng chi thực tế không vượt ngân sách |

**Non-AI alternative:** App tự đồng bộ giao dịch ngân hàng và ví, kèm 5 danh mục cố định phân loại bằng quy tắc theo tên người nhận. Phần còn lại chỉ là tiền mặt và các tên giao dịch không rõ nghĩa.

**AI hypothesis:** AI đọc nội dung giao dịch không rõ nghĩa và đề xuất danh mục; cho phép ghi tiền mặt bằng một câu tự nhiên thay vì mở form, tức giảm ma sát đúng ở bước 2.

**Quick gut:** `[x] Workflow` — phần lấy dữ liệu là rule, AI chỉ vào 2 bước hẹp, người xác nhận cuối.

```text
CURRENT STATE — ~50 phút/tháng, chỉ 30% khoản chi được ghi nhận

[1 Tiêu tiền]
→ [2 Định ghi lại nhưng bỏ qua: 0']   <-- bottleneck: dữ liệu thất thoát tại đây
→ [3 Mở lịch sử từng app: 15']
→ [4 Tự nhớ + tự phân loại: 30']
→ [5 Xem kết quả nhưng không tin: 5']

FUTURE STATE — dưới 15 phút/tháng, trên 90% giao dịch được ghi nhận

[1 Tiêu tiền]
→ [2a Chuyển khoản/ví: tự đồng bộ: 0']        -- Rule/app, không cần AI
→ [2b Tiền mặt: nhập 1 câu ngắn: 10"/lần]     -- AI hiểu câu tự nhiên
→ [3 AI gợi ý danh mục cho giao dịch lạ tên]  -- AI, độ mơ hồ thấp
→ [4 Người dùng xác nhận / sửa danh mục: 10'] <-- human boundary
→ [5 Xem báo cáo, so với ngân sách: 3']

Boundary:
- AI chỉ gợi ý phân loại, không sửa số tiền, không tự thêm giao dịch không được nhập.
- Danh mục AI gán phải hiện ra để người dùng xác nhận trước khi vào báo cáo.
- AI không đưa lời khuyên tài chính (đầu tư, vay nợ).

Fallback:
- Gán sai danh mục → sửa ở bước 4, số tiền gốc không đổi nên không mất dữ liệu.
- Phải sửa quá nửa số giao dịch → bỏ gợi ý AI, quay về 5 danh mục cố định (mức Rule).
```

---

### Problem Card #3 — Khó tìm tài liệu học phù hợp

**Problem 1 câu:** Khi bắt đầu chủ đề mới, sinh viên mất 2–3 giờ mở nhiều nguồn chỉ để đánh giá tài liệu nào phù hợp trình độ và mục tiêu của mình, tức mất hàng giờ trước khi thật sự bắt đầu học.

**Actor:** Sinh viên tự học một chủ đề mới ngoài giáo trình.

**Thời điểm:** Lúc mới nhận chủ đề mới hoặc trước kỳ thi, khi chưa biết bắt đầu từ đâu.

**Current workflow:**

```text
1. Có chủ đề mới, chưa biết bắt đầu từ nguồn nào
2. Search Google, YouTube, diễn đàn; mở hàng loạt tab
3. Mở từng nguồn, đọc lướt để đánh giá đúng phạm vi và trình độ chưa   <-- nghẽn
4. Bỏ phần lớn, giữ lại vài nguồn
5. Học, giữa đường thấy nguồn quá nông hoặc quá sâu → quay lại bước 2
```

**Bottleneck:** Bước 3. Tài liệu thì quá nhiều, cái khó là phải đọc một lúc mới biết có phù hợp không — vì tiêu chí phù hợp phụ thuộc trình độ hiện tại của người học, mà tiêu đề và mô tả không nói điều đó.

**Impact:** 2–3 giờ cho mỗi chủ đề mới trước khi học thật. Nặng hơn là vòng lặp ở bước 5: học nửa đường mới biết chọn sai nguồn, phải tìm lại từ đầu, và đó là lúc mất động lực và dễ bỏ chủ đề.

**Success metric:**

| | Baseline | Target | Cách đo |
|---|---|---|---|
| Thời gian tìm và đánh giá tài liệu | 2–3 giờ | Dưới 30 phút | Bấm giờ từ lúc bắt đầu tìm đến khi chốt bộ tài liệu |
| Số nguồn phải mở trước khi học | Mở nhiều nguồn rồi bỏ phần lớn | Chỉ giữ nguồn thật sự dùng | Đếm số nguồn tham khảo trước khi bắt đầu học |
| Mức độ hài lòng của người học | Thường phải quay lại tìm giữa đường | Không phải quay lại bước tìm kiếm | Tự chấm 1–5 sau mỗi chủ đề, kèm số lần đổi nguồn giữa đường |

**Non-AI alternative:** Dùng lộ trình đã được người khác sàng lọc: roadmap công khai, giáo trình môn học, danh sách tài liệu tổng hợp theo chủ đề, hoặc hỏi người đã học qua. Tốt với chủ đề phổ biến, không có sẵn với chủ đề hẹp.

**AI hypothesis:** Người học mô tả trình độ hiện tại, mục tiêu và thời gian có; AI đề xuất thứ tự học và với mỗi nguồn ghi rõ dành cho ai, phạm vi gì, cần biết trước gì. Người học mở link kiểm rồi tự chốt.

**Quick gut:** `[x] Workflow` — AI hỗ trợ đúng bước đánh giá, người học vẫn kiểm nguồn và tự quyết lộ trình.

```text
CURRENT STATE — 2-3 giờ trước khi bắt đầu học

[1 Nhận chủ đề mới]
→ [2 Search nhiều nơi, mở hàng loạt tab: 30']
→ [3 Đọc lướt từng nguồn để đánh giá: 60-120']   <-- bottleneck
→ [4 Bỏ phần lớn, giữ vài nguồn: 15']
→ [5 Học, thấy sai trình độ → quay lại bước 2]   <-- vòng lặp gây mất động lực

FUTURE STATE — dưới 30 phút trước khi bắt đầu học

[1 Mô tả trình độ + mục tiêu + thời gian có: 5']   -- Người, đầu vào quyết định
→ [2 AI đề xuất thứ tự học + 3-5 nguồn, mỗi nguồn
      ghi rõ dành cho ai, phạm vi gì: 3']          -- AI, đúng bước nghẽn
→ [3 Người mở từng link, kiểm nguồn có thật: 10']  <-- human boundary
→ [4 Chốt bộ tài liệu và bắt đầu học: 5']
→ [5 Học 30' thấy sai trình độ → mô tả lại và hỏi lại, không tìm lại từ đầu]

Boundary:
- AI chỉ đề xuất nguồn kèm link mở được; nguồn không kiểm được thì bỏ.
- AI không quyết lộ trình cuối và không dùng để học thay — phần đọc, hiểu vẫn là của người học.
- Môn có giáo trình chính thức thì giáo trình là nguồn chuẩn, AI chỉ bổ trợ.

Fallback:
- AI đưa link không tồn tại hoặc nguồn lệch nội dung → bước 3 phát hiện được,
  vì bắt buộc mở kiểm từng link trước khi chốt.
- AI đề xuất lệch trình độ → quay về roadmap công khai hoặc giáo trình môn học.
```

---

## Card muốn pitch nhất

**Card #3 — Khó tìm tài liệu học phù hợp.**

Vì sao:

- Actor là chính tôi và các bạn cùng lớp, nên kiểm chứng được ngay trong buổi lab.
- Bottleneck cụ thể ở bước 3, và baseline → target đều đo được: 2–3 giờ xuống dưới 30 phút.
- So sánh được đủ 4 mức: roadmap có sẵn (No AI) → quy tắc chọn nguồn (Rule) → AI đề xuất có trích nguồn kèm người kiểm link (Workflow) → agent tự tìm và học thay (không cần, sai mục đích).
- Rủi ro nhìn thấy rõ và chặn được: AI đưa nguồn không tồn tại, bước kiểm link của người học bắt được.

Card #1 có impact lớn nhất nhưng phụ thuộc dữ liệu lượt khám và quyền đổi quy trình của bệnh viện; nếu nhóm không tiếp cận được thì cả buổi chỉ là suy diễn. Card #2 metric chắc nhất nhưng actor chỉ là cá nhân.

Câu hỏi muốn nhóm phản biện:

1. "Phù hợp" nên định nghĩa bằng gì để đo được? Mức độ hài lòng tự chấm quá chủ quan — có nên đổi sang số lần phải đổi nguồn giữa đường?
2. Bottleneck thật là "đánh giá tài liệu mất thời gian", hay "chưa biết mình đang ở trình độ nào nên không biết cần gì"? Nếu là cái thứ hai thì AI đề xuất tài liệu không giải được gì.
3. Nếu nhóm muốn chọn Card #1 vì impact lớn hơn, nhóm lấy dữ liệu lượt khám theo giờ từ đâu?
