<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Установка с помощью WoN-deployer

### Требования
### Предварительные условия
- ```Функционирующий мозг (серьезно, вам нужно будет думать!)```

- [```Инструменты платформы Android```](https://developer.android.com/studio/releases/platform-tools)

- [```Драйверы ADB, установленные на вашем ПК```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)

- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/) (По соображениям производительности рекомендуется использовать Windows 11 24H2 (сборки, начинающиеся с 261XX, например 26100.2454))

- [```Драйверы```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```Разблокированный загрузчик``` (Если ваш загрузчик заблокирован и вы не знаете, как его разблокировать, воспользуйтесь [этим](unlock-bootloader-ru.md) руководством)

### Примечания:
> [!NOTE]
> Вы можете использовать любую прошивку Android для дуалбута - MIUI, HyperOS или любую другую
>
> Если вам нужна помощь, свяжитесь с нами в [чате Telegram](https://t.me/nabuwoaru)

> [!NOTE]
> Все ваши данные будут удалены! Сделайте резервную копию сейчас, если необходимо.
>
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ НИКАКИЕ ВИДЕОРУКОВОДСТВА НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ!**

### Запустите WoN Deployer (Установщик Windows on Nabu)
- Откройте **`PowerShell/Терминал`** от имени администратора и выполните следующую команду:

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

## 2. Как установить/переустановить Windows на Nabu 

<a href="won-deployer-install-ru.md"><img src="https://github.com/ArKT-7/won-deployer/blob/main/assets/Won-nabu-bg.png" width="280"></a>

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
> Если вы столкнулись с какой-либо ошибкой, выполните команду ниже и отправьте снимок экрана [@ArKT_7](https://telegram.me/ArKT_7) или попросите о помощи в [Официальной группе Telegram](https://telegram.me/nabuwoaru)
### перезапустите программу с подробным выводом логов

1. Закройте PowerShell/Терминал, который вы открыли ранее

2. Снова откройте PowerShell/Терминал от имени администратора и выполните следующую команду:

```shell
won-deployer --debug
```
## 3. Настройка Dualboot

### Требования
- ```Подключение к интернету на устройстве Nabu (требуется для загрузки файлов!)```

### Настройка - Android
- После завершения настройки Android перезагрузите ваше устройство Nabu.
- Откройте предустановленное приложение `Magisk` (фиктивное).
- Нажмите OK и установите новое приложение `Won deployer setup`. (если не удалось, попробуйте еще раз)
- Закройте приложение `Magisk` и убедитесь, что оно удалено из памяти/списка последних приложений.
- Откройте новое приложение `Won deployer setup`, установите оба приложения и образ UEFI (следуйте инструкциям на экране).
- Закройте все и снова откройте приложение `Magisk`, нажмите `OK`, чтобы завершить дополнительную настройку.
- После перезагрузки откройте приложение `WOA Helper` и предоставьте ему root-доступ.
- Нажмите `BACKUP BOOT IMAGE` > `Windows` > OK Готово!
- Теперь используйте приложение WOA Helper и нажмите кнопку **QUICKBOOT TO WINDOWS**.

<details>
<summary><b><strong>Если возникли проблемы с предыдущим методом, можно выполнить настройку Dualboot отсюда:</strong></b></summary>

### Требования
- [```Приложение Magisk```](https://raw.githubusercontent.com/arkt-7/won-deployer/main/files/Magisk_stable.apk)

- [```Приложение WoA Helper```](https://github.com/Marius586/WoA-Helper-update/releases/tag/WOA)

- [```Образ UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

### Настройка - Android вручную
- Скачайте и установите приложение `Magisk`.
- Скачайте и установите приложение `WOA Helper`, откройте его и предоставьте root-доступ.
- Скачайте `образ UEFI` и поместите его в папку `UEFI` на внутреннем хранилище.
- Откройте приложение WOA Helper и нажмите кнопку **QUICKBOOT TO WINDOWS**.

  </summary>
</details>

### Настройка - Windows
> [!Tip]
> Если это ваш первый запуск Windows и вы хотите пропустить вход в учетную запись Microsoft, нажмите кнопку **"У меня нет интернета"** на странице WiFi, затем выберите **"Продолжить с ограниченной настройкой"**.

#### Переключение на Android
- Запустите новый ярлык `Android` на рабочем столе (вы также можете закрепить его в меню «Пуск» или на панели задач для удобства).

#### Переключение на Windows
- Нажмите **"БЫСТРАЯ ЗАГРУЗКА В WINDOWS"** в приложении или используйте ярлык на панели быстрых настроек.

## Готово!

### Визуальный гайд

- Вот наглядный способ установки и проверки правильности установки Won-Deployer:

<img align="left" src="https://github.com/ArKT-7/won-deployer/blob/main/assets/tool-insatllation1.gif" width="720" alt="Installation Guide">
