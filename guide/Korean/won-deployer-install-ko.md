<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## WoN-deployer를 사용한 설치

### 준비물
- ```제대로 작동하는 두뇌 (진지하게, 생각해야 합니다!)```

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)
  
- [```ADB 드라이버가 설치된 PC```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
- [```ARM 윈도우 ESD```](https://worproject.com/esd) (항목 선택 - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```원하는 언어를 선택하세요```)
    
- [```드라이버```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```언락 상태의 부트 로더``` - (부트로더가 락 상태이며 언락 방법을 모를 경우 [이 가이드](unlock-bootloader.md)를 이용하세요)

### Notes:
> [!NOTE]
> You can use any Android version for dualboot - MIUI/HyperOS or any custom ROM
>
> If you need any help, please contact us in [Telegram chat](https://t.me/nabuwoa)


> [!Warning]
> All your data will be erased! Back up now if needed.
>
> **PLEASE DON'T USE ANY VIDEO GUIDES ON YOUTUBE OR ANY OTHER PLATFORM!**

### Get WoN Deployer (Windows on Nabu Installer)
- Open **`PowerShell/Terminal`** as an Administrator and run the following command:

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

## Finished!

