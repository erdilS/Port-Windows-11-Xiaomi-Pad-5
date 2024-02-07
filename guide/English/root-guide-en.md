<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Root guide



### Prerequisites
- Brain
  
- [Androif boot backup]()


## root
- Connect the tablet in Android to the computer and copy the boot.img file from the platform tools folder to the tablet. For this you can use the explorer or the command:


- Download and install the Magisk app from the official website on the tablet.
-  Open Magisk Manager on the tablet and click the Install button. Select the Select and Patch a File option and find the boot.img file on the tablet. Click the Let's Go button and wait for the patching process to complete.
- Copy the magisk_patched.img file from the downloads folder on the tablet to the platform tools folder on the computer. For this you can use the explorer or the command:

- Disconnect the tablet from the computer and reboot it in fastboot mode (for this, turn off the tablet and hold down the power and volume down buttons).
- Open the command line in the platform tools folder on the computer and enter the following commands (pressing Enter after each):

```
fastboot flash boot magisk_patched.img
```

- Reboot the tablet and check for the Magisk app in the list of applications. Open it and check the root status. If everything went well, you got root rights on your tablet.
