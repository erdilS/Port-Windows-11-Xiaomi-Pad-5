<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5**

## Restoring the Device in EDL Mode
> This guide includes two methods to flash your device in, if method 1 fails, use method 2

### Entering EDL Mode
> There are two methods for booting your Xiaomi Pad 5 into **EDL mode**. Use whichever one applies to you.

<details>
  <summary><strong>Method 1: Unlocked bootloader</strong></summary>

> If your bootloader is unlocked, simply run the following command in **fastboot mode**
```cmd
fastboot oem edl
```

</details>

<details>
  <summary><strong>Method 2: Locked bootloader or unbootable device</strong></summary>

- Insert an **EDL cable** if you have one into your device and press the button on the cable to boot into **EDL mode**.
> EDL cables that can be found online which should work must include V2 in the name, for example **Hydra V2 EDL Cable**.
- Alternatively, **short the test points** (requires opening the back panel of your device).

</details>

### Checking if everything is alright
- Open **Device Manager** on your PC and look for a new device, such as **Qualcomm HS-USB QDLoader 9008**.
- If the device is named **QUSB_BULK_CID** and/or has a yellow warning ⚠️ in **Device Manager**, you need install/update the drivers.
- To do this, ownload and extract **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)** file, select the device with errors in Device Manager, select **Update drivers**, then select the **QUD folder** you extracted.

<details>
  <summary><strong>Method 1: Free method</strong></summary>

## Method 1: Free method

### Prerequisites
- [`Patched MiFlash Tool`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/MiFlashPatched.zip)  
- [`Patched firehose (.elf) file`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/prog_ufs_firehose_sm7150_ddr.elf)
- `Extracted` [`fastboot ROM for Nabu`](http://xmfirmwareupdater.com/miui/nabu/) 

### Preparing necessary files
- Unzip the **fastboot ROM** for your Xiaomi Pad 5.
- Unzip the **MiflashPatched.zip** file you downloaded earlier.
- Copy the **firehose (.elf)** file from the **MiflashPatched.zip** folder into the **images** folder inside your extracted **fastboot ROM**, overwriting the existing file.

#### Open MiFlash Tool 
- Navigate to the **MiFlash** folder inside the extracted **MiflashPatched.zip**.
- Launch **XiaoMiFlash.exe** as an administrator.

### Flashing the ROM
- Click the **Select** button in **MiFlash** and choose the folder where you extracted your **fastboot ROM** (the one where you replaced the **firehose.elf** file).
- In the **MiFlash** tool, ensure the **"Clean All"** option is checked.
- Click **Refresh** in **MiFlash** to verify the connection to your device.
- After confirming your device is detected and the **"Clean All"** option is selected, click **Flash** to start the flashing process.

> [!Important]
> If you see any error that doesn't go away after 2 minutes, reboot the device into **EDL mode** again, then click **Refresh** and **Flash** again to retry.

#### Reboot the device
- Once the flashing is complete, click the **Reboot** button to restart the device.

</details>

<details>
  <summary><strong>Method 2: Paid EDL method</strong></summary>

## 📝 **Method 2: Paid Flashing via HXRU Tool**

### Prerequisites 
- `$3 USDT` and a crypto wallet for credits (some Russian bank accounts are also accepted)

- `Telegram account` for communication with HXRU support

- [`MiFlash HXRU Tool`](https://hxrutool.net/tool/Xiaomi_Auth_Tool_v9.0.0.5_mtk.zip)
 
- [`Stock fastboot ROM for Nabu`](http://xmfirmwareupdater.com/miui/nabu/)  
### Setting up HXRU Tool  
- Create an account on **[HXRU dashboard](https://dashboard.hxrutool.com/Register)**.
- Download and extract the **MiFlash HXRU** tool.

#### Buy Credits 
- Contact **@hxruofficial** on Telegram to purchase **5 credits** (approx. **$3**). You need these credits to proceed with flashing your device.

### Flashing your device
- Open **XiaoMiFlash.exe** and grant it administrator access.
- Download the stock fastboot rom for your device (which should have a .tgz extension) and open it. Inside there should be a .tar file. Extract the contents of this .tar file into any folder).
- Click the **select** button in **XiaoMiFlash** and select this folder.
- Press **flash**.
- If you get a `write time out` error, hold the **power** + **volume down** button for +- 30 seconds to reboot EDL. After this press the **flash** button again.
- After a few seconds a login popup should show up. Enter your HRXU account details here and press **Request Auth Flashing**.

#### Reboot the device
- After it says **flash done**, reboot your device by holding **power** for +- 14 seconds.

</details>

### Reflashing your rom with MiFlash
> [!Important]
> These tools only flash the rom to one slot. If your device ever switches slots, it'll boot back into EDL again.
- Reboot to fastboot mode.
- Flash the fastboot rom a second time using **MiFlash** or with the **flash_all.bat** file in the rom.
- Reboot after it finishes flashing.

#### Success!
Your Xiaomi Pad 5 should now be successfully restored to its original working state!
































