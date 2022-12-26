#### Start TWRP recovery through the PC with the command

```cmd
fastboot boot <twrp.img>
```

## Push script

```cmd
adb push msc.sh /sbin/
```

### Execute script

```cmd
adb shell sh /sbin/msc.sh
```

## Assign letters to disks

#### Start the Windows disk manager

> Once the Pad 5 is detected as a disk

```cmd
diskpart
```


### Assign `x` to Windows volume

#### Select the Windows volume of the phone
> Use `list volume` to find it, it's usually the one before the last

```diskpart
select volume <number>
```

#### Assign the letter x
```diskpart
assign letter=x
```

### Exit diskpart:
```diskpart
exit
```


# Install Drivers

> Replace `<nabudriversfolder>` with the location of the drivers folder

> Open cmd as administrator

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


##### Boot with Windows bootable UEFI image #####

```
fastboot flash boot <uefi.img>
```


# Finished!
