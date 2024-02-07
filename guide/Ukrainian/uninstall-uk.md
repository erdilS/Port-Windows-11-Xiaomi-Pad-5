<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск Windows на Xiaomi Pad 5

## Видалення

### Навіщо це потрібно?

Якщо ви хочете видалити Windows, це використовується замість видалення розділів вручну, щоб уникнути людської помилки + написання цілого спеціального посібника з простого видалення.

Якщо ви хочете повторно заблокувати завантажувач, вам знадобиться, щоб таблиця розділів була в наявності.

### Передумова

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [gpt_both0.bin](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin)

### Відновіть стандартної таблиці розділів

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Очищення ```userdata```, щоб уникнути нескінченного завантаження і відновити розмір файлової системи
```cmd
fastboot -w
```
### Перезавантаження на Android
```cmd
fastboot reboot 
```
## Зроблено!
