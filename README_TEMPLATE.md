<!--
Mẫu README namnd-org v1. Quy ước thẻ: README.md của namnd-org/.github, mục "Mẫu README".
- Tối đa ~50 dòng. Chi tiết (kiến trúc, vận hành, bằng chứng phát hành) để trong docs/.
- Thẻ đúng thứ tự: group · status · platform · stack · infra · (ci) · (live). Tối đa 7 thẻ.
- Chỉ badge tĩnh img.shields.io/badge (repo private: badge động báo lỗi). Không badge version.
- Chữ trên thẻ chỉ ASCII. Trong URL: dấu cách = _ , "+" = %2B , "-" = -- , "_" = __ .
- Bỏ dòng/mục không áp dụng (không có web thì bỏ thẻ live, không có CI thì bỏ thẻ ci).
- Xoá khối chú thích này khi dùng.
-->
# <Tên sản phẩm>

![group](https://img.shields.io/badge/group-<group>-24292f?style=flat-square)
![status](https://img.shields.io/badge/status-<live|beta|poc|wip|archived>-<2ea44f|0969da|fb8500|d4a72c|8c959f>?style=flat-square)
![platform](https://img.shields.io/badge/<iOS|Web|Worker|Tool>-<chi_tiết>-000000?style=flat-square&logo=<apple|cloudflare>&logoColor=white)
![stack](https://img.shields.io/badge/<Ngôn_ngữ>-<Framework>-<màu_brand>?style=flat-square&logo=<logo>&logoColor=white)
![infra](https://img.shields.io/badge/Cloudflare-<Workers_%2B_D1>-F38020?style=flat-square&logo=cloudflare&logoColor=white)
[![ci](https://github.com/namnd-org/<repo>/actions/workflows/<file>.yml/badge.svg)](https://github.com/namnd-org/<repo>/actions/workflows/<file>.yml)
[![live](https://img.shields.io/badge/live-<domain>-0969da?style=flat-square)](https://<domain>)

> <Một câu: sản phẩm làm gì, cho ai. Trùng description của repo, bỏ tiền tố [group].>

**Live:** <url> · **Admin:** <url> · **App Store / TestFlight:** <nhóm hoặc link> · **Repo liên quan:** <repo>

## Chạy nhanh

```sh
<cài đặt>
<chạy local>
<test>
```

## Cấu trúc

| Thư mục | Nội dung |
|---|---|
| `<dir>/` | <một dòng> |

## Deploy

<1–3 dòng: lệnh deploy, hoặc "push main → GitHub Actions <workflow>">.

## Tài liệu

- [<Tên>](docs/<FILE>.md) · [<Tên>](docs/<FILE>.md)
