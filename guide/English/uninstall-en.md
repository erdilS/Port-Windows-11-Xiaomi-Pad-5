<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## 🧹 Uninstallation

### ❓ Why is Uninstallation Needed?

#### 🔹 If you want to uninstall windows this is used instead of deleting partitions manually to avoid human error.
#### 🔹 If you want to relock your bootloader you'll need your partition table to be stock.

### 📋 Prerequisites

- a **cable** to connect your **Xiaomi Pad 5** to your **other device**
- **any other device (android, windows, mac or linux)**

> [!Warning]
> **All your data will be erased! Back up now if needed.**
>
> **Make sure to reboot to android before start the uninstallation process.**

--- 

### 🚀 Steps to Stock Partition Layout / Uninstall Windows 

1. **Reboot the Nabu device into fastboot mode:**
   - **Power off** your **Xiaomi Pad 5**
   - Hold down **`Power + Volume Down`** buttons until the device enters **`fastboot mode`.**
   
2. **Connect to the Fastboot Tool on the Website:**
   - Open the **[Nabu Fatboot Tool](https://arkt-7.github.io/nabu/)** in browser of other device.
   - Click on the **`Connect Device Fastboot`** button.
   - Select **`Android`** from the list that appears and **`allow`** permissions.

3. **Format and Make partition Stock:**
   - Scroll down to the **`Format/wipe make Partition Stock`** section.
   - In the input box, type **`format`**.
   - Finally, click the **`Format/Wipe`** button and Click **`OK`** to the warning popup.
   - Once formatting completes, a success popup will appear. Click **`OK`** on the popup.
   - After that, scroll up and click the **`Reboot Device`** button to restart.


> [!NOTE]
> If your device **rebooted into Recovery** perform the following actions:
> 1. Select **Wipe Data/Factory reset**
> 2. **Wipe All Data**
> 3. After Data is wiped successfully, Click Back To Main Menu
> 4. Click **Reboot**
> 5. Reboot to System

## Done!
