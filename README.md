# Huylighting — Custom DNS Lists

A personally maintained collection of **DNS allowlists and blocklists** for legitimate false-positive fixes and carefully selected custom blocking rules.

The project keeps allow and block rules in separate subscription files. This prevents a rule intended to allow a service from being mixed into a blocking feed, or vice versa.

## Repository contents

| File | Purpose | Rule syntax |
| --- | --- | --- |
| [allowlists.txt](./allowlists.txt) | Allow legitimate services that may be blocked by mistake | `@@||domain.tld^` |
| [blocklists.txt](./blocklists.txt) | Block selected domains | `||domain.tld^` |
| [README.md](./README.md) | Usage and maintenance documentation | — |

## Subscription URLs

Use the matching URL for the matching filter type. **Do not add the allowlist URL as a blocklist or the blocklist URL as an allowlist.**

### Allowlist

```text
https://raw.githubusercontent.com/Huylighting/huylighting-custom-allowlist/main/allowlists.txt
```

- AdGuard Home: **Filters → DNS allowlists → Add allowlist**
- Pi-hole v6+: add as a subscribed allowlist only if your installed version supports the rule format.
- Other products: use only if they support ABP-style network filter rules.

### Blocklist

```text
https://raw.githubusercontent.com/Huylighting/huylighting-custom-allowlist/main/blocklists.txt
```

- AdGuard Home: **Filters → DNS blocklists → Add blocklist**
- Pi-hole v6+: add as a subscribed blocklist only if your installed version supports the rule format.
- Other products: use only if they support ABP-style network filter rules.

The blocklist currently contains comments only; **there are no active block rules yet**. Add it as a subscription after active rules have been reviewed and published.

## Current allowlist entries

| Domain | Service | Reason |
| --- | --- | --- |
| `malighting.com` | MA Lighting | Stage-lighting products and services |
| `azota.vn` | Azota | Education platform |
| `tienganhcomaiphuong.vn` | Tieng Anh Co Mai Phuong | Education website |
| `yourhomework.net` | YourHomework | Education website |
| `console.tailscale.com` | Tailscale | Administration console |
| `login.tailscale.com` | Tailscale | Login and authentication |

## Rule formats

### Allow a domain

```text
@@||example.com^
```

Allows the specified domain and its subdomains on platforms that support ABP network-filter syntax.

### Block a domain

```text
||example.com^
```

Blocks the specified domain and its subdomains on platforms that support ABP network-filter syntax.

Put comments on their own lines, beginning with `!`. Keep allow and block rules in their respective files.

## Compatibility notes

- AdGuard Home supports AdGuard-style DNS filtering rules.
- Pi-hole compatibility depends on the installed version and the subscription/list format it supports. Pi-hole v5 and plain-domain-only import fields may require manual entries or a separately converted domain list.
- uBlock Origin and other ABP-compatible content blockers can use compatible network-filter rules, but they are not DNS-level filters.
- This is not a universal plain-domain list. Do not paste ABP rules into a field that accepts only bare domain names.

Always check the official documentation for the exact product and version before subscribing.

## Maintenance policy

### Allowlist
- Add only domains verified as necessary for a legitimate service.
- Prefer the narrowest domain exception that fixes the issue.
- Do not allow advertising, analytics, or tracking domains merely to restore an unrelated page element.
- Confirm suspected false positives in the DNS query log before adding an exception.

### Blocklist
- Add only domains with a clear, documented blocking purpose.
- Verify the domain and check for possible effects on legitimate services before adding it.
- Avoid broad rules when a narrower rule is sufficient.
- Review reports of breakage and remove obsolete or incorrect rules.

A rule in either list changes filtering behavior for the matching domain. Review changes before subscribing in a production network.

## Reporting an issue

When reporting a false positive or suggesting a block rule, include:
1. The affected service or application.
2. The exact domain.
3. The filtering product or source list, if known.
4. The reason the domain should be allowed or blocked.

## Disclaimer

This is a personal project maintained by Huylighting. It is not an official list endorsed by AdGuard, Pi-hole, or other filtering vendors. Rules are provided as-is; administrators are responsible for reviewing them and testing their effects on their own networks.

---

# Tiếng Việt

Bộ danh sách do Huylighting duy trì, gồm **Allowlist (danh sách cho phép)** và **Blocklist (danh sách chặn)** dành cho lọc DNS và nội dung.

Hai loại quy tắc được tách thành hai tệp riêng để tránh nhầm lẫn giữa quy tắc cho phép và quy tắc chặn.

## Cấu trúc repository

| Tệp | Chức năng | Cú pháp |
| --- | --- | --- |
| [allowlists.txt](./allowlists.txt) | Cho phép các dịch vụ hợp pháp bị chặn nhầm | `@@||domain.tld^` |
| [blocklists.txt](./blocklists.txt) | Chặn các tên miền được lựa chọn | `||domain.tld^` |
| [README.md](./README.md) | Hướng dẫn sử dụng và bảo trì | — |

## Địa chỉ đăng ký

