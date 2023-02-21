<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Installazione

## installare Windows

### Prerequisiti

- [Immagine Windows On Arm](https://uupdump.net/)
- [immagine UEFI](../../../../releases/tag/1.0)
- [script storage di massa](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/map220v/MiPad5-drivers)

### Riavvia di nuovo la recovery per avviare l'installazione di Windows

```cmd
fastboot boot <recovery.img>
```

#### Invia lo script msc al percorso /sbin 

```cmd
adb push msc.sh /sbin/
```

#### Esegui lo script msc

```cmd
adb shell sh /sbin/msc.sh
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
assign letter=x
```

### Assegna la lettera `Y` al volume ESP 

#### Seleziona il volume ESP (ESPNABU)
> Usa il comando `list volume` per trovarlo, é quello chiamato "ESPNABU"

```diskpart
select volume <number>
```

#### Assegna la lettera Y

```diskpart
assign letter=y
```

#### Esci da diskpart:
```diskpart
exit
```

  
  

### Installa

> Sostituisci `<path/to/install.wim>` con il percorso del file install.wim,

> `install.wim` si trova nella cartella "sources" dentro la ISO di Windows
> Puoi ottenere questo file montandola o estraendola

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Installazione drivers

> Sostituisci `<nabudriversfolder>` con la posizione della cartella dei drivers

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

  

### Crea i file del bootloader (file di avvio) di Windows per l'EFI 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

### Permetti i drivers non firmati

> Se non lo fai, riceverai un BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```


## Avvia Windows

### Crea un backup dell'immagine di avvio (boot.img) esistente

```cmd
adb shell "dd if=/dev/block/bootdevice/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Salva il backup sul computer

```cmd
adb pull /tmp/boot.img
```

### Riavvia il dispositivo nel bootloader

```cmd
adb reboot bootloader
```

### Esegui il flashing dell'immagine UEFI 

```cmd
fastboot flash boot boot-nabu.img
```

### Per riavviare il dispositivo in Android
> Usa il backup dell'immagine di avvio che hai salvato precedentemente sul tuo computer ed esegui il flashing da fastboot 

```cmd
fastboot flash boot boot.img
```

## Finito!
## [Per il dualboot](/guide/Italian/dualboot-it.md)