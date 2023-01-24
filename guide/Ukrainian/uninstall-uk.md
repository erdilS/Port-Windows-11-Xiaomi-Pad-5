## Видалення Windows

> Замініть <gpt_both0.bin> на шлях до файлу gpt_both0.bin, ви можете знайти його на [сторінці релізів](../../../../releases/tag/binaries)

# Відновіть стандартної таблиці розділів

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Очищення userdata, щоб уникнути постійного завантаження і відновити розмір файлової системи
```cmd
fastboot -w
```
