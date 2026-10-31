<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Ре-рутинг Android
В этом разделе мы подробно рассмотрим процесс повторного получения root-прав на вашем устройстве после обновления MIUI/Hyper OS, либо другой прошивки, после которого root-доступ был утрачен.

### Требования
- [```Образ recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```Android platform-tools```](troubleshooting-ru.md#adb-fastboot-not-recognized-ru)

- [```magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
### Перезагрузите планшет в **fastboot**
- Загрузите планшет в **fastboot**, удерживая кнопку **громкости вниз** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

### Загрузитесь в модифицированный recovery
> Находясь в fastboot, замените `путь\к\recovery.img` фактическим путём к образу recovery
```cmd
fastboot boot путь\к\recovery.img
```

### Прошивка magisk 
- Скачайте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на ваш ПК/Ноутбук
> Замените `путь\к\magisk.apk` на актуальный путь к magisk.apk
```cmd
adb push путь\к\magisk.apk /tmp/magisk.zip
adb shell twrp install /tmp/magisk.zip
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
- Откройте ```WOA Helper```
- Нажмите ```РЕЗЕРВНОЕ КОПИРОВАНИЕ BOOT ОБРАЗА``` > ```Windows```

## Готово!




