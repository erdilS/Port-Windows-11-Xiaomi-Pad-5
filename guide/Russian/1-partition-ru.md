<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Установка

### Требования
- ```Разблокированный загрузчик``` - (если он у вас не разблокирован, и вы не знаете как это сделать, посмотрите [этот](unlock-bootloader-ru.md) гайд)

-  ```Мозг```

- ```ПК/Ноутбук c Windows 10(или выше)```

- [```SDK platform-tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Модифицированный образ recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

### Заметки:
> [!NOTE]
> Вы можете использовать любой Android для dualboot - MIUI/HyperOS или любую кастомную прошивку 

> [!Warning]
> Все ваши данные будут удалены! Создайте резервную копию, если необходимо.
> 
> НЕ ПЕРЕЗАГРУЖАЙТЕ ПЛАНШЕТ, если вы считаете, что допустили ошибку, обратитесь за помощью в [чат Telegram](https://t.me/nabuwoa)

### Откройте CMD от имени администратора
> [!NOTE]
> Не знаете, с чего начать? Распакуйте загруженный [```SDK platform-tools```](https://developer.android.com/studio/releases/platform-tools), затем откройте ```командную строку``` от имени администратора и запустите следующую команду, заменив `"путь\к\platform-tools"` на фактический путь к папке platform tools
```cmd
cd "путь\к\platform-tools"
```
> Используйте это окно на протяжении всего руководства. Не закрывайте его.

> [!Note]
> Если ваше устройство не определяется в fastboot или recovery, вам потребуется установить драйверы USB с помощью [этого](troubleshooting-ru.md#device-is-not-recognized-in-fastboot-or-recovery) гайда

#### Перезагрузка в fastboot 
- Перезагрузите NABU в **fastboot**, удерживая нажатой кнопку **`уменьшения громкости`** во время перезагрузки с подключенным USB-кабелем.
- Или, если у вас включена отладка по USB, выполните команду ниже находясь в Android с подключенным USB-кабелем.
```cmd
adb reboot bootloader
```


### Загрузка в модифицированный recovery
> Находясь в режиме fastboot, замените `путь\к\recovery.img` фактическим путем к образу recovery
```cmd
fastboot boot путь\к\recovery.img
```

### Создайте резервную копию вашего существующего загрузочного образа
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

### Разметка устройства 
> Существует два способа разделения вашего устройства. Пожалуйста, выберите метод, который вы хотели бы использовать ниже.

#### Способ 1: Ручная разметка 

<details>
  <summary><strong>Нажмите здесь, чтобы развернуть способ 1</strong></summary> 

#### Размонтировать data 
> Игнорируйте все возможные ошибки и продолжайте
```cmd
adb shell umount /dev/block/by-name/userdata
``` 

#### Изменение размера таблицы разделов 
```cmd
adb shell sgdisk --resize-table 64 /dev/block/sda
```

#### Подготовка к разметке 
```cmd
adb shell parted /dev/block/sda
``` 

#### Отображение текущей таблицы разделов
> Parted выведет список разделов, **userdata** должен быть последним разделом в списке
```cmd
print
``` 

#### Удаление userdata
> Замените **$** номером раздела **userdata**, который должен быть **31**
```cmd
rm $
``` 

#### Повторное создание userdata
> Замените **10.9GB** на прежнее начальное значение **userdata**, которую мы только что удалили
>
> Замените **70GB** конечным значением, которое вы хотите иметь **userdata**. В этом примере ваше доступное полезное пространство в Android составит 70 ГБ \ -10.9 ГБ \ = **59 ГБ**
```cmd
mkpart userdata ext4 10.9GB 70GB
``` 

#### Создание раздела ESP
> Замените **70GB** на конечное значение **userdata**
>
> Замените **70.3GB** значением, которое вы использовали ранее, добавив к нему **0.3GB**
```cmd
mkpart esp fat32 70GB 70.3GB
``` 

#### Создание раздела для Windows
> Замените **70.3GB** на конечное значение **esp**
```cmd
mkpart win ntfs 70.3GB -0MB
``` 

#### Маркировка раздела ESP как загрузончный
> Используйте `print`, чтобы просмотреть все разделы. Замените **$** номером вашего раздела ESP, который должен быть **32**
```cmd
set $ esp on
``` 

#### Выход из parted
```cmd
quit
``` 

### Форматирование данных
> Убедитесь, что **userdata** действительно имеет номер раздела **31**, прокрутив его до выходных данных команды `print`
```cmd
adb shell mke2fs -t f2fs -f /dev/block/sda31
```

#### Проверьте, запускается ли Android по-прежнему
> Если этого не произойдет, загрузитесь в stock recovery и выполните **сброс к заводским настройкам** там
```cmd
adb reboot
```

### Форматирование разделов Windows и ESP
```cmd
adb shell mkfs.ntfs -f /dev/block/by-name/win -L WINNABU
``` 

```cmd
adb shell mkfs.fat -F32 -s1 /dev/block/by-name/esp -n ESPNABU
``` 

</details>

#### Способ 2: Автоматическое разделение

<details>
  <summary><strong>Нажмите здесь, чтобы ознакомиться со способом 2</strong></summary> 

### Запустите сценарий разбиения на разделы
> Замените **$** на объем хранилища, который вы хотите предоставить Windows (не добавляйте ГБ, просто напишите число)
> 
> Если он попросит вас запустить его еще раз, сделайте это
```cmd
adb shell partition $
``` 

#### Проверьте, запускается ли Android по-прежнему
> Если этого не произойдет, загрузитесь в stock recovery и выполните **сброс к заводским настройкам** там
```cmd
adb reboot
```

</details>

### [Следующий шаг: Получение root](/guide/Russian/2-rootguide-ru.md)

