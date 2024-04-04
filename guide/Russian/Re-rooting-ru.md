<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Re-rooting Android
В этом разделе мы расскажем вам о процессе повторного рутинга, когда MIUI обновляется и удаляет root.

### Prerequisites
- [```образ recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

### Запустите recovery через ПК с помощью команды
```cmd
fastboot boot <recovery.img>
```

### Создайте резервную копию вашего существующего загрузочного образа
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Перезагрузитесь обратно в Android
```cmd
adb reboot
```

### Patch boot 
- Скопируйте файл ```normal_boot.img``` из папки ```platform tools``` на ваш паншет 
- Откройте приложение Magisk и нажмите кнопку ```Install```. Выберите параметр ```Select and Patch a File``` и найдите файл ```normal_boot.img``` который вы скопировали на планшет. Нажмите кнопку ```Let's Go``` и дождитесь завершения процесса патчинга.
- Copy the ```magisk_patched....img``` file from the ```Downloads``` folder  on the tablet to the ```platform tools``` folder on your computer. 
- Reboot to fastboot
- Open command prompt in the platform tools folder 

### Flash patched boot 
 > Replace `<magisk_patched.img>` with the actual ```magisk_patched.img``` name/path.
```cmd
fastboot flash boot <magisk_patched.img>
```

### Update boot.img in Windows' C:\
- Reboot back to Android
- Open ```WOA Helper```
- Mount ```Windows```
- Open any file explorer and go to the ```Windows```  folder in your internal storage
- Delete ```boot.img```

> [!NOTE]
> **Обновлённый boot.img будет автоматически создан в C:\ при следующей перезагрузке в Windows**

## Готово!














