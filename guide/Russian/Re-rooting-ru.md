<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Ре-рутинг Android
В этом разделе мы подробно рассмотрим процесс повторного получения root-прав на вашем устройстве после обновления MIUI/Hyper OS, либо другой прошивки, после которого root-доступ был утрачен.

### Требования
- [```Образ рекавери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```SDK Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

- [```magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
### Перезагрузите планшет в **fastboot**
- Загрузите планшет в **fastboot**, удерживая кнопку **громкости вниз** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

### Загрузитесь в модифицированный рекавери
> Находясь в fastboot, замените `путь\к\recovery.img` фактическим путём к образу рекавери
```cmd
fastboot boot путь\к\recovery.img
```

### Прошивка magisk 
- Скачайте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на ваш ПК/Ноутбук
> Замените `путь\к\magisk.apk` на актуальный путь к magisk.apk
```cmd
adb push путь\к\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Перезагрузка в Android
> Если он не загружается, перезагрузите его вручную, нажав и удерживая кнопку питания.
```cmd
adb reboot
```

### Завершение настройки
- Настройте своё устройство, затем скачайте и установите [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), если он ещё не установлен.
- Откройте приложение **Magisk** и следуйте инструкциям на экране. Через несколько секунд ваше устройство перезагрузится.

### Обновите boot.img в Windows на диске C:\
- Перезагрузитесь обратно в Android 
- Откройте приложение ```WOA Helper```
- Смонтируйте ```Windows```
- Откройте любой проводник и отройте папку ```Windows``` во внутренней памяти планшета
- Удалите ```boot.img```
- Создайте копию вашего ```boot.img``` в приложении ```WOA Helper``` используя ```РЕЗЕРВНОЕ КОПИРОВАНИЕ BOOT ОБРАЗА```


## Готово!




