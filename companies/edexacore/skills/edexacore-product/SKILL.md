---
name: edexacore-product
description: Kiến thức sản phẩm và thông điệp định vị của EdexaCore (LMS/SIS tích hợp AI, Teacher CorePilot, AI cho học sinh và phụ huynh) trong giai đoạn dùng miễn phí. Dùng khi giới thiệu, viết nội dung, trả lời câu hỏi hoặc demo sản phẩm.
---

# EdexaCore — kiến thức sản phẩm

> **Nguồn sự thật duy nhất về sản phẩm.** Không mô tả tính năng nào không có ở đây.
> Mục nào còn `[CẦN BỔ SUNG]` thì hỏi board trước khi dùng trong tài liệu gửi ra ngoài.
> Các tính năng dưới đây đã đối chiếu với code trên nhánh `main` (cập nhật 2026-10-07).

## Sản phẩm là gì

EdexaCore là nền tảng quản lý và dạy học cho trường phổ thông (tiểu học, THCS, THPT),
kết hợp LMS/SIS với AI. Một ứng dụng web (giao diện tiếng Việt) và app di động (iOS/Android)
cho mọi vai trò; mỗi người chỉ thấy đúng phần việc mà quyền của mình cho phép.

| Thành phần | Dành cho | Giá trị cốt lõi |
| --- | --- | --- |
| **SIS** (quản lý thông tin học sinh) | Ban giám hiệu, giáo vụ | Quản lý lớp, học sinh, điểm, chuyên cần tập trung một chỗ |
| **LMS** (quản lý học tập) | Giáo viên, học sinh | Giao bài, nộp bài, học liệu trực tuyến |
| **Teacher CorePilot** | Giáo viên | Trợ lý AI soạn nháp giáo án, câu hỏi, bài tập, nhận xét học bạ, slide bài giảng; giáo viên duyệt trước khi dùng |
| **AI cho học sinh** | Học sinh | Trợ lý học tập gợi mở từng bước, không làm bài hộ |
| **AI cho phụ huynh** | Phụ huynh | Bản tóm tắt "Tuần này của con" do AI soạn |

### SIS và vận hành trường (đã có)

- Hồ sơ học sinh, gia đình, lớp, khối, môn, thời khoá biểu, năm học/học kỳ.
- Tuyển sinh: chiến dịch, hồ sơ, xét tuyển, thư mời nhập học.
- Điểm danh (có thể kết nối máy chấm công ZKTeco), sổ điểm, học bạ, nhận xét/hạnh kiểm.
- Học phí: lập hoá đơn, thu qua **VietQR**, đối soát giao dịch ngân hàng; miễn giảm, học bổng, hoàn tiền.
- Nhân sự, nghỉ phép, phê duyệt; thư viện, y tế học đường, cơ sở vật chất, kho, đưa đón.
- Bảng điều khiển theo vai trò cho Ban giám hiệu; mỗi con số bấm vào được để xem danh sách gốc.

### LMS (đã có)

- Giao bài, nộp bài, chấm bài; ngân hàng câu hỏi; sinh đề thi từ ngân hàng câu hỏi
  (thuật toán chọn/trộn câu, **không phải AI**).
- Học sinh xem bài tập, kết quả, học bạ, thời khoá biểu, chuyên cần trên web và app.

### Teacher CorePilot — danh sách tính năng chính xác

> Trong giao diện hiện tại, màn hình này mang tên **"Teacher Copilot"**.
> `Dùng CorePilot`

Các tính năng sau đều đã có cả phía máy chủ lẫn màn hình:

1. **Sinh câu hỏi** theo chủ đề, mức độ (Nhận biết → Vận dụng cao) và số lượng; câu hỏi vào
   ngân hàng ở trạng thái nháp, giáo viên duyệt từng câu. Gợi ý soạn câu hỏi và gắn thẻ ngay
   trong form ngân hàng câu hỏi.
2. **Soạn giáo án** cho một bài trong chương trình, có thể kèm ghi chú của giáo viên; hoặc
   **soạn giáo án từ tệp bài giảng** (.docx, .pdf, .txt). Giáo viên duyệt giáo án.
3. **Soạn nhận xét học bạ** cho từng học sinh, chỉ dựa trên điểm đã công bố và dẫn nguồn từng
   ý. Bản nháp không được lưu; giáo viên tự chép vào học bạ.
4. **Soạn bài tập về nhà**: tạo bài tập nháp (chưa báo phụ huynh) kèm câu hỏi nháp.
5. **Bài giảng AI**: AI đề xuất dàn ý → giáo viên duyệt → sinh slide, tạo lại từng slide,
   tải về **PPTX**.
6. **Gợi ý chấm bài bằng AI**: AI đề xuất điểm và nhận xét cho bài nộp; giáo viên sửa và chấp nhận.
   Điểm AI không bao giờ đến phụ huynh khi giáo viên chưa chấp nhận.
