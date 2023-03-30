<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Windows на Xiaomi Pad 5

## Удаление

### Почему это необходимо?

Если вы хотите удалить Windows, используйте данный упрощенный метод вместо ручного удаления разделов чтобы исключить риск ошибки.

Если вы хотите заблокировать загрузчик обратно, убедитесь что таблица разделов находится в заводском состоянии.

### Требования

- [ADB и Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)

### Восстановление GPT
> Замените ```<gpt_both0.bin>``` путём к файлу `gpt_both0.bin`.

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Очистите раздел `userdata` чтобы избежать цикличной перезагрузки и восстановить размер файловой системы
```cmd
fastboot -w
```
