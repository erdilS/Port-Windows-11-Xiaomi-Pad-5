<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Установка

### Разметка устройства

### Требования

- ```Разблокированный Загрузчик``` - (Если ваш загрузчик заблокирован и вы не знаете, как его разблокировать, воспользуйтесь [этим](unlock-bootloader-ru.md) руководством)

- ```Мозг```

- ```ПК/Ноутбук с Windows 10(или выше)```

- [```Образ рекавери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

### Примечания:
>[!NOTE]
> Вы можете использовать любой Android для двойной загрузки - MIUI/Hyper OS или любую кастомную прошивку

>[!Warning]
> Все ваши данные будут удалены! Если необходимо, создайте резервную копию сейчас.
>
> НЕ ПЕРЕЗАГРУЖАЙТЕ ПЛАНШЕТ, если вы считаете, что совершили ошибку, обратитесь за помощью в [чат Telegram](https://t.me/nabuwoa)
>
> **ПОЖАЛУЙСТА, НЕ ИСПОЛЬЗУЙТЕ УСТАРЕВШИЕ ВИДЕО-ГАЙДЫ НА YOUTUBE ИЛИ ЛЮБОЙ ДРУГОЙ ПЛАТФОРМЕ! ЭТИ ВИДЕО УСТАРЕЛИ, И ВЫ МОЖЕТЕ ОКИРПИЧИТЬ СВОЁ УСТРОЙСТВО, ИСПОЛЬЗУЯ ИХ! ЕСЛИ ВАМ НУЖЕН ВИДЕО-ГАЙД, ВОСПОЛЬЗУЙТЕСЬ ЭТИМ [НОВЫМ ВИДЕО-ГАЙДОМ](https://youtu.be/BbgTbTGbXYg ) ОТ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA )**

### Разметка устройства и резервное копирование загрузочного образа 
 
> [!NOTE]
> Не знаете с чего начать? Просто извлеките загруженные [```platform-tools```](https://developer.android.com/studio/releases/platform-tools), затем откройте ```командную строку``` или `powershell` как администратор и выполните следующую команду, заменив `"path\to\platform-tools"` на фактический путь к папке инструментов платформы
```cmd
cd "path\to\platform-tools"
```
> Используйте это окно терминала на протяжении всего руководства. Не закрывайте его.


#### Перезагрузитесь в fastboot
- Загрузите планшет в **fastboot**, удерживая кнопку **`уменьшения громкости`** во время перезагрузки.

- Подключите его к ПК/ноутбуку с помощью кабеля.

#### Загрузитесь в модифицированный recovery
> Замените **путь\к\recovery.img** на фактический путь к образу recovery
```cmd
fastboot boot путь\к\recovery.img
```

##### Разметка устройства
> Замените **$** на количество памяти, которое вы хотите выделить для системы Windows (не добавляйте ГБ, просто укажите число).
> 
> Если он попросит запустить его ещё раз, то так и сделайте

```cmd
adb shell partition $
```

### Сделайте резервную копию вашего загрузочного образа 

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Проверьте, запускается ли Android
> Перезагрузите планшет, чтобы проверить, работает ли Android.

```cmd
adb reboot
```
> [!NOTE]
> Если он завис на загрузочной анимации или загрузился в HyperOS/MIUI recovery выполните следующие шаги:
> 1. Выберите **`Wipe Data`**
> 2. **`Wipe All Data`**
> 3. После успешной очистки данных нажмите **`Back To Main Menu`**
> 4. Нажмите **`Reboot`**
> 5. **`Reboot to System`**


### [Следующий шаг: Получение root прав](/guide/Russian/2-rootguide-ru.md)
