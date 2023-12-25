<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Installation

## Installing Windows

### Prerequisites

- [Windows on ARM image](https://uupdump.net/)
- [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Boot recovery back to start installing Windows

```cmd
fastboot boot <recovery.img>
```

#### Execute the msc script

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

> Replace `<path/to/install.wim>` with the actual install.wim path,

> `install.wim` is located in sources folder inside your ISO
> You can get it either by mounting or extracting it

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Install Drivers

> You can download Drivers [here](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> When it ask you "Enter Drive letter..." type X:

```cmd
 Open folder with Drivers and run OfflineUpdater.cmd
```

### Create Windows bootloader files for the EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```




## Boot into Windows

### Make a backup of your existing boot image

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
> Download [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)

```cmd
fastboot flash boot <path to image>
```

### Boot back into Android
> Use your backup boot image and flash from fastboot

```cmd
fastboot flash boot boot.img
```
### Remove phantom drive letters (if they are not removed automatically)
> Run theese commands as admin to remove letter
```cmd
mountvol x: /d
mountvol y: /d
```
## Finished!

### [Last step: Setup Dualboot](guide/English/dualboot-en.md)
