<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# App e istruzioni utili per Windows su Xiaomi pad 5

## Installare Microsoft Office

- Scarica questo [file](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) al tablet
  
- Disattiva Windows Defender per evitare interferenze con l'installazione
  
- Fare clic con il pulsante destro del mouse sul file iso e selezionare Monta per aprirlo in Explorer

- Fare doppio clic su AUTORUN.exe per avviare la procedura guidata di installazione
  
- Scegliere la lingua e i componenti da installare, quindi fare clic su Avvia installazione
  
- Attendere il completamento dell'installazione e dell'attivazione

- Attivare nuovamente Windows Defender

- Divertiti con Office!

 ## Attiva Windows

> Aprire PowerShell e digitare: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> Quando viene visualizzata una finestra, selezionare 1


 ## Come usare la torcia

 - Scaricare [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) e decomprimere in qualsiasi cartella

> Eseguire torcia Flashlight.exe per abilitare torcia elettrica

> Premere un tasto qualsiasi per disabilitarlo

## Enabling charging and USB host mode

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

- Download  [Script from Misha803](https://t.me/droidscripts/22) to easy enable it
 
- Or use traditional method - In the registry editor, change the value of the parameter ```RoleSwitchMode``` from ```3``` to ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

