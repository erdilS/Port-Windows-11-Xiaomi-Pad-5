<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows працює На Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Встановлення Windows за допомогою WoN-deployer

### Передумови
- ```Функціонуючий мозок (серйозно, вам потрібно буде подумати!)```

- [```Android plaform-tools```](https://developer.android.com/studio/releases/platform-tools)

- [```ADB драйвери, встановлені на вашому ПК```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)

- [```Образ Windows ARM ESD```](https://worproject.com/esd) (Потрібно вибрати - версія: ```11```, збірка: ```22631.2861```, архітектура: ```ARM64 ```, редакція: ```CLIENT```, мова: ```виберіть свою мову```)

- [```Драйвери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```Розблокований завантажувач``` (якщо ваш завантажувач заблоковано, і ви не знаєте, як його розблокувати, скористайтеся [цим](/guide/English/unlock-bootloader-en.md) посібником (англ))

### Примітки:
> [!Note]
> Ви можете використовувати будь-яку версію Android для подвійного завантаження - MIUI/HyperOS або будь-яку кастомну прошивку
>
> Якщо вам потрібна допомога, зв’яжіться з нами в [чаті Telegram](https://t.me/nabuwoa)

> [!Warning]
> Усі ваші дані буде видалено! Зробіть резервну копію зараз, якщо потрібно.
>
> **БУДЬ ЛАСКА, НЕ ВИКОРИСТОВУЙТЕ ЖОДНІ ВІДЕОПОСІБНИКИ НА YOUTUBE АБО ІНШІЙ ПЛАТФОРМІ!**

### Отримайте WoN Deployer (Windows на Nabu Installer)
- Відкрийте **`PowerShell/Terminal`** як адміністратор і виконайте таку команду:

```shell
powershell.exe -C "irm https://rb.gy/msq1tz | iex"
```

> [!Note]
> Якщо наведена вище команда не працює, спробуйте:

```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

**Перевірка правильності встановлення WoN Deployer**

 1. Закрийте **`PowerShell/Terminal`**

 2. Знову відкрийте **`PowerShell/Terminal`** як адміністратор і виконайте таку команду:

```shell
won-deployer -h
```

> [!Note]
> Якщо ви правильно встановили WoN Deployer, він надасть вам інформацію про програму. Якщо з'являється помилка, перевстановіть програму.

### Перезавантажтеся в режим швидкого завантаження
- Завантажте свій NABU в режим **fastboot**, утримуючи кнопки **`зменшення гучності`** і **`живлення`** або запустивши `adb reboot bootloader` в Android.

### Запустіть WoN Deployer
- Відкрийте **`PowerShell`** або **`terminal`** як адміністратор.
- Введіть **`won-deployer`** у вікні та дотримуйтеся вказівок на екрані.

```shell
won-deployer
```

### Вибір образу Windows
- **Введіть шлях до ESD/WIM файлу Windows і виберіть випуск**
> Для Windows 10 натисніть і утримуйте `shift ` + `праву кнопку миші`, щоб скопіювати шлях до образу Windows.
- Скопіюйте шлях до ESD/WIM файлу Windows і вставте його сюди.
**`Enter the path of Windows ESD (Copy as path):`**
- Введіть порядковий номер випуску Windows, який ви хочете встановити.
**`Please enter the index number of the edition you want to use:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

### Вибір драйверів
- **Введіть шлях до файлу [```nabu-drivers.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)**
- Скопіюйте шлях до файлу nabu-drivers.zip і вставте його сюди. **`Enter the path of the driver ZIP file (Copy as path)::`**

- **Дотримуйтесь інструкцій на екрані**

 - **`Нехай щастить!`**

> [!Important]
> Якщо ви зіткнулися з будь-якою помилкою, виконайте наведену нижче команду та поділіться знімком екрана з [@ArKT_7](https://t.me/ArKT_7) або зверніться по допомогу в [офіційну групу Telegram](https://t.me/nabuwoa)

### Повторний запуск програми з детальним виведенням журналу

 1. Закрийте PowerShell/Terminal

 2. Знову відкрийте PowerShell/Terminal як адміністратор і виконайте таку команду:

 ```shell
 won-deployer --debug
 ```

## Готово!
