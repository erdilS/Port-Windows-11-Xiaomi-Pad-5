<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Cài đặt

### Phân vùng cho thiết bị

### Điều kiện tiên quyết

- [Recovery Image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Chú ý nha:
> [!WARNING]
>  Nếu bạn vô tình xoá bất kì phân vùng vào bằng kí tự diskpart hoặc windows sẽ gửi một lệnh ufs rằng có gì đó sai sai làm bạn bị xoá hết file ufs.
>
> Dữ liệu của bạn sẽ bị xoá sạch! Hãy backup từ bây giờ nếu cần thiết.
> 
> Những lệnh sử dụng ở đây đều đã được thử nghiệm thành công
> 
> Bỏ qua cảnh báo `udevadm`
> 
> Tuyệt đối KHÔNG nhập một lệnh 2 lần
> 
> Trong chế độ Recovery, màn hình không hoạt động
> 
> TUYỆT ĐỐI KHÔNG khởi động lại máy tính bảng, nếu cần hỗ trợ hãy hỏi tại [Telegram chat](https://t.me/nabuwoa)
>
>
> TUYỆT ĐỐI KHÔNG copy toàn bộ lệnh rồi làm 1 lần duy nhất. Câu lệnh sẽ cần thời gian để chạy nên không được làm thế đâu!
>
> KHÔNG ĐƯỢC SAI LẦM. MỘT CÂU LỆNH SAI CÓ THỂ KHIẾN MÁY BẠN KHÔNG BAO GIỜ HOẠT ĐỘNG TRỞ LẠI!!!


#### Boot recovery từ PC bằng lệnh
```cmd
fastboot boot <recovery.img>
```
> Nếu bạn đã cài TWRP, chỉ cần giữ nút Nguồn và Vol+ để khởi động

#### Khởi động ADB shell
```cmd
adb shell
```

#### Phân vùng cài đặt
> Để phân vùng Windows có thể hoạt động
```sh
sgdisk --resize-table 64 /dev/block/sda
```

#### Bắt đầu chia
```sh
parted /dev/block/sda
```

#### Xoá phân vùng `userdata`
> Hãy đảm bảo rằng 31 là số của userdata trước khi chạy (Nhìn vào xem phải 31 là user data hay không)
>  `print all`
```sh
rm 31
```

#### Tạo phân vùng
> Nếu có bất kì thông báo nào bảo bạn "ignore" (bỏ qua), cứ ấn i và enter


<details>
<summary><b><strong>Cho máy 128GB</strong></b></summary>

- Tạo phân vùng ESP (chứa Windows bootloader data và EFI files)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Tạo phân vùng chính để cài Windows
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Phân vùng cho Android hoạt động
```sh
mkpart userdata ext4 70.2GB 126GB
```
  </summary>
</details>

<details>
<summary><b><strong>Cho máy 256GB</strong></b></summary>

- Tạo phân vùng ESP (chứa Windows bootloader data và EFI files)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Tạo phân vùng chính để cài Windows
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- Phân vùng cho Android hoạt động
```sh
mkpart userdata ext4 120.8GB 254GB
```

  </summary>
</details>


#### Tạo phân vùng ESP có thể boot để EFI image có thể nhận diện
```sh
set 31 esp on
```

#### Thoát phân chia (parted)
```sh
quit
```
#### Reboot vào bootloader
```sh
reboot bootloader
```

#### Boot vào recovery
```cmd
fastboot boot <recovery.img>
```

#### Bắt đầu adb shell tiếp
```cmd
adb shell
```

#### Định dạng phân vùng
-  Định dạng phân vùng ESP là FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Định dạng phân vùng Windows là NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Định dạng userdata
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```


#### Hãy kiểm tra xem Android có hoạt động hay không
Chỉ cần khởi động lại xem Android có chạy hay không
Nếu không chạy, lặp lại hoặc hiệu ứng load không dừng, hãy dùng MIUI recovery hoặc các recovery khác để wipe data.

### [Bước tiếp theo: Cài đặt Windows](/guide/Vietnamese/2-install-vi.md)
