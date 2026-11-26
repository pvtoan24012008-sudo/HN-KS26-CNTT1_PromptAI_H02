# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** Phạm Viết Toàn
- **Lớp:** HNKS26CNTT1
- **Link repository Pha2:** https://github.com/pvtoan24012008-sudo/HN-KS26-CNTT1_PromptAI_H02.git
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** ChatGPT

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
json
[
  {
    "loai_ve": "VECH",
    "ngay_choi": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_tu": "nho",
    "ghi_chu": null
  },
  {
    "loai_ve": "VECN",
    "ngay_choi": "2027-01-03",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_tu": null,
    "ghi_chu": "Một người đang bó bột tay"
  },
  {
    "loai_ve": "VEVIP",
    "ngay_choi": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_tu": "lon",
    "ghi_chu": "một bạn đi xe lăn"
  }
]

```


**Link trò chuyện:** https://share.gemini.google/A62ri9EyCjC6

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
**1. Chuẩn hóa dữ liệu**

* **Loại vé:** VECN (Vé cả ngày) – Đơn giá người lớn: 250.000 đồng.
* **Số lượng khách:**
* Người lớn: 8 người.
* Trẻ em (cao từ 1 m đến 1,4 m): 4 bé (cao 1,05 m; 1,15 m; 1,2 m; 1,3 m).
* Trẻ em (cao dưới 1 m): 2 bé (miễn phí).


* **Dịch vụ phụ thu:** 6 áo phao – Đơn giá: 40.000 đồng/chiếc.

**2. Tính toán từng bước**

* **Tiền vé người lớn:** $8 \times 250.000 = 2.000.000\text{ đồng}$
* **Tiền vé trẻ em:**
* Đơn giá vé trẻ em (từ 1 m đến 1,4 m) = $60\% \times 250.000 = 150.000\text{ đồng}$
* Tổng tiền vé trẻ em = $(4 \times 150.000) + (2 \times 0) = 600.000\text{ đồng}$


* **Tiền vé sau giảm giá đoàn:**
* Tổng tiền vé ban đầu = $2.000.000 + 600.000 = 2.600.000\text{ đồng}$
* Do đoàn có 8 người lớn (đủ điều kiện từ 8 người lớn trở lên) nên được giảm 10% tiền vé:
* Tiền vé sau giảm = $2.600.000 \times (100\% - 10\%) = 2.340.000\text{ đồng}$


* **Phụ thu:** $6 \times 40.000 = 240.000\text{ đồng}$
* **Tổng tiền:** $2.340.000 + 240.000 = 2.580.000\text{ đồng}$

[RESULT: 2.580.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/IuhHqZOlUZe0

### b) Kiểm tra kết quả AI

AI trả lời đúng 

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
json
[
  {
    "loai_su_co": "dong_khu_choi",
    "so_khach": 4,
    "so_khu_bi_dong": 2,
    "tom_tat": "Gia đình 4 người phản ánh khu trượt nước và sóng nhân tạo đóng cửa cả ngày không báo trước."
  }
]
```

**Link trò chuyện:** https://share.gemini.google/T8UvlGIg6I2z

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
Đúng thông tin (50%)	0/5	
- Câu lỗi 1: "Vé chiều bên em 150k thôi ạ, mát rượi luôn." -> Lý do sai: Báo sai giá vé chiều (thông tin chuẩn là 180.000 đồng/vé người lớn).


- Câu lỗi 2: "Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha." -> Lý do sai: Sai chính sách khi đóng cửa do thời tiết (thông tin chuẩn là không hoàn tiền mặt; khách đã vào dưới 2 giờ được tặng 1 vé cùng loại dùng trong 30 ngày).

- Sửa câu 1: "Vé buổi chiều (VECH) có giá 180.000 đồng/vé người lớn ạ."


- Sửa câu 2: "Nếu công viên phải đóng cửa vì thời tiết khi quý khách mới vào được 1 tiếng (dưới 2 giờ), công viên sẽ tặng 1 vé cùng loại có thời hạn sử dụng trong 30 ngày ạ (không áp dụng hoàn tiền mặt)."

Đầy đủ (30%)	1.5/3	- Đã trả lời đủ 2 câu hỏi của khách nhưng thiếu phần mời khách cung cấp ngày chơi và số vé để đặt vé.	- Thêm câu mời đặt vé: "Anh/chị vui lòng cho em xin ngày đi và số lượng vé dự kiến để em hỗ trợ đặt vé cho mình ạ."
Giọng điệu (20%)	0.5/2	- Câu lỗi: "Hello chị! Vé chiều bên em 150k thôi ạ, mát rượi luôn. Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha. Cần gì ới em nhé!" -> Lý do sai: Dùng từ ngữ suồng sã, thiếu chuyên nghiệp ("Hello chị", "mát rượi luôn", "nha", "ới em"), đồng thời tự xưng "chị" khi khách chưa rõ giới tính/xưng hô.	- Sửa: "Dạ em chào quý khách. Vé buổi chiều có giá 180.000 đồng/vé người lớn ạ. Nếu công viên phải đóng cửa vì thời tiết khi quý khách vào dưới 2 giờ, bên em sẽ tặng 1 vé cùng loại sử dụng trong 30 ngày (không hoàn tiền mặt). Quý khách cho em xin ngày đi và số lượng vé để em hỗ trợ đặt vé nhé."
Tổng điểm: 2/10
```

**Link trò chuyện:** https://share.gemini.google/vVvGElgoB9JL
