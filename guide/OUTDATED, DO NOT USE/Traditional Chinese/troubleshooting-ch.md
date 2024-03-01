<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安裝 Windows

## 疑難解答

## 如何激活 PD / Xiaomi 33W 充電
- 在 Fastboot 模式中將此 UEFI Boot 鏡像刷入: https://github.com/kmille36/TempStorage/blob/main/xiaomi-nabu.img?raw=true
- 更新至最新版驅動: https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/driver-updating-selection.md
- 在Regedit 中定位到: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```
- 將 ```RoleSwitchMode``` 從 3 修改至 1 然後重新啟動 Windows
> 您需要在 Windows 啟動前插入充電器, 不然可能無法充電 (請保持充電器插入, 若您拔除充電器, 裝置可能無法充電, 直到您將 Windows 關機並在開機前插入充電器)

## 開機時出現 fsa4480.sys BSOD (藍屏) 畫面
- 開啟解壓後的驅動文件夾
- 移除 ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` 文件夾
- 重新安裝驅動程式
- 刷入 UEFI Boot 鏡像
- 在開機後, 重新安裝驅動文件

## 裝置可啟動 Android, 但 Bootloader 崩潰

### 請先準備下面的步驟
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
> [!WARNING]
> 這些步驟可能不適用於您的設備, 因為 Xiaomi Pad 5 仍沒有可以完全工作的第三方 Recovery, 並且和大多數較新的 A/B 裝置一樣, 沒有 TWRP 的安裝工具可用, 而且您很可能無法啟動到 Recovery 模式, 因為 Bootloader 會崩潰
>
> 如果您已經安裝了 AOSP ROM 並已經 ROOT, 很大概率它有一個預先安裝的 AOSP Recovery, 在這種情況下您可以根據本指南進行修復
>
> 請避免使用含有空格和特殊字符的分區名, 我們建議使用 ESPNABU 和 WINNABU, 因為他們已經經過測試
>
> 如果您的 MIUI 未被 Root, 並且因錯誤的分區名導致 Bootloader 崩潰, 您將必須使用 Xiaomi 內部授權帳戶來激活 EDL 模式以便恢復 ROM, 您很可能需要為此支付費用, 不在本指南的討論範圍內

這是由分割區的磁碟區名稱在 Bootloader 中無法處理造成的，修正方案：
- 重啟到 Recovery
- 連接設備到電腦
- 在電腦上開啟 CMD
- 執行 ```adb shell```
- 執行 ```parted```
- 執行 ```print``` 以列出所有分區
- 尋找名稱中帶有空格或特殊字符的分區, 例如「Basic Data Partition」,並記住其分區序號
- 執行 ```rm <vol number (剛才的分區序號)>```, 例如 ```rm 99```
