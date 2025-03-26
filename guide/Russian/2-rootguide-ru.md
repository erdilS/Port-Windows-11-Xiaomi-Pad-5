<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Рутируем ваш планшет
> [!NOTE]
> **Если вы уже рутированы, просто пропустите этот шаг и перейдите на следующую страницу**

### Предварительные условия
- ```Мозг```
  
- [```magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)

### Прошивка magisk 
- Скачайте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на ваш ПК/Ноутбук
> Замените `путь\к\magisk.apk` на актуальный путь к magisk.apk
```cmd
adb push путь\к\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Перезагрузка в Android
> Если он не загружается, войдите в режим восстановления и выполните **сброс к заводским настройкам**
```cmd
adb reboot
```

### Завершение настройки
- Настройте своё устройство, затем скачайте и установите [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), если он ещё не установлен.
- Откройте приложение **Magisk** и следуйте инструкциям на экране. Через несколько секунд ваше устройство перезагрузится.

### Создайте резервную копию загрузочного образа с правами суперпользователя
> Перезагрузитесь в модифицированный образ восстановления, затем выполните приведенную ниже команду
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md)













