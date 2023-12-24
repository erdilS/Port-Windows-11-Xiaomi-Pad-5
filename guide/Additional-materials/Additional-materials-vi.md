
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Các ứng dụng và hướng Dẫn hữu ích Cho Windows Trên Xiaomi pad 5

## Cài Đặt Microsoft Office

- Tải về này [tập tin](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) đến máy tính bảng
  
- Tắt Windows Defender để tránh bất kỳ sự can thiệp nào vào quá trình cài đặt
  
- Nhấp chuột phải vào tệp iso và chọn Gắn Kết để mở tệp đó trong explorer

- Nhấp đúp VÀO AUTORUN.exe để bắt đầu trình hướng dẫn cài đặt
  
- Chọn ngôn ngữ và các thành phần bạn muốn cài đặt, sau đó nhấp Vào Bắt đầu cài đặt
  
- Chờ quá trình cài đặt và kích hoạt hoàn tất

- Bật Lại Windows Defender

- Thưởng thức Sử dụng Văn phòng!

 ## Kích Hoạt Windows

> Mở PowerShell và nhập: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> Khi một cửa sổ xuất hiện, chọn 1

 ## Cách sử Dụng Đèn Pin

 - tải về [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) và giải nén vào bất kỳ thư mục nào

> chạy đèn flashlight.exe để bật đèn pin

> Nhấn phím bất kỳ để vô hiệu hóa nó

## Enabling charging and USB host mode

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

- Download  [Script from Misha803](https://t.me/droidscripts/22) to easy enable it
 
- Or use traditional method - In the registry editor, change the value of the parameter ```RoleSwitchMode``` from ```3``` to ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

