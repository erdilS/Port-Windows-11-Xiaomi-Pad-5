<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Chạy Windows trên Xiaomi Pad 5

## Gỡ cài đặt

### Tại sao nó lại cần thiết?

Nếu bạn muốn gỡ cài đặt windows, cách này được sử dụng thay vì xóa phân vùng theo cách thủ công để tránh lỗi của con người + viết toàn bộ hướng dẫn dành riêng cho việc gỡ cài đặt.

Nếu bạn muốn khóa lại bootloader của mình, bạn sẽ cần có bảng phân vùng gốc.

### Điều kiện tiên quyết

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)

## Khôi phục GPT


> Thay thế <gpt_both0.bin> với đường dẫn tới tệp gpt_both0.bin. bạn có thể tìm nó ở [releases page](../../../../releases/)


# Khôi phục bảng phân vùng gốc

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Xoá dữ liệu người dùng để tránh bị vòng lặp khởi động và khôi phục kích thước FS
```cmd
fastboot -w
```