Phải dùng đúng URL theo loại bộ lọc. **Không thêm Allowlist vào mục Blocklist hoặc ngược lại.**

### Allowlist

```text
https://raw.githubusercontent.com/Huylighting/huylighting-custom-allowlist/main/allowlists.txt
```

- AdGuard Home: **Filters → DNS allowlists → Add allowlist**
- Pi-hole v6+: chỉ đăng ký dưới dạng subscribed allowlist nếu phiên bản đang dùng hỗ trợ cú pháp này.
- Nền tảng khác: chỉ sử dụng nếu hỗ trợ quy tắc mạng kiểu ABP.

### Blocklist

```text
https://raw.githubusercontent.com/Huylighting/huylighting-custom-allowlist/main/blocklists.txt
```

- AdGuard Home: **Filters → DNS blocklists → Add blocklist**
- Pi-hole v6+: chỉ đăng ký dưới dạng subscribed blocklist nếu phiên bản đang dùng hỗ trợ cú pháp này.
- Nền tảng khác: chỉ sử dụng nếu hỗ trợ quy tắc mạng kiểu ABP.

Hiện tại `blocklists.txt` mới có phần tiêu đề và chú thích, **chưa có quy tắc chặn đang hoạt động**. Chỉ nên đăng ký sau khi đã bổ sung và kiểm tra các quy tắc thực tế.

## Các tên miền hiện được cho phép

| Tên miền | Dịch vụ | Lý do |
| --- | --- | --- |
| `malighting.com` | MA Lighting | Sản phẩm và dịch vụ chiếu sáng sân khấu |
| `azota.vn` | Azota | Nền tảng giáo dục |
| `tienganhcomaiphuong.vn` | Tiếng Anh Cô Mai Phương | Website giáo dục |
| `yourhomework.net` | YourHomework | Website học tập |
| `console.tailscale.com` | Tailscale | Bảng điều khiển quản trị |
| `login.tailscale.com` | Tailscale | Đăng nhập và xác thực |

## Cú pháp quy tắc

Cho phép tên miền:

```text
@@||example.com^
```

Chặn tên miền:

```text
||example.com^
```

Trên nền tảng hỗ trợ cú pháp ABP, các quy tắc trên áp dụng cho tên miền được chỉ định và các tên miền phụ. Chú thích phải nằm riêng trên từng dòng và bắt đầu bằng ký tự `!`.

## Lưu ý tương thích

- AdGuard Home hỗ trợ quy tắc lọc DNS theo cú pháp AdGuard.
- Khả năng tương thích với Pi-hole phụ thuộc phiên bản và định dạng danh sách được hỗ trợ. Pi-hole v5 hoặc trường nhập chỉ nhận tên miền thuần có thể cần nhập thủ công hoặc chuyển đổi sang định dạng riêng.
- uBlock Origin và các trình chặn tương thích ABP có thể sử dụng quy tắc tương ứng, nhưng đây không phải bộ lọc ở cấp DNS.
- Đây không phải danh sách tên miền thuần dùng được cho mọi sản phẩm. Không dán quy tắc ABP vào trường chỉ nhận tên miền.

Hãy kiểm tra tài liệu chính thức của đúng sản phẩm và phiên bản trước khi đăng ký.

## Nguyên tắc bảo trì

### Allowlist
- Chỉ thêm tên miền đã xác minh là cần thiết cho dịch vụ hợp pháp.
- Ưu tiên ngoại lệ hẹp nhất đủ để khắc phục lỗi.
- Không cho phép tên miền quảng cáo, phân tích hoặc theo dõi chỉ để khôi phục một thành phần không liên quan.
- Kiểm tra Query Log trước khi thêm ngoại lệ.

### Blocklist
- Chỉ thêm tên miền có mục đích chặn rõ ràng và được ghi chú.
- Xác minh tên miền và đánh giá ảnh hưởng đến dịch vụ hợp pháp trước khi thêm.
- Tránh quy tắc quá rộng nếu có thể dùng quy tắc hẹp hơn.
- Xem xét báo cáo lỗi và loại bỏ quy tắc không còn phù hợp.

Mỗi quy tắc đều làm thay đổi hành vi lọc đối với tên miền tương ứng. Hãy kiểm tra thay đổi trước khi sử dụng trên mạng đang hoạt động.

## Báo cáo và đề xuất

Khi báo cáo trường hợp bị chặn nhầm hoặc đề xuất chặn, vui lòng cung cấp:
1. Dịch vụ hoặc ứng dụng bị ảnh hưởng.
2. Tên miền chính xác.
3. Sản phẩm hoặc bộ lọc gây ra vấn đề (nếu biết).
4. Lý do cần cho phép hoặc chặn tên miền đó.

## Tuyên bố

Đây là dự án cá nhân do Huylighting duy trì, không phải danh sách chính thức được AdGuard, Pi-hole hay nhà cung cấp bộ lọc khác chứng nhận. Các quy tắc được cung cấp theo hiện trạng; quản trị viên cần tự xem xét và kiểm tra ảnh hưởng trước khi sử dụng.
