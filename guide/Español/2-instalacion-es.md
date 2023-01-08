# Instalar Windows

### Reinicia a recovery de nuevo para instalar Windows

```cmd
fastboot boot <recovery.img>
```

### Pasar msc a /sbin

```cmd
adb push msc.sh /sbin/
```

### Ejecutar el msc 

```cmd
adb shell sh /sbin/msc.sh
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
adb shell "dd if=/dev/block/bootdevice/by-name/boot_a of=/tmp/boot.img"
```

##### Pon el backup en el Pc

```cmd
adb pull /tmp/boot.img
```

### Reiniciar al bootloader

```cmd
adb reboot bootloader
```

### Flashea la imagen uefi desde TWRP

```cmd
fastboot flash boot boot-nabu.img
```

# Arrancar de nuevo en Android
> Usa el backup del boot.img en fastboot

```cmd
fastboot flash boot boot.img
```

# ¡Terminamos!
