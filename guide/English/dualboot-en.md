<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Dualbooting Android and Windows seamlessly

### Prerequisites

- Brain

- [Rooted Android boot backup]()

### Windows side of Dual Boot

- Install [STA](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

- Copy ```rooted_boot.img``` from ```platform tools``` folder on PC to ```C``` drive on NABU (C:\rooted_boot.img)


- Rename ```rooted_boot.img``` to ```boot.img```  (C:\boot.img)
> Make sure that you do not name this file ```boot.img.img``` if the file extension display is disabled


- Open shortcut on your desktop to switch to Android

### Android side of Dual Boot

- Install [switchtowin.apk](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/switchtowindows.apk) to device.
  
- Create folder Windows in Android storage

- Rename your UEFI file to boot.img

- Place your UEFI file to created folder (/Android storage/Windows/boot.img)

- Start app and give root privileges.

- Click "Switch to Windows" if you want to switch Windows.