7. **Trợ lý AI hỏi đáp** về lớp và học sinh của chính giáo viên, có dẫn nguồn dữ liệu.
8. **Hỏi đáp trên kho tài liệu của trường**, có dẫn nguồn.
9. **Giải thích mức nguy cơ học tập** (vốn tính bằng quy tắc) và **gợi ý kế hoạch học tập** cho
   một học sinh; chỉ giáo viên/nhân viên thấy, không hiển thị cho học sinh và phụ huynh.

Dành cho Ban giám hiệu: **Nhận định từ dữ liệu** (cảnh báo theo quy tắc kèm giải thích của AI,
bản tin tuần) và trợ lý hỏi đáp toàn trường trong phạm vi quyền.

**Không được nói:** AI soạn nhận xét hạnh kiểm (chưa có); AI tự ra đề thi (sinh đề không dùng AI);
AI tự gửi tin, tự đổi điểm, tự báo phụ huynh (AI chỉ soạn nháp, người duyệt và gửi).

### AI cho học sinh — "Trợ lý học tập" (web và app)

- Gia sư tiếng Việt hướng dẫn từng bước: nhắc lại đề → giải thích khái niệm → gợi ý → để
  học sinh tự thử; chỉ ra chỗ sai trước khi giải thích.
- Từ chối làm hộ khi nhận ra câu hỏi trùng bài tập đang mở, và đề nghị hướng dẫn phương pháp.
  (Học sinh gõ lại đề bằng lời khác thì có thể không nhận ra — không hứa "chặn gian lận tuyệt đối".)
- Không nói mức nguy cơ, điểm dự đoán, không so sánh với bạn cùng lớp; không truy cập đáp án,
  điểm chưa công bố.
- Tối đa 20 câu hỏi/học sinh/ngày; câu trả lời gắn nhãn "Do AI soạn"; không lưu nội dung hội thoại.
- **Chưa có:** cá nhân hoá theo kết quả học tập của từng em (đang trong kế hoạch). Không nói
  "cá nhân hoá theo năng lực" ở thời điểm này.

### AI cho phụ huynh — "Tuần này của con"

- Mỗi tuần, cho từng con: chuyên cần tuần này so với tuần trước, xu hướng kết quả đã công bố,
  môn mạnh nhất, môn cần chú ý, và một việc phụ huynh có thể làm.
- Chỉ đọc dữ liệu của chính con mình (học bạ đã công bố, chuyên cần, bài nộp). Không bao giờ
  có cờ nguy cơ, chi tiết vi phạm, điểm chưa công bố, hay dữ liệu học sinh khác.
- Phụ huynh tự mở xem; không tự động gửi; gắn nhãn do AI soạn.

Ngoài AI, phụ huynh có: xem tình hình con hôm nay, học phí và thanh toán VietQR, học bạ (PDF),
bài tập, thời khoá biểu, xin nghỉ cho con, đăng ký họp phụ huynh/hẹn gặp, nhắn tin với trường.
Thông báo đến qua app (push), Zalo, email, SMS, Telegram.

### Điều kiện để dùng AI (bắt buộc nói rõ)

- AI chạy theo mô hình **"tự mang khoá AI" (BYOK)**: nhà trường kết nối tài khoản nhà cung cấp AI
  của mình (OpenAI, Anthropic Claude, Google Gemini, DeepSeek, Qwen hoặc dịch vụ tương thích
  OpenAI) và **trả phí sử dụng model trực tiếp cho nhà cung cấp đó**. EdexaCore không bán lại token.
- Tính năng giáo viên/nhân viên dùng **kết nối của trường** (quản trị viên AI cấu hình).
- Trợ lý học tập của học sinh và bản tóm tắt cho phụ huynh dùng **kết nối cá nhân** của chính
  người dùng đó, không dùng khoá của trường.
- Trước khi gửi dữ liệu học sinh tới AI, trường phải xác nhận gói/hợp đồng với nhà cung cấp
  **không dùng dữ liệu để huấn luyện model**.

## Thông tin liên hệ và đường dẫn

- Website: https://www.edexacore.com
- Đăng ký tài khoản trường: nguyenvantien0620@gmail.com · Hotline/Zalo **0359 811 663** `[Board kiểm tra link chạy trên môi trường thật]`
- Đăng ký tư vấn & dùng thử: nguyenvantien0620@gmail.com · Hotline/Zalo **0359 811 663**
- Email hệ thống gửi đi: "EdexaCore" <no-reply@edexacore.com> — chỉ dùng cho email tự động.
- Không dùng các địa chỉ `@edexacore.vn`, `*.edexacore.vn`, `educore.vn` (còn sót trong một số
  bản nháp, chưa xác nhận đang hoạt động).

## Gói miễn phí

- Trường tự đăng ký, xác minh email là vào trạng thái dùng thử với đầy đủ tính năng.
- Hệ thống chưa áp giới hạn số tài khoản, thời hạn hay khoá tính năng nào trong giai đoạn này.
- Chi phí phát sinh ngoài EdexaCore mà trường cần biết: phí model AI (trả cho nhà cung cấp AI,
  xem BYOK ở trên); tin nhắn SMS và Zalo ZNS tính theo tin, nạp trước.
