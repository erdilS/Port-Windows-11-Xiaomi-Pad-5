<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上運行 Windows

## UEFI 更新
> [!Warning]
> 如果要從舊的 UEFI（1 月 15 日或之前）更新到 UEFI-V3，您還必須更新驅動程式，您可以使用 [驅動程式更新指南](update-tw.md)

### 為什麼需要本指南？

我不知道, 但有些人在問這個問題
### 先決條件
- [```WOA Helper app```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
  
- [```Latest UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

## Replace old UEFI with the new one
> 如果您尚未設置雙引導，請按照 [dualboot 指南] 進行操作(/guide/Traditional%20Chinese/dualboot-tw.md) 正確設置 WOA Helper
- 啟動到 Android
- 打開內部存儲中的 `UEFI` 資料夾
- 刪除舊的 UEFI
- 把新的放在裡面

## 完成後，切換到 Windows 並享受

> [!NOTE]
>  如果您收到藍屏死機或 Windows 無法正常啟動，請確保您使用的是最新的驅動程式並更新它們
