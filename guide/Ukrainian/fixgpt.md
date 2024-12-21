<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Працює на Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Виправлення GPT для безпечного використання Windows 24H2

### Передумови:
- [```Вже встановлена ​​Windows```](/guide/Ukrainian/selection-uk.md)

- [```Образ відновлення```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```platform-tools```](https://developer.android.com/studio/releases/platform-tools)

> [!Warning]
> Якщо ви хочете безпечно використовувати Windows 24H2, виконайте ці кроки, щоб уникнути проблем з EDL.

> [!ПРИМІТКА]
> Це не вплине на Android або Windows.

### Перезавантажтеся в режим швидкого завантаження
- Завантажте свій NABU в **режим fastboot**, утримуючи кнопку **`зменшення гучності`** під час перезавантаження з допомогою під’єднаним кабелем USB
- Або, якщо у вас увімкнено налагодження USB, виконайте у Android наведену нижче команду:
```cmd
adb reboot bootloder
```

### Завантажте модифіковане відновлення
> Замініть `path\to\recovery.img` на фактичний шлях до завантаженого **recovery.img**
```cmd
fastboot boot fastboot\до\recovery.img
```

### Виправлення GPT
> Після завантаження в образ відновлення
>
> Якщо вам буде запропоновано запустити його знову, зробіть це
```cmd
adb shell fixgpt
```

### Перезавантажте пристрій
```cmd
adb reboot
```

## ✅ Готово! Windows 24H2 тепер можна безпечно використовувати
