<img align="right" src=""https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

### Prerequisites
- ```A functioning brain (seriously, you'll need to think!)```
- [```ADB drivers installed on your PC```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)

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
