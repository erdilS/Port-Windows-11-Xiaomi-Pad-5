<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

> [!WARNING]
> **VUI LÒNG KHÔNG SỬ DỤNG HƯỚNG DẪN VIDEO LỖI THỜI TRÊN YOUTUBE HOẶC BẤT KỲ NỀN TẢNG NÀO KHÁC! NHỮNG VIDEO NÀY ĐÃ LỖI THỜI VÀ BẠN CÓ THỂ GẠCH THIẾT BỊ CỦA MÌNH BẰNG CÁCH SỬ DỤNG NÓ! NẾU BẠN CẦN MỘT VIDEO HƯỚNG DẪN, SỬ DỤNG NÀY [HƯỚNG DẪN VIDEO MỚI](https://youtu.be/BbgTbTGbXYg) TỪ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Hướng dẫn cài đặt

## Cài đặt Windows

### Điều kiện tiên quyết
  
- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```ARM Windows esd```](https://worproject.com/esd) (chọn - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```chọn ngôn ngữ của bạn```)
  
- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)


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
assign letter x
```

### Gán `Y` cho ổ ESP

#### Chọn ổ esp volume của tablet
> Dùng lệnh `list volume` để kiếm, thường nó tên là "ESPNABU"

```diskpart
select volume <number>
```

#### Gán kí tự Y

```diskpart
assign letter y
```

#### Thoát diskpart
```diskpart
exit
```

  
  

### Cài đặt
> Thay thế `<path\to\install.esd>` bằng đường dẫn thực tế của install.esd (nó cũng có thể được đặt tên là install.wim) 

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
``` 

> Nếu bạn gặp `Error 87`, hãy kiểm tra chỉ mục hình ảnh của bạn bằng `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, sau đó thay thế `index:6` bằng số chỉ mục thực tế của Windows 11 Pro trong hình ảnh của bạn 

### Cài Drivers

> Bạn có Thể tải Xuống Trình Điều khiển [tại đây](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> nếu nó ghi `"Automatic WINNABU detection failed! Enter Drive Letter manually"`, nhập **`X`**  

```cmd
Mở thư mục Với Trình Điều Khiển và chạy OfflineUpdater.cmd
```
### Tạo windows bootloader tới EFI
> Nếu xảy ra lỗi khi sao chép tệp khởi động, hãy kiểm tra `diskpart` để xem ESPNABU có còn chữ Y hay không. Nếu không, hãy thêm bất kỳ chữ cái nào khác (chẳng hạn như K) và thay thế chữ Y trong lệnh dưới đây bằng chữ cái đã nói tương ứng
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
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Reboot vào bootloader 

```cmd
adb reboot bootloader
```

### Tải và flash UEFI image
> Tải XUỐNG [HÌNH ẢNH UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
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
Sau Khi Windows đã được thiết lập, nhấn nút khởi động lại Trong Windows (KHÔNG TẮT MÁY), sau đó khi Nó khởi động lại, giữ `giảm âm lượng` + `quyền lực` để khởi động lại trở lại fastboot
> Sử dụng hình ảnh khởi động sao lưu của bạn và flash nó trong fastboot để trở Về Android


```cmd
fastboot flash boot rooted_boot.img
```
```cmd
fastboot reboot
```
## Xong rồi!
> Bạn có thể tham gia của chúng tôi [Telegram trò chuyện](https://t.me/nabuwoa) nhận tin tức mới nhất về dự án
### [Bước cuối cùng: Thiết Lập Khởi Động Kép](dualboot-vi.md)
