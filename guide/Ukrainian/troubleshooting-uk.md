<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Вирішення проблем

## Пристрій може завантажитися в Android, але не завантажувач

### Потрібні програми:

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
 Ймовірно, ці кроки вам не допоможуть, тому що Xiaomi Pad 5 не має повністю робочого користувацького відновлення, щоб прошити його на пристрій. Крім того, як і в більшості нових A/B-пристроїв, ми не маємо zip-файлу інсталятора TWRP тощо, і ви не можете завантажити наявний образ відновлення через несправність швидкого завантаження. Якщо ви вже встановили AOSP rom, ймовірно, у нього попередньо встановлено відновлення AOSP, і ви можете завантажити його безпосередньо, тож ви можете виконати ці дії. Якщо у вас нерутована MIUI, ці кроки вам не допоможуть.
>
> Тому, будь ласка, уникайте використання міток диска, які містять пробіли та спеціальні символи, і, якщо це можливо, просто використовуйте мітки ESPNABU та WINNABU, які перевірені мільйон разів. Якщо ви зламаєте швидке завантаження дисковими мітками та маєте нерутовану MIUI, вам доведеться прошити ПЗУ через EDL з авторизованим обліковим записом (ви повинні заплатити за це).

Це спричинено розділами з назвами томів, які завантажувач не може обробити, щоб виправити це їх потрібно видалити, для цього введіть ці команди:

- Завантажтеся у відновлення

- Під'єднайте планшет до комп'ютера

- Відкрийте `cmd' на комп'ютері

- Виконайте ```adb shell```

- Виконайте ```parted```

- Виконайте ```print``` щоб показати всі розділи

- Знайдіть розділи, у назвах яких є пробіли, наприклад, «Розділ основних даних», і запам’ятайте номер їхнього тому

- Виконайте ```rm <vol number>``` e.g ```rm 99```


## BSOD fsa4480.sys при завантаженні

- Відкрийте теку драйверів

- Видаліть теку ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB```

- Перевстановіть драйвери

- Завантажте UEFI

- Після завантаження знову додайте драйвер і знову встановіть драйвер


## Постійне завантаження після переходу на Android

- Запустіть fastboot

- ```fastboot set_active other```

- ```fastboot flash boot <boot.img>```

- ```fastboot reboot```
