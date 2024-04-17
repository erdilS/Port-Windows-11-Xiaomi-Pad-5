<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Rooting your tablet
> [!NOTE]
> **If you are already rooted just skip this step and go to the next page**

### Prerequisites
- ```Brain```
  
- [```Android boot backup```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (which you backed up on the first guide page)

### Patching your boot image
- Copy the ```normal_boot.img``` file from the ```platform tools``` folder onto your tablet 

- Download and install the [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) on the tablet
  
-  Open the Magisk app and click the ```Install``` button. Select ```Select and Patch a File``` option and find the ```normal_boot.img``` file that you copied to the tablet. Click the ```Let's Go``` button and wait for the patching process to complete.
  
- Copy the ```magisk_patched....img``` file from the ```Downloads``` folder on the tablet to the ```platform tools``` folder on your computer. 

- Reboot to fastboot
  
- Open command prompt in the platform tools folder 

### Flash the patched boot image
> Replace `<magisk_patched.img>` with the actual ```magisk_patched.img``` name/path.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Next step: Installing Windows](/guide/English/3-install-en.md)












