<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5
> [!WARNING]
> **PLEASE DON'T USE ANY VIDEO GUIDES AS THESE ARE USUALLY OUTDATED AND CAN AND PROBABLY WILL BRICK YOUR NABU!!! IF YOU ABSOLUTELY NEED A VIDEO GUIDE, USE THIS [VIDEO GUIDE](https://youtu.be/BbgTbTGbXYg) BY [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Installation

### Prerequisites
- ```Brain```

- [```DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)
  
- [```ARM Windows ESD```](https://worproject.com/esd) (Select - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```select your language```)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Boot back into the modded recovery
> Replace **path\to** with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

### Execute msc 
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

### Assign letters to WINNABU and ESPNABU
> Open the **DriveLetterAssigner V2.0** script and press `Y` on you your keyboard to automatically assign the letters **X** and **Y** to **WINNABU** and **ESPNABU**

### Installing Windows
> [!Important]
> Make sure that you are running CMD/Powershell as an **Administrator**

> Replace `path\to\install.esd` with the actual path of install.esd (it may also be named install.wim or 22631.2861.XXXXXXX.esd)

```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

> If you get `Error 87`, check the index of your image with `dism /get-imageinfo /ImageFile:path\to\install.esd`, then replace `index:6` with the actual index number of **Windows 11 Pro** in your image

### Copying your boot.img into Windows
- Drag and drop the **root.img** from the last page of the guide into the **WINNABU** disk in Windows Explorer, then rename it to **boot.img**.

### Installing Drivers
- Unpack the driver archive, then open the `OfflineUpdater.cmd` file (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> If it asks you to enter a letter, enter the drive letter of **WINNABU** (which should be **X**), then press enter

#### Create Windows bootloader files for the EFI
> If an error occurs when copying boot files, run **DriveLetterAssigner V2.0** again, then run the following command again, replacing **Y** with **U**
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Remove the drive letter for ESPNABU
> If this does not work, ignore it and skip to the next command. This phantom drive will disappear the next time you reboot your PC.
```cmd
mountvol y: /d
```

### Reboot to Android
> Set up your phone, then proceed to the last step
```cmd
adb reboot
```

## [Last step: Setting up dualboot](/guide/English/4-dualboot-en.md)









