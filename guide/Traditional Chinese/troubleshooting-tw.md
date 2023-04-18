<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# 在 Xiaomi Pad 5 上執行 Windows

## 疑難排解問題


## 裝置可開機至 Android，但無法開機至 Bootloader

### 先決條件

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> **警告** 這些步驟可能對您無濟於事，因為 Xiaomi Pad 5 沒有一個完全可運作的自訂 Recovery，無法將其刷新至裝置。另外，像大多數較新的 A/B 裝置一樣，我們沒有 TWRP 的安裝程式，而且您無法開機至現有的 Recovery 映像，因為 Fastboot 已經損毀。如果您已經安裝了 AOSP ROM，可能它有一個預先安裝的 AOSP Recovery，您就可以直接開機，所以您可以依循這些步驟進行作業。如果您的 MIUI 未被 Root，這個步驟將無法幫到您。

> 因此，請避免使用含有空格和特殊字元的磁碟標籤，如果可能的話，請使用 ESPNABU 和 WINNABU 標籤，這切標籤已經測試過無數次了。如果您因磁碟標籤導致 Fastboot 變磚，但您的 MIUI 並未被 Root，您必須透過授權帳戶的 EDL 刷新 ROM，您必須為此支付費用。


這是由分割區的磁碟區名稱在 Bootloader 中無法處理造成的，修正方案：

- 開機至 Recovery

- 將裝置連接至電腦

- 在電腦上開啟 CMD

- 執行 ```adb shell```

- 執行 ```parted```

- 執行 ```print``` 以列出所有分割區

- 尋找名稱中帶有空格的分割區，例如「Basic Data Partition」，並注意其磁碟區編號

- 立即執行 ```rm <vol number>```，例如 ```rm 99```


## 開機時出現 fsa4480.sys 藍色當機畫面

- 開啟驅動程式資料夾

- 移除 ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` 資料夾

- 重新安裝驅動程式

- 開機至 UEFI

- 在開機後，檢查驅動程式，並再次重新安裝驅動程式

## 如何充電與 USB 指南

- 在 Fastboot 模式中將此 UEFI 刷新至 Boot：https://github.com/kmille36/TempStorage/blob/main/xiaomi-nabu.img?raw=true

- 更新至最新版驅動程式：https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/driver-updating-selection.md

- 在登錄編輯程式 (Regedit) 中修改數值：Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters (將 RoleSwitchMode 從 3 修改至 1)。然後重新啟動 Windows！

*測試於 C to C 充電 (PD 支援)，Xiaomi 33W 充電器 (已測試)*

- 您需要在 Windows 啟動前插入充電器，不然將無法充電…(請保持充電器插入，若您拔除充電器，裝置將無法充電，直到您將 Windows 關機並在開機前再次插入充電器)。

- 同時 USB Type C 變壓器也能正常運作！！！

