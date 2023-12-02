<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows на Xiaomi Pad 5

## Переустановка
### Переустановка Windows если что-то пошло не так

- Если текущая версия Windows не подходит или была испорчена, вероятно, Вам поможет переустановка Windows, благо это довольно простой процесс.
- Если Вы не восстанавливали таблицу разделов, то используйте этот гайд с текущей таблицей разделов.

### Требования

- Существующие разделы для Windows и загрузки (*если их нет, [используйте данную инструкцию](/guide/Russian/partition-ru.md)*)
- [Образ рекавери](../../../../releases/tag/1.0)
- [ADB и Fastboot](https://developer.android.com/studio/releases/platform-tools)



### Запустите рекавери для форматирования разделов

```cmd
fastboot boot <recovery.img>
```

### Форматирование разделов

```cmd
adb shell format
```

#### Выполните скрипт msc

```cmd
adb shell sh /sbin/msc.sh
```

### Привязка букв к разделам
  

#### Запустите Менеджер дисков Windows

> Как только планшет определился как диск

```cmd
diskpart
```

- Раздел "WINNABU" уже должен отображаться с буквой `X`. В таком случае перейдите к разделу `Привязка буквы  "Y"  к разделу ESP`

#### Привязка буквы  `X`  к разделу Windows

#### Выберите Windows раздел планшета
> Используйте команду `list volume` чтобы найти раздел с названием "WINNABU"

```diskpart
select volume <number>
```

#### Привяжите букву X
```diskpart
assign letter=x
```

### Привязка буквы  `Y`  к разделу ESP

#### Выберите ESP раздел планшета
> Используйте команду `list volume` чтобы найти раздел с названием "ESPNABU"

```diskpart
select volume <number>
```

#### Привяжите букву Y

```diskpart
assign letter=y
```

- Если Вы получаете ошибку `The specified drive letter is not free to be assigned`, перезапустите компьютер и попробуйте снова. Пока что не трогайте планшет.

#### Закройте diskpart
```diskpart
exit
```


### [Следующий шаг](/guide/Russian/install-ru.md#установка-windows)
