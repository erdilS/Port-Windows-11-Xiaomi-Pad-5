<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Installazione

### Ripartizionare il dispositivo

### Prerequisiti

- [Immagine Recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> **Attenzione** se elimini una qualsiasi partizione tramite diskpart ora o in futuro, Windows invierá un comando UFS che verrá interpretato erroneamente che cancellerá tutti i tuoi UFS!!!
- Tutti i tuoi dati verranno eliminati! Salvali ora se ne hai bisogno.
- Questi comandi sono stati testati.
- Ignora gli avvisi `udevadm` 
- Non eseguire lo stesso comando due volte
- In recovery, lo schermo non funziona.
- NON RIAVVIARE IL TUO DISPOSITIVO se pensi di aver commesso un errore, chiedi aiuto nella [chat Telegram](https://t.me/nabuwoa)


#### ⚠️ Non eseguire tutti i comandi in una sola volta! Eseguili in ordine!

##### ⚠️ NON COMMETTERE NESSUN ERRORE!!! PUOI ROMPERE/BRICKARE IL TUO DISPOSITIVO CON I SEGUENTI COMANDI SE ESEGUITI IN MANIERA SBAGLIATA!!!


#### Avvia la recovery tramite PC con il seguente comando:
```cmd
fastboot boot <recovery.img>
```
> Se hai giá installato la recovery TWRP, tieni semplicemente premuti i pulsanti di accensione e vol+ all'avvio del dispositivo

#### Avvia ADB shell
```cmd
adb shell
```

#### Ridimensiona la tabella delle partizioni
> In modo che riusciremo a far entrare le partizioni di Windows
```sh
sgdisk --resize-table 64 /dev/block/sda
```

#### Avvia parted
```sh
parted /dev/block/sda
```

#### Elimina la partizione "userdata"
> Puoi assicurarti che "31" sia il numero della partizione "userdata" eseguendo
>  `print all`
```sh
rm 31
```

#### Crea le partizioni
> Se ricevi dei messaggi di avviso che dicono `ignore or cancel`, digita semplicemente i e premi invio


<details>
<summary><b><strong>Per modelli da 128GB</strong></b></summary>

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
  </summary>
</details>

<details>
<summary><b><strong>Per modelli da 256GB</strong></b></summary>

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

  </summary>
</details>


#### Rendi avviabile la partizione ESP in modo che l'immagine EFI possa rilevarla
```sh
set 31 esp on
```

#### Esci da parted
```sh
quit
```
#### Riavvia il dispositivo nel bootloader
```sh
reboot bootloader
```

#### Avvia il dispositivo in recovery
```cmd
fastboot boot <recovery.img>
```

#### Avvia di nuovo ADB Shell 
```cmd
adb shell
```

#### Formatta le partizioni
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


#### Verifica se Android si avvia 
riavvia il dispositivo e verifica se android si avvia ancora
Se non si avvia o va in bootloop, basta fare la pulizia dei dati con la recovery della MIUI o con un'altra recovery.

### [Prossimo passaggio: installa Windows](/guide/Italian/2-installazione-it.md)
