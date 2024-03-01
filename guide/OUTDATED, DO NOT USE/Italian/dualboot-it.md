<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Doppio avvio di Android e Windows senza problemi 

### Prerequisiti 
- Cervello 
- Una tavoletta radicata 
- Windows installato sul tablet 
- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
- [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [StA Installer](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Configurazione dell'app dualboot 
> Questa guida presuppone che tu sia rootato, se non lo sei, segui le istruzioni [guida alla radice](2-rootguide-it.md) Primo. 

### Impostare - Android
> [!NOTE]
> Se non riesci a spostare i file nella cartella Windows, significa che hai spento Windows invece di riavviarlo. Per risolvere questo problema, riavvia Windows e utilizza il riavvio, quindi quando si riavvia avvia l'avvio rapido e utilizzalo per tornare ad Android. 

- Scarica e installa il [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), quindi aprilo e concedigli l'accesso root. 
- Scarica il [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img) e inseriscilo nella cartella denominata `UEFI` nella memoria interna, se questa cartella non esiste, creala. 
- Ritorna al WOA Helper app e premere il  `Back up Android boot` pulsante. Seleziona entrambi i `Windows` e `Android` opzioni. 
- Premi il `Mount Windows` pulsante, quindi scarica e sposta [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) al appena creato `Windows` cartella nella memoria interna. 
- Ritorna al WOA Helper app e premere `Quickboot to Windows`.

### Impostare - Windows
- Navigate to `C:\StA_Installer_nabu.exe` ed eseguirlo. Se non funziona, assicurati che eventuali software antivirus siano disattivati, poiché probabilmente non consentiranno l'esecuzione dell'app. 

##### Avvio a android
  - Esegui il nuovo collegamento sul desktop (puoi anche aggiungerlo al menu Start/barra delle applicazioni per un facile accesso)

##### Avvio a windows
  - Premere `Quickboot to Windows` all'interno dell'app o utilizza l'interruttore appena creato nel pannello delle impostazioni rapide 
  
## Finito!
