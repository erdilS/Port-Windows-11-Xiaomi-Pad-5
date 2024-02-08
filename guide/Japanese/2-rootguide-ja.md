<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Get root 
> [!NOTE]
> **If you already have root just skip this step and go to the next page**

### Prerequisites
- ```Brain```
  
- [```Android boot backup```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (which you backup on the first guide page)


## Patch boot 

- Copy the ```normal_boot.img``` file from the ```platform tools``` folder to the tablet 


- Download and install the [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) to the tablet
  
-  Open the Magisk app and click the ```Install``` button. Select ```Select and Patch a File``` option and find the ```normal_boot.img``` file that you copyed to tablet. Click the ```Let's Go``` button and wait for the patching process to complete.
  
- Copy the ```magisk_patched....img``` file from the ```Downloads``` folder on tablet to the ```platform tools``` folder on your computer. 

- Reboot to fastboot
  
- Open command prompt in the platform tools folder 

 ## Flash patched boot 
 > Replace `<magisk_patched.img>` with the actual ```magisk_patched.img``` name/path.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Next step: Installing Windows](/guide/Japanese/3-install-ja.md)

