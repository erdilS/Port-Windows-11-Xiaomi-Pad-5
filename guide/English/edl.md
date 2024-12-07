<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 🚀 **Running Windows on the Xiaomi Pad 5**

---

## 📌 **Restoring the Device in EDL Mode**
> **Note:** This guide includes two methods to flash your device in **EDL mode**:  
> - **Method 1:** EDL Bypass Flashing (Free with patched tools)  
> - **Method 2:** Paid Flashing via HXRU Tool

---

### **🔧 Common Prerequisites**

Before starting either of the methods, ensure you have the following:

1. 💻 **PC with Windows installed**  
   Make sure you are using a Windows PC for flashing the device.

2. 📥 **EDL 9008 drivers installed**  
   - Download and extract the **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)** file.
   - If your device shows **QUSB_BULK_CID** with a yellow warning ⚠️ in **Device Manager**, update the drivers by browsing to the **QUD** folder you extracted.

3. ⚙️ **Fastboot ROM for Nabu (Xiaomi Pad 5)**  
   - Download the latest **Fastboot ROM** for your device from [here](http://xmfirmwareupdater.com/miui/nabu/).

4. 🔌 **USB-C cable or EDL cable**  
   - You can use a **USB-C cable** if the bootloader is unlocked or an **EDL cable** (e.g., **Hydra V2 EDL Cable**) if your device has a locked bootloader or is unbootable.

---

### **🔄 Entering EDL Mode**

There are two methods for booting your Xiaomi Pad 5 into **EDL mode**:

#### **1. Unlocked Bootloader:**
   - If your bootloader is unlocked, simply run the following command in **fastboot mode**:  
   **`fastboot oem edl`**
   - This should reboot your device into **EDL mode**.

#### **2. Locked Bootloader or Unbootable Device:**
   If your device is unbootable or the bootloader is locked, you will need to use one of the following methods:

   - **Using an EDL cable**:  
     - Insert the **EDL cable** into your device and press the button on the cable to boot into **EDL mode**.  
     - Alternatively, **short the test points** (requires opening the back panel of your device).

   - If your device enters **EDL mode**, you are ready to proceed with flashing the device.

---

## 📝 **Method 1: EDL Bypass Flashing (Free Method)**

### **🔧 Prerequisites for Method 1**
Before starting with Method 1, ensure you have the following:

1. **Patched MiFlash Tool**  
2. **Patched firehose (.elf) file**  
3. **Extracted Fastboot ROM for Nabu**  
4. **EDL 9008 drivers installed** (as described above)

---

### **🛠️ Steps for EDL Bypass Flashing**

1. **Extract Files:**  
   - Unzip the **Fastboot ROM** for your Xiaomi Pad 5.
   - Also, unzip the **MiflashPatched.zip** file you downloaded earlier.

2. **Replace Firehose:**  
   - Copy the **firehose (.elf)** file from the **MiflashPatched.zip** folder into the **images** folder inside your extracted **Fastboot ROM**.
   - Overwrite the existing **firehose** file in the **images** folder.

3. **Reconnect Device in EDL Mode:**  
   - Make sure your device is still in **EDL mode** (as explained above). If not, reconnect it using the **EDL cable** or the **test points** method.

4. **Open MiFlash Tool:**  
   - Navigate to the **MiFlash** folder inside the extracted **MiflashPatched.zip**.
   - Launch **XiaoMiFlash.exe** as administrator.

5. **Select Fastboot ROM Folder:**  
   - Click the **Select** button in **MiFlash** and choose the folder where you extracted your **Fastboot ROM** (the one where the **firehose.elf** file is now placed).

6. **Enable "Clean All" Option:**  
   - In the **MiFlash** tool, ensure the **"Clean All"** option is checked.

7. **Click "Refresh":**  
   - Once your device is detected, click **Refresh** in **MiFlash** to verify the connection.

8. **Click "Flash" to Start the Process:**  
   - After confirming your device is detected and the **"Clean All"** option is selected, click **Flash** to start the flashing process.

9. **Handle Errors (If Any):**  
   - If you see an error that doesn't go away after 2 minutes, reboot the device into **EDL mode** again, then click **Refresh** and **Flash** again to retry.

10. **Reboot Device:**  
    - Once the flashing is complete, click the **Reboot** button to restart the device.

11. **Fastboot Mode Reboot:**  
    - After rebooting, your device should enter **Fastboot mode**. If it does, proceed to the next step.

12. **Flash Again in Fastboot Mode:**  
    - Reflash your device in **Fastboot mode** by using the **flash_all.bat** script or through **MiFlash**. This ensures that the flash is properly applied.

---

## 📝 **Method 2: Paid Flashing via HXRU Tool**

### **🔧 Prerequisites for Method 2**

1. **$3 USDT** (crypto wallet) for credits  
2. **Telegram account** for communication with HXRU support  
3. **MiFlash HXRU Tool**  
4. **Stock Fastboot ROM for Nabu**

---

### **🛠️ Steps for Paid Flashing with HXRU Tool**

1. **Set up HXRU Tool:**  
   - Create an account on **[HXRU dashboard](https://dashboard.hxrutool.com/Register)**.
   - Download and extract the **MiFlash HXRU** tool.

2. **Buy Credits:**  
   - Contact **@hxruofficial** on Telegram to purchase **5 credits** (approx. **$3**). You need these credits to proceed with flashing your device.

3. **Boot Device into EDL Mode:**  
   - Follow the steps above to boot your device into **EDL mode** using **fastboot oem edl** or an **EDL cable**.

4. **Install EDL Drivers:**  
   - If not already done, install the **EDL 9008 drivers** using the steps above.

5. **Flash Device Using MiFlash HXRU Tool:**  
   - Open **MiFlash HXRU** and select your device model.
   - Sign in with your HXRU credentials and proceed with flashing.

6. **Reboot into Fastboot Mode:**  
   - Once flashing is complete, your device may boot into **Fastboot mode**. If this happens, proceed to the next step.

7. **Flash Again in Fastboot Mode:**  
   - Flash your device again using **MiFlash** or the **flash_all.bat** script.

8. **Final Reboot:**  
   - After completing the flashing process, your Xiaomi Pad 5 should boot into **Android**.

---

### 🎉 **Success!**  
Your Xiaomi Pad 5 should now be successfully restored and ready to run **Windows** or its original **Android OS**.

---

**Credits:**  
- **Tested by:** @ArKT_7, @panpantepan  
- **Special Thanks to:** @map220v, @MT6769T
