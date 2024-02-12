<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Khởi động song song Android và Windows một cách liền mạch 

### Điều kiện tiên quyết 
- Não 
- Máy tính bảng đã root 
- Windows được cài đặt trên máy tính bảng 
- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img)
- [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [StA Installer](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Thiết lập ứng dụng khởi động kép 
> Hướng dẫn này giả sử bạn đã root, nếu chưa, vui lòng làm theo hướng dẫn [hướng dẫn root](2-rootguide-vi.md) Đầu tiên.

### Cài đặt - Android
> [!NOTE]
> Nếu bạn không thể di chuyển tệp vào thư mục Windows, điều đó có nghĩa là bạn đã tắt Windows thay vì khởi động lại. Để khắc phục sự cố này, hãy khởi động lại Windows và sử dụng khởi động lại, sau đó khởi động lại thành fastboot và sử dụng nó để quay lại Android. 
- Tải xuống và cài đặt [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), sau đó mở nó và cấp cho nó quyền truy cập root.
- Tải về [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img) và đặt nó vào thư mục có tên `UEFI` trong bộ nhớ trong của bạn, nếu thư mục này không tồn tại, hãy tạo nó. 
- Quay lại ứng dụng WOA Helper và nhấn nút `Back up Android boot` cái nút. Chọn cả hai `Windows` và `Android` tùy chọn.
- Nhấn nút `Mount Windows` nút, sau đó tải xuống và di chuyển [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) đến cái mới được tạo `Windows` thư mục trong bộ nhớ trong của bạn. 
- Quay lại ứng dụng WOA Helper và nhấn  `Quickboot to Windows`.

### Cài đặt - Windows
- Điều hướng đến `C:\StA_Installer_nabu.exe` và chạy nó. Nếu nó không hoạt động, hãy đảm bảo rằng mọi phần mềm chống vi-rút đã tắt vì nó có thể sẽ không cho phép ứng dụng chạy. 

##### Khởi động vào Android
  - Chạy lối tắt mới trên màn hình của bạn (bạn cũng có thể ghim nó vào menu bắt đầu/thanh tác vụ để dễ truy cập) 

##### Khởi động vào Windows
  - Nhấn `Quickboot to Windows` bên trong ứng dụng hoặc sử dụng nút chuyển đổi mới được tạo trong bảng cài đặt nhanh của bạn 
  
## Hoàn thành!
