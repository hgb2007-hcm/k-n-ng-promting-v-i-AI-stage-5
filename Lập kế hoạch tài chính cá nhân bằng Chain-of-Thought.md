### Phần 1: Khai báo Prompt thiết kế và Dữ liệu đầu vào (Prompt & Inputs)

#### 1. Cấu trúc Prompt thiết kế (Chain-of-Thought Prompt)

> **Vai trò (Role):** Bạn là một chuyên gia hoạch định tài chính cá nhân.
> **Nhiệm vụ (Task):** Dựa trên dữ liệu tài chính đầu vào được cung cấp dưới đây, hãy lập kế hoạch phân bổ ngân sách hàng tháng tối ưu theo **quy tắc 50/30/20 cải tiến** (trong đó nhóm 50% thiết yếu được tách thành 30% chi phí cố định và 20% nghĩa vụ trả nợ bắt buộc; giữ nguyên 20% tiết kiệm và 30% chi tiêu linh hoạt).
> **Dữ liệu đầu vào (Inputs):**
> * **Tổng thu nhập hàng tháng:** $30.000.000\text{ VNĐ}$
> * **Chi phí cố định bắt buộc:** $9.000.000\text{ VNĐ}$ (nhà ở, điện, nước, internet, bảo hiểm bắt buộc)
> * **Khoản trả nợ tối thiểu:** $6.000.000\text{ VNĐ}$ (thanh toán gốc và lãi định kỳ)
> * **Mục tiêu tiết kiệm tối thiểu:** $20\%$ tổng thu nhập
> 
> 
> **Yêu cầu đầu ra (Output Format):**
> 1. Trình bày nhật ký suy luận logic qua 4 bước kèm công thức, phép tính trung gian và đối chiếu với quy tắc 50/30/20 cải tiến.
> 2. Tổng hợp kết quả dưới dạng bảng Markdown chuẩn xác với tổng tỷ lệ đạt đúng **100%**.
> 
> 
> **Chỉ thị kích hoạt (CoT Trigger):** *"Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra quyết định."*

#### 2. Bảng tổng hợp tham số đầu vào (Input Parameters)

| Tham số đầu vào | Giá trị khai báo | Ghi chú áp dụng |
| --- | --- | --- |
| **Tổng thu nhập ($I$)** | $30.000.000\text{ VNĐ}$ | Nguồn thu nhập ròng cố định hàng tháng |
| **Chi phí cố định ($F$)** | $9.000.000\text{ VNĐ}$ | Chiếm $30\%$ tổng thu nhập |
| **Nghĩa vụ trả nợ ($D$)** | $6.000.000\text{ VNĐ}$ | Chiếm $20\%$ tổng thu nhập |
| **Tỷ lệ tiết kiệm mục tiêu ($S\%$)** | $20\%$ tổng thu nhập | Tương đương $6.000.000\text{ VNĐ}$ |
| **Mô hình phân bổ** | Quy tắc 50/30/20 cải tiến | $50\%$ Thiết yếu & Nợ ($30\% + 20\%$) / $30\%$ Linh hoạt / $20\%$ Tiết kiệm |

---

### Phần 2: Nhật ký suy luận logic (Reasoning Steps)

*Chỉ thị kích hoạt:* **"Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra quyết định"**

* **Bước 1: Tính toán thu nhập khả dụng sau khi trừ chi phí cố định bắt buộc**
* *Công thức:* $\text{Thu nhập khả dụng} = I - F$
* *Dữ liệu:* $30.000.000 - 9.000.000$
* *Kết quả trung gian:* $21.000.000\text{ VNĐ}$ (chi phí cố định chiếm $30\%$ tổng thu nhập).
* *Ý nghĩa:* Đây là khoản tiền còn lại sau khi đã thanh toán các nhu cầu thiết yếu không thể cắt giảm (nhà cửa, điện nước, internet, bảo hiểm).


