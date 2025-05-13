<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Удаление Windows
> [!NOTE]
> Если вы хотите повторно заблокировать загрузчик, вам понадобится исходная таблица разделов.

> [!WARNING]
> **Все ваши данные будут удалены! При необходимости создайте резервную копию прямо сейчас.**

### Загрузка в Android
> [!NOTE]
> Если вы в последний раз загружались в Windows, сначала переключитесь на Android, прежде чем начинать процесс удаления

#### Перезагрузка в fastboot
- Загрузите NABU в режим **fastboot**, удерживая нажатой кнопку **`уменьшения громкости`** во время перезагрузки при подключенном USB-кабеле
- Или, если у вас включена отладка по USB, выполните приведённую ниже команду при загрузке Android.
```cmd
adb reboot bootloader
```

> [!NOTE]
>
> Нажмите ▶️, чтобы развернуть меню.

<details>
  <summary><strong>Способ 1 - Удаление с помощью adb shell restore</strong></summary>

### Предварительные условия
- [```SDK platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Моддифицированый образ recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img) 

#### Загрузка в моддифицированый recovery
> Замените ```путь\к\recovery.img``` на физический путь к recovery.img
```cmd
fastboot boot путь\к\recovery.img
```

### Восстановите таблицу разделов
> [!WARNING]
> Это приведет к удалению файлов Android. При необходимости сначала создайте резервную копию.

```cmd
adb shell restore
```

#### Перезагрузка в Android
```cmd
adb reboot 
```

## Готово!

</details>

<details>
  <summary><strong>Способ 2 - Удаление в fastboot</strong></summary>

### Предварительные условия
- [```SDK platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```gpt_both0.bin```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin) 

### Восстановление таблицы разделов   
> Замените ```путь\к\gpt_both0.bin``` на физический путь к gpt_both0.bin
```cmd
fastboot flash partition:0 путь\к\gpt_both0.bin
```

#### Удаление пользовательских данных
> Чтобы избежать сбоя при загрузке и восстановить размер FS
```cmd
fastboot -w
```

#### Перезагрузка в Android
```cmd
fastboot reboot
```

## Готово!

</details>

<details>
  <summary><strong>Способ 3 - Удаление с помощью "Nabu Fastboot Tool"</strong></summary>

### Предварительные условия
 **`Кабель`**` для подключения вашего `**`Xiaomi Pad 5`**` к `**`другому устройству`**`

 **`Любое другое устройство (Android, Windows, Mac или Linux)`**

### Подключитесь к Fastboot Tool на веб-сайте
- Откройте **[Nabu Fastboot Tool](https://arkt-7.github.io/nabu/)** в браузере любого устройства.
- Нажмите на кнопку **"Connect device Fastboot"**.
- Выберите **`Android`** из появившегося списка и нажмите **`Разрешить`**.

### Форматирование и создание разделов
- Прокрутите вниз до раздела **`Format/wipe make Partition Stock`**.
- В поле ввода введите **`FORMAT`**.
- Наконец, нажмите кнопку **`Format/Wipe`**.
- После завершения форматирования появится всплывающее окно с сообщением об успешном завершении. Нажмите **`ОК`** для закрытия всплывающего окна.
- Прокрутите вверх и нажмите кнопку **`Reboot Device`** для перезагрузки устройства.


 ### Если ваше устройство **перезагрузилось в режиме recovery** после удаления Windows, выполните следующие действия:

- Прокрутите вниз до раздела **`Format/wipe make Partition Stock`**.
- В поле ввода введите **`FORMAT`**.
- Наконец, нажмите кнопку **`Format/Wipe`**.
- После успешной очистки данных нажмите прокрутите вверх и нажмите кнопку **`Reboot Device`** для перезагрузки устройства.

## Готово!

</details>
