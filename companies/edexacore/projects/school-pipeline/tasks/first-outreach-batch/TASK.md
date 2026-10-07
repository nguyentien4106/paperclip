---
name: Soạn gói gửi cho lô lead đầu tiên
assignee: outreach-rep
project: school-pipeline
---

Soạn gói gửi cho lô lead đầu tiên theo skill `school-outreach-vi`.

- Đầu vào: CSV từ issue "Nghiên cứu lô lead đầu tiên". Nếu chưa có, đặt issue này `blocked`
  bởi issue đó.
- Bắt đầu với 10 lead có `diem_uu_tien` cao nhất để board kiểm tra giọng văn trước; khi board
  duyệt phong cách, soạn phần còn lại.
- Đầu ra: `send-pack-*.csv` + `send-pack-*.md` (artifact), interaction xác nhận cho board, issue ở `in_review`.
