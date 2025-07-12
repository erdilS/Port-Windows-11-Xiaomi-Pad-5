<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Переустановка
Если текущая версия Windows не подходит или была испорчена, вероятно, Вам поможет переустановка Windows, благо это довольно простой процесс.

> [!WARNING]
> Совершенно очевидно, что это сотрет все ваши файлы в Windows. Если вы хотите создать резервную копию ваших файлов, вы можете сделать это, смонтировав Windows с помощью приложения [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) и вручную скопировав все файлы, которые вы хотите сохранить

### Требования

- ```Существующие разделы для Windows и загрузки``` (*если их нет, [используйте данную инструкцию](/guide/Russian/partition-ru.md)*)
  
- [```Образ рекавери```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```Androis platform tools```](https://developer.android.com/studio/releases/platform-tools)

### Перезагрузите в **fastboot**
- Загрузите планшет в **fastboot**, удерживая кнопку **громкости вниз** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

### Запустите рекавери для форматирования разделов

```cmd
fastboot boot путь/к/recovery.img
```

### Форматирование разделов
> Если он попросит запустить его ещё раз, то так и сделайте
```cmd
adb shell format
```


### [Следующий шаг: Установка Windows](/guide/Russian/3-install-ru.md#Запустите-msc)
