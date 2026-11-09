# namnd-org/.github

Mặc định dùng chung cho mọi repo của namnd-org: mẫu PR, mẫu issue, workflow mẫu và workflow `pr-check`.
Repo nào có file riêng cùng loại thì file riêng được dùng thay.

| Đường dẫn | Dùng để |
|---|---|
| `.github/PULL_REQUEST_TEMPLATE.md` | Khung mô tả PR: Vì sao · Thay đổi gì · Kiểm tra thế nào · Rủi ro và rollback |
| `.github/ISSUE_TEMPLATE/` | Mẫu issue: Lỗi, Tính năng, Việc (tự gắn nhãn, tự vào bảng NAMND Work) |
| `.github/workflows/pr-check.yml` | Reusable workflow kiểm tra tên nhánh và tiêu đề PR |
| `workflow-templates/` | Hiện trong tab Actions › New workflow của mỗi repo |

## Quy ước

**Nhánh:** `<type>/<mô-tả-ngắn>`, có thể kèm số issue: `fix/42-otp-lap`, `feat/home-today-card`, `release/2026-11-09`.
Chữ thường, `a-z 0-9 . _ -`. Nhánh `main` là nhánh mặc định duy nhất.

**Tiêu đề PR** (Conventional Commits): `<type>(<scope>): <mô tả>`, ví dụ `fix(api): chặn OTP gửi lặp`.
Thêm `!` sau type khi phá tương thích: `feat(api)!: bỏ /v1/readings`.

| type | Khi nào |
|---|---|
| `feat` | Tính năng mới người dùng thấy được |
| `fix` | Sửa lỗi |
| `hotfix` | Sửa gấp trên production |
| `perf` | Nhanh hơn, nhẹ hơn |
| `refactor` | Đổi cấu trúc, không đổi hành vi |
| `content` | Nội dung, bài viết, dữ liệu tĩnh |
| `design` | Giao diện, không đổi logic |
| `docs` | Tài liệu |
| `test` | Chỉ test |
| `ci` | Workflow, build, deploy |
| `chore` | Dọn dẹp, phụ thuộc, cấu hình |
| `release` | Nhánh phát hành |
| `revert` | Hoàn tác |

**Nhãn** (có ở mọi repo): `bug` `feature` `task` `chore` `docs` · `P0` `P1` `P2` · `agent:claude` `agent:codex`.
Người hoặc agent tạo PR ghi bằng nhãn `agent:*`, không ghi vào tên nhánh.

`pr-check` chỉ báo đỏ để nhắc; repo private trên gói Free không chặn merge được.
