<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows en la Xiaomi Pad 5">


# Windows en la Xiaomi Pad 5

## Actualizar Drivers

### Requisitos previos

- [UEFI](../../../../releases/tag/1.0)
- [Recovery](../../../../releases/tag/1.0)
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)


#### Inicia el recovery desde el PC con este comando

```cmd
fastboot boot <recovery.img>
```


### Ejecutar msc

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

```cmd
Abra la carpeta con los controladores y ejecute OfflineUpdater.cmd
```  


##### Arrancar Windows con la imagen UEFI #####

```
fastboot flash boot <uefi.img>
```


# ¡Terminado!
