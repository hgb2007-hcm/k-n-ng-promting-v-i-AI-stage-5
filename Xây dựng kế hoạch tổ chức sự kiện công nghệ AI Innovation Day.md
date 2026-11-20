Phần 1: Hệ thống Prompt hoàn chỉnh (Kết hợp CoT + Prompt Chaining + Context Management)
Sơ đồ kiến trúc chuỗi xử lý
[THÔNG SỐ GỐC CỐ ĐỊNH: AI Innovation Day | 150 SV | 1 ngày | ≤ 15.000.000đ | 10 nhân sự]
       │
       ▼
[PROMPT 1: Phân tích Tính khả thi & Rủi ro] ──(Kỹ thuật: Chain-of-Thought)──► {{OUT_1_FEASIBILITY}}
       │
       ▼
[PROMPT 2: Lịch trình 1 ngày & Dự toán Ngân sách] ──(CoT + Chaining)────────► {{OUT_2_SCHEDULE_BUDGET}}
       │
       ▼
[PROMPT 3: Phân công 10 Nhân sự & Truyền thông] ───(Prompt Chaining)────────► {{OUT_3_OPS_COMMS}}
       │
       ▼
[PROMPT 4: Đóng gói Ngữ cảnh Dự án] ───────────────(Context Management)─────► {{CONTEXT_SUMMARY}}
       │
       ═══════════ (CHUYỂN SANG PHIÊN HỘI THOẠI MỚI / NEW CHAT) ═══════════
       │
       ▼
[PROMPT 5: Kiểm định Chéo & Hiệu chỉnh Kế hoạch] ─(CoT + Context Management)► [KẾ HOẠCH HOÀN THIỆN]


Bộ 5 Prompt chi tiết
Prompt 1: Phân tích tính khả thi (Kỹ thuật: Chain-of-Thought)
# VAI TRÒ
Bạn là Chuyên gia Quản lý Sự kiện và Vận hành Dự án Sinh viên.

# DỮ LIỆU ĐẦU VÀO CỐ ĐỊNH
- Tên sự kiện: AI Innovation Day (dành cho sinh viên trong trường).
- Quy mô tham dự: 150 sinh viên.
- Thời lượng: 1 ngày.
- Ngân sách tối đa: 15.000.000 VNĐ.
- Nhân sự tổ chức: 10 người.
- Mục tiêu cốt lõi: Giúp sinh viên hiểu và trực tiếp trải nghiệm ứng dụng AI trong học tập và công việc.

# YÊU CẦU TƯ DUY TỪNG BƯỚC (CHAIN-OF-THOUGHT)
Hãy phân tích tính khả thi của sự kiện tuần tự qua 4 bước sau trước khi đưa ra kết luận:
- Bước 1 (Bài toán Ngân sách bình quân): Chia 15.000.000 VNĐ cho 150 sinh viên để tính định mức chi phí/người. Xác định điều kiện tiên quyết về mặt bằng và công cụ AI để không vượt trần ngân sách.
- Bước 2 (Bài toán Tải trọng Nhân sự): Tính tỷ lệ nhân sự phục vụ trên số lượng sinh viên (10 người / 150 sinh viên) và đánh giá khả năng vận hành tại các điểm nóng (check-in, hướng dẫn thực hành).
- Bước 3 (Tính khả thi của Mục tiêu Trải nghiệm AI): Đánh giá cách thức tổ chức hoạt động thực hành AI trong 1 ngày cho 150 người với hạ tầng trường đại học.
- Bước 4 (Nhận diện Rủi ro & Kết luận): Liệt kê 3 rủi ro lớn nhất và chốt mức độ khả thi kèm điều kiện ràng buộc.


Prompt 2: Xây dựng lịch trình và dự toán ngân sách (Kỹ thuật: Prompt Chaining + CoT)
# VAI TRÒ
Bạn là Trưởng ban Điều phối & Quản lý Tài chính Sự kiện.

