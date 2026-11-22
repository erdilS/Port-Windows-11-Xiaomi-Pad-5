<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Resizing Windows partition after installation 

### Prerequisites
- ```Windows installed on nabu```

-  ```Brain```

- [```PowerStateControl tool```](https://github.com/Misha803/WOA-Tools/releases/tag/PowerStateControl)

- [```createandformatuserdata.exe```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/createandformatuserdata.exe)

### Notes:
> [!Warning]
> These actions will cause wipe of all **Android** data so make a backup if needed, windows data will be kept!
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)
---
### Disabling Hibernation and Page File using PowerStateControl
> [!NOTE]  
> You can skip this step if you already have hibernation and the page file disabled.

> [!Important]
> After finishing the resizing process, it is highly recommended to use the tool to enable the Page File back.

#### Use the tool
- Run the downloaded **`PowerStateControl_V2.0.exe`** tool.
- Click the **`Hibernation`** toggle to turn it off.
- Click the **`Page File (Swap)`** toggle to turn it off.
- Click the **`APPLY`** button.
- Click the **`EXIT`** button and confirm the reboot by clicking **`REBOOT NOW`** in the reboot dialog.

---

### Deleting userdata, resizing Windows partition, and creating new userdata:
> [!WARNING]  
> Do not delete/modify any other partition than that one described in the steps below!  
> If you have any questions etc on this step please ask in [Telegram chat](https://t.me/nabuwoa) to avoid bricking your device

#### Deleting userdata

- Open **`Windows Disk Management`** app  
- Find the big partition at the **end of drive 0** — userdata  
- Delete it

#### Resizing Windows partition
- Now resize your Windows partition:  
  - If you want to **increase** Windows space, right-click the **WINNABU** partition and choose **`Extend Volume`**  
  - If you want to **reduce** Windows space, right-click the **WINNABU** partition and choose **`Shrink Volume`**  
  - Enter the amount of space to shrink or extend as needed
  - Сlose the **`Windows Disk Management`** app  

#### Creating new userdata using createandformatuserdata.exe
> [!IMPORTANT]  
> This step important - Android will not boot if you'll skip it  
- Download [`createandformatuserdata.exe`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/createandformatuserdata.exe)  
- Run it by double-clicking it  
> It will automatically detect free space left and create new **`userdata`**  partition
- Wait for confirmation message (e.g. "Done")
- Close the tool  

---

### Rebooting to Android
- Use StA.exe to reboot to Android

### Setting up dualboot in Android after wipe
- Complete the initial setup to enter the desktop  
- Download and install [**Magisk**](https://github.com/topjohnwu/Magisk/releases/latest) app, then open it.
- Download and install the [**WOA Helper**](https://github.com/n00b69/woa-helper/releases/tag/APK) app, then open it and grant it root access.
- Download the **UEFI image** and place it inside the folder named `UEFI` in your internal storage.


### Done!
