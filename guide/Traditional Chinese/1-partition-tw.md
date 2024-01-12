<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 對您的磁碟進行分區

### 請先準備下面的步驟
- [Recovery 鏡像](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
- [ADB & Fastboot (Android Platform Tools)](https://developer.android.com/studio/releases/platform-tools)

### 注意：
> [!WARNING]
>
> 請不要使用 Windows Diskpart 新增/刪除任何分區, 否則您的 UFS 將會被完全清空
>
> 在安裝 Windows 的過程中所有在 Android 上的資料將會被清除, 如有必要, 請先備份
>
> 以下的命令已經經過測試, 但不要多次執行相同的命令
>
> 如果您在操作中遇到了 `udevadm` 警告, 請忽略它們
>
> 如果您遇到了意外錯誤, 請不要嘗試繼續執行後續命令或關機/重啟, 請到 [Telegram Chat](https://t.me/nabuwoa) 尋求幫助
>
> 請確保您的設備 Bootloader 已經解鎖
>
> 請不要一次性執行全部的命令
>
> 建議使用複製來避免輸入錯誤命令, 否則您可能會損壞您的設備

#### 請進入 Fastboot 模式, 並輸入以下命令來啟动到 Recovery
```cmd
fastboot boot <recovery.img的路徑>
```

#### 執行分區腳本

> 如果腳本提示您需要重新運行一次, 請重新執行下面的命令
> **本步骤为可选**
>
> 您可以通過 ```adb shell partition [Windows分區大小, 單位為GB]``` 來自定義分區大小
>
> *請不要添加GB, 直接輸入數字*
```cmd
adb shell partition
```

#### 檢查 Android 是否正常運行
您需要重新啟動平板電腦, 並查看 Android 在初始化後是否仍然正常運行
> 若無法正常啟動或在啟動畫面卡住, 請使用 MIUI Recovery 或其他 Recovery 來格式化 data 分區並再試一次

### [下一步：安裝 Windows](/guide/Traditional%20Chinese/2-install-tw.md)
