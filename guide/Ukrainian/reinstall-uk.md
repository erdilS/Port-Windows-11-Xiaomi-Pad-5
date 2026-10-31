<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Перевстановлення
Якщо вам не подобається ваша версія Windows, ви пошкодили встановлення Windows або маєте іншу проблему, вам, імовірно, потрібно просто перевстановити Windows. На щастя, цей процес дуже простий.

> [!IMPORTANT]
> Цілком очевидно, що це видалить усі ваші файли Windows. Якщо ви хочете створити резервну копію, підключіть Windows за допомогою програми [WOA Helper](https://github.com/n00b69/woa-helper/releases/tag/APK) і вручну скопіюйте потрібні файли.

> [!WARNING]
> Перед продовженням переконайтеся, що Android `boot.img` прошито. Якщо прошито `uefi.img`, але у вас немає резервної копії `boot.img` поточного Android ROM, можливо, вам доведеться отримати його з пакета ROM. Якщо ви використовуєте HyperOS/MIUI, ви можете завантажити root-образ із вбудованим TWRP для вашої версії HyperOS/MIUI [тут](https://github.com/ArKT-7/nabu/releases/tag/Nabu-boot-with-twrp).

### Передумови
- ```Наявні розділи Windows і boot``` (*Якщо їх немає, [поверніться та скористайтеся основним посібником](1-partition-uk.md)*)

- [```Образ recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform-tools```](troubleshooting-uk.md#adb-fastboot-not-recognized-uk)

#### Перезавантаження в режим fastboot
- Завантажте свій NABU у **режим fastboot**, утримуючи кнопку **`зменшення гучності`** під час перезавантаження з підключеним USB-кабелем.
- Або, якщо у вас увімкнено налагодження USB, виконайте наведену нижче команду, перебуваючи в Android.
```cmd
adb reboot bootloader
```

### Завантаження модифікованого recovery
> Замініть `шлях\до\recovery.img` на фактичний шлях до модифікованого образу recovery.
```cmd
fastboot boot шлях\до\recovery.img
```

### Створення резервної копії boot.img
> [!NOTE]
> Виконайте цю команду в **командному рядку (CMD)**. У PowerShell вона не працює.
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Форматування розділів
> Якщо команда попросить запустити її ще раз, зробіть це.
```cmd
adb shell format
```

## [Наступний крок: перевстановлення Windows](/guide/Ukrainian/3-install-uk.md)
