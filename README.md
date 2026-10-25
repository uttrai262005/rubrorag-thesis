# RubroRAG Thesis — Repository Starter

Bộ khung tài liệu để xây dựng lại sản phẩm khóa luận theo hướng spec-driven development. Đây chưa phải ứng dụng đã triển khai, và các sơ đồ kiến trúc đi kèm là đề xuất cần được xác nhận.

## Bắt đầu

1. Giải nén gói này vào một thư mục dự án mới.
2. Đọc AGENTS.md và context/01 đến context/11.
3. Làm theo GITHUB_SETUP_POWERSHELL.md để tạo repository GitHub riêng, mặc định Private.
4. Mở thư mục gốc bằng Codex.
5. Dán nội dung CODEX_BOOTSTRAP_PROMPT.md và yêu cầu Codex chỉ thực hiện F00 trước.
6. Review diff, chạy test/build phù hợp, commit và push.
7. Mỗi feature tiếp theo phải có spec, acceptance criteria và evidence kiểm thử.

## Cấu trúc

- context/ — nguồn sự thật về mục tiêu, kiến trúc, quy chuẩn, trạng thái và chất lượng.
- context/specs/ — đặc tả cho mỗi feature.
- context/decisions/ — Architecture Decision Records (ADR).
- docs/diagrams/ — sơ đồ PlantUML dạng văn bản, quản lý bằng Git.
- docs/references.md — nguồn tham khảo chính thức cần kiểm tra lại khi chọn công nghệ.
- .github/ — mẫu review/PR.
- AGENTS.md — chỉ dẫn bắt buộc cho Codex.

## Nguyên tắc không được phá vỡ

- Không tuyên bố feature hoàn thành nếu chưa có bằng chứng.
- Không đánh đồng điểm AI, feedback RubroRAG và điểm cuối cùng do HR duyệt.
- Không dùng dữ liệu demo làm ground truth nghiên cứu.
- Không sửa pipeline, rubric, prompt, ngưỡng hoặc thiết lập nghiên cứu để làm đẹp kết quả mà không có ADR và phê duyệt.
- Không đưa secret, dữ liệu cá nhân hoặc dữ liệu nghiên cứu bị hạn chế lên GitHub.
- Không tạo microservices, queue, realtime hoặc tích hợp trả phí nếu chưa có nhu cầu và quyết định rõ.
- Các sơ đồ mang nhãn proposed/draft không được coi là kiến trúc triển khai đã xác minh.

## Điểm cần xác minh trước khi code

Đối chiếu đề bài khóa luận, paper gốc, rubric/đề đã chốt và pipeline RubroRAG hiện hữu. Nếu một quyết định chưa được nguồn hỗ trợ, ghi nhận là Open Decision, không tự điền bằng giả định.
