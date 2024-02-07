<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5
> [!WARNING]
> **PLEASE DON'T USE OUTDATED VIDEO GUIDES ON YOUTUBE OR ANY OTHER PLATFORM! THESE VIDEOS ARE OUTDATED AND YOU CAN BRICK YOUR DEVICE USING THEM! IF YOU NEED A VIDEO GUIDE, USE THIS [NEW VIDEO GUIDE](https://www.youtube.com/watch?v=rGPbdFq7gKs) FROM [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

## Installation


### Prerequisites
- ```Brain```

- [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
  
- [ARM Windows esd](https://worproject.com/esd) Select - Version:  ```11 ``` Build:  ```22631.2861 ``` Architecture:  ```ARM64 ``` Edition:  ```CLIENT ``` Language:  ```select your language```
    
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Boot back into recovery to start installing Windows

```cmd
fastboot boot <recovery.img>
```

#### Execute msc 

> If it asks you to run it once again, do so

```cmd
adb shell msc
```
### Assign letters to disks
  

#### Start the Windows disk manager

> Once the Xiaomi Pad 5 is detected as a disk

```cmd
diskpart
```


#### Assign `X` to Windows volume

#### Select the Windows volume of the tablet
> Use `list volume` to find it, it's the one named "WINNABU"

```diskpart
select volume <number>
```

#### Assign the letter X
```diskpart
assign letter=x
```

### Assign `Y` to ESP volume

#### Select the esp volume of the tablet
> Use `list volume` to find it, it's the one named "ESPNABU"

```diskpart
select volume <number>
```

#### Assign the letter Y

```diskpart
assign letter=y
```

#### Exit diskpart
```diskpart
exit
```

  
  

### Install
> [!NOTE]
> **Now run the command prompt as an administrator**

> Replace `<path/to/install.wim>` with the actual install.wim path.

> `install.wim` is located in sources folder inside your ISO
> You can get it either by mounting or extracting it

> It may also be named **install.esd.** Change the path respectively.

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Install Drivers

> You can download the Drivers [here](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> When it ask you to "Enter Drive letter..." type **`X:`**

> Do not run it as an administrator, it will ask for administrator rights when needed.

```cmd
 Open the folder with Drivers and run OfflineUpdater.cmd
```

### Create Windows bootloader files for the EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## Remove drive letter for ESPNABU to avoid the appearance of a phantom drive letter
> If this does not work, ignore it and skip to the next command. These phantom drives will disappear the next time you reboot your PC.
```cmd
mountvol y: /d
```


## Boot into Windows

### Make a backup of your existing boot image
> [!NOTE]
> **Now go back to the platform tools command prompt**

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Pull backup to computer

```cmd
adb pull /tmp/boot.img
```



### Reboot to bootloader 

```cmd
adb reboot bootloader
```

### Download and flash UEFI image
> Download the [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)

```cmd
fastboot flash boot <path to image>
```
## Reboot to Windows
```cmd
fastboot reboot
```

> [!NOTE]
> On the first Windows boot, it will not see any Wi-Fi networks, just restart it by holding down the power button, and after reboot, when you try connect to your network and you see "ice-cream", click "try again" 7 times
### Boot back into Android
> Use your backup boot image and flash it in fastboot

```cmd
fastboot flash boot boot.img
```

## Finished!
> You can join our [Telegram chat](https://t.me/nabuwoa) to receive the latest news about this project

### [Last step: Set up Dualboot](dualboot-en.md)
