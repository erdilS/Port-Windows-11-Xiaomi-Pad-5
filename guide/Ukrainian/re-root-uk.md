<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Повторне рутування Android
Цей розділ проведе вас через процес повторного рутування, коли MIUI/Hyper OS оновлюється та видаляє root.

### Потрібні файли
- [```Образ відновлення```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform-tools```](https://developer.android.com/studio/releases/platform-tools)

### Перезавантажте планшет в **fastboot**
- Завантажте свій планшет у **fastboot**, утримуючи кнопку **зменшення гучності** під час перезавантаження

- Підключіть його до ПК/ноутбука за допомогою кабелю

### Завантажте модифіковане відновлення
> У режимі fastboot замініть `path\to\recovery.img` на фактичний шлях до образу відновлення
```cmd
fastboot boot fastboot\до\recovery.img
```

### Зробіть резервну копію наявного образу завантаження
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Перезавантажтеся в Android
```cmd
adb reboot
```

### Отримання root
- Скопіюйте файл ```normal_boot.img``` з папки ```platform-tools``` на планшет
- Відкрийте програму Magisk і натисніть кнопку ```Встановити```. Оберіть параметр ```Вибрати та пропатчити файл``` і знайдіть файл ```normal_boot.img```, який ви скопіювали на планшет. Натисніть кнопку ```Почати``` і дочекайтеся завершення процесу патчингу.
- Скопіюйте файл ```magisk_patched....img``` з папки ```Завантаження``` на планшеті в папку ```platform-tools``` на вашому комп’ютері.
- Перезавантажте плашнет в fastboot
- Відкрийте командний рядок у папці platform-tools

### Завантаження з виправленим флеш-пам'яттю
> Замініть `шлях\до\magisk_patched.img` фактичною назвою/шляхом до ```magisk_patched.img```.
```cmd
fastboot flash boot шлях\до\magisk_patched.img
```

### Оновіть boot.img у Windows
- Перезавантажтеся в Android
- Відкрийте ```WOA Helper```
- Натисніть "Змонтувати Windows"
- Відкрийте будь-який файловий провідник і перейдіть до папки ```Windows``` у внутрішній пам'яті
- Видаліть ```boot.img```

> [!Note]
> **Оновлений файл boot.img буде автоматично створено в C:\ під час наступного перезавантаження**

## Готово!
