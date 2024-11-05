<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Установка

### Разметка устройства

### Требования

- ```Разблокированный Загрузчик``` - (Если ваш загрузчик заблокирован, и вы не знаете, как его разблокировать, предлагаем вам ознакомиться с [этим](unlock-bootloader-ru.md) руководством)

- ```Мозг```

- ```ПК/Ноутбук с Windows 10(или выше)```

- [```Образ рекавери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```SDK platform tools```](https://developer.android.com/studio/releases/platform-tools)

### Примечания:
>[!NOTE]
> Вы можете использовать любую версию Android для двойной загрузки — будь то MIUI, HyperOS или любая другая кастомная прошивка

>[!Warning]
> Все ваши данные будут удалены! Если это необходимо, создайте резервную копию прямо сейчас.
>
> НЕ ПЕРЕЗАГРУЖАЙТЕ ПЛАНШЕТ. Если вы считаете, что допустили ошибку, обратитесь за помощью в [чат Telegram](https://t.me/nabuwoa)
>
> **ПОЖАЛУЙСТА, НЕ ПОЛЬЗУЙТЕСЬ УСТАРЕВШИМИ ВИДЕОГАЙДАМИ, ДОСТУПНЫМИ НА YOUTUBE ИЛИ ДРУГИХ ПЛАТФОРМАХ! ЭТИ МАТЕРИАЛЫ УЖЕ НЕ АКТУАЛЬНЫ, И ИХ ИСПОЛЬЗОВАНИЕ МОЖЕТ ПРИВЕСТИ К ПОЛОМКЕ ВАШЕГО УСТРОЙСТВА. ЕСЛИ ВАМ ТРЕБУЕТСЯ ВИДЕОГАЙД, РЕКОМЕНДУЕМ ОБРАТИТЬСЯ К ЭТОМУ [НОВОМУ ВИДЕО-ГАЙДУ](https://youtu.be/BbgTbTGbXYg ) ОТ [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA )**

### Разметка устройства и резервное копирование загрузочного образа 
 
> [!NOTE]
> Если вы не знаете, с чего начать, просто извлеките загруженный [```platform-tools```](https://developer.android.com/studio/releases/platform-tools), затем откройте ```командную строку``` или `powershell` от имени администратора и выполните следующую команду, заменив `"путь\к\platform-tools"` на фактический путь к папке "platform tools"
```cmd
cd "путь\к\platform-tools"
```
> Не закрывайте это окно терминала на протяжении всего руководства.


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
> Если он попросит запустить процесс снова, пожалуйста, сделайте это.

```cmd
adb shell partition $
```

### Создайте резервную копию вашего загрузочного образа

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Проверьте, запускается ли Android
> Перезагрузите планшет, чтобы убедиться, что Android работает исправно.

```cmd
adb reboot
```
> [!NOTE]
> Если ваш смартфон застрял на этапе загрузки или загрузился в режиме HyperOS/MIUI recovery, выполните следующие действия:
> 1. Выберите пункт **`Wipe Data`**
> 2. **`Wipe All Data`**
> 3. После успешной очистки данных нажмите пункт **`Back To Main Menu`**
> 4. Нажмите пункт **`Reboot`**
> 5. **`Reboot to System`**


### [Следующий шаг: Получение root прав](/guide/Russian/2-rootguide-ru.md)