# DỮ LIỆU ĐẦU VÀO
1. Ràng buộc cứng: Quy mô 150 SV | Thời gian 1 ngày | Ngân sách TỐI ĐA 15.000.000 VNĐ | 10 nhân sự | Mục tiêu: Hiểu & trải nghiệm AI.
2. Kết quả phân tích khả thi từ Bước 1:
{{OUT_1_FEASIBILITY}}

# NHIỆM VỤ & TƯ DUY TỪNG BƯỚC
- Bước 1 (Thiết kế Lịch trình 1 ngày): Xây dựng lịch trình chi tiết theo khung giờ (Sáng: Hiểu & Khai mở tư duy AI; Chiều: Trải nghiệm thực hành & Thử thách AI). Ghi rõ các mốc thời gian nghỉ trưa (lưu ý phương án ăn trưa phù hợp ngân sách).
- Bước 2 (Lập Dự toán Ngân sách): Lập bảng dự toán chi tiết từng hạng mục (Đơn giá × Số lượng = Thành tiền) tương ứng trực tiếp với các hoạt động trong lịch trình.
- Bước 3 (Tự kiểm tra toán học - CoT): Cộng tổng tất cả các khoản mục từng bước một, đảm bảo tổng cộng + quỹ dự phòng ≤ 15.000.000 VNĐ.


Prompt 3: Phân công 10 nhân sự và kế hoạch truyền thông (Kỹ thuật: Prompt Chaining)
# VAI TRÒ
Bạn là Trưởng ban Nhân sự & Truyền thông Sự kiện.

# DỮ LIỆU ĐẦU VÀO
1. Ràng buộc cứng: Đúng 10 nhân sự | Thu hút đủ 150 sinh viên tham dự thực tế | Ngân sách truyền thông nằm gọn trong mức đã duyệt ở {{OUT_2_SCHEDULE_BUDGET}}.
2. Phân tích khả thi: {{OUT_1_FEASIBILITY}}
3. Lịch trình & Ngân sách: {{OUT_2_SCHEDULE_BUDGET}}

# NHIỆM VỤ
1. Lập bảng phân công nhiệm vụ cụ thể cho đúng 10 nhân sự (đánh mã từ NV01 đến NV10), chia rõ đầu việc "Giai đoạn chuẩn bị" và "Trong ngày sự kiện" khớp với từng khung giờ của {{OUT_2_SCHEDULE_BUDGET}}.
2. Xây dựng kế hoạch truyền thông trước sự kiện (14 ngày) gồm các giai đoạn, kênh triển khai, thông điệp, KPI tiếp cận/đăng ký (tính cả tỷ lệ hao hụt để đảm bảo 150 người đến tham dự thực tế).


Prompt 4: Tạo bản tóm tắt ngữ cảnh dự án (Kỹ thuật: Context Management)
# VAI TRÒ
Bạn là Quản lý Tri thức Dự án (Project Knowledge Manager).

# DỮ LIỆU ĐẦU VÀO
- Phân tích khả thi: {{OUT_1_FEASIBILITY}}
- Lịch trình & Ngân sách: {{OUT_2_SCHEDULE_BUDGET}}
- Nhân sự & Truyền thông: {{OUT_3_OPS_COMMS}}

# NHIỆM VỤ
Hãy nén và cấu trúc lại toàn bộ thông tin quan trọng của dự án "AI Innovation Day" thành một **Bản Tóm Tắt Ngữ Cảnh (Context Snapshot)** chuẩn hóa, súc tích nhưng đầy đủ số liệu để tôi có thể sao chép sang một phiên hội thoại AI mới hoàn toàn mà không bị mất dữ liệu hay sai lệch ràng buộc.
Cấu trúc bắt buộc gồm 5 khối:
1. [FIXED_CONSTRAINTS]: Các thông số bất biến.
2. [BUDGET_STATE]: Chi tiết từng khoản tiền và tổng ngân sách.
3. [SCHEDULE_FLOW]: Các mốc giờ chính và hoạt động cốt lõi.
4. [STAFF_MATRIX]: Danh sách mã NV01–NV10 và vai trò chính.
5. [COMMS_KPI]: Mốc thời gian truyền thông và chỉ tiêu đăng ký.


