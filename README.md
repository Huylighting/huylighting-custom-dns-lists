# Huylighting — Custom Allowlist for DNS & Ad Blocking

A transparent, community-readable allowlist for legitimate websites and services that may be incorrectly blocked by filters. The project provides compatible rule files for multiple filtering platforms instead of assuming one syntax works everywhere.

The list is maintained by Huylighting. Every exception should have a clear purpose and be reviewed before it is added.

## Supported formats

| File | Format | Intended platforms |
| --- | --- | --- |
| [allowlists.txt](./allowlists.txt) | AdGuard / Adblock Plus (ABP) filter syntax | AdGuard Home, AdGuard DNS filtering, uBlock Origin and other blockers that accept compatible ABP network filters |
| [pihole-allowlist.txt](./pihole-allowlist.txt) | Pi-hole subscribed allowlist using supported ABP-style allow rules | Pi-hole v6 and later |

**Compatibility note:** Not every ad blocker uses the same rule format or supports remote allowlist subscriptions. Use the file documented for your platform. For other DNS filters (for example, products that accept only plain domain entries), convert/import the domains using that product's own documented format. Do not paste ABP rules into a plain-domain-only field.

## Subscribe with AdGuard Home

Add this Raw URL under **Filters → DNS allowlists**:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
```

1. Open the AdGuard Home web interface.
2. Go to **Filters → DNS allowlists**.
3. Choose **Add allowlist**.
4. Name it `Huylighting Custom Allowlist`.
5. Paste the Raw URL and save.
6. Refresh/update the filter lists if needed.

## Subscribe with Pi-hole

Pi-hole v6 added support for subscribing to external allowlists. Add this Raw URL as a **subscribed allowlist** in Pi-hole:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/pihole-allowlist.txt
```

Then update/reload the subscribed lists (Gravity). Make sure the source is configured as an **allowlist**, not a blocklist. Pi-hole's parser supports the ABP-style `@@||example.com^` syntax in subscribed allowlists. Pi-hole v5 does not support external allowlist subscriptions; on older versions, add the required domains manually using Pi-hole's domain allowlist.

