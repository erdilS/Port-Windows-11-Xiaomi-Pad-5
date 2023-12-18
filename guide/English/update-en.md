<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Updating Drivers

### Prerequisites


- [UEFI image](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)

- [Recovery](../../../../releases/tag/1.0)

- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### Start recovery through the PC with the command

```cmd
fastboot boot <recovery.img>
```


#### Execute script

```cmd
adb shell msc
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

> You can download Drivers [here](https://github.com/map220v/MiPad5-Drivers/releases/latest)

```cmd
 Open folder with Drivers and run OfflineUpdater.cmd
```


### Boot with Windows bootable UEFI image

```
fastboot flash boot <uefi.img>
```

## Finished!