Prompt 5: Kiểm tra tính thống nhất và hiệu chỉnh trong hội thoại mới (Kỹ thuật: Context Management + CoT)
# NGỮ CẢNH DỰ ÁN (ĐƯỢC NẠP TỪ PHIÊN TRƯỚC)
{{CONTEXT_SUMMARY}}

# VAI TRÒ & NHIỆM VỤ
Bạn là Chuyên gia Kiểm toán Vận hành Độc lập (QA Auditor). Dựa trên bản ngữ cảnh dự án vừa nạp ở trên, hãy rà soát chéo toàn bộ kế hoạch để phát hiện mâu thuẫn, điểm nghẽn vận hành hoặc chi phí ẩn.

# YÊU CẦU TƯ DUY KIỂM ĐỊNH (CHAIN-OF-THOUGHT)
Hãy thực hiện kiểm tra từng bước:
- Bước 1 (Kiểm tra tính nhất quán Ngân sách ↔ Lịch trình/Nhân sự): Có hoạt động nào trong lịch trình hoặc quyền lợi của 10 nhân sự/diễn giả bị thiếu kinh phí trong bảng dự toán không? Tổng tiền có vượt 15.000.000đ không?
- Bước 2 (Kiểm tra điểm nghẽn Nhân sự ↔ Quy mô 150 SV): Tại khung giờ cao điểm (check-in, chia nhóm thực hành AI), 10 nhân sự có bị quá tải hoặc trùng chéo nhiệm vụ không?
- Bước 3 (Kiểm tra Truyền thông ↔ Mục tiêu 150 người): Chỉ tiêu form đăng ký có đủ bù đắp tỷ lệ sinh viên đăng ký nhưng không đến (no-show) không?
- Bước 4 (Đề xuất Hiệu chỉnh): Đưa ra các điều chỉnh cụ thể để khắc phục toàn bộ lỗi phát hiện ở trên mà vẫn giữ nguyên 15.000.000đ, 150 sinh viên và 10 nhân sự.


