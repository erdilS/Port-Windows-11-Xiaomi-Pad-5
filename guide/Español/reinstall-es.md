<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Corriendo en una Xiaomi Pad 5">


# Ejecutando Windows en el Xiaomi Pad 5

## Reinstalar

### Reinstalar Windows si algo sale mal

- Si no le gusta su versión de Windows o ha bloqueado su instalación de Windows, o cualquier otra cosa, probablemente simplemente reinstale Windows. Afortunadamente, este proceso es muy fácil.

- Si no ha restaurado su tabla de particiones, puede usar esta guía con sus particiones existentes.

### Requisitos previos

- Windows existentes y particiones de arranque (*Si no se cumplen, [regrese y finja que esta guía nunca existió](/guide/English/1-partition-en.md)*)

- [Recovery](../../../../releases/tag/1.0)

- [ADB y Fastboot] (https://developer.android.com/studio/releases/platform-tools)


### Inicia el recovery para formatear Windows y las particiones de arranque

``` cmd
fastboot boot <recovery.img>
```
### Formatear las particiones


``` cmd
adb shell format
```

#### Ejecutar el script msc

``` cmd
adb shell msc
```

### Asignar letras a los discos... de nuevo
  

#### Inicie el administrador de discos de Windows

> Una vez que la Xiaomi Pad 5 se detecta como un disco

``` cmd
diskpart
```

- La partición "WINNABU" ya debería aparecer con la letra X. Si es así, salta a `Asignar "Y" al volumen ESP`

#### Asignar `X` al volumen de Windows

#### Seleccione el volumen de Windows de la tableta
> Usa `list volume` para encontrarlo, es el que se llama "WINNABU"

```diskpart
select volume <número>
```

#### Asignar la letra X
```diskpart
assign letter=x
```

### Asigna `Y` al volumen ESP

#### Seleccione el volumen esp de la tableta
> Usa `list volume` para encontrarlo, es el que se llama "ESPNABU"

```diskpart
select volume <número>
```

#### Asignar la letra Y

```diskpart
assign letter=y
```

- Si obtiene un error que dice `La letra de unidad especificada no se puede asignar libremente`, simplemente reinicie su computadora e intente nuevamente desde diskpart. No toques tu tablet todavía.

#### Salir de la parte del disco
```diskpart
exit
```


### Instalar

- Continuar la guía desde [aquí](2-instalacion-es.md#Instalar)
