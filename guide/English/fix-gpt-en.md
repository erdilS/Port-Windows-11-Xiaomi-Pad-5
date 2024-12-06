<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows on the Xiaomi Pad 5

## 🔧 Fix GPT to Use Windows 24H2 

### Prerequisites:

- [```Alredy installed Windows```](selection-en.md)

- [```Recovery image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

> [!important]
> If you want to use Windows 24H2, follow these steps to fix GPT so it can run normally without EDL brick issue:
 
> [!NOTE]
> This will not going to affect your current Windows or Android, so it is safe to do, nothing will be deleted or erased.

### 1️⃣ Connect Tablet in Fastboot Mode

- Boot your NABU to **fastboot** by holding down the **`volume down`** button during reboot

- Connect it to your PC/Laptop using a cable

### 2️⃣ Run the following command:
- Replace **`path_to_recovery.img`** with the correct path to downloaded **`recovery.img`** file.
  
```cmd
fastboot boot path_to_recovery.img
```


### 3️⃣ After twrp booted,  Run this command:
- If prompted, run the command again.
  
```cmd
adb shell fixgpt
```

### 4️⃣ Reboot your device
```cmd
adb reboot
```

### ✅ Done! Enjoy Windows 24H2 or can update normally.