Phần 2: Kết quả thực thi mẫu toàn bộ kế hoạch
1. Bản phân tích tính khả thi (Kết quả Bước 1 – CoT)
Bước 1 — Phân tích định mức ngân sách: Với tổng ngân sách 15.000.000 VNĐ cho 150 sinh viên, chi phí bình quân tối đa là 100.000 VNĐ/sinh viên (bao gồm cả chi phí vận hành chung, diễn giả, in ấn và hậu cần). Mức ngân sách này khả thi với điều kiện tiên quyết: (a) Tận dụng hội trường/phòng máy của trường miễn phí mặt bằng; (b) Không bao cấp ăn trưa cho 150 sinh viên; (c) Sử dụng các công cụ AI phiên bản miễn phí/gói giáo dục (Gemini, ChatGPT Free, NotebookLM, Canva, Gamma) để không tốn phí bản quyền phần mềm.
Bước 2 — Phân tích tải trọng nhân sự: Tỷ lệ phục vụ là 1 nhân sự / 15 sinh viên (10 người / 150 người). Tỷ lệ này khả thi nếu áp dụng quy trình tự động hóa (check-in bằng mã QR, tài liệu hướng dẫn thực hành dạng số) và phân bổ nhân sự linh hoạt theo khung giờ thay vì chia cứng nhân sự ngồi cố định tại các bàn trống.
Bước 3 — Phân tích khả thi mục tiêu "Hiểu & Trải nghiệm AI": Hoàn toàn khả thi trong 1 ngày bằng cách chia cấu trúc chương trình thành 2 nửa: Buổi sáng cung cấp tư duy nền tảng và demo trực quan (giúp sinh viên hiểu); Buổi chiều chia thành các trạm thực hành ứng dụng AI giải quyết bài toán thật như tóm tắt giáo trình, làm slide, viết CV, hỗ trợ lập trình (giúp sinh viên trải nghiệm).
Bước 4 — Rủi ro trọng yếu & Kết luận:
Rủi ro 1: Nghẽn mạng Wi-Fi hội trường khi 150 thiết bị cùng truy cập các công cụ AI vào buổi chiều.
Rủi ro 2: Ùn tắc tại bàn check-in đầu giờ sáng nếu chỉ bố trí 1–2 người kiểm tra thủ công.
Rủi ro 3: Tỷ lệ sinh viên đăng ký ảo (no-show) khiến số người tham dự thực tế thấp hơn 150.
Kết luận: Sự kiện KHẢ THI nếu kiểm soát chặt chi phí hậu cần và tối ưu quy trình điều phối 10 nhân sự.
2. Lịch trình sự kiện theo khung giờ (1 ngày)
Khung giờ	Hoạt động chính	Nội dung chi tiết & Mục tiêu trải nghiệm
07:30 – 08:15	Đón khách & Check-in	Quét mã QR điểm danh, phát thẻ tham dự & bộ tài liệu số (Prompt Kit). Trải nghiệm góc check-in tạo ảnh chân dung bằng AI.
08:15 – 08:30	Khai mạc chương trình	Tuyên bố lý do, giới thiệu Ban tổ chức, diễn giả và thể lệ thử thách "AI Challenge" cuối ngày.
08:30 – 09:45	Keynote 1: AI trong Học tập & Nghiên cứu	Diễn giả hướng dẫn phương pháp dùng AI (NotebookLM, Gemini) để đọc tài liệu, hệ thống kiến thức, học ngoại ngữ và tránh đạo văn.
09:45 – 10:15	Teabreak & Networking	Nghỉ giải lao nhẹ, giao lưu trực tiếp cùng diễn giả và tham quan khu vực trưng bày sản phẩm AI của CLB.
10:15 – 11:30	Keynote 2 & Panel: AI trong Công việc & Tuyển dụng	Chia sẻ thực tế cách doanh nghiệp ứng dụng AI; demo quy trình dùng AI tối ưu CV, luyện phỏng vấn và tự động hóa tác vụ văn phòng.
11:30 – 13:30	Nghỉ trưa tự túc	Sinh viên nghỉ trưa tự túc ngoài khuôn viên hội trường (BTC phát nhạc nhẹ tại sảnh cho các bạn ở lại nghỉ ngơi).
13:30 – 15:15	Hands-on Lab: 3 Trạm Trải nghiệm Thực hành AI	Sinh viên mang laptop/điện thoại thực hành theo 3 chủ đề xoay vòng: (1) AI làm Slide & Thiết kế; (2) AI phân tích dữ liệu & Excel; (3) AI hỗ trợ Code & Tự động hóa.
15:15 – 16:30	Mini-Hackathon: "AI Prompt Battle"	Thi đấu giải quyết 1 tình huống thực tế (học tập/công việc) bằng AI trong 45 phút theo nhóm nhỏ; chấm điểm trực tiếp trên sân khấu.
16:30 – 17:00	Trao giải, Tổng kết & Bế mạc	Trao giải thưởng Mini-Hackathon, cảm ơn diễn giả, quét mã nhận Giấy chứng nhận điện tử (E-Certificate) và chụp ảnh lưu niệm.
3. Bảng dự toán ngân sách (Khớp trần 15.000.000 VNĐ)
STT	Hạng mục chi phí	Diễn giải chi tiết (Đơn giá × Số lượng)	Thành tiền (VNĐ)	Tỷ trọng
1	Địa điểm & Kỹ thuật hội trường	Hội trường trường miễn phí; chi phí bồi dưỡng kỹ thuật viên âm thanh/ánh sáng & vệ sinh hội trường	1.000.000	6,7%
2	In ấn & Nhận diện sự kiện	Backdrop sân khấu (1.000.000đ) + 2 Standee (400.000đ) + 160 thẻ đeo & dây đeo (800.000đ) + Hashtag cầm tay (300.000đ)	2.500.000	16,7%
3	Diễn giả & Giải thưởng	Quà cảm ơn 3 diễn giả/mentor (3 × 800.000đ = 2.400.000đ) + Giải thưởng Mini-Hackathon (Nhất 1.000k, Nhì 600k, Ba 500k = 2.100.000đ)	4.500.000	30,0%
4	Teabreak & Nước uống	Bánh ngọt & trái cây teabreak cho 165 người (150 SV + 10 BTC + 5 khách mời × 22.000đ = 3.630.000đ) + Nước suối chai & ly giấy (870.000đ)	4.500.000	30,0%
5	Truyền thông & Hạ tầng mạng	Thuê 2 bộ phát Wi-Fi 4G/5G công suất cao dự phòng cho buổi chiều (600.000đ) + In poster dán bảng tin & văn phòng phẩm (400.000đ)	1.000.000	6,7%
6	Quỹ dự phòng phát sinh	Dự phòng 10% tổng ngân sách cho các phát sinh ngoài dự kiến	1.500.000	10,0%
TỔNG CỘNG	Đảm bảo không vượt trần ngân sách 15.000.000 VNĐ	15.000.000	100%
4. Bảng phân công 10 nhân sự
Mã NV	Vai trò	Nhiệm vụ giai đoạn chuẩn bị (Trước sự kiện)	Nhiệm vụ trong ngày sự kiện (07:00 – 17:30)
NV01	Trưởng BTC (PM)	Lập kế hoạch tổng thể, xin phép hội trường, điều phối tiến độ chung giữa các nhóm.	Giám sát toàn bộ vận hành, xử lý sự cố phát sinh và điều tiết ngân sách dự phòng.
NV02	Điều phối Sân khấu & MC	Viết kịch bản dẫn chương trình (MC script), chạy thử timeline với diễn giả.	Dẫn dắt chương trình, kiểm soát thời lượng (timekeeper) từng phiên sáng và chiều.
NV03	Trưởng ban Đối ngoại	Mời 3 diễn giả/mentor, thu thập slide bài giảng, chuẩn bị quà cảm ơn & thư mời.	Đón tiếp, chăm sóc diễn giả suốt chương trình và hỗ trợ chấm điểm Mini-Hackathon.
NV04	Trưởng ban Truyền thông	Lập kế hoạch truyền thông 14 ngày, quản lý form đăng ký, điều phối seeding.	Chụp ảnh/quay video highlight sự kiện và đăng tải cập nhật nóng lên Fanpage.
NV05	Thiết kế & Nội dung	Thiết kế bộ nhận diện (Backdrop, Standee, thẻ đeo, poster, E-Certificate).	Hỗ trợ bàn Check-in (07:30–08:15); điều khiển slide/visual màn hình LED sân khấu.
NV06	Trưởng ban Kỹ thuật & AI	Xây dựng nội dung 3 Trạm thực hành AI, biên soạn bộ "AI Prompt Kit" và đề thi Hackathon.	Điều phối chính 3 Trạm thực hành AI buổi chiều và chấm kỹ thuật vòng thi đấu.
NV07	Kỹ thuật Âm thanh & Mạng	Kiểm tra hệ thống âm thanh, máy chiếu, lắp đặt 2 bộ phát Wi-Fi 4G/5G dự phòng.	Trực kỹ thuật âm thanh, micro, xử lý sự cố kết nối Wi-Fi cho 150 sinh viên.
NV08	Trưởng ban Hậu cần & Tài chính	Đặt in ấn, đặt bánh nước teabreak, mua vật tư văn phòng phẩm, giữ chứng từ thu chi.	Quản lý kho vật tư, nhận hàng teabreak, chuẩn bị quà diễn giả và tiền giải thưởng.
NV09	Phụ trách Check-in & Điều phối 1	Tạo danh sách mã QR check-in, gửi email nhắc lịch cho sinh viên đã đăng ký.	Trực bàn Check-in sáng (07:30–08:15), hướng dẫn chỗ ngồi, làm Mentor hỗ trợ Trạm AI 1.
NV10	Phụ trách Check-in & Điều phối 2	Chuẩn bị thẻ đeo, phân chia khu vực ngồi và sơ đồ di chuyển các trạm thực hành.	Trực bàn Check-in sáng (07:30–08:15), điều phối khu vực Teabreak, làm Mentor Trạm AI 2.
5. Kế hoạch truyền thông trước sự kiện (14 ngày)
Mục tiêu chuyển đổi: Thu hút 200 lượt đăng ký hợp lệ (dự phòng tỷ lệ hao hụt/no-show 25% để đảm bảo 150 sinh viên có mặt thực tế).

