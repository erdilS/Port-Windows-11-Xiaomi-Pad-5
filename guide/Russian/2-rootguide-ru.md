
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Запуск Windows на Xiaomi Pad 5

## Получить root
> [!NOTE]
> **Если у вас уже есть root права просто пропустите эту страницу и перейдите к следующей**

### Требования
- ```Мозг```

- [```Бэкап образа boot от Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (вы делали его на первой странице)

### Пропатчите загрузочный образ

- Скопируйте файл **`normal_boot.img`** из папки **`platform-tools`** на планшет 

- Скачайте и установите [Приложение Magisk](https://github.com/topjohnwu/Magisk/releases/latest) на планшет
  
- Откройте приложение Magisk и нажмите кнопку **`Установка`**. Выберите опцию **`Пропатчить boot-образ`** и найдите файл **`normal_boot.img`** который вы скопировали на планшет. Нажмите на кнопку **`Установить`** и дождитесь завершения процесса.
  
- Скопируйте файл **`magisk_patched....img`** из папки **`Downloads`** на планшете, в папку **`platform tools`** на компьютере. 

### Перезагрузите в режим fastboot
- Загрузите планшет в режим **fastboot**, удерживая кнопку **`уменьшения громкости`** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

- Вернитесь в окно командной строки, которое вы открыли ранее
 

### Прошейте патченый boot-образ
> Замените `<magisk_patched.img>` актуальным путём/названием файла.
```cmd
fastboot flash boot magisk_patched.img
```

### Перезагрузка в Android
```cmd
fastboot reboot
```

#### Завершите настройку 
- Снова откройте приложение **Magisk**.
- Следуйте инструкциям на экране, и ваше устройство должно перезагрузиться через несколько секунд.

### Ко
> After your device has booted

- A superuser request for Shell might appear on your phone's screen. If it does, grant it access.
```cmd
adb shell "su -c cp /dev/block/by-name/boot$(getprop grep ro.boot.slot_suffix) /sdcard/rooted_boot.img" & adb pull /sdcard/rooted_boot.img
```

### [Next step: Installing Windows](/guide/English/3-install-en.md)

### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md)
