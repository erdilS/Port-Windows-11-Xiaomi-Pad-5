<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Установка с помощью WoN-deployer

### Требования
### Предварительные условия
- ```Функционирующий мозг (серьезно, вам нужно будет думать!)```

- [```Инструменты платформы Android```](https://developer.android.com/studio/releases/platform-tools)

- [```Драйверы ADB, установленные на вашем ПК```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)

- [```ARM Windows ESD```](https://worproject.com/esd) (Выберите - Версия: ```11``` Сборка: ```22631.2861``` Архитектура: ```ARM64``` Издание: ```КЛИЕНТ``` Язык: ```выберите язык```)

- [```Драйверы```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```Разблокированный загрузчик``` (Если ваш загрузчик заблокирован и вы не знаете, как его разблокировать, воспользуйтесь [этим](unlock-bootloader-ru.md) руководством)

### Примечания:
> [!NOTE]
> Вы можете использовать любую версию Android для двойной загрузки - MIUI/HyperOS или любую другую прошивку
>
> Если вам нужна помощь, свяжитесь с нами в [чате Telegram](https://t.me/nabuwoa)

> [!Предупреждение]
> Все ваши данные будут удалены! Сделайте резервную копию сейчас, если необходимо.
>
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ НИКАКИЕ ВИДЕОРУКОВОДСТВА НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ!**

### Запустите WoN Deployer (Установщик Windows on Nabu)
- Откройте **`PowerShell/Terminal`** как администратор и выполните следующую команду:

```shell
powershell.exe -C "irm https://rb.gy/msq1tz | iex"
```

> [!NOTE]
> Если указанная выше команда не работает, попробуйте:

```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

**Проверка правильности установки WoN Deployer**

1. Закройте **`PowerShell/Terminal`**, который вы открыли ранее

2. Снова откройте **PowerShell/Terminal** как администратор и выполните следующую команду:

```shell
won-deployer -h
```
> [!NOTE]
> Если вы правильно установили WoN Deployer, он предоставит вам информацию о приложении. Если появится ошибка, перезапустите установку.
### Перезагрузитесь в режим fastboot
- Загрузите планшет в режим **fastboot**, удерживая кнопки **`уменьшения громкости`** + **`питания`** или запустив `adb reboot bootloader` во время загрузки в Android.

### Запустите WoN Deployer
- Откройте **`PowerShell`** или **`Терминал`** как администратор.
- Введите **`won-deployer`** в окне и следуйте инструкциям на экране.

```shell
won-deployer
```

### Выбор образа Windows
- **Введите путь к файлу Windows ESD или WIM и выберите редакцию**
> Для Windows 10 нажмите и удерживайте `shift ` + `правую кнопку мыши`, чтобы скопировать путь к образу Windows.
- Скопируйте путь к файлу Windows ESD/WIM и вставьте его в окно консоли:
**`Введите путь к Windows ESD (Копировать как путь):`**
- Выберите индекс редакции Windows, которую вы хотите установить.
**`Выберите индексный номер издания, которое вы хотите использовать:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

### Выбор драйверов
- **Введите путь к файлу [```nabu-drivers.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)**
- Скопируйте путь к файлу nabu-drivers.zip и вставьте его здесь.
**`Введите путь к ZIP-файлу драйвера (Копировать как путь)::`**

- **Следуйте инструкциям на экране**

- **`Удачи`**.

> [!IMPORTANT]
> Если вы столкнулись с какой-либо ошибкой, выполните команду ниже и отправьте снимок экрана [@ArKT_7](https://telegram.me/ArKT_7) или попросите о помощи в [Официальной группе Telegram](https://telegram.me/nabuwoa)
### перезапустите программу с подробным выводом логов

1. Закройте PowerShell/Терминал, который вы открыли ранее

2. Снова откройте PowerShell/Терминал как администратор и выполните следующую команду:

```shell
won-deployer --debug
```

## Готово!
