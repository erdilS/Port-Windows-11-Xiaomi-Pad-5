## Requirements of Dual Boot

- Brain

- Only works on slot A!

- Rooted Android and rooted Android boot backup

- [Download Files](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Windows side of Dual Boot

- Install [Cygwin](https://www.cygwin.com/setup-x86_64.exe) with coreutils (it will install default)

- Rename your boot file to boot.img

- Place your Android boot to C:\ (C:\boot.img)

- Start bat file as administrator or make shorcut with administrator privileges

### Android side of Dual Boot

- Install switchtowin.apk to device.

- Rename your UEFI file to boot.img

- Place your UEFI file to /sdcard/windows (/sdcard/windows/boot.img)

- Start app and give root privileges.

- Click "Switch to Windows" if you want to switch Windows.

# Fixing GPU on Windows

- Go to Device Manager (hold the Windows logo and find Device Manager)
- Find Display adapters and expand it
- Hold the Microsoft Basic Display Adapter
- Select Update driver
- Select "Browse my computer for drivers"
- Select "Let me pick from a list of available drivers on my computer"
- Select "Mi Pad 5 Adreno 640 GPU" and click next
- Display will flicker when updating
- Done!
