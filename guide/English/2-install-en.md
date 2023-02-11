<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Installation

### Installing Windows

### Boot recovery back to start installing Windows

```cmd
fastboot boot <recovery.img>
```

#### Push msc script to /sbin

```cmd
adb push msc.sh /sbin/
```

#### Execute the msc script

```cmd
adb shell sh /sbin/msc.sh
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

##### Assign the letter X
```diskpart
assign letter=x
```

#### Assign `Y` to ESP volume

##### Select the esp volume of the tablet
> Use `list volume` to find it, it's the one named "ESPNABU"

```diskpart
select volume <number>
```

##### Assign the letter Y

```diskpart
assign letter=y
```

#### Exit diskpart:
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

> Replace `<nabudriversfolder>` with the location of the drivers folder

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

  

### Create Windows bootloader files for the EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

### Allow unsigned drivers

> If you don't do this you'll get a BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

## Boot into Windows

#### Make a backup of your existing boot image

```cmd
adb shell "dd if=/dev/block/bootdevice/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Pull backup to computer

```cmd
adb pull /tmp/boot.img
```

#### Reboot to bootloader 

```cmd
adb reboot bootloader
```

#### Flash the uefi image from TWRP

```cmd
fastboot flash boot boot-nabu.img
```

### Boot back into Android
> Use your backup boot image and flash from fastboot

```cmd
fastboot flash boot boot.img
```

### Finished!
