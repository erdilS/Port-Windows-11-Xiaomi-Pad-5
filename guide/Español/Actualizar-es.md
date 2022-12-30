#### Inicia el recovery desde el PC con este comando

```cmd
fastboot boot <recovery.img>
```

## Transferir msc

```cmd
adb push msc.sh /sbin/
```

### Ejecutar msc

```cmd
adb shell sh /sbin/msc.sh
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


# Instalar los drivers

> Reemplazar `<nabudriversfolder>` con la ruta de la carpeta que tenga los driveres.

> Abre un cmd como administrador.

```cmd
driverupdater.exe -d <nabudriversfolder>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabudriversfolder> -p X:
```


##### Arrancar Windows con la imagen UEFI #####

```
fastboot flash boot <uefi.img>
```


# ¡Terminado!
