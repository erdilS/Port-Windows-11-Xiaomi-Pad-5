<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Aggiornare i driver

### Prerequisiti


- [```UEFI image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### Avvia la recovery tramite PC con il seguente comando: 

```cmd
fastboot boot <recovery.img>
```


#### Esegui lo script
> Se ti chiede di eseguirlo un altra volta allora fallo.

```cmd
adb shell msc
```

### Assegna le lettere ai dischi

#### Avvia il gestore delle partizioni di Windows (diskpart)

> Quando il dispositivo é rilevato come disco

```cmd
diskpart
```


### Assegna la lettera `X` al volume di Windows

#### Seleziona il volume di Windows (WINNABU)
> Usa il comando `list volume` per trovarlo, é quello che si chiama "WINNABU"

```diskpart
select volume <number>
```

#### Assegna la lettera x
```diskpart
assign letter=x
```

#### Esci da diskpart:
```diskpart
exit
```

### Installazione drivers

> È possibile scaricare i driver [qui](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> se scrive `"Automatic WINNABU detection failed! Enter Drive Letter manually"` digita **`X`**
```cmd
Apri la cartella con i driver ed esegui OfflineUpdater.cmd
```
### Riavvia per avviare rapidamente per eseguire il flash, UEFI
> Oppure, se il tuo UEFI è già stato flashato, riavvia semplicemente con `adb reboot`
```cmd
adb reboot bootloader
```

### Avvia Windows con l'immagine UEFI
> Reemplace <uefi.img> por la ruta real de la imagen UEFI
```
fastboot flash boot <uefi.img>
```

## Finito!
