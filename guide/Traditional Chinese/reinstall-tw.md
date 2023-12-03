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
```cmd
adb shell format
```

#### 執行 msc 模式腳本
```cmd
adb shell msc
```

### 重新分配驅動器號

#### 啟動 Windows 磁碟管理員
> 請確認您的 Xiaomi Pad 5 被 Windows 識別為磁碟
```cmd
diskpart
```

#### 確認分區掛載情況
> 如果「WINNABU」分區已經被掛載在 X, 那麽請跳至分配 ESP 分區
>
> 如果「ESPNABU」分區已經被掛載在 Y, 那麽請直接退出 Diskpart 並繼續

#### 選中平板上的 Windows 分區
> 使用 `list volume` 以找到名為「WINNABU」的分區
```diskpart
select volume <number>
```

#### 分配 Windows 分區到 `X` 盤
> 如果您遇到錯誤「指定的磁碟機代號已在使用中，因此無法指定」, 請重啟您的電腦 (不是平板電腦) 並打開 Diskpart 再試一次
```diskpart
assign letter=x
```

#### 選中平板上的 ESP 分區
> 使用 `list volume` 以找到名為「ESPNABU」的分區
```diskpart
select volume <number>
```

#### 分配 ESP 分區到 `Y` 盤
> 如果您遇到錯誤「指定的磁碟機代號已在使用中，因此無法指定」, 請重啟您的電腦 (不是平板電腦) 並打開 Diskpart 再試一次
```diskpart
assign letter=y
```

#### 退出 DiskPart
```diskpart
exit
```

### 安裝
- 繼續來自[這裡](/guide/Traditional%20Chinese/2-install-tw.md#install)的指南