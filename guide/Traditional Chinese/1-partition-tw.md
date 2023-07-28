<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# 在 Xiaomi Pad 5 上執行 Windows

## 安裝

### 分割您的裝置

### 先決條件

- [Recovery 映像](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### 注意：
> [!WARNING]
> 如果您以後或現在透過 Diskpart 刪除任何分割區，Windows 會傳送一個被誤解的 ufs 命令，從而刪除您的所有 ufs
> 所有資料將會被清除！如有必要，請先備份。
> 這些命令已經過測試。
> 忽略 `udevadm` 警告。
> 不要多次執行相同的命令。
> 在 Recovery 中，螢幕將不會運作。
> 若您認為您的作業出現錯誤，請不要將您的平板電腦重新開機，請至 [Telegram chat](https://t.me/nabuwoa) 尋求協助
>
>
>
> 不要一次執行所有命令，請依順序執行！
>
> 
> 不要犯任何錯誤！！！如果您錯誤地執行了命令，您可能會損毀您的裝置！！！


#### 透過電腦命令開機至 Recovery
```cmd
fastboot boot <recovery.img>
```
> 若您已經安裝了 TWRP，僅需按住「電源」按鈕和「音量+」按鈕開機

#### 啟動 ADB Shell
```cmd
adb shell
```

#### 調整磁碟分割表格大小
> 這樣，Windows 分割區即可適合大小
```sh
sgdisk --resize-table 64 /dev/block/sda
```

#### 開始分割
```sh
parted /dev/block/sda
```

#### 刪除 `Userdata` 分割區
> 您可以透過執行 `print all` 以確保 31 是 Userdata 分割區的編號
```sh
rm 31
```

#### 建立分割區
> 若您收到讓您忽略或取消的警示訊息，僅需輸入 i 並按下 Enter


<details>
<summary><b><strong>適用於 128GB 機型</strong></b></summary>

- 建立 ESP 分割區 (儲存 Windows Bootloader 資料和 EFI 檔案)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- 建立主要分割區，Windows 將會被安裝在此處
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- 建立 Android 資料分割區
```sh
mkpart userdata ext4 70.2GB 126GB
```
  </summary>
</details>

<details>
<summary><b><strong>適用於 256GB 機型</strong></b></summary>

- 建立 ESP 分割區 (儲存 Windows Bootloader 資料和 EFI 檔案)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- 建立主要分割區，Windows 將會被安裝在此處
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- 建立 Android 資料分割區
```sh
mkpart userdata ext4 120.8GB 254GB
```

  </summary>
</details>


#### 使 ESP 分割區可開機，以便 EFI 映像可以偵測到它
```sh
set 31 esp on
```

#### 離開分割
```sh
quit
```
#### 重新開機至 Bootloader
```sh
reboot bootloader
```

#### 開機至 Recovery
```cmd
fastboot boot <recovery.img>
```

#### 再次啟動 ADB Shell
```cmd
adb shell
```

#### 格式化分割區
-  將 ESP 分割區格式化為 FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  將 Windows 分割區格式化為 NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  格式化 Userdata
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```


#### 檢查 Android 是否仍可啟動
僅需重新啟動平板電腦，並查看 Android 是否仍然正常運作
若無法開機或循環動畫，請使用 MIUI Recovery 或其他 Recovery 抹除資料。

### [下一步：安裝 Windows](/guide/Traditional%20Chinese/2-install-tw.md)
