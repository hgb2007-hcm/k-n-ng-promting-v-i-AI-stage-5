Phần 1: Sơ đồ chuỗi Prompt & Hệ thống Prompt Chaining
1. Sơ đồ mô tả luồng dữ liệu chuỗi Prompt (Prompt Chaining)
[DỮ LIỆU GỐC KHÓA HỌC]
(Python cơ bản | SV năm nhất 18–20 tuổi | 8 tuần | Mục tiêu: 100 đăng ký tư vấn | FB & TikTok)
         │
         ▼
┌─────────────────────────────────────────────────────────┐
│ PROMPT 1: Phân tích Chân dung Khách hàng Mục tiêu       │
└────────┬────────────────────────────────────────────────┘
         │ Xuất biến: {{OUTPUT_1_PERSONA}}
         ▼
┌─────────────────────────────────────────────────────────┐
│ PROMPT 2: Xác định Thông điệp Truyền thông Chính        │
│ (Đầu vào: Dữ liệu gốc + {{OUTPUT_1_PERSONA}})            │
└────────┬────────────────────────────────────────────────┘
         │ Xuất biến: {{OUTPUT_2_KEY_MESSAGE}}
         ▼
┌─────────────────────────────────────────────────────────┐
│ PROMPT 3: Lập Kế hoạch Nội dung 7 Ngày (FB & TikTok)    │
│ (Đầu vào: Dữ liệu gốc + {{OUTPUT_1}} + {{OUTPUT_2}})    │
└────────┬────────────────────────────────────────────────┘
         │ Xuất biến: {{OUTPUT_3_CONTENT_PLAN}}
         ▼
┌─────────────────────────────────────────────────────────┐
│ PROMPT 4: Sáng tạo Bài đăng Facebook & Kịch bản TikTok  │
│ (Đầu vào: Dữ liệu gốc + {{OUTPUT_1}} + {{OUTPUT_2}}     │
│           + {{OUTPUT_3_CONTENT_PLAN}})                  │
└────────┬────────────────────────────────────────────────┘
         │ Xuất biến: {{OUTPUT_4_CREATIVES}}
         ▼
┌─────────────────────────────────────────────────────────┐
│ PROMPT 5: Kiểm định Tính Nhất quán Toàn Chiến dịch      │
│ (Đầu vào: Toàn bộ dữ liệu gốc + {{OUTPUT_1}} đến {{4}}) │
└────────┬────────────────────────────────────────────────┘
         ▼
[BÁO CÁO KIỂM ĐỊNH & BỘ TÀI NGUYÊN CHIẾN DỊCH HOÀN CHỈNH]


2. Bộ 5 Prompt liên tiếp (Sử dụng biến truyền dữ liệu)
Prompt 1: Phân tích chân dung khách hàng mục tiêu
# VAI TRÒ
Bạn là Chuyên gia Nghiên cứu Thị trường & Chiến lược Marketing Giáo dục.

# DỮ LIỆU KHÓA HỌC GỐC (CỐ ĐỊNH - KHÔNG ĐƯỢC THAY ĐỔI)
- Khóa học: Python cơ bản dành cho người mới bắt đầu.
- Đối tượng mục tiêu: Sinh viên năm nhất, độ tuổi 18–20.
- Thời lượng đào tạo: 8 tuần.
- Mục tiêu chiến dịch: Thu hút 100 lượt đăng ký tư vấn.
- Kênh triển khai: Facebook và TikTok.

# NHIỆM VỤ
Phân tích chi tiết Chân dung khách hàng mục tiêu (Target Persona) cho chiến dịch tuyển sinh trên. Trình bày rõ ràng 4 khía cạnh:
1. Nhân khẩu học & Bối cảnh hiện tại (tâm lý chuyển cấp từ THPT lên Đại học).
2. Nỗi đau (Pain points) và rào cản khi tiếp cận lập trình.
3. Mong muốn & Động lực học tập (kỳ vọng sau 8 tuần).
4. Hành vi tiêu thụ nội dung trên Facebook và TikTok của nhóm 18–20 tuổi.

