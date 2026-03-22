<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Установка с помощью WoN-deployer

### Требования
- ```Наличие функционирующего мозга (серьёзно, вам нужно будет думать!)```

 - ```Разблокированный загрузчик``` (Если ваш загрузчик заблокирован и вы не знаете, как его разблокировать, воспользуйтесь [этим](unlock-bootloader-ru.md) руководством)

- ``` Компьютер/Ноутбук с Windows 10 (Или выше)```

- [```Драйверы ADB, установленные на вашем ПК```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)

- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/) (Выберите - Версия: `select build` Язык: `select your language`)

- [```Драйверы & Образ UEFI```](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)

---
### Примечания:
> [!NOTE]
> Для первой установки лучше прошить стоковую MIUI или HyperOS.
>
> Если вы переустанавливаете Windows, обязательно сначала загрузитесь в Android, а затем перезагрузитесь в режим fastboot перед продолжением установки.
>
> 
> Если вам нужна помощь, пожалуйста, обращайтесь в [Telegram чате](https://t.me/nabuwoaru).

> [!WARNING]
> Все ваши данные будут удалены! Сделайте резервную копию сейчас, если необходимо.
>
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ НИКАКИЕ ВИДЕОРУКОВОДСТВА НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ! ЭТИ МАТЕРИАЛЫ НЕ ЯВЛЯЮТСЯ АКТУАЛЬНЫМИ**

---

### 1. Скачать WoN Deployer (Windows on Nabu Installer)
- Откройте **`Terminal/PowerShell`** от имени администратора и пропишите эту команду:


```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

<details>
<summary><b><strong>Проверка правильности установки WoN Deployer</strong></b></summary>

1. Закройте **`PowerShell/Terminal`**, который вы открыли ранее

2. Снова откройте **`PowerShell/Terminal`** как администратор и выполните следующую команду:

```shell
won-deployer -h
```
> Если вы правильно установили WoN Deployer, он предоставит вам информацию о приложении. Если появится ошибка, перезапустите установку.

</details>

---
### 2. Как установить/переустановить Windows на Nabu 

<a href="won-deployer-install-ru.md"><img src="https://github.com/ArKT-7/won-deployer/blob/main/assets/Won-nabu-bg.png" width="280"></a>

### Перезагрузитесь в режим fastboot
- Загрузите планшет в режим **fastboot**, удерживая кнопки **`уменьшения громкости`** + **`питания`** или запустив `adb reboot bootloader` в загруженном Android со включенной откладкой USB.

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
- **Введите путь к файлу [```MiPad5-Drivers.7z```](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)**
- Скопируйте путь к файлу MiPad5-Drivers.7z и вставьте его здесь.
**`Введите путь к ZIP-файлу драйвера (Копировать как путь)::`**

### **Следуйте инструкциям на экране**

- **`Удачи`**.

> [!IMPORTANT]
> Если вы столкнулись с какой-либо ошибкой, выполните команду ниже и создайте issue co снимком экрана в [репозитории](https://github.com/ArKT-7/won-deployer) или попросите о помощи в [официальной группе Telegram](https://telegram.me/nabuwoaru)


<details>
<summary><b><strong> Как запустить программу программу с подробным выводом логов(только для случаев когда установка выдает ошибку) </strong></b></summary>

1. Закройте `PowerShell/Терминал` который вы открыли ранее

2. Снова откройте `PowerShell/Терминал` от имени администратора и выполните следующую команду:

```shell
won-deployer --debug
```

</details>

---
## 3. Настройка Dualboot

### Требования
- ```Подключение к интернету на устройстве Nabu (требуется для загрузки файлов!)```

### Настройка - Android
- После завершения настройки Android перезагрузите ваш планшет.
- Откройте предустановленное приложение `Won-deployer Setup`.
- Нажмите на каждую кнопку и следуйте инструкции на экране.
- Закройте все и снова откройте приложение `Magisk`, нажмите `OK`, чтобы завершить дополнительную настройку.
- После перезагрузки откройте приложение `WOA Helper` и предоставьте ему root-доступ.
- Нажмите `РЕЗЕРВНОЕ КОПИРОВАНИЕ BOOT ОБРАЗА` > `Windows` > `OK` Готово!
- Теперь используйте приложение WOA Helper и нажмите кнопку **БЫСТРАЯ ПЕРЕЗАГРУЗКА В WINDOWS**.

<details>
<summary><b><strong>Если возникли проблемы с предыдущим методом, можно выполнить настройку Dualboot отсюда:</strong></b></summary>

### Требования
- [```Приложение Magisk```](https://raw.githubusercontent.com/arkt-7/won-deployer/main/files/Magisk_stable.apk)

- [```Приложение WoA Helper```](https://github.com/n00b69/woa-helper/releases/tag/APK)

- [```Образ UEFI```](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases)

### Настройка - Android вручную
- Скачайте и установите приложение `Magisk`.
- Скачайте и установите приложение `WOA Helper`, откройте его и предоставьте root-доступ.
- Скачайте `образ UEFI` и поместите его в папку `UEFI` на внутреннем хранилище.
- Откройте приложение WOA Helper и нажмите кнопку **БЫСТРАЯ ЗАГРУЗКА В WINDOWS**.

</details>

### Настройка - Windows
> [!Tip]
> Если это ваш первый запуск Windows и вы хотите пропустить вход в учетную запись Microsoft, нажмите кнопку **"У меня нет интернета"** на странице Wi-Fi, затем выберите **"Продолжить с ограниченной настройкой"**.

#### Переключение на Android
- Запустите новый ярлык `Android` на рабочем столе (вы также можете закрепить его в меню «Пуск» или на панели задач для удобства).

#### Переключение на Windows
- Нажмите **"БЫСТРАЯ ЗАГРУЗКА В WINDOWS"** в приложении или используйте ярлык на панели быстрых настроек.

## Готово!
---
### Наглядный гайд

- Вот наглядный способ установки и проверки правильности установки Won-Deployer:

<img align="left" src="https://github.com/ArKT-7/won-deployer/blob/main/assets/tool-insatllation1.gif" width="720" alt="Installation Guide">
