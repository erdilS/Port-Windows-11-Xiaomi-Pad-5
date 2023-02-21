<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Aggiornare i driver

### Prerequisiti

- [UEFI](../../../../releases/tag/1.0)
- [script storage di massa](../../../../releases/tag/1.0)
- [TWRP](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/map220v/MiPad5-Drivers)

#### Avvia la recovery tramite PC con il seguente comando: 

```cmd
fastboot boot <recovery.img>
```

#### Invia lo script

```cmd
adb push msc.sh /sbin/
```

#### Esegui lo script

```cmd
adb shell msc.sh
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


### Installa i nuovi drivers

> Sostituisci `<nabudriversfolder>` con la posizione della cartella dei drivers

> Apri il CMD (prompt dei comandi) come amministratore


```cmd
DriverUpdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


### Avvia Windows con l'immagine UEFI

```
fastboot flash boot <uefi.img>
```

## Finito!
