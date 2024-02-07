<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

> [!WARNING]
> **VUI LÒNG KHÔNG SỬ DỤNG HƯỚNG DẪN VIDEO LỖI THỜI TRÊN YOUTUBE HOẶC BẤT KỲ NỀN TẢNG NÀO KHÁC! NHỮNG VIDEO NÀY ĐÃ LỖI THỜI VÀ BẠN CÓ THỂ GẠCH THIẾT BỊ CỦA MÌNH BẰNG CÁCH SỬ DỤNG NÓ! NẾU BẠN CẦN MỘT VIDEO HƯỚNG DẪN, SỬ DỤNG NÀY [HƯỚNG DẪN VIDEO MỚI](https://www.youtube.com/watch?v=rGPbdFq7gKs) TỪ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Hướng dẫn cài đặt

## Cài đặt Windows

### Điều kiện tiên quyết
  
- [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)

- [ARM Windows esd](https://worproject.com/esd) (Select - Version:  ```11 ``` Build:  ```22631.2861 ``` Architecture:  ```ARM64 ``` Edition:  ```CLIENT ``` Language:  ```select your language```)
  
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)


### Boot vào recovery để tiếp tục cài Windows
> Nếu nó yêu cầu bạn chạy nó một lần nữa, hãy làm như vậy
```cmd
fastboot boot <recovery.img>
```


#### Thực thi msc
```cmd
adb shell msc
```

### Gán kí tự cho ổ đĩa
  

#### Khởi động Windows disk manager (Windows trình quản lí ổ đĩa)

> Duy nhất Xiaomi Pad 5 được nhận diện là ổ đĩa

```cmd
diskpart
```


#### Gán `X` cho ổ Windows

#### Chọn ổ Windows của máy tính bảng
> Dùng lệnh `list volume` để kiếm, thường nó tên là "WINNABU"

```diskpart
select volume <number>
```

#### Gán kí tự X
```diskpart
assign letter=x
```

### Gán `Y` cho ổ ESP

#### Chọn ổ esp volume của tablet
> Dùng lệnh `list volume` để kiếm, thường nó tên là "ESPNABU"

```diskpart
select volume <number>
```

#### Gán kí tự Y

```diskpart
assign letter=y
```

#### Thoát diskpart
```diskpart
exit
```

  
  

### Cài đặt
> [!NOTE]
> **Bây giờ hãy chạy dấu nhắc lệnh với tư cách quản trị viên**

> Thay `<path/to/install.wim>` bằng đường dẫn thực tế của `install.wim`.

> `install.wim` nằm ở mục source folder, bên trong file ISO
> Bạn có thể kiếm nó bằng cách giải nén file ISO

> Nó cũng có thể được đặt tên **install.esd.** Thay đổi đường dẫn tương ứng.
```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Cài Drivers

> Bạn có Thể tải Xuống Trình Điều khiển [tại đây](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Khi nó yêu cầu bạn "Inter Drive letter..." loại **`X:`**


> Không chạy nó với tư cách quản trị viên, nó sẽ yêu cầu quyền quản trị viên khi cần thiết.
```cmd
Mở thư mục Với Trình Điều Khiển và chạy OfflineUpdater.cmd
```
### Tạo windows bootloader tới EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
## Xóa ký tự ổ ĐĨA CHO ESPNABU để tránh sự xuất hiện của ký tự ổ đĩa ảo
```cmd
mountvol y: /d
```


## Boot vào Windows

### Tạo backup cho file boot hiện hành
> [!NOTE]
> **Bây giờ quay lại dấu nhắc lệnh công cụ nền tảng**

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Đẩy file backup lên máy tính

```cmd
adb pull /tmp/boot.img
```


### Reboot vào bootloader 

```cmd
adb reboot bootloader
```

### Tải và flash UEFI image
> Tải XUỐNG [HÌNH ẢNH UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
```cmd
fastboot flash boot <đường dẫn đến hình ảnh>
```
## Khởi động Lại Windows
```cmd
fastboot reboot
```
> [!NOTE]
> Trong Lần Khởi Động Windows Đầu tiên, Nó sẽ không thấy bất kỳ mạng Wi-Fi nào, chỉ cần khởi động lại bằng cách giữ nút nguồn và sau khi khởi động lại khi bạn thử kết nối với mạng yuor và bạn thấy "kem" nhấp vào "thử lại" 7 lần

### Boot trở lại vào Android
> Dùng backup boot của bạn và flash từ fastboot

```cmd
fastboot flash boot boot.img
```

## Xong rồi!
> Bạn có thể tham gia của chúng tôi [Telegram trò chuyện](https://t.me/nabuwoa) nhận tin tức mới nhất về dự án
### [Bước cuối cùng: Thiết Lập Khởi Động Kép](dualboot-vi.md)
