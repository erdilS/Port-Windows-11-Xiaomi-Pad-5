<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Запуск вікон на майданчику Xiaomi 5

## Відновлення пристрою в режимі EDL
> Цей посібник включає два методи для прошивки вашого пристрою, якщо метод 1 не вдається, використовуйте метод 2

## Введення планшету у режим EDL
> Існує два методи завантаження вашої Xiaomi Pad 5 в режим **EDL**

> [!Note]
>
> ▶ ️ Клацніть, щоб розкрити меню

<details>
 <summary><strong>Метод 1: Розблокований завантажувач</strong></summary>

> Якщо ваш завантажувач розблокований, просто запустіть наступну команду в режимі **fastboot**:
```cmd
fastboot oem edl
```

</details>

<details>
 <summary><strong>Метод 2: Заблокований завантажувач або якщо пристрій не завантажується</strong></summary>

- Вставте **EDL** кабель у свій пристрій (якщо у вас він є), і натисніть кнопку на кабелі, щоб завантажити планшет у **EDL** режим.
> Кабелі EDL, які можна знайти в Інтернеті повинні включати v2 в назві, наприклад, **Hydra v2 EDL кабель**.
- Крім того, ви можете замкнути **test point** (вимагає відкриття задньої панелі вашого пристрою).

</details>

### Перевірка, чи все гаразд
- Відкрийте **Менеджер пристроїв** на своєму ПК та знайдіть новий пристрій, наприклад, **Qualcomm HS-USB QDLoader 9008**.
- Якщо пристрій має назву **QUSB_BULK_CID** та/або має жовте попередження ⚠ вам потрібно встановити/оновити драйвери.
- Для цього завантажте, розпакуйте архів **[qud.zip](https://github.com/n00b69/woa-betalm/release/download/qfil/qud.zip)**, виберіть пристрій з помилкою в Менеджер пристроїв, виберіть **Оновлення драйверів**, а потім виберіть папку яку ви щойно розпакували.

## Прошивка

### Передумови
- `Виправлений Mi Flash` (https://github.com/erdils/port-windows-11-xiaomi-pad-5/release/download/1.0/miflashpatched.zip)

- `Виправлений firehose (.elf) файл` (https://github.com/erdils/port-windows-11-xiaomi-pad-5/release/download/1.0/prog_ufs_firehose_sm7150_ddr.elf)

- `Розпакована Fastboot прошивка для планшету` (http://xmfirmwareupdater.com/miui/nabu/)

### Підготовка необхідних файлів
- Розпакуйте **Fastboot прошивку** для вашого плашнету Xiaomi Pad 5.
- Розпакуйте **MiflashPatched.zip** файл, який ви завантажили раніше.
- Скопіюйте раніше завантажений файл **firehose (.elf)** у папку **images** всередині вашої витягнутої **прошивки**, перезаписавши існуючий файл.

### Відкрийте MiFlash
- Перейдіть до папки **MiFlash** всередині витягнутої **MiflashPatched.zip**.
- Запустіть **xiaomiflash.exe** від імені адміністратора.

### Прошивка
- Натисніть кнопку **Select** в **MiFlash** і виберіть папку з **прошивкою** (там де ви замінили файл **firehose (.elf)**).
- У інструменті **MiFlash** переконайтеся, що ви обрали варіант **Flash all**.
- Клацніть **Refresh** в **MiFlash**, щоб перевірити з'єднання з вашим пристроєм.
- Після підтвердження вашого пристрою виявлено і вибрано **Flash all**, натисніть кнопку **Flash**, щоб запустити процес прошивки.

> [!WARNING]
> Якщо ви бачите будь-яку помилку, яка не проходить через 2 хвилини, перезавантажте пристрій у режим **EDL** знову, а потім натисніть **Refresh** і **Flash** для прошивки.

### Перезавантажте пристрій
- Після завершення прошивки натисніть кнопку **Reboot**, щоб перезапустити пристрій.

## Кінець
Ваш Xiaomi Pad 5 тепер повинен бути успішно відновлений до початкового робочого стану!