## Gỡ cài đặt Windows


> Thay thế <gpt_both0.bin> với đường dẫn tới tệp gpt_both0.bin. bạn có thể tìm nó ở [releases page](../../../../releases/)


# Khôi phục bảng phân vùng gốc

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Xoá dữ liệu người dùng để tránh bị vòng lặp khởi động và khôi phục kích thước FS
```cmd
fastboot -w
```