See the official [Pi-hole Domain Database documentation](https://docs.pi-hole.net/database/domain-database/) for subscription and syntax details.

## Current entries

| Domain | Service | Purpose |
| --- | --- | --- |
| `malighting.com` | MA Lighting | Stage-lighting products and services |
| `azota.vn` | Azota | Education and learning platform |
| `console.tailscale.com` | Tailscale | Administration console |
| `login.tailscale.com` | Tailscale | Login and authentication |

The AdGuard/ABP rules and Pi-hole subscription rules are maintained separately so each platform has a clearly named source file.

## Rule syntax

The compatible ABP-style allow rule is:

```text
@@||example.com^
```

It allows the domain and its subdomains on platforms that support this syntax. In this repository, lines beginning with `!` are comments.

## Reporting a false positive

Before requesting an exception:

1. Open the filtering platform's query log.
2. Reproduce the website or service issue.
3. Identify the exact domain that was blocked.
4. Confirm that the domain is genuinely required for the service.
5. Explain why the block appears to be a false positive.

Please include the affected service, exact blocked domain, filtering product/list (if known), and a short reason the domain is needed.

Do not add broad exceptions when a narrower rule is sufficient. Do not allow advertising, analytics, or tracking domains just to restore an unrelated page element. An allowlist exception reduces filtering for the matching domain and may affect privacy or ad blocking.

## Maintenance and scope

This is a personally maintained project, not an official list endorsed by AdGuard, Pi-hole, or other filtering vendors. Entries may be added, changed, or removed as services evolve and reports are reviewed.

The project focuses on **false-positive fixes for legitimate services**. It is not intended to disable ad blocking globally or to guarantee that every website feature will work.

Use the list only if you trust the maintainer and have reviewed its contents. Administrators are responsible for deciding whether each exception is appropriate for their network.

## Links

- **AdGuard / ABP Raw list:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
- **Pi-hole v6 Raw list:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/pihole-allowlist.txt
- **Repository:** https://github.com/Huylighting/adguard-custom-allowlist

---

# Tiếng Việt

Danh sách cho phép (allowlist) này dành cho các website và dịch vụ hợp pháp có thể bị bộ lọc chặn nhầm. Dự án cung cấp các tệp quy tắc phù hợp với nhiều nền tảng lọc DNS và quảng cáo, thay vì giả định rằng mọi nền tảng đều dùng chung một cú pháp.

Danh sách do Huylighting duy trì. Mỗi ngoại lệ cần có mục đích rõ ràng và được kiểm tra trước khi thêm vào.

## Các định dạng được hỗ trợ

| Tệp | Định dạng | Nền tảng dự kiến |
| --- | --- | --- |
| [allowlists.txt](./allowlists.txt) | Cú pháp bộ lọc AdGuard / Adblock Plus (ABP) | AdGuard Home, AdGuard DNS, uBlock Origin và các trình chặn hỗ trợ bộ lọc mạng tương thích ABP |
| [pihole-allowlist.txt](./pihole-allowlist.txt) | Allowlist đăng ký trong Pi-hole, sử dụng quy tắc cho phép kiểu ABP được hỗ trợ | Pi-hole phiên bản 6 trở lên |

**Lưu ý về khả năng tương thích:** Không phải trình chặn quảng cáo nào cũng dùng cùng định dạng quy tắc hoặc hỗ trợ đăng ký danh sách từ xa. Hãy sử dụng đúng tệp được hướng dẫn cho nền tảng của bạn. Với các bộ lọc DNS khác chỉ chấp nhận tên miền thuần, hãy chuyển đổi hoặc nhập tên miền theo định dạng được tài liệu chính thức của sản phẩm đó hướng dẫn. Không dán quy tắc ABP vào trường chỉ chấp nhận tên miền thuần.

## Đăng ký danh sách trên AdGuard Home

Thêm Raw URL sau trong mục **Filters → DNS allowlists**:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
```

1. Mở giao diện quản trị AdGuard Home.
2. Truy cập **Filters → DNS allowlists**.
3. Chọn **Add allowlist**.
4. Đặt tên là `Huylighting Custom Allowlist`.
5. Dán Raw URL và lưu lại.
6. Làm mới/cập nhật danh sách bộ lọc nếu cần.

## Đăng ký danh sách trên Pi-hole

Pi-hole phiên bản 6 đã hỗ trợ đăng ký allowlist từ bên ngoài. Thêm Raw URL sau làm **subscribed allowlist** trong Pi-hole:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/pihole-allowlist.txt
```

Sau đó cập nhật/tải lại các danh sách đã đăng ký (Gravity). Hãy bảo đảm nguồn được cấu hình là **allowlist**, không phải blocklist. Bộ phân tích của Pi-hole hỗ trợ cú pháp cho phép kiểu ABP `@@||example.com^` trong các allowlist đã đăng ký.

Pi-hole phiên bản 5 không hỗ trợ đăng ký allowlist từ xa. Với phiên bản cũ hơn, bạn cần thêm thủ công các tên miền cần thiết trong mục allowlist tên miền của Pi-hole.

Tham khảo tài liệu chính thức [Pi-hole Domain Database](https://docs.pi-hole.net/database/domain-database/) để biết thêm về đăng ký danh sách và cú pháp.

## Các mục hiện có

| Tên miền | Dịch vụ | Mục đích |
| --- | --- | --- |
| `malighting.com` | MA Lighting | Sản phẩm và dịch vụ chiếu sáng sân khấu |
| `azota.vn` | Azota | Nền tảng giáo dục và học tập |
| `console.tailscale.com` | Tailscale | Bảng điều khiển quản trị |
| `login.tailscale.com` | Tailscale | Đăng nhập và xác thực |

Các quy tắc AdGuard/ABP và quy tắc đăng ký cho Pi-hole được duy trì trong hai tệp riêng biệt, giúp xác định rõ nguồn danh sách dành cho từng nền tảng.

## Cú pháp quy tắc

Ví dụ quy tắc cho phép kiểu ABP tương thích:

```text
@@||example.com^
```

Trên các nền tảng hỗ trợ cú pháp này, quy tắc sẽ cho phép tên miền được chỉ định và các tên miền phụ của nó. Trong repository này, các dòng bắt đầu bằng ký tự `!` là chú thích.

## Báo cáo trường hợp bị chặn nhầm

Trước khi đề xuất thêm một ngoại lệ:

1. Mở nhật ký truy vấn (Query Log) của nền tảng lọc DNS.
2. Thử truy cập lại website hoặc dịch vụ đang gặp lỗi.
3. Xác định chính xác tên miền bị chặn.
4. Kiểm tra xem tên miền đó có thực sự cần thiết cho dịch vụ hay không.
5. Giải thích vì sao đây có thể là trường hợp bị chặn nhầm.

Khi gửi báo cáo, vui lòng cung cấp tên dịch vụ bị ảnh hưởng, tên miền chính xác, sản phẩm/danh sách bộ lọc gây chặn (nếu biết) và lý do ngắn gọn vì sao cần cho phép tên miền đó.

Không thêm ngoại lệ quá rộng nếu có thể sử dụng quy tắc hẹp hơn. Không cho phép các tên miền quảng cáo, phân tích hoặc theo dõi chỉ để khôi phục một thành phần không liên quan của trang web. Ngoại lệ allowlist sẽ giảm mức lọc đối với tên miền tương ứng và có thể ảnh hưởng đến quyền riêng tư hoặc khả năng chặn quảng cáo.

## Bảo trì và phạm vi dự án

Đây là dự án cá nhân do Huylighting duy trì, không phải danh sách chính thức được AdGuard, Pi-hole hay nhà cung cấp bộ lọc khác chứng nhận. Các mục có thể được thêm, chỉnh sửa hoặc xóa khi dịch vụ thay đổi và báo cáo được xem xét.

Dự án tập trung xử lý **các trường hợp chặn nhầm dịch vụ hợp pháp**. Mục tiêu không phải tắt toàn bộ khả năng chặn quảng cáo và cũng không bảo đảm mọi chức năng của tất cả website đều hoạt động.

Chỉ sử dụng danh sách nếu bạn tin tưởng người duy trì và đã xem xét nội dung. Quản trị viên chịu trách nhiệm quyết định từng ngoại lệ có phù hợp với mạng của mình hay không.

## Liên kết

- **Danh sách Raw dành cho AdGuard / ABP:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
- **Danh sách Raw dành cho Pi-hole v6:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/pihole-allowlist.txt
- **Repository:** https://github.com/Huylighting/adguard-custom-allowlist
