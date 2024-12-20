<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 работает на Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Установка

### Требования
- ```Разблокированный загрузчик``` - (Если ваш загрузчик заблокирован и вы не знаете, как его разблокировать, воспользуйтесь [этим](https://github.com/Andrew-star2008/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/Russian/unlock-bootloader-ru.md) руководством)

- ```Мозг```

- ```ПК/ноутбук с Windows 10 (или более поздней версией)```

- [```Инструменты платформы Android```](https://developer.android.com/studio/releases/platform-tools)

- [```Модифицированный образ recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

### Примечания:
> [!NOTE]
> Вы можете использовать любой Android для dualboot — MIUI/Hyper OS или любую кастомную прошивку

> [!WARNING]
> Все ваши данные будут удалены! При необходимости сделайте резервную копию.
> 
> НЕ ПЕРЕЗАГРУЖАЙТЕ ПЛАНШЕТ, если считаете, что допустили ошибку, обратитесь за помощью в [чат Telegram](https://t.me/nabuwoa)

### Открытие CMD от имени администратора
> [!NOTE]
> Не знаете, как начать? Распакуйте загруженные [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools), затем откройте **```командную строку```** от имени администратора и выполните следующую команду, заменив `"путь\к\папке"` на фактический путь к папке platform tools
```cmd
cd "путь\к\папке"
```
> Используйте это окно на протяжении всего руководства. Не закрывайте его.

> [!NOTE]
> Если ваше устройство не определяется в fastboot или recovery, вам потребуется установить USB-драйверы с помощью [этого](troubleshooting-en.md#device-is-not-recognized-in-fastboot-or-recovery) руководства

#### Перезагрузка в fastboot 
- Перезагрузите NABU в **fastboot**, удерживая нажатой кнопку **`уменьшения громкости`** во время перезагрузки с подключенным USB-кабелем.
- Или, если у вас включена отладка по USB, выполните команду ниже находясь в Android с подключенным USB-кабелем.
```cmd
adb reboot bootloader
```

### Загрузка recovery 
> В режиме быстрой загрузки замените `путь\к\recovery.img` на фактический путь к образу recovery
```cmd
fastboot boot путь\к\recovery.img
```

### Разметка устройства
> Замените **$** на объём памяти, который вы хотите выделить для Windows (не добавляйте ГБ, просто напишите число)
> 
> Если вас попросят выполнить команду ещё раз, сделайте это
```sh
adb shell partition $
```

### Создайте резервную копию boot.img
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### Проверьте, загружается ли Android
> Перезагрузитесь, чтобы проверить
```cmd
adb reboot
```

> [!NOTE]
> Если устройство не загружается в Android, перезагрузите его в fastboot и выполните `fastboot -w` или загрузитесь в стандартное recovery и сделайте **Factory Reset**

### [Следующий шаг: получение root](/guide/English/2-rootguide-ru.md)
