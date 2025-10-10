<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Unlocking the Bootloader: A Step-by-Step Guide for HyperOS/MIUI

### Prerequisites
- [`📲 Mi Community App(only for HyperOS/MIUI 14)`](https://apkpure.net/xiaomi-community/com.mi.global.bbs/download).

- [`🔧 Mi Unlock Tool`](https://miuirom.xiaomi.com/rom/u1106245679/6.5.224.28/miflash_unlock-en-6.5.224.28.zip).

- [`🛠️ HyperSploit (bypass method)`](https://github.com/TheAirBlow/HyperSploit/releases/download/1.0.0/HyperSploit-Windows.exe).

> [!WARNING]
>
> Backup Data: Unlocking the bootloader will erase all data on your device. Make sure to back up important data before proceeding.

### Enable developer options
- **For HyperOS:**
  - Go to **Settings → My device → Detailed info and specs → OS version**.
  - Tap the OS version multiple times until developer options are enabled (you will see a popup message).

- **For MIUI:**
  - Go to **Settings → About phone → MIUI version**.
  - Tap the MIUI version multiple times until developer options are enabled (you will see a popup message).

### Enable OEM Unlocking and USB Debugging
- Go to **Settings → Additional settings → Developer options**.
- Enable **OEM unlocking** and **USB debugging**.

### New method (For HyperOS/MIUI 14)
<details>
  <summary><strong>Click to open</strong></summary>

  <details>
   <summary><strong>Method 1: Using HyperSploit Bypass (Recommended) </strong></summary>

**This method will Bypass the daily quota limit while appling in the Mi Community app.**

### Add platfrom tools to PATH (for HyperSploit to work)
- Open **`PowerShell`** as admin and run:
```powershell
irm https://s.tx0.su/getadb | iex
```
- Wait for it to complete then close PowerShell app.

### Apply to Unlock (HyperSploit)
- Run **HyperSploit-Windows.exe** as Administrator.
- When prompted on your device, tap **OK** to allow USB debugging.
- Follow the on-screen instructions in the **HyperSploit** window. When asked to **attempt to bind account** :
- Go to **Settings → Additional settings → Developer options → Mi Unlock status**.
- Click on **Add account and device**, Once added, HyperSploit will confirm with **Successfully binded**

  </details>
  
  <details>
    <summary><strong>Method 2: Using the Time Trick </strong></summary>
    
**If your device is the global version, you can apply for the bootloader unlock at a specific time.**
- Xiaomi allows **2,000 devices to unlock daily**.
- The reset time for this daily limit is **7 PM Moscow time**.

### Apply to unlock
- Align your local time with **7 PM Moscow time** and be ready at this time — timing is crucial.
- Open the **Xiaomi Community app**, set it to Global, and sign in with the same account as on your device.
- Go to the **"Me"** tab, click on **"Unlock bootloader,"** then click on **"Apply"**.
- Once granted access, go to **Settings → Additional settings → Developer options → Mi Unlock status**.
- Click on **Add account and device**, After a successful addition, you will see **Added Successfully**.

  </details>
  
</details>

### Regular method (for MIUI 13 and below)
<details>
  <summary><strong>Click to open</strong></summary>

### Bind Mi Account
- Go to **Settings** > **Additional settings** > **Developer options** > **Mi Unlock status**.
- Click on **Add your Mi Account**. After a successful addition, you will see **Added Successfully**.

</details>

### Unlocking the Bootloader
- Open the **Mi Flash Unlock Tool** and sign in with the same Mi account.
- Boot your device into **fastboot mode** and connect it to your PC.
- Use the Mi Unlock Tool on your PC to unlock the bootloader.
- If a waiting period error appears `likely 168 hrs/7 days`, close everything, wait until the period ends, then repeat this step.

> [!NOTE]
> Waiting period in Mi Unlock Tool may be different than what is described in this guide.
>
> During the waiting period, do not reset your device or log out of your Xiaomi account.


### Credits & Acknowledgements
- **This guide has been tested and verified by** [@ArKT_7](https://t.me/ArKT_7)  **GitHub:** [@ArKT-7](https://github.com/ArKT-7)






















