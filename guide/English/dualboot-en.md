<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Dualbooting Android and Windows seamlessly

### Prerequisites
- ```Brain```
- ```A rooted tablet```
- ```Windows installed on the tablet```
- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WoA Helper app```](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

## Setting up the dualboot app
> This guide assumes you are rooted, if you aren't, please follow the [root guide](2-rootguide-en.md) first

### Setup - Android
- Download and install the **WOA Helper** app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.
- Open the WOA Helper app and use the **STA CREATOR** in **WOA TOOLBOX**.
> [!Important]
> If `/sdcard/Windows` is empty, your rom does not support mounting and you will have to make a boot.img backup inside the app, then copy it manually to Windows once you boot to it (for example by uploading it somewhere and then downloading it while booted into Windows). The same applies to the StA files, which are also generated in your internal storage.
>
> Do the same thing if the folder is read-only.
- Press the **QUICKBOOT TO WINDOWS** button.

### Setup - Windows
> [!Tip]
> If this is your first time booting Windows and you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.
- Navigate to `C:\sta` and create a shortcut of **sta.exe** to your desktop, if one isn't already present

#### Booting to Android
- Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press `QUICKBOOT TO WINDOWS` inside the app, or use the newly created toggle in your quick settings panel
  
## Finished!

> [!TIP]
> Don't forget to check out [**```Useful apps and instructions```**](Additional-materials-en.md) page. You'll find a guide on how to activate your Windows, as well as other helpful information.










