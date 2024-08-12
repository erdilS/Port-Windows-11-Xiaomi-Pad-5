<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Installation using WoN-deployer

### Prerequisites
- ```A functioning brain (seriously, you'll need to think!)```
  
- [```ADB drivers installed on your PC```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
- [```ARM Windows ESD```](https://worproject.com/esd) (Select - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```select your language```)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```Unlocked bootloader``` (If your bootloader is locked and you don't know how to unlock it use [this](unlock-bootloader-en.md) guide)

### Notes:
> [!NOTE]
> You can only use MIUI/HyperOS to install windows using WoN-deployer, you can flash any custom ROM after Windows Installation 
>
> If you need any help, please contact us in [Telegram chat](https://t.me/nabuwoa)


> [!Warning]
> All your data will be erased! Back up now if needed.
>
> **PLEASE DON'T USE ANY VIDEO GUIDES ON YOUTUBE OR ANY OTHER PLATFORM!**

### Get WoN Deployer (Windows on Nabu Installer)
- Open **`Terminal/PowerShell`** as an Administrator and run the following command:

```shell
powershell.exe -C "irm https://rb.gy/msq1tz | iex"
```

> [!NOTE]
> If the above command doesn't work, try:

```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

**Checking if WoN Deployer was installed properly**

   1. Close the **`PowerShell/Terminal`** you have opened earlier

   2. Open **`PowerShell/Terminal`** as an Administrator again and run the following command:

```shell
won-deployer -h
```
> [!NOTE]
> If you installed WoN Deployer properly, it will give you information about the app. If an error appears, restart the installation.

### Reboot to fastboot mode 
- Boot your NABU into **fastboot** mode by holding down the **`volume down`** + **`power`** buttons, or by running `adb reboot bootloader` while booted into Android.

### Run the WoN Deployer
- Open **`PowerShell`** or **`terminal`** as an Administrator.
- Type **`won-deployer`** in the window and follow the on-screen instructions.
  
```shell
won-deployer
```

### Selecting the Windows image
- **Enter Windows ESD or WIM file path and select edition**
> For Windows 10, press and hold  `shift ` + `right mouse button` to copy the path of the Windows image.
- Copy the path of your Windows ESD/WIM file and paste the path here.
**`Enter the path of Windows ESD (Copy as path)::`**
- Enter the index number of which edition of Windows you want to Install.
**`Please enter the index number of the edition you want to use:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

### Selecting the drivers
- **Enter [```nabu-drivers.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers) file path**
- Copy the path of your nabu-drivers.zip file and paste the path here.
**`Enter the path of the driver ZIP file (Copy as path)::`**

- **Follow the on-screen Instruction**

   - **`Good Luck`**.

> [!IMPORTANT]
> If you faced any error please run the below command and share the screenshot to [@ArKT_7](https://telegram.me/ArKT_7) or ask for help in the [Offcial Telegram Group](https://telegram.me/nabuwoa)
### re-run program with detailed log output

   1. Close the PowerShell/Terminal you have open earlier

   2. Open PowerShell/Terminal as an Administrator again and run the following command:

   ```shell
   won-deployer --debug
   ```

## Dualboot setup

### Prerequisites

- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```WoA Helper app```](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

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

