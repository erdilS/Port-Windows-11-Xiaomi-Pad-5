<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Запуск Windows на Xiaomi Pad 5

## Перевстановлення

### Запуск Windows на Xiaomi Pad 5 Windows якщо щось йде не так

- Якщо вам не подобається ваша версія Windows, зіпсували Windows, або щось інше, ви, ймовірно, можете просто перевстановити Windows. На щастя, цей процес дуже простий.

- Якщо ви не відновили таблицю розділів, ви можете скористатися цим посібником із наявними розділами.

### Вимоги

- Існуючий завантажувальний і основний розділ Windows (*Якщо цих розділів немає, [поверніться до основного посібника](/guide/Ukrainian/install-uk.md)*) та уявіть, що цей ніколи не існував

- [Образ відновлення](../../../../releases/tag/1.0)

- [ADB й Fastboot](https://developer.android.com/studio/releases/platform-tools)


### Завантаження у відновлення для форматування основного і завантажувального розділа Windows

```cmd
fastboot boot <recovery.img>
```
### Форматування розділів


```cmd
adb shell format
```

#### Виконайте сценарій msc.sh

```cmd
adb shell msc
```

### Призначте літери дискам.

#### Запустіть диспетчер дисків Windows

> Як тільки Xiaomi Pad 5 буде виявлено як диск

```cmd
diskpart
```

- Розділ "WINNABU" вже повинен відображатися з літерою X:. Якщо так і є, перейдіть до призначення літери Y для розділу завантаження Windows

#### Призначення літери X основному розділу Windows

#### Виберіть розділ Windows у планшеті
> Використовуйте `list volume`, щоб знайти його, він називається "WINNABU"

```diskpart
select volume <number>
```

#### Призначте літеру X
```diskpart
assign letter=x
```

### Призначення літери Y для розділу завантаження Windows

#### Виберіть розділ Windows у планшеті
> Використовуйте `list volume`, щоб знайти його, він називається "ESPNABU"

```diskpart
select volume <number>
```

#### Призначте літеру Y

```diskpart
assign letter=y
```

- Якщо ви отримуєте помилку «Зазначену букву диска не можна призначити», просто перезавантажте комп’ютер і повторіть спробу. Поки що не торкайтеся планшета.

#### Вийдіть з diskpart
```diskpart
exit
```



### Встановлення

- Продовжуйте з [цього](/guide/Ukrainian/install-uk.md#Встановлення) моменту
