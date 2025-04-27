<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Полезные инструкции для Windows на Xiaomi pad 5

### Отключение SecureBoot
> [!Important]
> Используйте этот гайд, только если вам необходимо отключить SecureBoot.

- [Перейдите на страницу гайда и следуйте ему](/guide/Russian/disable-secureboot-ru.md)

### Списки поддерживаемых игр/приложений
> Эти списки ни в коем случае не полные, однако в них перечислены те игры/приложения, что были протестированы сообществом.

- [Google таблица Renegade](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

- [ARM Repo (нативные ARM приложения)](https://armrepo.ver.lt/)

- [Новости и поддерживаемые приложения](https://windowsonarm.org/)


### Переключение режима USB хоста
> [!WARNING]
> Выключите режим USB хоста, если вы используете USB-хаб с питанием,посколько он может сломать ваш порт. Если вы не используете такой хаб, включите режим USB хоста, иначе ни одно устройство USB не будет работать.

- Запустите [USB Host Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) для включения или отключения режима USB хоста, а затем подтвердите свой выбор.
- Если режим USB хоста включен,но устройства USB всё равно не работают, выключите режим USB хоста и включите занаво.

#### Готово!


### Установка Microsoft Office
- Перейдите на [страницу установки Office от Gravesoft](https://gravesoft.dev/office_c2r_links).
- Скачайте установщик, подходящий вашим требованиям. Убедитесь, что вы выбрали установщик `Online x64`.
- Откройте `setup.exe` и следуйте всем инструкциям в приложении.

#### Готово!


### Активация Windows / Office
- [Следуйте этой инструкции от Massgravel](https://github.com/massgravel/Microsoft-Activation-Scripts)

#### Готово!


### Включение плавающей клавиатуры
> [!WARNING]
> Убедитесь,что вы выполняете эти шаги на планшете, а не на вашем компьютере!

- Откройте консоль от имени администратора и введите ```reg delete HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Scaling /v MonitorSize```
- После этого нажмите `y`.
- Перезагрузите планшет.

##### Готово!

