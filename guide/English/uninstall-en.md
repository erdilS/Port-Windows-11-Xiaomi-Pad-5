<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Uninstallation

### Prerequisites
- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Modified Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img) (new method)

- [```gpt_both0.bin```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin) (old method)

### Switch to Android 
> If your last boot was Windows, Switch to Android first before starting the uninstallation process

#### Reboot into fastboot mkde
- Boot your NABU into **fastboot mode** by holding down the **`volume down`** button while rebooting with a USB cable connected
- Alternatively, run the below command while booted in Android
```cmd
adb reboot bootloader
```

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
> If you are rebooted into MIUI Recovery, perform the following actions:
- Select **Wipe Data**
- Select **Wipe All Data**
- After data has been wiped successfully, select **Back To Main Menu**
- Select **Reboot**

### Alternative way of restoring the partition table
> Use this if the above method fails to remove Windows and restore the tablet
>
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























