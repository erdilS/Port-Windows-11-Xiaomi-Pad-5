<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Restoring the Device in EDL Mode

### Entering EDL Mode
> There are two methods for booting your Xiaomi Pad 5 into **EDL mode**. Use whichever one applies to you.

> [!NOTE]
>
> ▶️ Click to expand the menu.

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
- Alternatively, **short the test points** (To do this, you need to disassemble the tablet through the display; instructions can be found on YouTube).

</details>

### Checking if everything is alright
- Open **Device Manager** on your PC and look for a new device, such as **Qualcomm HS-USB QDLoader 9008**.
- If the device is named **QUSB_BULK_CID** and/or has a yellow warning ⚠️ in **Device Manager**, you need install/update the drivers.
- To do this, download and extract **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)** file, select the device with errors in Device Manager, select **Update drivers**, then select the **QUD folder** you extracted.

> [!NOTE]
>
> ▶️ Click to expand the menu.

<details>
  <summary><strong>Flashing with MiFlash</strong></summary>

## Flashing with MiFlash

### Prerequisites
- [`Patched MiFlash Tool`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/MiFlashPatched.zip)

- [`Patched firehose (.elf) file`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/prog_ufs_firehose_sm7150_ddr.elf)

- `Extracted` [`fastboot ROM for Nabu`](https://hyperos.fans/en/devices/nabu)

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

---

</details>

---

#### Success!
Your Xiaomi Pad 5 should now be successfully restored to its original working state!
