* **Bước 2: Phân bổ khoản tiền trả nợ tối thiểu**
* *Công thức:* $\text{Dòng tiền sau trả nợ} = \text{Thu nhập khả dụng} - D$
* *Dữ liệu:* $21.000.000 - 6.000.000$
* *Kết quả trung gian:* $15.000.000\text{ VNĐ}$ (khoản trả nợ chiếm $20\%$ tổng thu nhập).
* *Ý nghĩa:* Đảm bảo nghĩa vụ tín dụng được hoàn thành đúng hạn, tránh phát sinh lãi phạt quá hạn. Tổng chi phí cố định và trả nợ hiện đạt $30\% + 20\% = 50\%$ tổng thu nhập.


* **Bước 3: Trích lập quỹ tiết kiệm theo tỷ lệ cam kết**
* *Công thức:* $\text{Dòng tiền sau tiết kiệm} = \text{Dòng tiền sau trả nợ} - (I \times S\%)$
* *Dữ liệu:* $15.000.000 - 6.000.000$ (với $\text{Quỹ tiết kiệm} = 30.000.000 \times 20\% = 6.000.000\text{ VNĐ}$)
* *Kết quả trung gian:* $9.000.000\text{ VNĐ}$
* *Ý nghĩa:* Xây dựng quỹ dự phòng khẩn cấp và tích lũy tài sản dài hạn trước khi phân bổ tiền cho các nhu cầu cá nhân khác.


* **Bước 4: Phân bổ phần còn lại cho chi tiêu linh hoạt (Wants) và đối chiếu quy tắc 50/30/20 cải tiến**
* *Công thức:* $\text{Ngân sách chi tiêu linh hoạt} = \text{Dòng tiền sau tiết kiệm}$
* *Kết quả trung gian:* $9.000.000\text{ VNĐ}$ (chiếm $\frac{9.000.000}{30.000.000} \times 100\% = 30\%$ tổng thu nhập).
* *Đối chiếu quy tắc 50/30/20 cải tiến:* Cơ cấu phân bổ sau 4 bước khớp hoàn toàn với **quy tắc 50/30/20 cải tiến**:
* **50% Thiết yếu & Nghĩa vụ bắt buộc ($15.000.000\text{ VNĐ}$):** Gồm $30\%$ Chi phí cố định ($9.000.000\text{ VNĐ}$) + $20\%$ Trả nợ bắt buộc ($6.000.000\text{ VNĐ}$).
* **30% Chi tiêu linh hoạt – Wants ($9.000.000\text{ VNĐ}$):** Dùng cho ăn uống ngoài, giải trí, mua sắm cá nhân và các phát sinh ngắn hạn trong tháng.
* **20% Tiết kiệm & Đầu tư – Savings ($6.000.000\text{ VNĐ}$):** Đạt đúng mục tiêu tích lũy đề ra.





---

### Phần 3: Bảng phân bổ ngân sách cuối cùng

Bảng dưới đây tổng hợp cơ cấu phân bổ ngân sách hàng tháng theo quy tắc 50/30/20 cải tiến, đảm bảo tổng tỷ lệ đạt chính xác **100%**:

| Hạng mục | Nhóm quy tắc 50/30/20 cải tiến | Số tiền (VNĐ) | Tỷ lệ % | Ghi chú |
| --- | --- | --- | --- | --- |
| **1. Chi phí cố định** | Thiết yếu & Nghĩa vụ (50%) | 9.000.000 | 30.00% | Nhà ở, điện, nước, internet, bảo hiểm bắt buộc |
| **2. Trả nợ** | Thiết yếu & Nghĩa vụ (50%) | 6.000.000 | 20.00% | Thanh toán gốc và lãi các khoản nợ đúng hạn |
| **3. Tiết kiệm & Đầu tư** | Tiết kiệm & Đầu tư (20%) | 6.000.000 | 20.00% | Quỹ dự phòng khẩn cấp và tích lũy cá nhân (Đạt chuẩn 20%) |
| **4. Chi tiêu linh hoạt** | Chi tiêu linh hoạt (30%) | 9.000.000 | 30.00% | Ăn uống, giải trí, mua sắm và phát sinh cá nhân |
| **TỔNG CỘNG** | **100% Ngân sách** | **30.000.000** | **100.00%** | **Cân đối hoàn hảo, không có thâm hụt ngân sách** |