Giai đoạn 1: Khởi động & Gây tò mò (Ngày T-14 đến T-10)

Kênh: Fanpage CLB, các hội nhóm sinh viên của trường, nhóm Zalo lớp/khóa.

Hoạt động: Đăng bài Teasing "Sinh viên thời AI: Dùng AI để bứt phá hay bị AI thay thế?" kèm video ngắn 30s giới thiệu các tình huống ứng dụng AI hài hước trong học tập.

Giai đoạn 2: Mở cổng đăng ký & Công bố giá trị (Ngày T-9 đến T-4)

Kênh: Fanpage CLB, Poster dán tại bảng tin các tòa nhà giảng đường & căn-tin.

Hoạt động: Tung bài viết chính thức mở form đăng ký (giới hạn 150 suất tham dự trực tiếp); lần lượt hé lộ profile 3 diễn giả và nội dung thực hành tại 3 Trạm AI buổi chiều; tặng ngay E-book "50 Câu lệnh AI cho Sinh viên" cho người đăng ký sớm.

Giai đoạn 3: Thúc đẩy hành động & Nhắc lịch (Ngày T-3 đến T-1)

Kênh: Fanpage CLB, Email cá nhân & SMS/Zalo nhắc lịch.

Hoạt động: Đếm ngược (Countdown) số suất còn lại; gửi email xác nhận kèm mã QR Check-in cá nhân và dặn dò sinh viên mang theo laptop/điện thoại sạc đầy pin để thực hành buổi chiều.

