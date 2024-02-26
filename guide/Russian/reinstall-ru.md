<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Переустановка
Если текущая версия Windows не подходит или была испорчена, вероятно, Вам поможет переустановка Windows, благо это довольно простой процесс.

> [!IMPORTANT]
> Quite obviously, this will erase all of your Windows files. If you'd like to back up any of them, you can do so by mounting Windows using the [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) app and manually copying any files you wish to keep

### Требования

- Существующие разделы для Windows и загрузки (*если их нет, [используйте данную инструкцию](/guide/Russian/partition-ru.md)*)
  
- [Образ рекавери](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [ADB и Fastboot](https://developer.android.com/studio/releases/platform-tools)



### Запустите рекавери для форматирования разделов

```cmd
fastboot boot <recovery.img>
```

### Форматирование разделов
> Если он попросит запустить его ещё раз, то так и сделайте

```cmd
adb shell format
```


### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md#Запустите-msc)
