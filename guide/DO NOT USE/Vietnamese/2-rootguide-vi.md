<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Nhận quyền root
> [!NOTE]
> **Nếu bạn đã root thì bỏ qua bước này và chuyển sang trang tiếp theo**

### Điều kiện tiên quyết
- ```Não```
  
- [```Sao lưu khởi động Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (mà bạn đã sao lưu ở trang hướng dẫn đầu tiên)


## Khởi động bản vá

- Sao chép ```normal_boot.img``` tập tin từ ```platform tools``` thư mục vào máy tính bảng

- Tải xuống và cài đặt [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) lên máy tính bảng
  
-  Mở ứng dụng Magisk và nhấp vào ```Install``` cái nút. Lựa chọn ```Select and Patch a File``` tùy chọn và tìm ```normal_boot.img``` tập tin mà bạn đã sao chép vào máy tính bảng. Nhấn vào ```Let's Go``` và đợi quá trình vá lỗi hoàn tất.
  
- Sao chép ```magisk_patched....img``` tập tin từ ```Downloads``` thư mục trên máy tính bảng vào ```platform tools``` thư mục trên máy tính của bạn.

- Khởi động lại để fastboot
  
- Mở dấu nhắc lệnh trong platform tools thư mục

## Khởi động được vá flash
 > Thay thế `<magisk_patched.img>` với thực tế ```magisk_patched.img``` tên/đường dẫn.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Bước tiếp theo: Cài đặt Windows](/guide/Vietnamese/3-install-vi.md)

