<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Installation using WoN-deployer

### Prerequisites
- ```A functioning brain (seriously, you'll need to think!)```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)
  
- [```ADB drivers installed on your PC```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
- [```ARM Windows ESD```](https://worproject.com/esd) (Select - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```select your language```)
    
- [```Drivers```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```Unlocked bootloader``` - (If your bootloader is locked and you don't know how to unlock it use [this](unlock-bootloader.md) guide)

### Notes:
>[!NOTE]
> You can use any Android for dualboot - MIUI/Hyper OS or any custom ROM
>
> If you need any help please contact us in [Telegram chat](https://t.me/nabuwoa)


> [!Warning]
> All your data will be erased! Back up now if needed.
> 
> **PLEASE DON'T USE ANY VIDEO GUIDES ON YOUTUBE OR ANY OTHER PLATFORM!**


### Get WoN Deployer (Windows on Nabu Installer)

   Open **`PowerShell/Terminal`** as an Administrator and run the following command:

   ```shell
   powershell.exe -C "irm https://rb.gy/msq1tz | iex"
   ```

>[!NOTE]
>If the above command doesn't work, try:

   ```shell
   powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
   ```

**Checking if installed properly**

   1. Close the **`PowerShell/Terminal`** you have open earlier

   2. Open **`PowerShell/Terminal`** as an Administrator again and run the following command:

   ```shell
   won-deployer -h
   ```
>[!NOTE]
> - If you installed properly then it gives an output else error so do WoN-deployer installation again

### Reboot to **fastboot** 
- Boot your NABU to **fastboot** by holding down the **`volume down`** button during reboot

- Connect it to your PC/Laptop using a cable

### Run the WoN Deployer
- Open **`PowerShell/terminal`** as Administrator
- Type **`won-deployer`** in the PowerShell and follow the on-screen instructions.
  
   ```shell
   won-deployer
   ```
 
- **Enter Windows ESD or WIM file path and select edition**
 > For Windows 10, press and hold  `shift ` +  `mouse right click ` for option copy as path

   - Copy as path your Windows ESD/WIM file and Paste path here.
  **`Enter the path of Windows ESD (Copy as path)::`**

   - Enter Index number of which edition of Windows you want to Install.
  **`Please enter the index number of the edition you want to use:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

- **Enter [```nabu-driver.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers) file path**

   - copy as path your nabu-driver.zip file and Paste path here.
  **`Enter the path of the driver ZIP file (Copy as path)::`**

- **Follow on-screen Instruction**

   - **`Good Luck`**.


>[!IMPORTANT]
> If you faced any error please contact [@ArKT_7](https://telegram.me/ArKT_7) or ask for help in [Offcial Telegram Group](https://telegram.me/nabuwoa)
