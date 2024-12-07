<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Uninstallation

### Why is Uninstallation Needed?
> If you want to relock your bootloader you'll need your partition table to be stock.

> [!Warning]
> **All your data will be erased! Back up now if needed.**

### Switch to Android 
> If your last boot was Windows, Switch to Android first before starting the uninstallation process

#### Reboot into fastboot mode
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Or, if you have USB debugging enabled, run the below command while booted into Android.
```cmd
adb reboot bootloader
```

> [!NOTE]
>
> ▶️ Click to expand the menu.

>

<details>
  <summary><strong>Method 1 - Uninstall using adb shell restore</strong></summary>

>

### Prerequisites
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img) 

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

## Done!

</details>


>

<details>
  <summary><strong>Method 2 - Uninstall in fastboot</strong></summary>
  
>

### Prerequisites
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```gpt_both0.bin```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin) 

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

### Prerequisites
 `A `**`cable`**` to connect your `**`Xiaomi Pad 5`**` to your `**`other device`**`

 **`Any other device (Android, Windows, Mac or Linux)`**

### Connect to the Fastboot Tool on the website
- Open the **[Nabu Fastboot Tool](https://arkt-7.github.io/nabu/)** in the browser of any device.
- Click on the **`Connect Device Fastboot`** button.
- Select **`Android`** from the list that appears and **`allow`** permissions.

### Format and Make partition Stock
- Scroll down to the **`Format/wipe make Partition Stock`** section.
- In the input box, type **`format`**.
- Finally, click the **`Format/Wipe`** button and press **`OK`** when a warning popup appears.
- Once the formatting completes, a success popup will appear. Click **`OK`** to dismiss the popup.
- Scroll up and click on the **`Reboot Device`** button to restart your device.

> [!NOTE]
> If your device **rebooted into Recovery** perform the following actions:
> 1. Select **Wipe Data/Factory reset**
> 2. **Wipe All Data**
> 3. After Data is wiped successfully, Click Back To Main Menu
> 4. Click **Reboot**
> 5. Reboot to System

## Done!

</details>























