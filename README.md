# namnd-org/.github

![group](https://img.shields.io/badge/group-platform-24292f?style=flat-square)
![status](https://img.shields.io/badge/status-live-2ea44f?style=flat-square)
![platform](https://img.shields.io/badge/GitHub-org_defaults-000000?style=flat-square&logo=github&logoColor=white)
![stack](https://img.shields.io/badge/GitHub_Actions-YAML-2088FF?style=flat-square&logo=githubactions&logoColor=white)

> Mặc định dùng chung cho mọi repo của namnd-org: mẫu README, mẫu PR, mẫu issue, workflow mẫu và workflow `pr-check`.

Repo nào có file riêng cùng loại thì file riêng được dùng thay.

| Đường dẫn | Dùng để |
|---|---|
| `README_TEMPLATE.md` | Khung README chung cho mọi repo (xem mục Mẫu README); bản chạy được nằm ở `namnd-org/repo-template` |
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

## Tạo repo mới

Repo mới tạo từ [`namnd-org/repo-template`](https://github.com/namnd-org/repo-template): có sẵn README theo mẫu, `pr-check.yml`, `CREDITS.md`, `docs/`, `.gitignore`.
GitHub không chép nhãn, description, topics theo template, nên chạy đủ 3 lệnh:

```sh
gh repo create namnd-org/<slug> --private --template namnd-org/repo-template \
  --description "[<group>] <Tên> — <một câu>" --clone
gh label clone namnd-org/repo-template -R namnd-org/<slug> --force
gh repo edit namnd-org/<slug> --add-topic <group> --add-topic <stack>
```

Sau đó điền README (thay mọi `<...>`, xoá khối chú thích). Khi sửa `README_TEMPLATE.md` ở đây, sửa luôn `README.md` của `repo-template`.

## Mẫu README

Mọi repo dùng [`README_TEMPLATE.md`](README_TEMPLATE.md): tên sản phẩm, hàng thẻ, một câu mô tả, dòng link, rồi 4 mục ngắn
**Chạy nhanh · Cấu trúc · Deploy · Tài liệu**. Tối đa khoảng 50 dòng; phần dài đưa vào `docs/`.

Thẻ đặt đúng thứ tự, tối đa 7 thẻ. Chỉ thẻ `status` mang màu theo trạng thái:

| Thẻ | Giá trị | Màu |
|---|---|---|
| `group` | `namnd` `phyra` `platform` `capture-action` `poc` `fun-labs` (khớp tiền tố `[...]` trong description) | `24292f` |
| `status` | `live` · `beta` (TestFlight, chưa public) · `poc` · `wip` (chưa chạy được) · `archived` | `2ea44f` · `0969da` · `fb8500` · `d4a72c` · `8c959f` |
| `platform` | `iOS 18+`, `Web`, `Worker`, `Tool`… | `000000`, logo `apple` / `cloudflare` / `github` |
| `stack` | `Swift 6 · SwiftUI`, `TypeScript · Astro`, `Go · WASM`, `Expo · SDK 56`… | màu brand, logo simple-icons |
| `infra` | `Cloudflare · Workers + D1 (+ R2)` | `F38020` |
| `ci` | Chỉ khi repo có workflow build/test (không tính `pr-check`) | badge gốc của GitHub Actions |
| `live` | Domain đang chạy, bấm vào mở được | `0969da` |

Repo private nên chỉ dùng badge tĩnh `img.shields.io/badge/...`: badge động (stars, last commit, release, coverage) không đọc được repo private.
Không dùng badge version vì badge tĩnh sẽ cũ; version xem ở TestFlight hoặc Releases. Chữ trên thẻ chỉ ASCII; nội dung README viết tiếng Việt.
