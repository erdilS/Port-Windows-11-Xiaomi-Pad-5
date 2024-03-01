<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="410" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows
> [!WARNING]
> **请不要在YOUTUBE或任何其他平台上使用过时的视频指南！ 这些视频是过时的,你可以砖你的设备使用它! 如果您需要视频指南，请使用此 [新视频指南](https://youtu.be/BbgTbTGbXYg) 从 [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## 安裝 Windows


### 請先準備下面的步驟
  
- [```UEFI boot 映像```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```驅動文件```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

- [```ARM Windows esd```](https://worproject.com/esd) (选择 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```选择你的语言```)
  


### 請進入 Fastboot 模式, 並輸入以下命令來啟动到 Recovery
```cmd
fastboot boot <recovery.img>
```

#### 大容量ストレージモードを有効にする
> 如果腳本提示您需要重新運行一次, 請重新執行下面的命令
```cmd
adb shell msc
```

### 重新分配驅動器號

#### 啟動 Windows 磁碟管理員
> 請確認您的 Xiaomi Pad 5 被 Windows 識別為磁碟
```cmd
diskpart
```

#### 選中平板上的 Windows 分區
> 使用 `list volume` 以找到名為「WINNABU」的分區
```diskpart
select volume <number>
```

#### 分配 Windows 分區到 `X` 盤
```diskpart
assign letter x
```

#### 選中平板上的 ESP 分區
> 使用 `list volume` 以找到名為「ESPNABU」的分區
```diskpart
select volume <number>
```

#### 分配 ESP 分區到 `Y` 盤
```diskpart
assign letter y
```

#### 退出 DiskPart
```diskpart
exit
```

### 安裝

> 替換 `<path\to\install.esd>` 與 install.esd 的實際路徑（也可能命名為 install.wim） 

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
``` 

> 如果你得到 `Error 87`, 檢查圖像的索引 `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, 然後將 `index:6` 替換為映像中 Windows 11 Pro 的實際索引號 



### 安裝驅動程式
> 您可以下载驱动程序[这里](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> 如果它寫 `"Automatic WINNABU detection failed! Enter Drive Letter manually"`，則鍵入 **`X`**  键入 


```cmd
打开带有驱动程序的文件夹并运行 OfflineUpdater.cmd
```

### 重建 Windows EFI
> 如果在複製引導檔時發生錯誤，請檢查`diskpart`以查看 ESPNABU 是否仍然有字母 Y。如果沒有，請添加任何其他字母（例如 K），並分別將以下命令中的 Y 替換為該字母
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
## 删除ESPNABU的驱动器号，以避免出现幻影驱动器号
```cmd
mountvol y: /d
```

## 啟動到 Windows

### 備份現在的 Boot 分區
> [!NOTE]
> **现在回到平台工具命令提示符**

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### 重啟到 Bootloader
```cmd
adb reboot bootloader
```

### 下載並刷入與您顯示面板相對應的 UEFI Boot 鏡像
> 下载[UEFI图像](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img)

```cmd
fastboot flash boot <图像路径>
```
## 重新启动到Windows
```cmd
fastboot reboot
```

> [!NOTE]
> 在第一次Windows启动时，它不会看到任何Wi-Fi网络，只需按住电源按钮重新启动它，重新启动后，当您尝试连接到yuor网络时，您会看到"冰淇淋"点击"再试一次"7次

### 回退到 Android **可選**
> 使用您之前備份過的 Boot 鏡像, 並刷入到當前激活的 slot
```cmd
fastboot flash boot rooted_boot.img
```

```cmd
fastboot reboot
```
## 完成
> 你可以加入我们的 [Telegram 聊天](https://t.me/nabuwoa) 接收有关计划的最新消息
### [最后一步：设置双启动](dualboot-tw.md)
