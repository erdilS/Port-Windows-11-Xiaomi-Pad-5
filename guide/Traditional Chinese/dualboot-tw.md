<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 在 Android / Windows 切換

### 請先準備下面的文件
- 已經 Root 的 Android 和 Android Boot 鏡像備份
### Windows --> Android
- 安裝 [STA](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)
- 將您的 Android Boot 鏡像重命名為 boot.img
- 將您的 Android Boot 鏡像放置於  C:\ (C:\boot.img)
- 打开桌面上的快捷方式切换到Android

### Android --> Windows
- 在您的設備上安裝 [switchtowin.apk](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/switchtowindows.apk)
- 在Android存储中创建文件夹"Windows"
- 將您的 Windows UEFI 鏡像重命名為 boot.img
- 将您的UEFI文件放到创建的文件夹中 (/Android存储/Windows/boot.img)
- 啟動應用程式並授予 Root 權限
- 按一下「Switch to Windows」即可切換至 Windows
