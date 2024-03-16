<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Запуск Windows на Xiaomi Pad 5

Цей крок потрібен щоби ми створили розділи, де буде знаходитись Windows

### Необхідні файли

- ```розблокований завантажувач```

- [```Відновлення```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

## Нотатки:
> [!NOTE]
> Не знаєте, як почати? Просто Розпакуйте завантажений [```Android platform tools```](http://developer.android.com/studio/release/platform-tools), наприклад ```"C:\platform-tools"``` потім відкрийте ```командний рядок``` або `powershell` як адміністратор і введіть:

```cmd
cd "шлях\до\platform-tools"
```
> Замініть ```"шлях\до\platform-tools"``` фактичним шляхом до папки platform tools



> [!WARNING]\
> Якщо ви видалили будь-який розділ використовуючи diskpart, Windows рано или пізно відправить команду пам'яти, яка буде неправильно розпізнана, і тому пам'ять буде стерта.
> 
> Усі ваші дані будуть видалені! Зробіть резервне копіювання, якщо потрібно.
> 
> Усі команди були перевірені.
>
> НЕ ПЕРЕЗАВАНТАЖУЙТЕ ВАШ ПЛАНШЕТ якщо думаєте, що зробили помилку - зверніться в [Telegram-чат проекту](https://t.me/nabuwoa).

#### Завантажте TWRP через комп'ютер за допомогою fastboot
```cmd
fastboot boot <recovery.img>
```

##### Запустіть скрипт розмітки
> Якщо скрипт попросить запустити його ще раз, то так і зробіть

> Це необов'язково, але ви можете встановити власні розміри за допомогою цього сценарію

> Щоб встановити власні розміри, виконайте ``adb shell partition [цільовий розмір розділу з Windows у ГБ]``

> Переконайтеся, що ви не додаєте GB в кінці, лише кількість
```cmd
adb shell partition
```

### Створіть резервну копію наявного образу завантаження 

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### Перевірте, чи запускається Android 
> Перезавантажте, щоб перевірити, чи працює Android. Якщо він не завантажується, зітріть усі дані та повторіть спробу. 

```cmd
adb reboot
```

## [Наступний крок: отримання root](/guide/Ukrainian/2-rootguide-uk.md)
