<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Dualboot guide

### Prerequisites
- [```Magisk```](https://github.com/topjohnwu/Magisk/releases/latest)

- [```UEFI image```](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)

- [```WoA Helper app```](https://github.com/n00b69/woa-helper/releases/tag/APK)

## Setting up the dualboot app
> This guide assumes you are rooted, if you aren't, please follow the [root guide](2-rootguide-en.md) first

### Back Up the Boot Image
> [!NOTE]
> Only do this step if you just changed your Android ROM and are setting up dualboot again. If you just installed Windows and are setting up dualboot for the first time, you can skip this step.

> Before setting up dual boot, you need to create a backup of the current boot image.

- Open **WOA Helper**.
- Go to **Back up boot image**.
- Select **Windows** as the target.

> This will create a backup of the Android boot image so the device can properly switch between Android and Windows during dual-boot.

### Setup - Android

- Download and install the **WOA Helper** app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.
- Open the WOA Helper app and press the **QUICKBOOT TO WINDOWS** button.

### Setup - Windows
> [!Tip]
> If this is your first time booting Windows and you wish to skip the Microsoft Account login, press the **I don't have internet** button in the WiFi page, then when prompted, press the **Continue with limited setup** button.

#### Booting to Android
- Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

#### Booting to Windows
- Press **QUICKBOOT TO WINDOWS** inside the app, or use the newly created toggle in your quick settings panel
  
## Finished!


















