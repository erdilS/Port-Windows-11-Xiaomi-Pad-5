<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5
> [!WARNING]
> **PLEASE DON'T USE ANY VIDEO GUIDES AS THESE ARE USUALLY OUTDATED AND CAN AND PROBABLY WILL BRICK YOUR NABU!!! IF YOU ABSOLUTELY NEED A VIDEO GUIDE, USE THIS [VIDEO GUIDE](https://youtu.be/BbgTbTGbXYg) BY [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Installation

### Prerequisites
- ```Brain```

- [```DriveLetterAssigner script```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe)
  
- [```ARM Windows esd```](https://worproject.com/esd) (Select - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```select your language```)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### Boot back into recovery to start installing Windows
```cmd
fastboot boot <recovery.img>
```

### Execute msc 
> If it asks you to run it once again, do so
```cmd
adb shell msc
```
### Assign letters to WINNABU and ESPNABU partitions 

#### Just run  [```DriveLetterAssigner script```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe) and press `Y` on you your keyboard 
> It will automatically assign the letters X and Y to Windows and ESP partitions of the tablet

### Installing Windows
> [!Important]
> make sure that you using **admin cmd**

> Replace `<path\to\install.esd>` with the actual path of install.esd (it may also be named install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
```

> If you get `Error 87`, check the index of your image with `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, then replace `index:6` with the actual index number of Windows 11 Pro in your image

### Installing drivers
> Unpack the driver archive, then open the `OfflineUpdater.cmd` file

> If it asks you to enter a letter, enter the drive letter of **WINNABU** (which should be X), then press enter

#### Create Windows bootloader files for the EFI
> If an error occurs when copying boot files, just run [```DriveLetterAssigner script```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DriveLetterAssigner.V1.0.exe) again, it will assign letter U to ESPNABU, then run the following command again replacing Y with U
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### Remove the drive letter for ESPNABU
> If this does not work, ignore it and skip to the next command. This phantom drive will disappear the next time you reboot your PC.
```cmd
mountvol y: /d
```

### Reboot to Android
```cmd
adb reboot
```

> Set up your device, then go to the last step

## [Last step: Set up Dualboot](dualboot-en.md)









