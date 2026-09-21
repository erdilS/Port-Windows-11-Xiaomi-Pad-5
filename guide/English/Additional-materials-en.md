<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Useful apps and instructions for Windows on Xiaomi pad 5

### List of supported apps/games
> These are by no means comprehensive lists, they do however list apps/games that have been tested by the community

- [Renegade Google Sheets list](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

- [ARM Repo (native ARM software)](https://armrepo.ver.lt/)

- [News & supported applications](https://windowsonarm.org/)

#### Finished!


### Installing Camera Drivers <a id="camera-drivers"></a>
> The Xiaomi Pad 5 cameras now work on Windows 11, but image quality is currently not as good as on Android. The drivers are experimental and test-signed, so use them at your own risk.

- Disable Secure Boot and enable **Windows Test Mode** on your Xiaomi Pad 5 by following [this guide](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/English/disable-secureboot-en.md).
- Download the latest available package from the [community driver project](https://github.com/deskcj/xiaomi-pad5-windows11-camera).
- Extract the ZIP archive.
- Right-click `Install-AV137.cmd` and select **Run as administrator**.
- Wait for the green success message, then test both cameras in Windows Camera. If the installer requests a restart, restart Windows and run it again.

#### Enjoy!

### Disable adaptive brightness
- Open Windows 11 Settings by pressing **`Win + I`** or by right-clicking the Start button and selecting "Settings".
- Navigate to the **`System`** section from the left sidebar.
- Select **`Display`** within the System settings.
- In the **`Brightness`** section, you'll see two options:
**```1. Change brightness automatically when lighting changes:```**
> Turn this option off by toggling the switch to the **`Off`** position.
 **```2. Change brightness based on content:```**
> Turn this option off by selecting **`Off`** from the dropdown menu.

#### Finished!

### Set up Android boot.img auto-flashing

>[!NOTE]
> Use Android boot.img auto-flashing on Windows boot or when the battery is low to prevent the battery from dying while `uefi.img` is flashed.

- Download the latest **boot.img Auto-Flasher** [here](https://github.com/Misha803/WOA-Tools/releases/tag/boot.img-Auto-Flasher).
- Run it and follow the setup wizard to choose when Android `boot.img` should be auto-flashed.
- Use the battery slider to choose the threshold from **10% to 30%**.
> If the service is already installed, use **`REINSTALL/UPDATE`** to update it.

#### Finished! 

### Toggling USB host mode
> [!Warning]
> Disable USB host mode if you use a powered USB hub, as this can irreversibly damage your device. If you don't use a powered USB hub, enable USB host mode or you will not be able to use any USB devices.

- Run [USB Mode Control tool](https://github.com/Misha803/WOA-Tools/releases/tag/USB-Host-Mode-Control) (newer) or [usbhostmodenative tool](https://github.com/n00b69/usbhostmode) to toggle USB mode between HOST and DEVICE (enable or disable USB host mode).
- If USB is currently in HOST mode and USB does not work, switch it to DEVICE, then back to HOST.

#### Finished!


### Install Microsoft Office
- Go to [Gravesoft's Office installer page](https://gravesoft.dev/office_c2r_links).
- Download the installer that fits your purposes. Make sure you select `Online x64`.
- Open the `setup.exe` and follow any instructions provided within.

#### Finished!


### Activate Windows / Office
- Follow the instructions by Massgravel [here](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Finished!

## Сan I update my Windows using Windows Update or an ISO image?
- ✅ **Yes!** You can install any updates that appear in Windows Update and you can also use an ISO image for this

## Can I update my Android after installing Windows?
- ✅ **Yes!** You can update Android in any way, just use the [Re-rooting Android guide](Re-rooting-en.md) after the update

