<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5

## Installazione

### Ripartizionare il dispositivo

### Prerequisiti

- [Immagine Recovery](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> [!WARNING]\
> se elimini una qualsiasi partizione tramite diskpart ora o in futuro, Windows invierá un comando UFS che verrá interpretato erroneamente che cancellerá tutti i tuoi UFS!!!
> 
> Tutti i tuoi dati verranno eliminati! Salvali ora se ne hai bisogno.
> 
> Questi comandi sono stati testati.
> 
> Ignora gli avvisi `udevadm`
> 
> Non eseguire lo stesso comando due volte
> 
> In recovery, lo schermo non funziona.
> 
> NON RIAVVIARE IL TUO DISPOSITIVO se pensi di aver commesso un errore, chiedi aiuto nella [chat Telegram](https://t.me/nabuwoa)
> 
>
> Non eseguire tutti i comandi in una sola volta! Eseguili in ordine!
>
> 
> NON COMMETTERE NESSUN ERRORE!!! PUOI ROMPERE/BRICKARE IL TUO DISPOSITIVO CON I SEGUENTI COMANDI SE ESEGUITI IN MANIERA SBAGLIATA!!!


#### Avvia la recovery tramite PC con il seguente comando:
```cmd
fastboot boot <recovery.img>
```
Esegui lo script di partizionamento
Se ti chiede di eseguirlo un altra volta allora fallo.

Questa parte è facoltativa ma puoi mettere la grandezza della memoria personalizzata utilizzando questo script.

Per utilizzare delle grandezze personalizzate esegui ad Shell partition[GRANDEZZA DEL BERSAGLIO DI Windows IN GB]

Fai in modo di non aggiungere GB alla fine,inserisci  solo il numero


```cmd
adb shell partition
```


#### Verifica se Android si avvia 
riavvia il dispositivo e verifica se android si avvia ancora
Se non si avvia o va in bootloop, basta fare la pulizia dei dati con la recovery della MIUI o con un'altra recovery.

### [Prossimo passaggio: installa Windows](/guide/Italian/2-installazione-it.md)