6. Bản tóm tắt ngữ cảnh dự án (Context Management Snapshot)
=== CONTEXT_SNAPSHOT: AI INNOVATION DAY ===
1. [FIXED_CONSTRAINTS]
- Sự kiện: AI Innovation Day | Thời gian: 1 ngày (07:30 - 17:00)
- Quy mô bắt buộc: 150 sinh viên tham dự thực tế
- Ngân sách trần: 15.000.000 VNĐ (tuyệt đối không vượt)
- Nhân sự cố định: 10 người (mã NV01 - NV10)
- Mục tiêu: Sinh viên hiểu & trực tiếp trải nghiệm AI trong học tập và công việc

2. [BUDGET_STATE] (Tổng hiện tại: 15.000.000 VNĐ)
- Địa điểm & Kỹ thuật: 1.000.000đ (Hội trường trường miễn phí)
- In ấn & Nhận diện: 2.500.000đ
- Diễn giả & Giải thưởng: 4.500.000đ (3 diễn giả + giải Mini-Hackathon)
- Teabreak & Nước uống: 4.500.000đ (165 suất x 22k + nước suối)
- Truyền thông & Wi-Fi dự phòng: 1.000.000đ (2 bộ phát 4G/5G + in poster)
- Quỹ dự phòng: 1.500.000đ

3. [SCHEDULE_FLOW]
- 07:30-08:30: Check-in QR & Khai mạc
- 08:30-11:30: Keynote 1 (AI học tập), Teabreak (09:45), Keynote 2 (AI công việc)
- 11:30-13:30: Nghỉ trưa tự túc
- 13:30-17:00: 3 Trạm thực hành AI (13:30) -> Mini-Hackathon (15:15) -> Trao giải & Bế mạc (16:30)

4. [STAFF_MATRIX]
- NV01: Trưởng BTC | NV02: MC/Điều phối sân khấu | NV03: Đối ngoại/Diễn giả
- NV04: Trưởng Truyền thông | NV05: Thiết kế/Visual | NV06: Trưởng Kỹ thuật/AI Lab
- NV07: Kỹ thuật Âm thanh/Mạng | NV08: Hậu cần/Tài chính | NV09 & NV10: Check-in & Mentor trạm

