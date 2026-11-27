# Huylighting — AdGuard Home Custom Allowlist

Danh sách ngoại lệ DNS cá nhân dành cho **AdGuard Home**. Repository này lưu các quy tắc cho phép những tên miền bị bộ lọc DNS chặn nhầm nhưng cần thiết cho việc học tập, công việc và sử dụng dịch vụ.

## Sử dụng

Thêm URL Raw bên dưới vào AdGuard Home dưới dạng **DNS allowlist**:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
```

### Các bước cấu hình

1. Mở giao diện quản trị AdGuard Home.
2. Vào **Filters → DNS allowlists**.
3. Chọn **Add allowlist**.
4. Đặt tên, ví dụ: `Huylighting Custom Allowlist`.
5. Dán URL Raw ở trên vào trường URL rồi lưu.
6. Cập nhật danh sách bộ lọc nếu AdGuard Home chưa tự tải ngay.

> Dùng URL Raw (`raw.githubusercontent.com`), không dùng URL trang hiển thị trên GitHub (`github.com/.../blob/...`).

## Quy tắc hiện có

| Tên miền | Mục đích |
| --- | --- |
| `malighting.com` | MA Lighting — thiết bị và giải pháp điều khiển ánh sáng sân khấu |
| `azota.vn` | Azota — nền tảng học tập và giáo dục |

Các quy tắc được lưu trong [allowlists.txt](./allowlists.txt).

## Cú pháp

Danh sách sử dụng cú pháp lọc tương thích với AdGuard:

- `@@||example.com^` — cho phép tên miền `example.com` và các tên miền con.
- Mỗi quy tắc nằm trên một dòng riêng.
- Dòng bắt đầu bằng `!` là chú thích.

Ví dụ:

```text
@@||example.com^
```

## Xử lý khi website vẫn chưa truy cập được

Allowlist chỉ gỡ chặn những tên miền khớp với quy tắc. Một website có thể tải nội dung từ nhiều tên miền khác nhau.

1. Mở **Query Log** trong AdGuard Home.
2. Thử truy cập lại website.
3. Kiểm tra các truy vấn bị chặn có liên quan trực tiếp đến website.
4. Chỉ bổ sung ngoại lệ khi đã xác định tên miền đó cần thiết và bị chặn nhầm.

Không nên cho phép hàng loạt tên miền CDN, quảng cáo hoặc theo dõi chỉ để sửa một lỗi hiển thị. Quy tắc quá rộng có thể làm giảm hiệu quả lọc DNS.

## Đề xuất cập nhật

Đây là allowlist cá nhân do Huylighting duy trì. Khi đề xuất thêm tên miền, hãy cung cấp:
- Website hoặc dịch vụ cần truy cập.
- Tên miền bị AdGuard Home chặn trong Query Log.
- Lý do tên miền đó cần được cho phép.

## Lưu ý

- Allowlist không bảo đảm mọi thành phần của website đều hoạt động nếu còn tên miền phụ thuộc khác bị chặn.
- Chỉ sử dụng danh sách nếu bạn tin tưởng người duy trì repository.
- Người quản trị AdGuard Home vẫn chịu trách nhiệm kiểm tra các quy tắc trước khi áp dụng.

---

**Raw list:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
