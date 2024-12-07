<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## 🧹 Uninstallation

### ❓ Why is Uninstallation Needed?

#### 🔹 If you want to uninstall windows this is used instead of deleting partitions manually to avoid human error.
#### 🔹 If you want to relock your bootloader you'll need your partition table to be stock.

> [!Warning]
> **All your data will be erased! Back up now if needed.**

>[!NOTE]
>
> ▶️ Click to Expand the menu.

>

<details>
  <summary><strong>Method 1 - Uninstall using adb shell restore</strong></summary>

>

### Prerequisites
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img) 

### Switch to Android 
> If your last boot was Windows, Switch to Android first before starting the uninstallation process

#### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected

#### Boot the modded recovery
> Open a CMD window inside the platform-tools folder, then (while your tablet is in fastboot mode) run
```cmd
fastboot boot path\to\recovery.img
```

### Restore the partition layout
> [!Warning]
> This will wipe your Android files. Backup first if needed.

```cmd
adb shell restore
```

#### Reboot into Android 
```cmd
adb reboot 
```

> [!NOTE]
> If your device **rebooted into Recovery** perform the following actions:
> 1. Select **Wipe Data/Factory reset**
> 2. **Wipe All Data**
> 3. After Data is wiped successfully, Click Back To Main Menu
> 4. Click **Reboot**
> 5. Reboot to System

</details>


>

<details>
  <summary><strong>Method 2 - Uninstall in fastboot</strong></summary>
  
>

### Prerequisites
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```gpt_both0.bin```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin) 

### Switch to Android 
> If your last boot was Windows, Switch to Android first before starting the uninstallation process

#### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected

### Restore partition table   
> Replace ```path\to\gpt_both0.bin``` with the path to the gpt_both0.bin file.
```cmd
fastboot flash partition:0 path\to\gpt_both0.bin
```

#### Erase userdata
> To avoid a bootloop and restore FS size
```cmd
fastboot -w
```

#### Reboot into Android
```cmd
fastboot reboot
```

## Done!

</details>


>

<details>
  <summary><strong>Method 3 - Uninstall using "Nabu Fastboot Tool"</strong></summary>
  
>

### 📋 Prerequisites

- a **cable** to connect your **Xiaomi Pad 5** to your **other device**
- **any other device (android, windows, mac or linux)**

> [!Warning]
> **Make sure to reboot to android before start the uninstallation process.**

--- 

### 🚀 Steps to Stock Partition Layout / Uninstall Windows 

1. **Reboot the Nabu device into fastboot mode:**
   - **Power off** your **Xiaomi Pad 5**
   - Hold down **`Power + Volume Down`** buttons until the device enters **`fastboot mode`.**
   
2. **Connect to the Fastboot Tool on the Website:**
   - Open the **[Nabu Fatboot Tool](https://arkt-7.github.io/nabu/)** in browser of other device.
   - Click on the **`Connect Device Fastboot`** button.
   - Select **`Android`** from the list that appears and **`allow`** permissions.

3. **Format and Make partition Stock:**
   - Scroll down to the **`Format/wipe make Partition Stock`** section.
   - In the input box, type **`format`**.
   - Finally, click the **`Format/Wipe`** button and Click **`OK`** to the warning popup.
   - Once formatting completes, a success popup will appear. Click **`OK`** on the popup.
   - After that, scroll up and click the **`Reboot Device`** button to restart.


> [!NOTE]
> If your device **rebooted into Recovery** perform the following actions:
> 1. Select **Wipe Data/Factory reset**
> 2. **Wipe All Data**
> 3. After Data is wiped successfully, Click Back To Main Menu
> 4. Click **Reboot**
> 5. Reboot to System

## Done!

</details>
