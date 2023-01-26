Questi sono i passaggi necessari per creare le partizioni necessarie per l'installazione di Windows

## Note:
> **Attenzione** se elimini una qualsiasi partizione tramite diskpart ora o in futuro, Windows invierá un comando UFS che verrá interpretato erroneamente che cancellerá tutti i tuoi UFS!!!
- Tutti i tuoi dati verranno eliminati! Salvali ora se ne hai bisogno.
- Questi comandi sono stati testati.
- Ignora gli avvisi `udevadm` 
- Non eseguire lo stesso comando due volte
- In recovery, lo schermo non funziona.
- NON RIAVVIARE IL TUO DISPOSITIVO se pensi di aver commesso un errore, chiedi aiuto nella [chat Telegram](https://t.me/nabuwoa)

#### Avvia la recovery tramite PC con il seguente comando:
```cmd
fastboot boot <recovery.img>
```
> Se hai giá installato la recovery TWRP, tieni semplicemente premuti i pulsanti di accensione e vol+ all'avvio del dispositivo

#### Smonta le partizioni
```cmd
adb shell twrp unmount /data
```

## Invia parted al percorso /tmp/
> Per partizionare le partizioni
```cmd
adb push parted /tmp/
```

## Avvia ADB Shell
```cmd
adb shell
```

### Ridimensiona la tabella delle partizioni
> In modo che riusciremo a far entrare le partizioni di Windows
```sh
sgdisk --resize-table 64 /dev/block/sda
```

### Dai i permessi necessari a parted
```sh
chmod 755 /tmp/parted
```

### Avvia parted
```sh
/tmp/parted /dev/block/sda
```


### Elimina la partizione "userdata"
> Puoi assicurarti che "31" sia il numero della partizione "userdata" eseguendo
>  `print all`
```sh
rm 31
```

### Crea le partizioni
> Se ricevi dei messaggi di avviso che dicono `ignore or cancel`, digita semplicemente i e premi invio

#### Per i modelli da 128GB: 

- Crea la partizione ESP (in cui saranno salvati i file di avvio di Windows e i file EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Crea la partizione principale in cui sará installato Windows
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Crea la partizione "userdata" in cui saranno salvati i dati di android
```sh
mkpart userdata ext4 70.2GB 126GB
```

#### Per i modelli da 256GB:

- Crea la partizione ESP (in cui saranno salvati i file di avvio di Windows e i file EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Crea la partizione principale in cui sará installato Windows
```sh
mkpart win ntfs 11.4GB 120.8GB
```

- Crea la partizione "userdata" in cui saranno salvati i dati di android
```sh
mkpart userdata ext4 120.8GB 254GB
```


### Rendi avviabile la partizione ESP in modo che l'immagine EFI possa rilevarla
```sh
set 31 esp on
```

### Esci da parted
```sh
quit
```
### Riavvia il dispositivo nel bootloader
```sh
reboot bootloader
```

### Avvia il dispositivo in recovery
```cmd
fastboot boot <recovery.img>
```

### Avvia di nuovo ADB Shell sul tuo PC
```cmd
adb shell
```

### Formatta le partizioni
-  Formatta la partizione ESP come FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Formatta la partizione di windows come NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Formatta la partizione userdata
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```

### Verifica se Android si avvia 
riavvia il dispositivo e verifica se android si avvia ancora
Se non si avvia o va in bootloop, basta fare la pulizia dei dati con la recovery della MIUI o con un'altra recovery.

## [Prossimo passaggio: installa Windows](/guide/Italian/2-installazione-it.md)
