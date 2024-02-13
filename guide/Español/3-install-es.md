<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 En La Xiaomi Pad 5">

# Windows 11 En La Xiaomi Pad 5

> [!WARNING]
> **¡POR FAVOR, NO USES GUÍAS DE VIDEO DESACTUALIZADAS EN YOUTUBE NI EN NINGUNA OTRA PLATAFORMA! ¡ESTOS VIDEOS ESTÁN DESACTUALIZADOS Y PUEDES BLOQUEAR TU DISPOSITIVO USÁNDOLOS! SI NECESITA UNA GUÍA DE VIDEO, USE ESTO [NUEVA GUÍA DE VIDEO](https://www.youtube.com/watch?v=rGPbdFq7gKs) DESDE [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**

# Instalar Windows

### Reinicia a recovery de nuevo para instalar Windows

### Requisitos previos
  
- [```UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img)

- [```ARM Windows esd```](https://worproject.com/esd) (Seleccione - Version:  ```11``` Build:  ```22631.2861``` Architecture:  ```ARM64``` Edition:  ```CLIENT``` Language:  ```seleccione su idioma```)
  
- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)


### Iniciar recovery para instalar Windows
```cmd
fastboot boot <recovery.img>
```


### Ejecutar el msc 
> Si le pide que lo ejecute una vez más, hágalo

```cmd
adb shell msc
```

## Asignar letras a los discos
  

#### Iniciar el administrador de discos de Windows

> Una vez que LA Xiaomi Pad 5 se detectE como un disco

```cmd
diskpart
```


### Asignar la letra `X` to Windows volumeal volumen de Windows

#### Seleccionar el volumen de Windows de la tablet
> Usa `list volume` para encontrarlo, Son los que se llaman "WINNABU" y "ESPNABU"

```diskpart
select volume <number>
```

#### Asignar la letra X
```diskpart
assign letter=x
```

### Asignar la letra `Y` al volumen esp

#### Selecciona el volumen esp de la tablet
> Usa `list volume` para encontrarlo, normalmente es el último

```diskpart
select volume <number>
```

#### Asigna la letra Y

```diskpart
assign letter=y
```

### Salir de diskpart:
```diskpart
exit
```

  
  

## Instalar
> [!NOTE]
> **Ahora ejecute el símbolo del sistema como administrador**

>  Reemplazar `<path/to/install.esd>` con el camino real de install.esd

>  Si obtuvo su imagen de Windows en otro lugar (que también podría llamarse `install.wim`), reemplazar `index:6` con `index:1`

```cmd
dism /apply-image /ImageFile:<path/to/install.esd> /index:6 /ApplyDir:X:\
```

# Instalar los Drivers

> Puede descargar los controladores [aquí](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Cuando le pida que "Enter Drive letter....."tipo **`X`**


```cmd
Abra la carpeta con los controladores y ejecute OfflineUpdater.cmd
```  

# Crear los archivos del bootloader de Windows para la EFI 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## Elimine la letra de unidad de ESPNABU para evitar la aparición de una letra de unidad fantasma

```cmd
mountvol y: /d
```
  

# Arrancar en Windows

### Haz un backup de tu partición de arranque actual
> [!NOTE]
> **Ahora regrese al símbolo del sistema de herramientas de la plataforma**

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

### Reiniciar al bootloader

```cmd
adb reboot bootloader
```
### Download and flash UEFI image
>Descargar [Imagen UEFI](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img)
### Flashea la imagen uefi 

```cmd
fastboot flash boot <ruta a la imagen>
```
## Reiniciar en Windows
```cmd
fastboot reboot
```

> [!NOTE]
> En el primer arranque de Windows, no verá ninguna red Wi-Fi, simplemente reinícielo manteniendo presionado el botón de encendido y, después de reiniciar, cuando intente conectarse a su red y vea "helado", haga clic en" intentarlo de nuevo " 7 veces

# Arrancar de nuevo en Android
Después de configurar Windows, presione el botón Reiniciar en Windows (NO APAGAR), luego, cuando se reinicia, mantener `bajar volumen` + `potencia` para reiniciar de nuevo a fastboot
> Usa el backup del boot.img en fastboot

```cmd
fastboot flash boot rooted_boot.img
```

# ¡Terminamos!
> Puedes unirte a nuestro [Telegram chat](https://t.me/nabuwoa) para recibir las últimas noticias sobre el proyecto
### [Último paso: Configurar el arranque dual](dualboot-es.md)
