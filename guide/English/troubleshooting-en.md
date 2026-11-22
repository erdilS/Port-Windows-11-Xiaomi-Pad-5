<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Troubleshooting Issues

## I can't move files to the Windows folder from Android 

If you are unable to move files to the Windows folder, it means you shut down Windows instead of restarting it. To fix this issue, boot back to Windows and use restart, then as it restarts boot to fastboot and use it to return to Android

##### Done!

## adb or fastboot is not recognized as an internal or external command <a id="adb-fastboot-not-recognized"></a>
If your terminal says `adb` or `fastboot` _is not recognized as an internal or external command_, install Android platform tools first:
```powershell
winget install Google.PlatformTools
```
- Wait for the installation to finish, then close and reopen PowerShell or Command Prompt.

> If you installed them manually, make sure the platform-tools folder is added to your system PATH.

##### Done!

## Device is not recognized in fastboot or recovery mode by my PC/Laptop what should I do?
> This likely means you don't have (proper) USB drivers installed
- Download [QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip) here and extract it.
- Open Device Manager and find an **`⚠️Unknown Device`** or device with errors that may be called **Android**, **ADB Interface**, or **QUSB_BULK**.
- Right click this device, select **```Update Drivers```** → **`Browse files`**, then select the **QUD folder** you extracted before.

##### Done!

## Charging in Windows is slow or does not work
The v2611.21 release makes charging functional with most chargers and cables, without requiring a Xiaomi charger, but charging is currently limited to 18 W. Compatibility still varies between chargers and cables.

Some high-power chargers may not work properly and can trigger foldback protection, causing the charging indicator to blink. If this happens, try a different charger.

##### Done!


## Device can boot into Android and/or Windows but not bootloader

### Prerequisites:
- [`Termux`](https://play.google.com/store/apps/details?id=com.termux)

- [```Android platform tools```](troubleshooting-en.md#adb-fastboot-not-recognized)

- [`TWRP Recovery`](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

#### If you have access to Android:
> [!Important]
> It will only work if you have root access.

- Install **Termux** and grant it root access.
- Install **tsu** and **parted** using these two commands, press `Y` if it asks you to confirm:
```cmd
pkg install tsu
```
```cmd
pkg install parted
```
- Run the below command to open parted:
```cmd
parted /dev/block/sda
```
- Run ```print``` to list all partitions.
- Look for partitions that are more than 16 characters long, for example "Basic Data Partition" and note their volume number.
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have.
- Run ```quit```.

##### Done!


#### If you have access to Windows:
- Rename **C:\boot.img** to **C:\bootb.img**.
- Download the **TWRP recovery** image, rename it to **boot.img**, and place it in `C:\`.
- Run the **Switch to Android** or **Android** shortcut to flash and boot into TWRP recovery.
- Once booted into the recovery, connect your device to your PC and run:
```cmd
adb shell parted /dev/block/sda
```
- Run ```print``` to list all partitions.
- Look for partitions that are more than 16 characters long, for example "Basic Data Partition" and note their volume number.
- Rename this partition with ```name $ test```, replacing **$** with the partition number, and replacing **test** with the name you want the partition to have.
- Run ```quit```.
- Run ```adb reboot bootloader```, and when you see the **FASTBOOT** logo on your screen, flash your Android boot image with ```fastboot flash boot_a path\to\boot.img```.
- You may have to do the same for **boot_b** if your device does not boot, or if it boots back to the recovery.

> [!important]
> If you used Windows method, make sure to delete boot.img file in C:\ and rename **C:\bootb.img** back to **C:\boot.img** after finishing.

##### Done!


## Bootloop after switching to Android 
- Boot to fastboot

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```

##### Done!

















