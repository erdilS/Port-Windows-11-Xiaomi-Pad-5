<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 在 Android / Windows 切換

### 請先準備下面的文件
- 已經 Root 的 Android 和 Android Boot 鏡像備份
- [Dualboot 工具](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Windows --> Android
- 安裝 [Cygwin](https://www.cygwin.com/setup-x86_64.exe)
- 將您的 Android Boot 鏡像重命名為 boot.img
- 將您的 Android Boot 鏡像放置於  C:\ (C:\boot.img)
- 以管理員啟動對應當前激活的 slot 的腳本

### Android --> Windows
- 在您的設備上安裝 switchtowin.apk
- 將您的 Windows UEFI 鏡像重命名為 boot.img
- 將您的 Windows UEFI 鏡像放置於 /sdcard/windows (/sdcard/windows/boot.img)
- 啟動應用程式並授予 Root 權限
- 按一下「Switch to Windows」即可切換至 Windows