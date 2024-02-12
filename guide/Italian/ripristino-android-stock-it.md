<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Disinstallare Windows su mi pad 5

## Disinstallazione

### Perché seguire questa guida? 

Se vuoi disinstallare windows velocemente, al posto di eliminare le partizioni manualmente ed eventualmente commettere anche errori + per evitare anche di scrivere un'intera guida solo per la disinstallazione...

Se vuoi bloccare il bootloader, dovrai per forza ripristinare le partizioni allo stato originale.

### Prerequisiti

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [gpt_both0.bin](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin)

### Ripristina GPT
> Sostituisci ```<gpt_both0.bin>``` con il percorso del file gpt_both0.bin.

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Formatta ```userdata``` per evitare bootloop e ripristinare la dimensione di FS
```cmd
fastboot -w
```

### Riavvia ad Android
```cmd
fastboot reboot 
```
## Fatto!
