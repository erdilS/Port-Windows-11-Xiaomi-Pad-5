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
> 
> 所有資料將會被清除！如有必要，請先備份。
> 
> 這些命令已經過測試。
> 
> 忽略 `udevadm` 警告。
> 
> 不要多次執行相同的命令。
> 
> 在 Recovery 中，螢幕將不會運作。
> 
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

##### 运行分区脚本

如果脚本提示您重新运行一次，请重新打开脚本

（本步骤为可选）
您可以通过 ```adb shell partition [Windows分区大小，单位为GB]``` 来自定义分区大小
*请不要添加GB，直接输入数字

```cmd
adb shell partition
```

#### 檢查 Android 是否仍可啟動
僅需重新啟動平板電腦，並查看 Android 是否仍然正常運作
若無法開機或循環動畫，請使用 MIUI Recovery 或其他 Recovery 抹除資料。

### [下一步：安裝 Windows](/guide/Traditional%20Chinese/2-install-tw.md)