5. [COMMS_KPI]
- Chiến dịch 14 ngày (T-14 đến T-1) | KPI Form đăng ký: 200 lượt (dự phòng 25% no-show -> đạt 150 SV thực tế).
===========================================


7. Báo cáo kiểm tra và hiệu chỉnh kế hoạch (Kết quả thực thi Prompt 5 trong phiên mới)
A. Kết quả rà soát từng bước (Chain-of-Thought Audit)
Kiểm tra Ngân sách ↔ Nhân sự & Lịch trình:
Phát hiện lỗ hổng 1 (Chi phí ăn trưa đội ngũ vận hành): Lịch trình quy định sinh viên nghỉ trưa tự túc (11:30–13:30), nhưng 10 nhân sự BTC (NV01–NV10) và 3 diễn giả/mentor phải trực tại hội trường để giữ đồ, kiểm tra kỹ thuật chuẩn bị cho phiên chiều. Bảng dự toán hiện tại chưa có khoản cơm trưa cho 13 nhân sự cốt lõi này.
Kiểm tra Điểm nghẽn Nhân sự ↔ Quy mô 150 sinh viên:
Phát hiện lỗ hổng 2 (Quá tải bàn Check-in): Khung giờ 07:30–08:15 (45 phút) đón 150 sinh viên nhưng chỉ có 3 người trực bàn (NV05, NV09, NV10), trung bình 50 sinh viên/người dễ gây ùn ứ.
Phát hiện lỗ hổng 3 (Thiếu Mentor tại 3 Trạm AI buổi chiều): Có 3 Trạm thực hành AI (13:30–15:15) cho 150 sinh viên nhưng mới chỉ phân công NV06, NV09, NV10 (mỗi trạm chỉ có 1 người hỗ trợ cho 50 sinh viên).
Kiểm tra Tính nhất quán Truyền thông:
Đánh giá: KPI 200 đơn đăng ký để lọc ra 150 người tham dự thực tế là hợp lý, nhưng thiếu cơ chế ràng buộc cam kết nên vẫn có rủi ro thiếu hụt hoặc dư chỗ ngồi.
B. Phương án hiệu chỉnh cụ thể (Giữ nguyên 15.000.000đ, 150 SV, 10 nhân sự)
Hạng mục phát hiện	Giải pháp hiệu chỉnh chi tiết	Tác động đến ràng buộc
1. Bổ sung cơm trưa cho 10 BTC + 3 Diễn giả	Trích 500.000 VNĐ từ Quỹ dự phòng (giảm Quỹ dự phòng từ 1.500.000đ xuống còn 1.000.000đ) chuyển sang mục Hậu cần để đặt 15 suất cơm trưa văn phòng (15 × 33.000đ = 495.000đ) cho 10 nhân sự BTC, 3 diễn giả và 2 kỹ thuật viên hội trường.	Tổng ngân sách giữ nguyên chính xác 15.000.000 VNĐ.
2. Giải tỏa điểm nghẽn Check-in & Tăng cường Mentor AI	Điều động thêm NV08 (Hậu cần) hỗ trợ Check-in trong khung 07:30–08:15 (tổng 4 người trực = 37 SV/người). Buổi chiều (13:30–15:15), điều động NV01, NV04, NV05 tham gia làm trợ giảng hướng dẫn thao tác công cụ AI cơ bản tại 3 Trạm (nâng lên 2 mentor/trạm).	Số lượng nhân sự giữ nguyên 10 người, tối ưu hiệu suất theo khung giờ.
3. Siết chặt quy trình xác nhận tham dự	Khi đủ 200 đơn đăng ký, đóng form và gửi email yêu cầu sinh viên bấm nút "Xác nhận tham dự" trước 48 giờ để kích hoạt mã QR vào cửa; nếu quá hạn chưa xác nhận sẽ chuyển suất cho danh sách dự bị (Waitlist).	Đảm bảo con số tham dự thực tế sát mức 150 sinh viên, tránh lãng phí teabreak và thẻ đeo.
