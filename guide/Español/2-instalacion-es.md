<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 En La Xiaomi Pad 5">

# Windows 11 En La Xiaomi Pad 5


# Instalar Windows

### Reinicia a recovery de nuevo para instalar Windows

### Requisitos previos

- [Windows ARM](https://uupdump.net/)
  
- [UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)
  
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)


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

> Reemplaza `<path/to/install.wim>` por la ruta actual de install.wim 

> `install.wim` está en la carpeta sources de tu ISO
> Puede obtenerlo montándolo o extrayéndolo

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

# Instalar los Drivers

> Puede descargar los controladores [aquí](https://github.com/map220v/MiPad5-Drivers/releases/latest)

```cmd
Abra la carpeta con los controladores y ejecute OfflineUpdater.cmd
```  

# Crear los archivos del bootloader de Windows para la EFI 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# Arrancar en Windows

### Haz un backup de tu partición de arranque actual

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Pon el backup en el Pc

```cmd
adb pull /tmp/boot.img
```

### Reiniciar al bootloader

```cmd
adb reboot bootloader
```
### Download and flash UEFI image
>Descargar [Imagen UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_secureboot-v2.img)

### Flashea la imagen uefi desde TWRP
> Reemplaza ```<panel>``` por el panel de tu dispositivo

```cmd
fastboot flash boot <ruta a la imagen>
```
> [!NOTE]
> En el primer arranque de Windows, no verá ninguna red Wi-Fi, simplemente reinícielo manteniendo presionado el botón de encendido y, después de reiniciar, cuando intente conectarse a su red y vea "helado", haga clic en" intentarlo de nuevo " 7 veces

# Arrancar de nuevo en Android
> Usa el backup del boot.img en fastboot

```cmd
fastboot flash boot boot.img
```

# ¡Terminamos!
> Puedes unirte a nuestro [Telegram chat](https://t.me/nabuwoa) para recibir las últimas noticias sobre el proyecto
### [Último paso: Configurar el arranque dual](dualboot-es.md)
