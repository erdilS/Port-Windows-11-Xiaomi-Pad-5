<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows en la Xiaomi Pad 5">


# Windows en la Xiaomi Pad 5

## Actualizar Drivers

### Requisitos previos


- [```UEFI imagen```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Recovery imagen```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
  
- [```Controladores```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### Inicia el recovery desde el PC con este comando

```cmd
fastboot boot <recovery.img>
```


### Ejecutar msc
> Si le pide que lo ejecute una vez más, hágalo

```cmd
adb shell msc
```

## Asignar letras a los discos

#### Inicia el Administrador de dispositivos en el PC

> Una vez que la Pad 5 sea detectada como un disco

```cmd
diskpart
```


### Asigna `x` al volumen de Windows

#### Selecciona el volumen de Windows de la Pad 5
> Usa `list volume` para encontrarlo, suele ser el penúltimo.

```diskpart
select volume <number>
```

#### Asignar la letra x
```diskpart
assign letter=x
```

### Salir de diskpart:
```diskpart
exit
```

# Instalar los Drivers

> Puede descargar los controladores [aquí](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Si escribe `"Automatic WINNABU detection failed! Enter Drive Letter manually"` tipo **`X`**
```cmd
Abra la carpeta con los controladores y ejecute OfflineUpdater.cmd
```  
### Reiniciar para fastboot a flash UEFI
> O si su UEFI ya ha sido flasheada, simplemente reinicie con ```adb reboot```
```cmd
adb reboot bootloader
```

#### Arrancar Windows con la imagen UEFI 
> Reemplace <uefi.img> por la ruta real de la imagen UEFI

```
fastboot flash boot <uefi.img>
```


# ¡Terminado!
