<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Risoluzione dei problemi...


## Il dispositivo si avvia su Android ma non si avvia nel bootloader

### Prerequisiti

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]
> Probabilmente questi passaggi non ti saranno utili perché mi pad 5 non dispone di una recovery personalizzata perfettamente funzionante da flashare sul dispositivo (infatti, possiamo solo eseguire il BOOT di essa). Inoltre, come sulla maggior parte dei dispositivi piú recenti con partizioni A/B, non disponiamo di un installer TWRP, e non puoi avviare la immagine della recovery proprio perché fastboot in questo caso non funziona. Se hai installato una rom AOSP, molto probabilmente hai gia una recovery AOSP installata e potrai avviarla direttamente, quindi potrai seguire questi passaggi. Se hai miui non rootata, questi passaggi purtroppo non ti saranno utili.
>
> Quindi, per favore, evita di utilizzare etichette di disco che contengono SPAZI e CARATTERI SPECIALI, e se possibile, utilizza solo le etichette ESPNABU e WINNABU, che sono state testate milioni di volte. Se causi un brick di fastboot a causa di etichette di disco con spazi e/o caratteri speciali, e, hai miui non rootata, dovrai per forza flashare la ROM tramite modalitá EDL con un ACCOUNT AUTORIZZATO e dovrai PAGARE per ottenerlo.


Questo problema é causato da partizioni con nomi non compatibili con fastboot, per risolvere:

- Avvia in recovery

- Collega il dispositivo al PC

- Apri il CMD sul PC

- Esegui ```adb shell```

- Esegui ```parted```

- Esegui ```print``` to list all partitions

- Trova tutte le partizioni che contengono nomi con spazi e/o caratteri speciali esempio: "Basic Data Partition" e prendi nota del loro numero.

- Adesso esegui ```rm <numero del volume>``` esempio ```rm 99```


## BSOD con errore "fsa4480.sys" all'avvio

- Apri la cartella dei driver

- Rimuovi la cartella ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB``` 

- Reinstalla i drivers

- Avvia l'UEFI

- Dopo l'avvio, rileggi il driver e reinstalla nuovamente il driver.