# RÀNG BUỘC
- Tuyệt đối không thay đổi độ tuổi (18–20), đối tượng (sinh viên năm nhất) hay thời lượng (8 tuần).
- Định dạng đầu ra rõ ràng theo từng mục để làm đầu vào cho bước tiếp theo.


Prompt 2: Xác định thông điệp truyền thông chính
# VAI TRÒ
Bạn là Giám đốc Sáng tạo (Creative Director) chuyên mảng EdTech.

# DỮ LIỆU ĐẦU VÀO
1. Thông tin khóa học gốc: Khóa Python cơ bản cho người mới bắt đầu | Sinh viên năm nhất (18–20 tuổi) | Thời lượng 8 tuần | Mục tiêu: 100 lượt đăng ký tư vấn | Kênh: Facebook & TikTok.
2. Chân dung khách hàng mục tiêu từ bước trước:
{{OUTPUT_1_PERSONA}}

# NHIỆM VỤ
Từ những nỗi đau và mong muốn trong {{OUTPUT_1_PERSONA}}, hãy xây dựng:
1. Một (01) Thông điệp truyền thông chính (Key Message) ngắn gọn, dễ nhớ, đánh trúng tâm lý sinh viên năm nhất và nêu bật được lộ trình 8 tuần dành cho người mới bắt đầu.
2. Ba (03) thông điệp bổ trợ (Supporting Pillars) làm cơ sở triển khai nội dung kêu gọi đăng ký tư vấn.

# RÀNG BUỘC
- Thông điệp phải phục vụ trực tiếp mục tiêu chuyển đổi 100 lượt đăng ký tư vấn.
- Không cam kết sai lệch thông tin khóa học (chỉ dừng ở mức Python cơ bản trong 8 tuần).


Prompt 3: Xây dựng kế hoạch nội dung trong 7 ngày
# VAI TRÒ
Bạn là Trưởng nhóm Content Marketing đa kênh (Facebook & TikTok).

# DỮ LIỆU ĐẦU VÀO
1. Thông tin khóa học gốc: Khóa Python cơ bản cho người mới bắt đầu | SV năm nhất (18–20 tuổi) | 8 tuần | Mục tiêu: 100 lượt đăng ký tư vấn.
2. Chân dung khách hàng mục tiêu: {{OUTPUT_1_PERSONA}}
3. Thông điệp truyền thông chính: {{OUTPUT_2_KEY_MESSAGE}}

# NHIỆM VỤ
Xây dựng lịch đăng nội dung chi tiết trong 7 ngày liên tiếp trên 2 kênh Facebook và TikTok theo mô hình phễu chuyển đổi (Nhận biết -> Quan tâm -> Khao khát -> Hành động) để đạt mục tiêu 100 lượt đăng ký tư vấn.
Trình bày dưới dạng bảng gồm các cột: Ngày | Giai đoạn phễu | Kênh (FB/TikTok) | Định dạng | Chủ đề & Ý tưởng chính | Mục tiêu & Kêu gọi hành động (CTA).

# RÀNG BUỘC
- Mọi chủ đề phải bám sát {{OUTPUT_2_KEY_MESSAGE}} và giải quyết đúng nỗi đau trong {{OUTPUT_1_PERSONA}}.
- Đảm bảo phân bổ hợp lý cả 2 kênh Facebook và TikTok trong tuần.


Prompt 4: Viết bài quảng cáo Facebook và kịch bản video TikTok
# VAI TRÒ
Bạn là Copywriter & TikTok Scriptwriter chuyên viết nội dung chuyển đổi cho đối tượng Gen Z (18–20 tuổi).

# DỮ LIỆU ĐẦU VÀO
1. Thông tin khóa học gốc: Python cơ bản cho người mới bắt đầu | SV năm nhất (18–20 tuổi) | 8 tuần | Mục tiêu: 100 lượt đăng ký tư vấn.
2. Chân dung khách hàng: {{OUTPUT_1_PERSONA}}
3. Thông điệp truyền thông chính: {{OUTPUT_2_KEY_MESSAGE}}
4. Kế hoạch nội dung 7 ngày: {{OUTPUT_3_CONTENT_PLAN}}

