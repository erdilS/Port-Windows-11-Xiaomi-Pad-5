Bước này là bắt buộc để chúng ta có thể tạo ra các phân vùng nơi mà Windows sẽ được cài đặt

## Ghi chú:
> **Cảnh báo** nếu bạn xoá sai bất kì phân vùng nào trong diskpart sau này hoặc ngay bây giờ, windows sẽ gửi lệnh ufs bị hiểu sai có thể dẫn đến việc toàn bộ ufs của bạn sẽ bị xoá sạch 

- Tất cả dữ liệu của bạn sẽ bị xoá sạch! Hãy sao lưu nếu cần thiết.
- Những câu lệnh sau đây đã được thử nghiệm. 
- Bỏ qua những cảnh báo `udevadm`.
- Không được chạy cùng một lệnh hai lần 
- Ở chế độ recovery, màn hình sẽ không hoạt động.
- KHÔNG KHỞI ĐỘNG LẠI ĐIỆN THOẠI CỦA BẠN nếu như bạn đã làm sai bước nào đó, hãy yêu cầu trợ giúp trong [Telegram chat](https://t.me/nabuwoa)

#### Khởi động vào recovery thông qua PC với lệnh
```cmd
fastboot boot <recovery.img>
```
> Nếu như bạn đã cài đặt TWRP, chỉ cần giữ nút nguồn và nút tăng âm lượng khi khởi động

#### Ngắt kết nối tất cả các phân vùng
```cmd
adb shell twrp unmount /data
```

## Đẩy tệp parted tới /tmp/
> Để phân chia lại các phân vùng
```cmd
adb push parted /tmp/
```

## Bắt đầu chế độ ADB shell
```cmd
adb shell
```

### Thay đổi kích thước bảng phân vùng
> Vì thế, các phân vùng Windows sẽ phù hợp 
```sh
sgdisk --resize-table 64 /dev/block/sda
```

### Sửa lại các quyền của parted
```sh
chmod 755 /tmp/parted
```

### Bắt đầu parted
```sh
/tmp/parted /dev/block/sda
```


### Xoá phân vùng `userdata`
> Bạn có thể chắc chắn rằng 31 là số phân vùng userdata bằng cách chạy lệnh
>  `print all`
```sh
rm 31
```

### Tạo phân vùng
> Nếu bạn nhận được bất kỳ thông báo cảnh báo nào yêu cầu bạn bỏ qua hoặc hủy, chỉ cần nhập i và nhấn enter

#### Đối với máy 128Gb:

- Tạo phân vùng ESP (nơi sẽ lưu trữ dữ liệu bộ nạp khởi động Windows và tệp EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Tạo phân vùng chính nơi mà Windows sẽ được cài đặt vào đó
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Tạo phân vùng dữ liệu cho hệ điều hành Android
```sh
mkpart userdata ext4 70.2GB 126GB
```

#### Đối với máy 256Gb:

- Tạo phân vùng ESP (nơi sẽ lưu trữ dữ liệu bộ nạp khởi động Windows và tệp EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Tạo phân vùng chính nơi mà Windows sẽ được cài đặt vào đó
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- Tạo phân vùng dữ liệu cho hệ điều hành Android
```sh
mkpart userdata ext4 120.8GB 254GB
```


### Làm cho phân vùng ESP có thể khởi động được để EFI có thể phát hiện ra
```sh
set 31 esp on
```

### Thoát parted
```sh
quit
```
### Khởi động vào bootloader
```sh
reboot bootloader
```

### Khởi động vào recovery
```cmd
fastboot boot <recovery.img>
```

### Vào lại chế độ adb ở PC bạn
```cmd
adb shell
```

### Định dạng lại các phân vùng
-  Định dạng phân vùng ESP là FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Định dạng phân vùng Windows dưới dạng NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Định dạng phân vùng userdata của Android
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```

### Kiểm tra xem Android có còn khởi động được không
Chỉ cần khởi động lại điện thoại của bạn, và xem Android có còn hoạt động không.
Nếu nó không khởi động hoặc bị treo, hãy sử dụng công cụ khôi phục của MIUI hoặc các phục hồi khác để xóa dữ liệu.

## [Bước tiếp theo: Cài đặt Windows](/guide/Vietnamese/2-cài-đặt-vi.md)
