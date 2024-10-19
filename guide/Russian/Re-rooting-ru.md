<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Running Windows on the Xiaomi Pad 5

## Re-rooting Android
В этом разделе мы расскажем вам о процессе повторного рутинга, когда MIUI/Hyper OS обновляется и удаляет root.

### Требования
- [```образ recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

### Перезагрузите планшет в **fastboot**
- Загрузите планшет в **fastboot**, удерживая кнопку **громкости вниз** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

### Загрузитесь в модифицированное recovery
> Находясь в fastboot, замените `путь\к\recovery.img` фактическим путём к образу recovery 
```cmd
fastboot boot путь\к\recovery.img
```

### Создайте резервную копию вашего существующего загрузочного образа
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Перезагрузитесь обратно в Android
```cmd
adb reboot
```

### Пропатчите boot 
- Скопируйте файл ```normal_boot.img``` из папки ```platform tools``` на ваш паншет 
- Откройте приложение Magisk и нажмите кнопку ```Install```. Выберите параметр ```Select and Patch a File``` и найдите файл ```normal_boot.img``` который вы скопировали на планшет. Нажмите кнопку ```Let's Go``` и дождитесь завершения процесса патчинга.
- Скопируйте файл ```magisk_patched....img``` из папки ```Downloads``` на вашем планшете в папку ```platform tools``` на вашем компьютере. 
- Перезагрузитсь в fastboot
- Откройте командную строку в папке platform tools 

### Прошейте пропатченый boot  
 > Замените `путь\к\magisk_patched.img` существующим путём/именем ```magisk_patched.img```
```cmd
fastboot flash boot путь\к\magisk_patched.img
```

### Обновите boot.img в Windows C:\
- Перезагрузитесь обратно в Android 
- Откройте приложение ```WOA Helper```
- Смонтируйте ```Windows```
- Откройте любой проводник и отройте папку ```Windows``` во внутренней памяти планшета
- Удалите ```boot.img```

> [!NOTE]
> **Обновлённый boot.img будет автоматически создан в C:\ при следующей перезагрузке в Windows**

## Готово!