# NHIỆM VỤ
Dựa trên kế hoạch ở {{OUTPUT_3_CONTENT_PLAN}}, hãy sản xuất chi tiết 4 nội dung sau:
1. Hai (02) bài đăng Facebook (1 bài chia sẻ giá trị/gỡ rào cản tâm lý cho người mới; 1 bài quảng cáo chuyển đổi trực tiếp). Cấu trúc gồm: Hook thu hút, Thân bài thuyết phục, CTA rõ ràng.
2. Hai (02) kịch bản video TikTok có thời lượng chuẩn 30–45 giây (1 kịch bản đánh vào nỗi đau/bắt trend; 1 kịch bản giới thiệu giá trị lộ trình 8 tuần). Trình bày dạng bảng gồm: Phân cảnh & Thời lượng (giây) | Hình ảnh & Diễn xuất | Lời thoại & Text trên màn hình.

# RÀNG BUỘC
- Văn phong tự nhiên, gần gũi với sinh viên năm nhất (18–20 tuổi), không dùng từ ngữ quá hàn lâm gây sợ hãi.
- Bắt buộc nhắc chính xác thời lượng "8 tuần", đối tượng "người mới bắt đầu/sinh viên năm nhất" và CTA "đăng ký tư vấn".


Prompt 5: Kiểm tra tính thống nhất của toàn bộ chiến dịch
# VAI TRÒ
Bạn là Chuyên gia Kiểm định Chất lượng Marketing (Marketing QA Auditor).

# DỮ LIỆU ĐẦU VÀO
1. Thông số gốc bắt buộc: Khóa Python cơ bản cho người mới bắt đầu | Đối tượng: SV năm nhất (18–20 tuổi) | Thời lượng: 8 tuần | Mục tiêu: 100 lượt đăng ký tư vấn | Kênh: Facebook & TikTok.
2. Chân dung khách hàng: {{OUTPUT_1_PERSONA}}
3. Thông điệp chính: {{OUTPUT_2_KEY_MESSAGE}}
4. Kế hoạch 7 ngày: {{OUTPUT_3_CONTENT_PLAN}}
5. Bộ nội dung FB & TikTok: {{OUTPUT_4_CREATIVES}}

# NHIỆM VỤ
Thực hiện rà soát chéo toàn bộ chuỗi đầu ra từ Bước 1 đến Bước 4 và lập Báo cáo kiểm tra tính nhất quán theo 5 tiêu chí:
1. Độ chính xác thông số khóa học (có bị sai lệch độ tuổi, thời lượng 8 tuần hay cấp độ cơ bản không?).
2. Sự liên kết giữa Chân dung khách hàng -> Thông điệp -> Nội dung chi tiết.
3. Tính nhất quán của Thông điệp chính xuyên suốt 7 ngày và trên cả 2 kênh.
4. Mức độ hướng tới mục tiêu chuyển đổi 100 lượt đăng ký tư vấn (CTA có rõ ràng, đồng bộ không?).
5. Đề xuất điểm cần tinh chỉnh trước khi chạy chiến dịch thực tế.


Phần 2: Kết quả thực thi mẫu theo chuỗi Prompt
1. Chân dung khách hàng mục tiêu (Đầu ra Prompt 1)
Nhân khẩu học & Bối cảnh: Sinh viên năm nhất (18–20 tuổi), vừa chuyển từ môi trường phổ thông lên đại học. Sống tại ký túc xá hoặc nhà trọ, thời gian biểu tự do hơn nhưng dễ bị choáng ngợp bởi khối lượng môn học mới; ngân sách học tập thường cần tham khảo ý kiến gia đình hoặc trích từ tiền sinh hoạt.

Nỗi đau (Pain points) & Rào cản:

Sợ "mất gốc" ngay từ đầu: Chưa từng viết dòng code nào ở cấp 3 nên lo lắng không theo kịp các môn tin học/nhập môn lập trình trên giảng đường.

