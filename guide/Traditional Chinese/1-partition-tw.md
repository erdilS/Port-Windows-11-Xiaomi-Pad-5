<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 對您的磁碟進行分區

### 請先準備下面的步驟
- [```Recovery 鏡像```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

### 注意：
> [!WARNING]
>
> 請不要使用 Windows Diskpart 新增/刪除任何分區, 否則您的 UFS 將會被完全清空
>
> 在安裝 Windows 的過程中所有在 Android 上的資料將會被清除, 如有必要, 請先備份
>
> 以下的命令已經經過測試,
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


> **本步骤为可选**
>
> 如果腳本提示您需要重新運行一次, 請重新執行下面的命令
>
> 您可以通過 ```adb shell partition [Windows分區大小, 單位為GB]``` 來自定義分區大小
>
> *請不要添加GB, 直接輸入數字*
```cmd
adb shell partition
```

### 備份現有的啟動映像

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### 檢查 Android 是否仍啟動
> 重新啟動以檢查 Android 是否仍然有效。如果無法啟動，請擦除恢復中的所有數據，然後重試.

```cmd
adb reboot
```

### [下一步：Get root](/guide/Traditional%20Chinese/2-rootguide-tw.md)
