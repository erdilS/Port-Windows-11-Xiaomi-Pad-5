<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Запуск Windows на Xiaomi Pad 5

## Перевстановлення

### Запуск Windows на Xiaomi Pad 5 Windows якщо щось йде не так

- Якщо вам не подобається ваша версія Windows, зіпсували Windows, або щось інше, ви, ймовірно, можете просто перевстановити Windows. На щастя, цей процес дуже простий.

- Якщо ви не відновили таблицю розділів, ви можете скористатися цим посібником із наявними розділами.

### Вимоги

- Існуючий завантажувальний і основний розділ Windows (*Якщо цих розділів немає, [поверніться до основного посібника](/guide/Ukrainian/install-uk.md)*) та уявіть, що цей ніколи не існував

- [Образ відновлення](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB й Fastboot](https://developer.android.com/studio/releases/platform-tools)


### Завантаження у відновлення для форматування основного і завантажувального розділа Windows

```cmd
fastboot boot <recovery.img>
```
### Форматування розділів
> Якщо він попросить запустити його ще раз так і зробіть


```cmd
adb shell format
```



- Продовжуйте з [цього](/guide/Ukrainian/3-install-uk.md#Запустити-msc) моменту