Mông lung định hướng: Không biết nên bắt đầu từ ngôn ngữ lập trình nào giữa quá nhiều thông tin trên mạng.

Ngại lộ trình dài dòng, nặng lý thuyết: Sợ các khóa học kéo dài nhiều tháng gây quá tải với lịch học ở trường.

Mong muốn & Động lực:

Nắm chắc tư duy lập trình cơ bản từ con số 0 trong thời gian ngắn gọn (8 tuần) để tự tin học tốt các môn trên trường.

Có sản phẩm thực hành nhỏ (mini-project) để thấy mình thực sự làm được việc, tạo động lực theo đuổi ngành.

Được tư vấn rõ ràng lộ trình trước khi quyết định đăng ký học.

Hành vi trên Facebook & TikTok:

TikTok: Xem video ngắn 30–45 giây với nhịp độ nhanh, thích nội dung góc nhìn thứ nhất (POV), hài hước hoặc chia sẻ mẹo học tập thực tế cho sinh viên; dễ lướt qua nếu mở đầu khô khan.

Facebook: Thường xuyên tương tác trong các hội nhóm tân sinh viên, thích đọc bài chia sẻ lộ trình bài bản, lưu bài viết hữu ích và nhắn tin trực tiếp qua Messenger để hỏi chi tiết học phí, lịch học.

2. Một thông điệp truyền thông chính (Đầu ra Prompt 2)
Thông điệp chính (Key Message): "8 tuần làm chủ Python từ con số 0 – Xóa nỗi lo mất gốc lập trình cho sinh viên năm nhất."

Ba trụ cột thông điệp bổ trợ:

