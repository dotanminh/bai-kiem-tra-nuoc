---
name: bai-kiem-tra-nuoc
description: >
  Phân loại bất kỳ nội dung nào (bài mạng xã hội, bài báo, sách, transcript YouTube,
  thinking output của AI) thành 2 nhóm rõ ràng: (1) việc nên giao cho AI làm ngay,
  (2) kỹ năng cần tự học/trải nghiệm thêm. Kích hoạt khi user share link, bài viết,
  transcript, hoặc hỏi "tôi áp dụng được gì", "AI làm được không", "tôi cần học thêm gì".
version: 1.0.0
status: approved
author: Minh Đỗ
source: Kevin Kelly — WAIC 2026, Thượng Hải, 17/7/2026
created: 2026-07-24
keywords: [phan-loai, ai-delegate, hoc-them, kiem-tra-nuoc, has-it-touched-water, cong-viec, ky-nang]
---

# Bài Kiểm Tra Nước — Has It Touched Water?

> Nguồn gốc: Kevin Kelly (73 tuổi, sáng lập Wired) phát biểu tại WAIC 2026 Thượng Hải.
> Câu gốc: "AI được huấn luyện trên chữ viết về thế giới. Nó biết về bơi lội vì đọc hàng triệu trang sách. Nhưng nó chưa bao giờ thật sự ướt người."

## Triết lý cốt lõi

Mọi kỹ năng, công việc, hoạt động đều rơi vào 1 trong 2 thế giới:

| Thế giới Chữ (Text-World) | Thế giới Thật (Real-World) |
|---|---|
| AI học được từ văn bản, pattern, dữ liệu | Chỉ học được qua trải nghiệm thực |
| Có thể mô tả thành quy trình rõ ràng | Phụ thuộc vào bối cảnh, cảm nhận, mối quan hệ |
| Lặp lại có cấu trúc, output dự đoán được | Mơ hồ, thiếu thông tin, cần phán đoán |
| AI làm tốt hơn người, giao đi | Đây là chỗ bạn đứng, không thể bị thay thế |

**Câu hỏi chẩn đoán duy nhất:**
> "Kỹ năng này AI học từ sách hay học từ đời thật?"
> Từ sách → Thế giới Chữ → delegate.
> Từ đời thật → Thế giới Thật → tự học, đầu tư thêm.

---

## When to Use (Trigger)

Kích hoạt skill này khi user:
- Share link bài viết, bài báo, sách, transcript YouTube
- Paste nội dung bài đăng mạng xã hội để phân tích
- Hỏi: "tôi áp dụng được gì từ bài này?", "AI làm được không?", "tôi cần học thêm gì?"
- Sau khi Agent trả về phân tích/thinking → user muốn lọc ra phần actionable
- Keyword: "bài kiểm tra nước", "has it touched water", "phân loại công việc"

---

## Procedure

### Bước 1 — Thu thập input

Nhận 1 trong các dạng:
- **Link:** dùng `tavily_extract` hoặc `read_url_content` để lấy nội dung
- **Paste text:** đọc trực tiếp
- **Transcript YouTube:** đọc từ file `transcript.txt` trong youtube-learn folder
- **Thinking/output của Agent:** đọc từ nội dung cuộc trò chuyện

### Bước 2 — Extract danh sách kỹ năng/công việc/hoạt động

Đọc toàn bộ nội dung. Liệt kê TẤT CẢ các kỹ năng, công việc, hoạt động, phương pháp được đề cập.
Mỗi item viết ngắn gọn, dạng động từ + bổ ngữ. Ví dụ: "Viết email cold outreach", "Đọc tín hiệu cảm xúc khách hàng", "Phân tích dữ liệu bán hàng".

### Bước 3 — Áp dụng Bài Kiểm Tra Nước

Với mỗi item, hỏi: **"AI học điều này từ sách hay từ đời thật?"**

Dùng 5 marker để phân loại nhanh:

**Marker Thế giới Chữ (AI giỏi):**
- Có thể viết thành checklist, template, quy trình rõ ràng
- Output là văn bản, số liệu, hoặc pattern có cấu trúc
- Lặp lại nhiều lần ra kết quả tương tự
- Không đòi hỏi cảm nhận ngữ cảnh thời gian thực
- Học được qua sách, video, tài liệu

**Marker Thế giới Thật (Người giỏi hơn):**
- Đòi hỏi "đọc phòng": cảm nhận cảm xúc, năng lượng, sự im lặng
- Kết quả phụ thuộc vào tin tưởng và mối quan hệ tích lũy
- Cần phán đoán trong tình huống mơ hồ, thiếu dữ liệu
- Gắn với bối cảnh địa phương, văn hóa, con người cụ thể
- Học chủ yếu qua thất bại và phản hồi thực tế

### Bước 4 — Xuất bảng phân loại

Xuất bảng theo format chuẩn (xem `resources/output-template.md`):

```
## Bài Kiểm Tra Nước — [Tên nội dung/nguồn]
Nguồn: [URL hoặc mô tả]
Ngày: [YYYY-MM-DD]

### Thế giới Chữ — Delegate cho AI ngay
| Kỹ năng/Công việc | AI làm được bằng cách nào |
|---|---|
| ... | ... |

### Thế giới Thật — Tự học/Trải nghiệm thêm
| Kỹ năng/Công việc | Tại sao cần người | Gợi ý học thêm |
|---|---|---|
| ... | ... | ... |

### Ưu tiên hành động
- Delegate ngay (tuần này): [top 3 việc nên giao AI]
- Đầu tư học (tháng này): [top 2 kỹ năng nên tự rèn]
- Bỏ qua hoàn toàn: [nếu có - những thứ không liên quan công việc Minh]
```

### Bước 5 — Lưu output

Lưu kết quả vào:
`D:\1_MINH DO\2_Areas\Agent_Skills\bai-kiem-tra-nuoc\resources\analyses\YYYY-MM-DD_[ten-ngan].md`

Cập nhật `CHANGES.log` theo quy định.

---

## Pitfalls

- **KHÔNG phân loại cả chủ đề lớn** — phải phân loại từng kỹ năng/công việc cụ thể bên trong. Ví dụ: không phân loại "Marketing" mà phân loại "Viết copy quảng cáo", "Xây dựng quan hệ với KOL", "Phân tích A/B test".
- **KHÔNG để item ở vùng xám** — mỗi item phải rơi dứt khoát vào 1 trong 2 cột. Nếu phân vân, ưu tiên hỏi: "Nếu AI làm việc này và sai, hậu quả có nghiêm trọng không?" Nếu có → Thế giới Thật.
- **KHÔNG bỏ qua phần "Bỏ qua hoàn toàn"** — đây là phần tiết kiệm thời gian nhất cho Minh.
- **Ưu tiên hành động phải cụ thể, không chung chung** — "Học thêm về leadership" là sai. "Xem 2 buổi coaching 1-1 với người đã làm quản lý >5 năm" là đúng.

---

## Output nhanh (Quick Mode)

Khi user cần nhanh, bỏ qua format đầy đủ, chỉ trả về:

```
DELEGATE NGAY: [3 việc]
TỰ HỌC THÊM: [2 kỹ năng]
BỎ QUA: [nếu có]
```

---

## Ví dụ áp dụng

Xem `references/kevin-kelly-source.md` để thấy bài phân tích mẫu đầu tiên được tạo từ transcript WAIC 2026.
