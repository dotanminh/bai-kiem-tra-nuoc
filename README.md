# Bài Kiểm Tra Nước: Has It Touched Water?

> **Skill phân loại kỹ năng AI vs Người.** Framework thực tế để quyết định cái gì nên giao cho AI, cái gì cần tự học thêm.

---

## Nguồn gốc

Framework này được rút ra từ bài phát biểu của **Kevin Kelly** (73 tuổi, nhà sáng lập tạp chí *Wired*) tại **WAIC 2026** (World AI Conference), Thượng Hải, ngày 17/7/2026.

Câu gốc:
> *"AI biết về bơi lội vì đọc hàng triệu trang sách. Nhưng nó chưa bao giờ thật sự ướt người."*

---

## Khái niệm cốt lõi

Mọi kỹ năng và công việc đều rơi vào 1 trong 2 thế giới:

| Thế giới Chữ (Text-World) | Thế giới Thật (Real-World) |
|---|---|
| AI học được từ văn bản và pattern | Chỉ học được qua trải nghiệm thực |
| Tóm tắt, viết, phân tích, giải thích | Đọc phòng, xây tin tưởng, phán đoán tình huống |
| Giao hoàn toàn cho AI | Đây là chỗ bạn đứng, không thể bị thay thế |

**Câu hỏi chẩn đoán duy nhất:**
> *"Kỹ năng này AI học từ sách hay học từ đời thật?"*

- Từ sách → **Delegate cho AI**
- Từ đời thật → **Tự học, đầu tư thêm**

---

## Cấu trúc

```
bai-kiem-tra-nuoc/
├── SKILL.md                          ← Hướng dẫn đầy đủ cho AI Agent
├── resources/
│   ├── output-template.md            ← Template bảng phân loại chuẩn
│   └── analyses/                     ← Kết quả phân tích lưu theo ngày
└── references/
    └── kevin-kelly-source.md         ← Nguồn gốc + bài phân tích mẫu đầu tiên
```

---

## Cách dùng với AI Agent

Trigger skill bằng một trong các cách:

```
"bài kiểm tra nước bài này" + [paste link hoặc nội dung]
"AI làm được gì từ bài này?"
"tôi cần học thêm gì từ transcript này?"
```

Agent sẽ đọc `SKILL.md`, áp dụng framework và trả về bảng phân loại theo format chuẩn trong `resources/output-template.md`.

---

## Ví dụ output

```
### Thế giới Chữ: Delegate cho AI ngay
| Kỹ năng | AI làm bằng cách nào |
|---|---|
| Dịch transcript tiếng Anh | Pattern dịch thuật từ dữ liệu song ngữ |
| Tóm tắt bài phát biểu 60 phút | Rút ý chính từ văn bản có cấu trúc |

### Thế giới Thật: Tự học thêm
| Kỹ năng | Tại sao cần người |
|---|---|
| Phán đoán insight nào đúng thị trường Việt | Cần hiểu bối cảnh địa phương thực tế |
| Cảm nhận câu nào thật sự chạm người đọc | Học từ phản hồi thực qua nhiều bài đăng |

### Ưu tiên hành động
- Delegate ngay: Dịch transcript, viết bản nháp bài Facebook
- Tự học thêm: Kiểm chứng insight với người trong ngành
```

---

## Cài đặt

Clone repo vào thư mục Agent Skills của bạn:

```bash
git clone https://github.com/dotanminh/bai-kiem-tra-nuoc.git
```

Đăng ký đường dẫn vào `skills.json`:

```json
{
  "entries": [
    { "path": "D:/your-path/Agent_Skills" }
  ]
}
```

---

## Liên quan

- Video nguồn: [Kevin Kelly tại WAIC 2026](https://youtu.be/LwH2T9pPCc0) (Kênh Thanh Trần, 5 Phút AI)
- Tường thuật WAIC: [Reuters 17/7/2026](https://www.reuters.com/video/innovations)
- [Global Times, WAIC 2026](https://www.globaltimes.cn/page/202607/1366252.shtml)

---

*Tạo bởi Minh Đỗ, 24/7/2026*
