<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Resizing Windows partition after installation 

### Prerequisites
- ```Windows installed on nabu```

-  ```Brain```

- [```PowerStateControl tool```](https://github.com/Misha803/My-Scripts/releases/tag/PowerStateControl)

- [```createandformatuserdata.exe```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/createandformatuserdata.exe)

### Notes:
> [!Warning]
> These actions will cause wipe of all **Android** data so make a backup if needed, windows data will be kept!
> 
> DO NOT REBOOT YOUR TABLET if you think you made a mistake, ask for help in the [Telegram chat](https://t.me/nabuwoa)
---
### Disabling page file  
> [!NOTE]  
> You can skip this step if you already have page file disabled  

#### Open System Properties  
- Press **`Win + S`** and search for **`View advanced system settings`**  
- Click the result to open **System Properties** window  

#### Open Performance Options  
- In the **Advanced** tab, click **`Settings`** under **Performance**  
- This opens the **Performance Options** window  

#### Disable page file  
- Go to the **Advanced** tab  
- Click **`Change...`** under **Virtual memory**  
- Uncheck **`Automatically manage paging file size for all drives`**  
- Select your **Windows drive** (usually C:)  
- Choose **`No paging file`**  
- Click **`Set`** → **`OK`**  
> Do not confirm reboot dialog

---

### Disabling hibernation using PowerStateControl tool  
> [!NOTE]  
> You can skip this step if you already have hibernation disabled  

#### Disable hibernation  
- Run downloaded **`PowerStateControl`** tool   
- Click **`HIBERNATION: ENABLED/DISABLED`** button once  
- Click **`EXIT`** button and confirm reboot - click **`REBOOT NOW`** button in reboot dialog

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
- Download [`createandformatuserdata.exe`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/createandformatuserdata.exe)  
- Run it by double-clicking it  
> It will automatically detect free space left and create new **`userdata`**  partition
- Wait for confirmation message (e.g. “Done”)  
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
