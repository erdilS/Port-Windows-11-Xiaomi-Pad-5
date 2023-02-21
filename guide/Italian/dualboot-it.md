<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Eseguire il dualboot tra Windows e Android

### Prerequisiti

- Un cervello (per favore)

- Android rootato e il backup dell'immagine di avvio creato in precedenza (boot.img)

- [Scarica i file necessari](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Configurazione dualboot dalla parte di Windows

- Installa [Cygwin](https://www.cygwin.com/setup-x86_64.exe) con coreutils (sará installato di default)

- Rinomina l'immagine di avvio di Android in boot.img

- Posiziona l'immagine di avvio (boot.img) nel percorso C:\ (C:\boot.img)

- Avvia il file .bat come amministratore oppure crea un collegamento con i privilegi di amministratore

### Configurazione dualboot dalla parte di Android

- Installa switchtowin.apk su Android.

- Rinomina il file UEFI in boot.img

- Posiziona il file UEFI nel percorso /sdcard/windows (/sdcard/windows/boot.img)

- Apri l'app e concedi i permessi di root.

- Clicca su "Switch to Windows" se vuoi avviare Windows.

#### FINITO.

### Altri link utili...

### [Aggiornare i driver](/guide/Italian/aggiornamento-driver-it.md)

### [Risolvere problemi](/guide/Italian/risoluzione-problemi-it.md)

### [Stato del progetto](/guide/Italian/stato-progetto-it.md)

### [Ripristino totale del tablet, eliminare Windows e ripristinare le partizioni](/guide/Italian/ripristino-android-stock-it.md)


