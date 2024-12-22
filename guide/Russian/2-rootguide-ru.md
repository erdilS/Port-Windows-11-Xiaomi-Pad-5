<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Рутируем ваш планшет
> [!NOTE]
> **Если вы уже рутированы, просто пропустите этот шаг и перейдите на следующую страницу**

### Предварительные условия
- ```Мозг```
  
- [```Резервная копия boot образа Android```](/guide/Russian/1-partition-ru.md#Make-a-backup-of-your-existing-boot-image) (который вы скопировали на первой странице руководства)

### Патчинг вашего boot образа
- Скопируйте файл ```normal_boot.img``` в папку ```platform tools``` на вашем ПК

- Скачайте и установите [приложение Magisk](https://github.com/topjohnwu/Magisk/releases/latest) на планшет
  
-  Откройте приложение Magisk и нажмите на кнопку ```Установка```. Выберите опцию ```Пропатчить boot-образ``` и найдите файл ```normal_boot.img``` который вы скопировали на свой планшет. Нажмите кнопку ```Начать``` и подождите пока идёт процесс патчинга boot образа
  
- Скопируйте файл```magisk_patched....img``` в папку ```Downloads``` на планшете, потом в папку ```platform tools``` на вашем ПК. 

### Перезагрузка в fastboot
```cmd
adb reboot bootloader
```

### Прошивка патченого boot образа
> Замените `magisk_patched.img` на актуальное ```magisk_patched.img``` имя/путь.
```cmd
fastboot flash boot magisk_patched.img
```

### Перезагрузка в Android
```cmd
fastboot reboot
```

#### Заканчиваем установку
- Откройте приложение **Magisk** снова.
- Следуйте инструкциям на экране, и ваше устройство должно перезагрузиться через несколько секунд.

### Скопируйте рутированый boot образ
> После того, как ваше устройство снова загрузится на Android.
- Запрос суперпользователя для Shell может появиться на экране вашего телефона. Если это произойдет, предоставьте ему доступ.
- Если команда завершится неудачно, откройте **Magisk**, нажмите на `Superuser`, найдите **Shell**, и предоставьте ему доступ.
```cmd
adb shell "su -c cp /dev/block/by-name/boot$(getprop ro.boot.slot_suffix) /sdcard/rooted_boot.img" & adb pull /sdcard/rooted_boot.img
```

### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md)













