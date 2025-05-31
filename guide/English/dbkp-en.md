<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Dualboot guide (DualbootKernelPatcher)
> There are two methods listed below, the first one requires root, the second one does not. Use whichever method suits you the most, as they both do the same.

### Prerequisites (method 1: root required)
- [WOA Helper app](https://github.com/n00b69/woa-helper/releases/tag/APK)

### Setup - Android
- Download and install the **WOA Helper** app, then open it and grant it root access.
- Open **WOA Toolbox**, then press the **DUALBOOT KERNEL PATCHER** button and select the option you would like to use (dualboot using the **magnetic case**, or with **volume buttons**).
- Wait for it to finish, then reboot your device.

#### Booting into Windows - Magnetic Case method
- Close the **magnetic case** and reboot (or turn on) your device.

#### Booting into Windows - Volume button method
- Reboot (or turn on) your device and hold any **volume button** once you see the unlock icon or the Aloha logo (upside down V).

#### Booting into Android
- Open the **magnetic case** and reboot (or turn on) your device.
- If you are using the **volume button** method, simply do not press any volume button while (re)booting the device.

## Finished!


### Prerequisites (method 2: no root required)
- [Modified recovery image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [Magiskboot](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/magiskboot.exe)

- [DualBoot Kernel Patcher](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DualBootKernelPatcher.zip)

- [.fd file (magnetic case method](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/nabu.fd)

- [.fd file (volume button method](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/nabuVolumebuttons.fd)

### Opening CMD as an admin
> Open CMD as an **administrator**, then run the below command, replacing `path\to\platform-tools` with the actual path to the platform-tools folder, for example **C:\platform-tools**.
>
> Do not close this window. You will need to use it throughout this entire guide.
```cmd
cd path\to\platform-tools
```

### Boot the modded recovery
> While in fastboot mode, replace `path\to\recovery.img` with the actual path of the recovery image
```cmd
fastboot boot path\to\recovery.img
```

#### Back up your boot image
> This will back up your boot image in the current directory (for example `C:\platform-tools`).
```cmd
adb pull /dev/block/by-name/boot_a boot.img
```

#### Setting up required files
- Download **magiskboot.exe** and move it into the `platform-tools` folder.
- Download **DualBootKernelPatcher.zip** and extract the **DualBootKernelPatcher** folder into the `platform-tools` folder.
- Download **nabu.fd** move it into the `platform-tools` folder.

### Unpacking your boot image
> Make sure **boot.img** is in the `platform-tools` folder.
```cmd
magiskboot unpack boot.img
```

### Patching your boot image
```cmd
DualBootKernelPatcher\bin\Windows\DualBootKernelPatcher-x86_64.exe kernel nabu.fd output DualBootKernelPatcher\Config\DualBoot.Sm8150.cfg DualBootKernelPatcher\ShellCode\ShellCode.Nabu.bin
```

### Renaming the kernel file
- Delete or rename the **kernel** file in the `platform-tools` folder, then rename the **output** file to `kernel`

### Repacking your boot image
> This will repack your patched boot image into a new file called **new_boot.img**
```cmd
magiskboot repack boot.img
```

### Reboot to fastboot
```cmd
adb reboot bootloader
```

### Flashing the patched boot image
> Replace `path\to\new_boot.img` with the actual path of the image
```cmd
fastboot flash boot_a path\to\new_boot.img
```
```cmd
fastboot flash boot_b path\to\new_boot.img
```

#### Reboot your device
```cmd
fastboot reboot
```

#### Booting into Windows - Magnetic Case method
- Close the **magnetic case** and reboot (or turn on) your device.

#### Booting into Windows - Volume button method
- Reboot (or turn on) your device and hold any **volume button** once you see the unlock icon or the Aloha logo (upside down V)

#### Booting into Android
- Open the **magnetic case** and reboot (or turn on) your device.
- If you are using the **volume button** method, simply do not press any volume button while (re)booting the device.

## Finished!

















