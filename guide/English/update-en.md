<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Driver updating

### Prerequisites

- [UEFI](../../../../releases/tag/1.0)
- [Mass storage mode script](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/map220v/MiPad5-Drivers)

#### Start recovery through the PC with the command

```cmd
fastboot boot <recovery.img>
```

#### Push script

```cmd
adb push msc.sh /sbin/
```

#### Execute script

```cmd
adb shell msc.sh
```

### Assign letters to disks

#### Start the Windows disk manager

> Once the Pad 5 is detected as a disk

```cmd
diskpart
```


### Assign `X` to Windows volume

#### Select the Windows volume of the tablet
> Use `list volume` to find it, it's the one named "WINNABU"

```diskpart
select volume <number>
```

#### Assign the letter X
```diskpart
assign letter=x
```

#### Exit diskpart
```diskpart
exit
```


### Install Drivers

> Replace `<nabudriversfolder>` with the location of the drivers folder

> Open cmd as administrator


```cmd
DriverUpdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


### Boot with Windows bootable UEFI image

```
fastboot flash boot <uefi.img>
```

## Finished!
