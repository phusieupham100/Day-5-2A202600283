# Phân tích UX — Chatbot NEO (Vietnam Airlines)

## 4 paths (khung lab)

| Path | Câu hỏi gốc | Quan sát khi dùng NEO |
|------|-------------|------------------------|
| **1 — Khi AI đúng** | User thấy gì? Hệ thống xác nhận thế nào? | Tra cứu chuyến theo số hiệu + ngày: bot trả thông tin rút gọn và **xin xác nhận** trước khi đi tiếp — giảm nhầm lẫn ở bước đầu. Intent rõ (vd. tra VN123) thì flow ổn. |
| **2 — Khi AI không chắc** | Im lặng? Hỏi lại? Đưa lựa chọn? | Hệ thống xử lý bằng cách gợi ý user liên hệ tư vấn viên / Trung tâm CSKH. đưa thông tin liên hệ. |
| **3 — Khi AI sai** | User biết sai bằng cách nào? Sửa được không? Mất mấy bước? | **Mất ngữ cảnh:** sau khi đang nói VN123 và xin confirm, user hỏi tiếp *“Còn delay không?”* — bot **không bám chuyến đang tra** mà **đẩy lại bước chọn phương án tra cứu** → cảm giác sai / reset. User phát hiện bằng so với kỳ vọng cuộc hội thoại liền mạch; **sửa** bằng nhắc lại đủ thông tin (số hiệu + ngày) hoặc chuyển kênh khác. **Câu hỏi lạ** (vd. hoàn vé bằng Bitcoin): bot có thể trả lời **ổn định, bảo thủ**  |
| **4 — Khi user mất tin** | Có exit? Fallback người / thủ công? Dễ thấy không? | Hỏi *“Khiếu nại ở đâu?”*: có **chuyển sang nhân viên** (message chờ hỗ trợ). Chatbot đã chuyển fall back về tư vấn viên |

### Path xử lý tốt nhất / yếu nhất

- **Tốt nhất:** Path **1** (đúng intent + bước confirm) và phần **4** (có hướng thoát sang người khi chủ đề nhạy cảm).
- **Yếu nhất:** Path **3** **sai** kiểu **state loss / follow-up** không được nối với chuyến vừa tra.

### Tự phân tích nhanh

- Marketing vs thực tế: kỳ vọng “trợ lý thông minh” đối lập với bot **tự động có thể sai** và **không kiểm duyệt trước** (theo điều khoản) → cần **disclaimer + “xác minh kênh chính thức”** sát trải nghiệm chat, không chỉ trong ToS.

---

## Gap marketing vs thực tế

Trang giới thiệu NEO nhấn mạnh hỗ trợ nhanh, đa nhiệm qua AI, tạo kỳ vọng “hỏi bot là đủ”. Trong khi Điều khoản sử dụng lại nêu rõ phản hồi được tạo tự động, không kiểm duyệt trước, có thể sai, hãng không bảo đảm độ chính xác, và khuyến cáo không dựa hoàn toàn vào bot cho quyết định quan trọng — phải xác minh trên kênh chính thức. Thực tế dùng thử còn thấy lỗi hành vi (vd. mất ngữ cảnh, ép chọn menu), làm trải nghiệm lệch so với hình ảnh “trợ lý thông minh”. Gap cốt lõi là kỳ vọng tin cậy như nhân viên so với bản chất sản phẩm công cụ tự động có rủi ro sai sót.
