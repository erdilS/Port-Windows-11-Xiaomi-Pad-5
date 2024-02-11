
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## 取得root權限 
> [!NOTE]
> **如果您已經擁有root權限，請跳過此步驟並進入下一頁**

### 先決條件
- ```腦```
  
- [```安卓開機備份```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (您在第一個指南頁備份的內容)


## 補丁引導

- 複製 ```normal_boot.img``` 文件來自 ```platform tools``` 資料夾到平板電腦 

- 下載並安裝 [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) 到平板電腦
  
-  打開 Magisk 應用程式並點擊 ```Install``` 按鈕。 選擇 ```Select and Patch a File``` 選項並找到 ```normal_boot.img``` 您複製到平板電腦的檔案。 點選 ```Let's Go``` 按鈕並等待修補過程完成。
  
- 複製 ```magisk_patched....img``` 文件來自 ```Downloads``` 平板電腦上的資料夾 ```platform tools``` 計算機上的資料夾。

- 重新啟動至 fastboot
  
- 在中開啟命令提示符 platform tools 資料夾 

 ## 快閃記憶體修補引導
 > 代替 `<magisk_patched.img>` 與實際的 ```magisk_patched.img``` 名稱/路徑.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [下一步：安裝 Windows](/guide/Traditional%20Chinese/3-install-tw.md)
