<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Рутируем ваш планшет
> [!NOTE]
> **Если вы уже рутированы, просто пропустите этот шаг и перейдите на следующую страницу**

### Что нужно
- ```Мозг```
  
- [```Резервное копирование boot-образа```](/guide/Russian/1-partition-ru.md#Make-a-backup-of-your-existing-boot-image) (которые вы скопировали на первой странице руководства)

### Патчим ваш boot-образ
- Скопируйте файл ```normal_boot.img``` из папки ```platform tools``` на свой планшет

- Скачайте и установите [приложение Magisk](https://github.com/topjohnwu/Magisk/releases/latest) на ваш планшет
  
-  Откройте Magisk, потом нажмите кнопку ```Установка```. Выберите ```Пропатчить boot-образ``` выберите файл ```normal_boot.img``` который вы скопировали на свой планшет. Нажмите на ```Начать``` и подождите когда процесс закончится
  
- Скопируйте ```magisk_patched....img``` файл, в папку ```Downloads``` на вашем планшете, в папку ```platform tools``` на вашем ПК. 

### Перезагрузитесь в fastboot
```cmd
adb reboot bootloader
```

### Прошейте патченый boot-образ
> Замените `magisk_patched.img` на физический путь к ```magisk_patched.img```.
```cmd
fastboot flash boot magisk_patched.img
```

### Перезагрузитесь в Android
```cmd
fastboot reboot
```

#### Закончите установку
- Откройте приложение **Magisk** снова.
- Следуйте инструкциям на экране, и через несколько секунд ваше устройство перезагрузится.

### Копирование рутированого boot-образа
> Загрузка вашего устройства

- На экране вашего планшета может появиться запрос суперпользователя для Shell. Если оно появится, предоставьте доступ.
```cmd
adb shell "su -c cp /dev/block/by-name/boot$(getprop grep ro.boot.slot_suffix) /sdcard/rooted_boot.img" & adb pull /sdcard/rooted_boot.img
```

### [Следующий шаг: установка Windows](https://github.com/Andrew-star2008/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/Russian/3-install-ru.md)
