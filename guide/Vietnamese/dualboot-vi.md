<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Dualboot cho Windows và Android

### Điều kiện tiên quyết

- Cần não

- Android đã root và bản backup của Android boot

- [Tải Files](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Phía Windows Dual Boot

- Cài [Cygwin](https://www.cygwin.com/setup-x86_64.exe) với coreutils (nó sẽ cài đặt mặc định)

- Sửa tên file boot thành boot.img

- Đặt file boot Android vào C:\ (C:\boot.img)

- Chạy file bat bằng quyền Administrator

### Phía Android Dual Boot

- Cài switchtowin.apk lên thiết bị.

- Sửa file UEFI thành boot.img

- Đặt file UEFI ở /sdcard/windows (/sdcard/windows/boot.img)

- Khởi động app và cấp quyền root

- Ấn vào "Switch to Windows" khi muốn đổi qua Windows.

