<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Hướng dẫn gỡ cài đặt

### Khi nào cần tới?

Nếu bạn muốn gỡ bỏ Windows, đây là cách thay vì việc xoá phân vùng thủ công để tránh lỗi do con người + viết toàn bộ cái này chỉ để chỉ cách gỡ bỏ.

Nếu muốn relock bootloader, bạn sẽ cần tới phân vùng của máy tính bảng ban đầu (ban đầu/gốc).

### Điều kiện tiên quyết

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [gpt_both0.bin](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin)

### Khôi phục GPT
> Thay ```<gpt_both0.bin>``` bằng đường dẫn tới gpt_both0.bin file.

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Xoá userdata để tránh bootloop và restore FS size
```cmd
fastboot -w
```
