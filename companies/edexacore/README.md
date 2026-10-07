# EdexaCore — Agent Company

Đội Growth bằng agent cho **EdexaCore**, nền tảng LMS/SIS tích hợp AI (Teacher CorePilot,
AI cho học sinh và phụ huynh) dành cho trường phổ thông Việt Nam. Đội ngũ tìm người liên hệ
tại các trường **tiểu học, THCS, THPT** theo từng tỉnh/thành, giới thiệu sản phẩm, đưa trường
vào **dùng miễn phí** và kích hoạt giáo viên.

> Giai đoạn hiện tại: **miễn phí** — đo bằng số trường được kích hoạt, không phải doanh thu.
> Agent **chỉ soạn** tin nhắn; **người thật tự gửi**.

## Luồng công việc

```
CEO ──chọn tỉnh, KPI──▶ Lead Researcher ──CSV lead──▶ Outreach Rep ──gói gửi──▶ 👤 Board gửi thủ công
                                                          ▲                         │
                                                          └──── dán phản hồi ◀──────┘
                                                          │
                                         quan tâm ────────▼
                                               Customer Success ──▶ trường "active"
                                                          │
                  Content Marketer ◀── cần tài liệu ──────┘   (one-pager, FAQ, hướng dẫn, case study)
```

Mô hình **hub-and-spoke**: CEO điều phối; luồng lead đi theo pipeline
`researched → drafted → contacted → replied → demo_scheduled → onboarding → active`
(chi tiết trong `skills/lead-pipeline`).

## Sơ đồ tổ chức

| Agent | Chức danh | Báo cáo cho | Skills |
| --- | --- | --- | --- |
| `ceo` | Giám đốc điều hành (Head of Growth) | — | paperclip, edexacore-product, lead-pipeline |
| `lead-researcher` | Chuyên viên nghiên cứu khách hàng | ceo | paperclip, vn-school-prospecting, lead-pipeline |
| `outreach-rep` | Chuyên viên tiếp cận khách hàng | ceo | paperclip, school-outreach-vi, edexacore-product, lead-pipeline |
| `customer-success` | Onboarding & Thành công khách hàng | ceo | paperclip, free-pilot-onboarding, edexacore-product, lead-pipeline |
| `content-marketer` | Nội dung & Sales Enablement | ceo | paperclip, edexacore-product, school-outreach-vi |

- **CEO** — chọn tỉnh/phân khúc ưu tiên, giao lô việc, báo cáo pipeline hằng tuần cho board.
- **Lead Researcher** — lập danh sách trường và đầu mối liên hệ *công khai, có nguồn*; xuất CSV.
- **Outreach Rep** — soạn email/Zalo/kịch bản gọi cá nhân hoá, chờ board gửi, xử lý phản hồi và follow-up.
- **Customer Success** — chuẩn bị demo, onboarding, đồng ý của phụ huynh, theo dõi kích hoạt.
- **Content Marketer** — one-pager, FAQ, xử lý phản đối, hướng dẫn giáo viên, case study.

## Skills

| Skill | Nội dung |
| --- | --- |
| `edexacore-product` | Kiến thức sản phẩm, thông điệp, cách nói về "miễn phí" và dữ liệu học sinh |
| `lead-pipeline` | Schema CSV, vòng đời trạng thái, chấm điểm ưu tiên, khử trùng lặp, KPI |
| `vn-school-prospecting` | Cấu trúc quản lý trường, nguồn dữ liệu được phép/bị cấm, quy trình một lô |
| `school-outreach-vi` | Giọng văn, mẫu email/Zalo/gọi điện, nhịp 3 lần chạm, gói gửi, chống spam |
| `free-pilot-onboarding` | Định nghĩa "kích hoạt", demo, thiết lập, đào tạo, theo dõi |
| `paperclip` | Skill vận hành Paperclip (có sẵn trong thư viện skill của instance) |

## Projects & tasks

| Project | Owner | Task khởi động |
| --- | --- | --- |
| Pipeline trường học | ceo | Kế hoạch GTM 90 ngày → Nghiên cứu lô đầu tiên → Soạn gói gửi lô đầu tiên |
| Kích hoạt & thành công khách hàng | customer-success | Bộ công cụ onboarding |
| Tài liệu bán hàng & đào tạo | content-marketer | Bộ tài liệu giới thiệu ra mắt |

Routine định kỳ (giờ Việt Nam): báo cáo pipeline (T2 8:00), nghiên cứu lead (T2–T6 9:00),
xử lý phản hồi & follow-up (T2–T6 15:00), rà soát kích hoạt (T5 9:00).

## Tuân thủ

- Chỉ dùng thông tin liên hệ công khai, chính thức của nhà trường; mọi bản ghi có URL nguồn.
- Nghị định 13/2023/NĐ-CP, Luật Bảo vệ dữ liệu cá nhân; Nghị định 91/2020/NĐ-CP về chống thư rác.
- Không liên hệ học sinh; dữ liệu học sinh cần sự đồng ý của cha mẹ/người giám hộ.
- Từ chối → `do_not_contact` vĩnh viễn.

Đây là hướng dẫn vận hành, không phải tư vấn pháp lý — nên nhờ luật sư rà soát mẫu đồng ý và
chính sách dữ liệu trước khi triển khai rộng.

## Bắt đầu

```bash
paperclipai company import --from companies/edexacore
```

Sau khi import:

1. Điền các mục `[CẦN BỔ SUNG]` trong `skills/edexacore-product/SKILL.md` (hoặc trả lời câu hỏi CEO sẽ gửi).
2. Đảm bảo adapter của Lead Researcher có quyền tìm kiếm/duyệt web.
3. Mỗi khi Outreach Rep đưa gói gửi: đọc, chỉnh, tự gửi, rồi xác nhận và dán phản hồi vào issue.

## Tham khảo

- Đặc tả Agent Companies: https://agentcompanies.io/specification
- Paperclip: https://github.com/paperclipai/paperclip
