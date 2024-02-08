
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5'te Windows çalıştırma

## Almak root 
> [!NOTE]
> **Zaten kökünüz varsa, bu adımı atlayın ve bir sonraki sayfaya gidin**

### Önkoşullar
- ```Beyin```
  
- [```Android önyükleme yedeklemesi```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (which you backup on the first guide page)


## Yama önyüklemesi

- Kopyala ```normal_boot.img``` dosyadan ```platform tools``` tablete klasör


- Indirin ve yükleyin [Magisk uygulama](https://github.com/topjohnwu/Magisk/releases/latest) tablete
  
- Magisk uygulamasını açın ve ```Install``` button. Select ```Select and Patch a File``` option and find the ```normal_boot.img``` file that you copyed to tablet. Click the ```Let's Go``` button and wait for the patching process to complete.
  
- Copy the ```magisk_patched....img``` file from the ```Downloads``` folder on tablet to the ```platform tools``` folder on your computer. 

- Reboot to fastboot
  
- Open command prompt in the platform tools folder 

 ## Flash patched boot 
 > Replace `<magisk_patched.img>` with the actual ```magisk_patched.img``` name/path.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Next step: Installing Windows](/guide/Turkish/3-install-tr.md)
