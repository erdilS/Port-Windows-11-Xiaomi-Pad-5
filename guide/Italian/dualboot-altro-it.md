## Requisiti per il dual-boot

- Un cervello :)

- Funziona solo sullo slot A!

- Android rootato e backup dell'immagine di avvio (boot) rootata

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

