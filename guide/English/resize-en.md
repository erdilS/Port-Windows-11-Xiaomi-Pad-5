<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Resizing Windows partition after installation 

### Prerequisites
- ```Windows installed on nabu```

-  ```Brain```

- [```PowerStateControl tool```](https://github.com/Misha803/My-Scripts/releases/tag/PowerStateControl)

- [```fixuserdataname.exe```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/fixuserdataname.exe)

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

#### Creating new userdata using Windows Disk Management app  
- Locate the **unallocated space** at the end of **Drive 0**  
- Right-click the unallocated block → choose **`New Simple Volume`**  
- Follow the wizard:  
  - Skip drive letter assignment  
  - Format as **NTFS**  
  - Leave the volume label empty  
- After creation, close **`Windows Disk Management`** app  

#### Fixing partition name using fixuserdataname.exe  
> [!IMPORTANT]  
> This step is very important as by default Windows labels the partition "Basic Data Partition", which is more than 16 symbols long — this breaks fastboot!  
- Download [`fixuserdataname.exe`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/fixuserdataname.exe)  
- Run it by double-clicking it  
> It will automatically detect and rename the newly created partition to **`userdata`**  
- Wait for confirmation message (e.g. “Renamed successfully”)  
- Close the tool  
---

### Rebooting to Android and formatting data:
- Use StA.exe to reboot to Android
- When mi logo appears press and hold **`Volume +`** button to boot Android recovery
- In recovery select **`Wipe Data`** - **`Wipe All Data`**
- After Data is wiped successfully, Click **`Back To Main Menu`**
- Click **`Reboot`** - **`Reboot to System`**

> If you couldn't format data via recovery you can use **`fastboot -w`** command in fastboot (connect nabu in fastboot to your PC and run this command via platform tools cmd)

### Done!