Chuẩn hóa cho người mới (18–20 tuổi): Thiết kế riêng cho sinh viên năm nhất chưa từng biết code, đi từ tư duy nền tảng dễ hiểu nhất.
Lộ trình tinh gọn 8 tuần: Vừa vặn trong 2 tháng, không gây áp lực lên lịch học đại học nhưng vẫn đủ thời gian thực hành thành thạo các bài toán cơ bản.
Tư vấn lộ trình cá nhân hóa 1-1: Hỗ trợ giải đáp mọi thắc mắc về định hướng học lập trình cho tân sinh viên trước khi nhập học.
3. Lịch đăng nội dung trong 7 ngày (Đầu ra Prompt 3)
Ngày	Giai đoạn phễu	Kênh	Định dạng	Chủ đề & Ý tưởng chính	Mục tiêu & Kêu gọi hành động (CTA)
Ngày 1	Nhận biết (Awareness)	TikTok	Video ngắn (35s)	POV tân sinh viên lần đầu mở màn hình code: Bắt trend nỗi sợ "mất gốc" lập trình năm nhất và giới thiệu lối đi dễ thở với Python.	Thu hút lượt xem & tương tác; CTA bình luận nhận tài liệu làm quen Python.
Ngày 2	Nhận biết (Awareness)	Facebook	Bài viết kèm bộ ảnh (Carousel)	"Bản đồ sinh tồn cho sinh viên 18–20 tuổi: Tại sao Python là ngôn ngữ dễ bắt đầu nhất từ con số 0?"	Tăng lượt lưu (Save) và chia sẻ; CTA inbox fanpage để được tư vấn lộ trình.
Ngày 3	Quan tâm (Interest)	TikTok	Video ngắn (40s)	"8 tuần học Python cơ bản từ số 0 thì sinh viên năm nhất làm được gì?" (Trình chiếu 3 bài tập/ứng dụng nhỏ trực quan).	Chứng minh hiệu quả thực tế của khóa 8 tuần; CTA bấm link bio đăng ký tư vấn.
Ngày 4	Quan tâm (Interest)	Facebook	Bài viết gỡ rào cản tâm lý	"Chưa từng viết một dòng code nào ở cấp 3, liệu 18–20 tuổi có theo kịp khóa Python 8 tuần?" (Giải đáp chi tiết phương pháp học).	Xóa bỏ rào cản người mới; CTA để lại thông tin nhận tư vấn 1-1 miễn phí.
Ngày 5	Khao khát (Desire)	Facebook	Bài chia sẻ trải nghiệm thực tế	Hành trình 8 tuần của một sinh viên năm nhất: Từ sợ môn Tin học đại cương đến tự tin viết chương trình Python đầu tiên.	Xây dựng niềm tin (Social Proof); CTA nhắn tin nhận tư vấn lịch học phù hợp.
Ngày 6	Hành động (Action)	TikTok	Video Q&A giải đáp nhanh (35s)	"3 câu hỏi sinh viên năm nhất hay hỏi nhất trước khi học Python 8 tuần" (Học từ đầu được không? Có nặng lịch trường không? Đăng ký thế nào?).	Thúc đẩy quyết định; CTA đăng ký tư vấn ngay qua link trên trang cá nhân.
Ngày 7	Hành động (Action)	Facebook	Bài quảng cáo chuyển đổi trực tiếp	Tổng hợp quyền lợi khóa Python cơ bản 8 tuần dành riêng cho sinh viên năm nhất (18–20 tuổi) – Mở cổng đăng ký tư vấn tuần này.	Chốt chuyển đổi tối đa hướng tới mục tiêu 100 lượt đăng ký tư vấn.
4. Hai bài đăng Facebook & Hai kịch bản video TikTok (Đầu ra Prompt 4)
Bài đăng Facebook 1: Bài chia sẻ giá trị & Gỡ rào cản (Triển khai Ngày 4)
CHƯA TỪNG VIẾT MỘT DÒNG CODE NÀO Ở CẤP 3, SINH VIÊN NĂM NHẤT CÓ THEO KỊP KHÓA PYTHON 8 TUẦN? Bước chân vào giảng đường đại học ở tuổi 18–20, không ít bạn tân sinh viên rơi vào cảm giác "choáng ngợp" khi thấy bạn bè xung quanh đã rành công nghệ, còn mình thì ngay cả khái niệm biến, vòng lặp hay cú pháp lập trình cũng chưa từng nghe qua. Sự thật là: Bạn không cần phải giỏi sẵn mới bắt đầu học lập trình, bạn chỉ cần chọn đúng ngôn ngữ khởi đầu. Với cú pháp gần giống tiếng Anh tự nhiên và dễ đọc, Python luôn là lựa chọn số 1 dành cho người mới bắt đầu. Tại khóa học Python cơ bản 8 tuần, lộ trình được thiết kế đo ni đóng giày cho sinh viên năm nhất:

Tuần 1 – 2: Làm quen tư duy lập trình từ con số 0, cài đặt môi trường và viết những dòng lệnh đầu tiên.
Tuần 3 – 5: Nắm vững cấu trúc điều kiện, vòng lặp, hàm và xử lý dữ liệu cơ bản mà không bị ngợp lý thuyết.
Tuần 6 – 8: Thực hành giải quyết bài toán thực tế và hoàn thiện sản phẩm cá nhân nhỏ đầu tay.
Chỉ gói gọn trong 8 tuần, bạn vừa có nền tảng vững vàng để tự tin vượt qua các môn nhập môn trên trường, vừa không lo ảnh hưởng đến lịch học chính khóa. 👉 Bạn đang băn khoăn chưa biết bắt đầu từ đâu? Bình luận "TƯ VẤN" bên dưới hoặc nhắn tin trực tiếp cho fanpage để được đội ngũ chuyên môn tư vấn lộ trình học Python 1-1 hoàn toàn miễn phí!

