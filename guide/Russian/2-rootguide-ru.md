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
> Если он не загружается, войдите в режим **recovery** и выполните **сброс к заводским настройкам**
```cmd
adb reboot
```

### Завершение настройки
- Пройдите первоначальную настройку устройства, затем скачайте и установите [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), если он ещё не установлен.
- Откройте приложение **Magisk** и следуйте инструкциям на экране. Через несколько секунд ваше устройство перезагрузится.

### Создайте резервную копию загрузочного образа с правами суперпользователя
> Перезагрузитесь в [модифицированный образ recovery](https://github.com/ngk13/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/Russian/1-partition-ru.md#%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B2-%D0%BC%D0%BE%D0%B4%D0%B8%D1%84%D0%B8%D1%86%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B9-recovery), затем выполните приведенную ниже команду
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md)













