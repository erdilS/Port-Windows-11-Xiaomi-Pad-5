<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Установка

### Разметка устройства

### Требования

- [```Образ рекавери```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```ADB и Fastboot```](https://developer.android.com/studio/releases/platform-tools)

### Примечание:
> [!WARNING]
> если вы удалите любой раздел с помощью diskpart сейчас или позже, Windows рано или поздно отправит команду памяти, которая будет неправильно распознана в следствие чего вся память будет стёрта!
> 
> Все пользовательские файлы будут уалены! Создайте резервную копию, если это необходимо.
> 
> Эти команды были протестированы.
> 
> Игнорируйте ошибки `udevadm`.
> 
> НЕ ПЕРЕЗАГРУЖАЙТЕ ПЛАНШЕТ! Если вы считаете, что совершили ошибку, обратитесь за помощью в [чат Telegram](https://t.me/nabuwoa).
>
>  Не запускайте все команды сразу, выполняйте их по очереди!
>
> Следуйте инструкции с осторожностью! В случае ошибки велика вероятность нарушить работоспособность устройства!


#### Запустите рекавери с компьютера при помощи команды
```cmd
fastboot boot <recovery.img>
```
##### Разметка устройства
> Если он попросит запустить его ещё раз, то так и сделайте

> Это **необязательно**, но вы также можете установить **пользовательские размеры (по умолчанию это делит хранилище пополам)**

> Чтобы задать пользовательские размеры, выполните ``adb shell partition [ЦЕЛЕВОЙ РАЗМЕР РАЗДЕЛА С WINDOWS В ГБ]``

> Убедитесь, что вы не добавили GB в конце, только число 
```cmd
adb shell partition
```

### Make a backup of your existing boot image

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Check if Android still starts
> just see if Android still works
If isn't boot or looping on animation, use MIUI recovery or other recoveries for wiping data.

```cmd
adb reboot
```



### [Следующий шаг: Получить root](/guide/Russian/2-rootguide-ru.md)
