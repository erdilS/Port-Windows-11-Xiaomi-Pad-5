<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Dualbooting Android and Windows seamlessly

### Prerequisites
- ```Brain```
- ```A rooted tablet```
- ```Windows installed on the tablet```
- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [```WoA Helper app```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [```StA Installer```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Setting up the dualboot app
> This guide assumes you are rooted, if you aren't, please follow the [root guide](2-rootguide-en.md) first

### Setup - Android
- Download and install the WoA Helper app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.
- Press the `MOUNT WINDOWS` button, then download and move **StA_Installer_nabu.exe** to the newly created `Windows` folder in your internal storage.
- Return to the WoA Helper app and press `QUICKBOOT TO WINDOWS`.
  
> [!NOTE]
> The first Windows boot can take up to 10 minutes, don't worry and just wait

### Setup - Windows
- Navigate to `C:\StA_Installer_nabu.exe` and run it. If it doesn't work, make sure that any antivirus software is off, as it will probably not let the app run

#### Booting to Android
- Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press `QUICKBOOT TO WINDOWS` inside the app, or use the newly created toggle in your quick settings panel
  
## Finished!











