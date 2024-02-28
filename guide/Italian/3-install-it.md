<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5
> [!WARNING]
> **SI PREGA DI NON UTILIZZARE GUIDE VIDEO OBSOLETE SU YOUTUBE O QUALSIASI ALTRA PIATTAFORMA! QUESTI VIDEO SONO OBSOLETI E SI PUÒ MATTONE IL DISPOSITIVO CHE LO UTILIZZA! SE HAI BISOGNO DI UNA GUIDA VIDEO, USA QUESTO [NUOVA GUIDA VIDEO](https://youtu.be/BbgTbTGbXYg) DA [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**


## Installazione

## installare Windows

### Prerequisiti
  
- [```Immagine UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```ARM Windows esd```](https://worproject.com/esd) (Selezionare - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```seleziona la tua lingua```)
  
- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Riavvia di nuovo la recovery per avviare l'installazione di Windows

```cmd
fastboot boot <recovery.img>
```


#### Esegui lo msc
> Se ti chiede di eseguirlo un altra volta allora fallo.

```cmd
adb shell msc
```

### Assegna le lettere ai dischi 
  

#### Avvia il gestore delle partizioni di Windows (diskpart) 

> Quando lo Xiaomi Pad 5 viene rilevato come disco

```cmd
diskpart
```


#### Assegna la lettera `X` al volume di Windows

#### Seleziona il volume di Windows (WINNABU)
> Usa il comando `list volume` per trovarlo , é quello chiamato "WINNABU"

```diskpart
select volume <number>
```

#### Assegna la lettera X
```diskpart
assign letter x
```

### Assegna la lettera `Y` al volume ESP 

#### Seleziona il volume ESP (ESPNABU)
> Usa il comando `list volume` per trovarlo, é quello chiamato "ESPNABU"

```diskpart
select volume <number>
```

#### Assegna la lettera Y

```diskpart
assign letter y
```

#### Esci da diskpart:
```diskpart
exit
```

  
  

### Installa

> Sostituisci `<path\to\install.esd>` con il percorso effettivo di install.esd (potrebbe anche essere denominato install.wim)

```cmd
dism /apply-image /ImageFile:<path\to\install.esd> /index:6 /ApplyDir:X:\
``` 

> Se ricevi `Error 87`, controlla l'indice della tua immagine con `dism /get-imageinfo /ImageFile:<path\to\install.esd>`, quindi sostituisci `kndex:6` con il numero di indice effettivo di Windows 11 Pro nell'immagine 



### Installazione drivers

> È possibile scaricare i driver [qui](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> se scrive `"Automatic WINNABU detection failed! Enter Drive Letter manually"` digita **`X`**

```cmd
Apri la cartella con i driver ed esegui OfflineUpdater.cmd
```

  

### Crea i file del bootloader (file di avvio) di Windows per l'EFI 
> Se si verifica un errore durante la copia dei file di avvio, controllare `diskpart` per vedere se ESPNABU ha ancora la lettera Y. In caso contrario, aggiungi qualsiasi altra lettera (come K) e sostituisci rispettivamente la Y nel comando seguente con detta lettera
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## Rimuovere la lettera di unità per ESPNABU per evitare la comparsa di una lettera di unità fantasma

```cmd
mountvol y: /d
```
 
  
## Avvia Windows

### Crea un backup dell'immagine di avvio esistente
> [!NOTE]
> **Ora torna al prompt dei comandi di platform tools**

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Riavvia il dispositivo nel bootloader

```cmd
adb reboot bootloader
```

### Scarica e installa l'immagine UEFI
> Scarica [immagine UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
```cmd
fastboot flash boot <path to image>
```
## Riavvia a Windows
```cmd
fastboot reboot
```
> [!NOTE]
> Al primo avvio di Windows, non vedrà alcuna rete Wi-Fi, basta riavviarlo tenendo premuto il pulsante di accensione e dopo il riavvio quando si tenta di connettersi alla rete e si vede" gelato "fare clic su" riprova " 7 volte

### Per riavviare il dispositivo in Android
Dopo aver configurato Windows, premi il pulsante di riavvio in Windows (NON SPENTO), quindi al riavvio, tieni premuto `volume giù` + `potenza` per riavviare di nuovo a fastboot
> Usa il backup dell'immagine di avvio che hai salvato precedentemente sul tuo computer ed esegui il flashing da fastboot 

```cmd
fastboot flash boot rooted_boot.img
```

```cmd
fastboot reboot
```
## Finito!
> Puoi unirti al nostro [Telegram chat](https://t.me/nabuwoa) per ricevere le ultime notizie sul progetto
## [Per il dualboot](/guide/Italian/dualboot-it.md)
