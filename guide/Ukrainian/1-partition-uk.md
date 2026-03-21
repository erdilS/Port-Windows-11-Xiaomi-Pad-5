<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Інсталяція

### Вимоги
- ```Розблокований завантажувач``` - (якщо ваш завантажувач заблокований і ви не знаєте як розблокувати, використовуйте [цей](unlock-bootloader-uk.md) гайд)

- ```Windows 10(або вище) ПК/Ноутбук```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Модифікований образ recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

### Примітки:
> [!NOTE]
> Ви можете використовувати будь який Android для dualboot - MIUI/Hyper OS або будь-яку кастомну прошивку

> [!Warning]
> Всі ваші дані будуть видалені! Зробіть резервне копіювання якщо потрібно.
> 
> НЕ ПЕРЕЗАПУСКАЙТЕ ПЛАНШЕТ, якщо ви думаєте що зробили помилку, запитайте допомоги в [Telegram чаті](https://t.me/nabuwoa)

### Відкрийте CMD з правами адміністратора
> [!NOTE]
> Не знаєте як почати? Розархівуйте завантажений [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), після цього відкрийте ```командний рядок``` з правами адміністратора і виконайте наступні команди, замінюючи `"шлях\до\platform-tools"` з актуальним шляхом до папки platform tools
```cmd
cd "шлях\до\platform-tools"
```
> Використовуйте це вікно протягом всього гайду. Не закривайте його.

> [!Note]
> Якщо пристрій не визначається в режимі fastboot або recovery, встановіть USB-драйвери [за цим гайдом](troubleshooting-en.md#device-is-not-recognized-in-fastboot-or-recovery)

#### Перезавантаження в режим fastboot
- Запустіть свій NABU в **режим fastboot** тримаючи кнопку **`зменшення гучності`** під час перезавантаження з підключеним USB кабелем
- Або, виконайте команду коли Android запущений
```cmd
adb reboot bootloader
```

### Запустіть модифікований образ recovery
> В режимі fastboot, замініть `шлях\до\recovery.img` на реальний шлях до образу recovery
```cmd
fastboot boot шлях\до\recovery.img
```

### Резервна копія поточного образу boot
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Розбивка пристрою на розділи
> Є два методи для розбивки. Виберіть метод який вам більше до вподоби 
 
> [!NOTE]
>
> ▶️ Натисніть щоб відкрити меню.

### Метод 1: Ручна розбивка (лише якщо знаєте що робите)

<details>
  <summary><strong>Натисніть сюди для метода 1</strong></summary> 

#### Відмонтування data
> Ігноруйте можливі помилки і продовжуйте
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### Зміна розміру таблиці розділів
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

### Підготовка до розбивки
```cmd
adb shell parted /dev/block/sda
``` 

#### Перегляд поточної таблиці розділів
> Parted виведе список розділів, **userdata** має бути останнім розділом в списку
```cmd
print
``` 

#### Видалення userdata
> Замініть **$** на номер розділу **userdata** в списку, він мав би бути **31**
```cmd
rm $
``` 

#### Створення userdata заново
> Замініть **10.9GB** на попереднє початкове значення **userdata** яке було тільки що видалене
>
> Замініть **70GB** на бажане кінцеве значення **userdata**. Наприклад вільний простір Android буде 70GB-10.9GB = **59GB**
```cmd
mkpart userdata ext4 10.9GB 70GB
``` 

#### Створення розділу ESP
> Замініть **70GB** на кінцеве значення **userdata**
>
> Замініть **70.3GB** додавши **0.3GB** до кінцевого значення **userdata**
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Створення розділу Windows
> Замініть **70.3GB** на кінцеве значення **esp**
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Позначення ESP як завантажувального
> Використайте `print` для перегляду всіх розділів. Замініть "$" на номер розділу ESP, який має бути **32**
```cmd
set $ esp on
``` 

#### Вихід з parted
```cmd
quit
``` 

### Форматування розділів Windows та ESP
> переконайтесь що **win** має номер **33**
```cmd
adb shell mkfs.ntfs -f /dev/block/sda33 -L WINNABU
``` 

> переконайтесь що **esp** має номер **32**
```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/sda32 -n ESPNABU
```

### Виправлення GPT
> Або Windows може зламати ваш пристрій
```cmd
adb shell fixgpt
```

#### Перезавантажте пристрій
> Для перевірки чи запускається Android
>
> Якщо Android не стартує — перезавантажтесь у стокове recovery та виконайте скидання до заводських налаштувань
```cmd
adb reboot
```

### [Наступний крок: Рутування пристрою](/guide/Ukrainian/2-rootguide-uk.md)

----

</details>

### Метод 2: Автоматична розбивка (рекомендовано)

<details>
  <summary><strong>Натисніть сюди для метода 2</strong></summary> 

### Запуск скрипта розбивки
> Замініть **$** на кількість гігабайт для Windows (лише цифра, без GB).
> 
> Якщо скрипт попросить запустити ще раз — зробіть це.
```cmd
adb shell partition $
```

### [Наступний крок: Рутування пристрою](/guide/Ukrainian/2-rootguide-uk.md)

</details>

----


