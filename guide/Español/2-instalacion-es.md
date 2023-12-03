<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 En La Xiaomi Pad 5">

# Windows 11 En La Xiaomi Pad 5


# Instalar Windows

### Reinicia a recovery de nuevo para instalar Windows

### Requisitos previos

- [Windows ARM](https://uupdump.net/)
- [UEFI](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/map220v/MiPad5-drivers)


### Iniciar recovery para instalar Windows
```cmd
fastboot boot <recovery.img>
```


### Ejecutar el msc 

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

> Reemplazar `<nabudriversfolder>` por la localizacion de la carpeta de los drivers

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```

  

# Crear los archivos del bootloader de Windows para la EFI 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# Permite los drivers no firmados

> Si no haces esto recibirás un BSOD

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

# Arrancar en Windows

### Haz un backup de tu partición de arranque actual

```cmd
adb shell "dd if=/dev/block/bootdevice/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Pon el backup en el Pc

```cmd
adb pull /tmp/boot.img
```

### Identifica tu panel

```cmd
adb shell panel
```

### Reiniciar al bootloader

```cmd
adb reboot bootloader
```
### Download and flash UEFI image
> Descargar imagen para [Huaxing](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_huaxing.img) o [Tianma](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_tianma.img) panel

### Flashea la imagen uefi desde TWRP
> Reemplaza ```<panel>``` por el panel de tu dispositivo

```cmd
fastboot flash boot boot-nabu_<panel>.img
```

# Arrancar de nuevo en Android
> Usa el backup del boot.img en fastboot

```cmd
fastboot flash boot boot.img
```

# ¡Terminamos!
