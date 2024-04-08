<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Updating Drivers

### Prerequisites
- [```Recovery image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Start recovery through the PC with the command
```cmd
fastboot boot <recovery.img>
```

### Activate mass storage mode
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

#### Start the Windows disk manager
> Once the Pad 5 is detected as a disk
```cmd
diskpart
```

#### Select the Windows volume of the tablet
> Use `list volume` to find it, it's the one named **WINNABU**
```diskpart
select volume <number>
```

#### Assign the letter X
```diskpart
assign letter x
```

### Exit diskpart
```diskpart
exit
```


### Install Drivers
> If it says `"Automatic WINNABU detection failed! Enter Drive Letter manually"` type **`X`**
```cmd
 Open the folder with Drivers and run OfflineUpdater.cmd
```

### Reboot to fastboot to flash UEFI
> You can also use the WOA Helper app, in which case you can reboot with ```adb reboot```
>
> Make sure you use the latest UEFI, because Windows might not boot if you update drivers without updating the UEFI
```cmd
adb reboot bootloader
```

#### Boot with Windows bootable UEFI image
> Replace <uefi.img> with the actual path of the UEFI image
```cmd
fastboot flash boot <uefi.img>
```

## Finished!









