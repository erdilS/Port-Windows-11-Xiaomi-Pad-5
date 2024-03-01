<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Ottieni il root
> [!NOTE]
> **Se hai già root, salta questo passaggio e vai alla pagina successiva**

### Prerequisiti
- ```Cervello```
  
- [```Backup di avvio di Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (di cui hai eseguito il backup nella prima pagina della guida)


## Avvio con toppa 

- Copia il ```normal_boot.img``` file da ```platform tools``` cartella sul tablet


- Scarica e installa il [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) sulla tavoletta
  
-  Apri l'app Magisk e fai clic su ```Install``` pulsante. Selezionare ```Select and Patch a File``` opzione e trova il file ```normal_boot.img``` file che hai copiato sul tablet. Clicca il ```Let's Go``` pulsante e attendere il completamento del processo di patch.
  
- Copia il ```magisk_patched....img``` file da ```Downloads``` cartella sul tablet nel file ```platform tools``` cartella sul tuo computer.

- Riavvia in fastboot
  
- Apri il prompt dei comandi nella cartella degli strumenti della platform tools 

 ## Avvio con patch flash
 > Sostituire `<magisk_patched.img>` con l'effettivo ```magisk_patched.img``` nome/percorso.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Passaggio successivo: installazione di Windows](/guide/Italian/3-install-it.md)
