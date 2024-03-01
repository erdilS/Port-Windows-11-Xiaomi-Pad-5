<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Esecuzione di Windows sullo Xiaomi Pad 5

## Reinstallazione
Se non ti piace la tua versione di Windows o hai bloccato l'installazione di Windows o qualsiasi altra cosa, probabilmente reinstallerai Windows. Per fortuna questo processo è molto semplice.

> [!IMPORTANT]
> Ovviamente, questo cancellerà tutti i tuoi file di Windows. Se desideri eseguire il backup di uno di essi, puoi farlo montando Windows utilizzando l'app [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) e copiando manualmente tutti i file che desideri conservare


### Prerequisiti

- ```Partizioni esistenti di Windows e di avvio``` (*Se non soddisfatte, [torna indietro e fai finta che questa guida non sia mai esistita](/guide/Italian/1-partition-it.md)*)

- [```Recovery Immagine```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)


### Ripristino dell'avvio per formattare le partizioni Windows ed ESP

```cmd
fastboot boot <recovery.img>
```

### Formattare le partizioni
> Se ti chiede di eseguirlo ancora una volta, fallo
```cmd
adb shell format
```
## [Passaggio successivo: reinstallazione di Windows](/guide/Italian/3-install-it.md#Esegui-lo-msc)

