#### Avvia la recovery tramite PC con il seguente comando: 

```cmd
fastboot boot <recovery.img>
```

## Invia lo script

```cmd
adb push msc.sh /sbin/
```

### Esegui lo script

```cmd
adb shell sh /sbin/msc.sh
```

## Assegna le lettere ai dischi

#### Avvia il gestore delle partizioni di Windows (diskpart)

> Quando lo xiaomi pad 5 viene rilevato come disco

```cmd
diskpart
```


### Assegna la lettera `X` al volume di Windows

#### Seleziona il volume di Windows (WINNABU)
> Usa il comando `list volume` per trovarlo, di solito é il penultimo

```diskpart
select volume <number>
```

#### Assegna la lettera x
```diskpart
assign letter=x
```

### Esci da diskpart:
```diskpart
exit
```


# Installa i nuovi drivers

> Sostituisci `<nabudriversfolder>` con la posizione della cartella dei drivers

> Apri il CMD (prompt dei comandi) come amministratore

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


##### Avvia Windows con l'immagine UEFI #####

```
fastboot flash boot <uefi.img>
```


# Finito!
