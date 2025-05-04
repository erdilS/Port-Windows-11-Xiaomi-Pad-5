<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Updating drivers

### Prerequisites
- [`ADB & Fastboot`](https://developer.android.com/studio/releases/platform-tools)

- [`Modified recovery image`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```DriveLetterAssigner Tool```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)

- [`UEFI image`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/UEFI)

- [`Drivers`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Boot back into the modded recovery
> Replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

#### Execute the msc script
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

### Assign letter to WINNABU 
> [!NOTE]
> You can skip this step if WINNABU already has a drive letter assigned 

> Run the **DriveLetterAssigner** and click **`Assign Drive Letter X to Windows Volume Only`** to automatically assign the letter **X** to **WINNABU**

### Installing drivers
> [!Note]
> This process will take between 3 and 6 hours Do not worry, this is normal.

- Unpack the driver archive, then open the `OfflineUpdater.cmd` file (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> If it asks you to enter a letter, enter the drive letter of **WINNABU** (which should be **X**), then press enter

#### Reboot your device
> [!Warning]
> Make sure to also change the UEFI image in Android, otherwise you may face a "blue screen of death" (BSoD) when booting Windows later.
```cmd
adb reboot
```

## Finished!