Bài đăng Facebook 2: Bài quảng cáo chuyển đổi trực tiếp (Triển khai Ngày 7)
[DÀNH RIÊNG CHO SINH VIÊN NĂM NHẤT 18–20 TUỔI] 8 TUẦN LÀM CHỦ PYTHON TỪ CON SỐ 0 – XÓA NỖI LO MẤT GỐC LẬP TRÌNH! Đừng để nỗi sợ "chưa biết gì về code" cản bước bạn ngay từ năm nhất đại học! Khóa học Python cơ bản (8 tuần) chính thức mở đợt tư vấn tuyển sinh dành riêng cho các bạn sinh viên độ tuổi 18–20 muốn xây dựng nền tảng lập trình bài bản từ đầu. Vì sao khóa học 8 tuần này phù hợp với bạn? ✅ Dành cho người mới bắt đầu 100%: Giảng dạy cầm tay chỉ việc từ kiến thức nền tảng nhất, không yêu cầu kinh nghiệm trước đó. ✅ Thời lượng tinh gọn 8 tuần: Lộ trình cô đọng, tập trung thực hành trực tiếp trên lớp giúp bạn nắm chắc kiến thức chỉ sau 2 tháng. ✅ Hỗ trợ kèm cặp sát sao: Giải đáp lỗi code (debug) trực tiếp cùng giảng viên và trợ giảng trong suốt quá trình học. ✅ Tư vấn định hướng 1-1 trước khi học: Giúp bạn hiểu rõ mục tiêu và lựa chọn ca học linh hoạt theo lịch giảng đường. 🎯 Trung tâm đang mở 100 suất tư vấn lộ trình học Python miễn phí trong chiến dịch tuần này dành cho các bạn tân sinh viên. 📩 Đăng ký nhận tư vấn ngay hôm nay bằng cách bấm vào nút "Đăng ký ngay" bên dưới hoặc inbox trực tiếp để giữ suất hỗ trợ sớm nhất!

Kịch bản TikTok 1: Bắt trend nỗi đau tân sinh viên (Triển khai Ngày 1 — Thời lượng: 35 giây)
Phân cảnh & Thời lượng	Hình ảnh & Diễn xuất	Lời thoại (Voice-over) & Text trên màn hình
Cảnh 1: Hook (00s – 05s)	Sinh viên năm nhất ngồi trước laptop, mặt hoang mang ôm đầu nhìn màn hình toàn chữ tiếng Anh khó hiểu.	Text: POV: Sinh viên năm nhất lần đầu học lập trình...

Thoại: "18 tuổi lên đại học, tưởng code ngầu như phim ai ngờ mở máy lên toàn lỗi đỏ lòm?" | | Cảnh 2: Nỗi đau (05s – 15s) | Chuyển cảnh nhanh: lật vở ghi chép dày đặc, nhìn bạn bên cạnh gõ code thoăn thoắt. | Text: Chưa từng học code ở cấp 3 = Mất gốc?


Thoại: "Chưa từng viết một dòng code nào ở cấp 3 nên học đâu cũng thấy ngợp, sợ rớt môn ngay từ kỳ đầu?" | | Cảnh 3: Giải pháp (15s – 28s) | Nhân vật mỉm cười, gập cuốn sách dày lại, mở giao diện Python đơn giản và chạy thành công chương trình nhỏ. | Text: Python cơ bản – Lộ trình 8 tuần từ số 0


Thoại: "Bình tĩnh nhé! Bắt đầu bằng Python cơ bản thì người mới hoàn toàn vẫn theo kịp. Chỉ cần 8 tuần đi từ con số 0 là bạn đã nắm chắc tư duy lập trình rồi." | | Cảnh 4: CTA (28s – 35s) | Nhân vật chỉ tay xuống góc bình luận / bio kênh, biểu cảm thân thiện. | Text: Đăng ký tư vấn lộ trình 8 tuần tại Bio!


Thoại: "Sinh viên năm nhất 18 đến 20 tuổi muốn biết lộ trình học chi tiết thì bấm vào link trên bio để đăng ký tư vấn miễn phí ngay nhé!" |

Kịch bản TikTok 2: Giá trị lộ trình 8 tuần (Triển khai Ngày 3 — Thời lượng: 40 giây)
Phân cảnh & Thời lượng	Hình ảnh & Diễn xuất	Lời thoại (Voice-over) & Text trên màn hình
Cảnh 1: Hook (00s – 05s)	Người dẫn đứng trước bảng trắng hoặc màn hình máy tính, giơ 8 ngón tay hướng về camera.	Text: 8 tuần học Python từ số 0 làm được gì?

