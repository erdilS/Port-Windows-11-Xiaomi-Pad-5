<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## 無縫雙啟動 Android 和 Windows

### 先決條件
- 腦
- 已root的平板電腦
- 安裝在平板電腦上的 Windows
- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img)
- [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [StA Installer](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Setting up the dualboot app
> 本指南假設您已取得 root 權限，如果尚未取得 root 權限，請依照 [根引導](2-rootguide-tw.md) 第一的.

### 設定 - Android
> [!NOTE]
> 如果您無法將檔案移至 Windows 資料夾，則表示您關閉了 Windows，而不是重新啟動它。若要解決此問題，請啟動回 Windows 並使用重新啟動，然後在重新啟動時啟動至 fastboot 並使用它返回 Android.
- 下載並安裝 [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), 然後打開它並授予它root存取權限.
- 下載 [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img) 並將其放在內部儲存中名為 `UEFI` 的資料夾中，如果該資料夾不存在，請建立它.
- 返回 WOA Helper 應用程式並按 `Back up Android boot` 按鈕. 選擇兩個 `Windows` 和 `Android` 選項.
- 按 `Mount Windows` button, 然後下載並移動 [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) 到內部儲存中新建的 `Windows` 資料夾.
- 返回 WOA Helper 應用程式並按 `Quickboot to Windows`.

### 設定 - Windows
- 導航至 `C:\StA_Installer_nabu.exe` 並執行它。如果它不起作用，請確保所有防毒軟體已關閉，因為它可能不會讓應用程式運行.

##### 啟動至 Android
  - 在桌面上運行新的快捷方式（您也可以將其固定到開始功能表/工作列以方便存取）

##### 啟動至 Windows
  - 按 "Quickboot to Windows" 在應用程式內，或使用快速設定面板中新建立的切換開關
  
## 完成的!