- Hiện tại toàn bộ chức năng được dùng miễn phí mà không giới hạn số tài khoản và sẽ được duy trì trong giai đoạn thử nghiệm.

## Dữ liệu và bảo mật — những gì được phép nói

Đã có trong sản phẩm:

- Dữ liệu mỗi trường tách riêng; mọi truy vấn đều lọc theo trường.
- Phân quyền theo vai trò, kiểm tra ở máy chủ (không chỉ ẩn nút).
- Xác thực hai lớp (TOTP) — trường chọn vai trò nào bắt buộc; khoá tài khoản sau 5 lần đăng nhập
  sai; chặn mật khẩu đã bị lộ.
- Nhật ký thao tác (audit log) ghi tự động mọi thay đổi.
- Khoá AI của trường được mã hoá; nội dung câu hỏi gửi AI không được lưu (chỉ lưu dấu băm).
- AI không bao giờ thấy điểm chưa công bố, chi tiết vi phạm kỷ luật, đáp án đề thi.
- Ghi nhận sự đồng ý của cha mẹ/người giám hộ theo từng học sinh.

Nơi lưu trữ: cơ sở dữ liệu PostgreSQL và tệp trên Cloudflare R2.
**Không được nói** "dữ liệu lưu tại Việt Nam" hay "sao lưu hằng ngày" khi board chưa xác nhận.

## Nhập dữ liệu từ hệ thống trường đang dùng

- Nhập bằng **file Excel (.xlsx)** theo mẫu có sẵn: học sinh kèm phụ huynh, nhân viên, phụ huynh,
  câu hỏi; sao kê ngân hàng (.xlsx/.csv) để đối soát học phí. Lớp tạo hàng loạt trên giao diện.
- Có bước kiểm tra trước khi ghi, báo lỗi từng dòng; nhập học sinh có thể hoàn tác.
- **Chưa** nhập điểm cũ bằng file; **chưa** kết nối trực tiếp với vnEdu, SMAS, CSDL ngành
  hay hệ thống khác. Cách nói đúng: "chuyển dữ liệu qua file Excel từ hệ thống cũ".

## Khách hàng tham chiếu

- Hiện **chưa có** trường đang dùng thử hay khách hàng tham chiếu được xác nhận. Không nêu tên
  trường, số liệu sử dụng, lời chứng thực hay số giờ tiết kiệm.

## Thông điệp định vị (giai đoạn miễn phí)

- **Một câu:** "EdexaCore giúp thầy cô bớt việc giấy tờ để dành thời gian cho học sinh — với trợ lý AI Teacher CorePilot — và nhà trường dùng miễn phí."
- **Với Ban giám hiệu:** nắm bức tranh toàn trường, hỗ trợ chuyển đổi số, không tốn ngân sách trong giai đoạn này.
- **Với giáo viên:** tiết kiệm thời gian soạn giáo án, câu hỏi, bài tập, slide và nhận xét nhờ AI soạn nháp — thầy cô luôn là người duyệt.
- **Với phụ huynh:** theo dõi việc học của con dễ hơn.

Khi nói "miễn phí" mà có nhắc tới AI, luôn kèm: "phần AI dùng tài khoản AI của nhà trường".

## Về chữ "miễn phí"

- Được nói: "Hiện EdexaCore cho các trường sử dụng miễn phí."
- Không được nói: "miễn phí mãi mãi", báo giá tương lai, hứa giảm giá, "AI miễn phí" — trừ khi board đã xác nhận bằng văn bản.
- Nếu bị hỏi "sau này có thu phí không?": trả lời trung thực rằng giai đoạn hiện tại là miễn phí, mọi thay đổi sẽ được thông báo trước và nhà trường có quyền quyết định tiếp tục hay không. `[Board xác nhận câu trả lời này]`

## Dữ liệu học sinh và AI — cách nói đúng

- Dữ liệu học sinh là dữ liệu cá nhân của trẻ em. Theo Luật Bảo vệ dữ liệu cá nhân 91/2025/QH15
  và Nghị định 356/2025/NĐ-CP, nhà trường cần sự đồng ý của cha mẹ/người giám hộ (và của chính
  học sinh từ 7 tuổi). **Không** viện dẫn Nghị định 13/2023 — đã bị bãi bỏ từ 2026-01-01.
- Không khẳng định chứng nhận/tiêu chuẩn bảo mật nào (ISO 27001, v.v.) nếu board chưa cung cấp bằng chứng.
- AI là trợ lý, không phải người quyết định: mọi kết quả AI là bản nháp có nhãn, người duyệt mới thành hồ sơ.

## Bối cảnh cạnh tranh (chỉ dùng nội bộ)

Nhiều trường đã dùng các hệ thống sổ điểm/sổ liên lạc điện tử, nền tảng giao bài hoặc
học trực tuyến khác. Định vị EdexaCore là **bổ sung lớp AI cho giáo viên** và có thể
dùng song song; không nói xấu đối thủ. Không hứa đồng bộ tự động với hệ thống đối thủ
(chưa có tích hợp).