Thoại: "Nếu bạn là sinh viên năm nhất chưa biết gì về code, thì sau 8 tuần học Python cơ bản bạn sẽ làm được những gì?" | | Cảnh 2: Tuần 1–4 (05s – 18s) | Quay cận màn hình code chạy các bài toán tính điểm trung bình, quản lý chi tiêu đơn giản. | Text: Tuần 1–4: Nắm chắc tư duy & cú pháp


Thoại: "4 tuần đầu, bạn làm chủ toàn bộ cú pháp nền tảng, vòng lặp, hàm và tự viết được các công cụ tính toán tự động siêu tiện cho việc học." | | Cảnh 3: Tuần 5–8 (18s – 32s) | Quay cảnh màn hình chạy một mini-game đơn giản hoặc ứng dụng quản lý dữ liệu nhỏ bằng Python. | Text: Tuần 5–8: Hoàn thiện Mini-Project đầu tay


Thoại: "4 tuần tiếp theo, bạn bắt tay xử lý dữ liệu thực tế và hoàn thiện trọn vẹn một mini-project Python của riêng mình, tự tin cân đẹp các môn nhập môn trên trường." | | Cảnh 4: CTA (32s – 40s) | Người dẫn quay lại khung hình chính, chỉ tay vào nút liên kết tư vấn. | Text: 100 suất tư vấn miễn phí cho SV 18–20 tuổi


Thoại: "Trung tâm đang mở 100 suất tư vấn lộ trình 1-1 cho các bạn 18 đến 20 tuổi. Bấm ngay link ở bio để đăng ký tư vấn hôm nay nhé!" |

5. Báo cáo kiểm tra tính nhất quán (Đầu ra Prompt 5)
Tiêu chí kiểm định	Kết quả đối chiếu giữa các bước	Trạng thái
1. Độ chính xác thông số khóa học	Toàn bộ 4 bước đều giữ nguyên thông số gốc: Khóa Python cơ bản cho người mới bắt đầu, đối tượng sinh viên năm nhất (18–20 tuổi), thời lượng 8 tuần. Không tự ý thêm cam kết việc làm hay nâng cấp thành khóa chuyên sâu.	Đạt (100%)
2. Liên kết Chân dung ➔ Thông điệp ➔ Nội dung	Nỗi đau lớn nhất ở Bước 1 (sợ mất gốc do chưa học code ở cấp 3, ngại lộ trình dài) đã được chuyển hóa trực tiếp thành Key Message ở Bước 2 ("8 tuần làm chủ Python từ con số 0 – Xóa nỗi lo mất gốc...") và thể hiện xuyên suốt trong cả 2 bài Facebook lẫn 2 kịch bản TikTok ở Bước 4.	Đạt (100%)
3. Tính đồng bộ kênh triển khai	Lịch 7 ngày phân bổ cân đối giữa TikTok (Ngày 1, 3, 6 – tập trung thu hút sự chú ý và giải đáp nhanh) và Facebook (Ngày 2, 4, 5, 7 – tập trung cung cấp thông tin chi tiết, bằng chứng xã hội và chốt chuyển đổi).	Đạt (100%)
4. Mức độ bám sát mục tiêu 100 đăng ký tư vấn	Tất cả các điểm chạm từ Ngày 2 đến Ngày 7 đều gắn CTA kêu gọi đăng ký tư vấn (qua inbox Messenger trên Facebook hoặc link bio trên TikTok) thay vì bán khóa học trực tiếp quá sớm, phù hợp với mục tiêu thu hút 100 lượt tư vấn.	Đạt (100%)
5. Điểm cần lưu ý khi triển khai thực tế	Cần gắn mã theo dõi (UTM link / mã chiến dịch riêng) cho từng bài đăng Facebook và link bio TikTok để đo lường chính xác kênh nào đóng góp bao nhiêu trong tổng số 100 lượt đăng ký tư vấn, từ đó dồn ngân sách quảng cáo vào bài có tỷ lệ chuyển đổi tốt nhất từ Ngày 5 đến Ngày 7.	Khuyến nghị bổ sung
