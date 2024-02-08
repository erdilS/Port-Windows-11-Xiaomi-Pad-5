<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上執行 Windows

## 重新安裝

### 若發生錯誤，您可重新安裝 Windows
- 如果您不喜歡您的 Windows 版本, 或者您的 Windows 安裝損壞, 或有其他的原因, 您可能會想要重新安裝 Windows
- 如果您尚未還原您的分區表 (您的設備仍然包含 Windows 和 ESP 分區), 您可以參考以下指南
- 如果您已經初始化了分區表到原廠狀態, [請回到這篇文章來繼續](/guide/Traditional%20Chinese/1-partition-tw.md)

### 請先準備下面的步驟
- [Recovery 鏡像](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [ADB & Fastboot (Android Platform Tools)](https://developer.android.com/studio/releases/platform-tools)

#### 請進入 Fastboot 模式, 並輸入以下命令來啟動到 Recovery
```cmd
fastboot boot <recovery.img>
```

#### 格式化 Windows 和 EFI 分區
> 如果腳本提示您需要重新運行一次, 請重新執行下面的命令
```cmd
adb shell format
```


### 安裝
- 繼續來自[這裡](/guide/Traditional%20Chinese/3-install-tw.md#執行-msc)的指南
