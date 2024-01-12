<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Corriendo en una Xiaomi Pad 5">


# Ejecutando Windows en el Xiaomi Pad 5

## Reinstalar

### Reinstalar Windows si algo sale mal

- Si no le gusta su versión de Windows o ha bloqueado su instalación de Windows, o cualquier otra cosa, probablemente simplemente reinstale Windows. Afortunadamente, este proceso es muy fácil.

- Si no ha restaurado su tabla de particiones, puede usar esta guía con sus particiones existentes.

### Requisitos previos

- Windows existentes y particiones de arranque (*Si no se cumplen, [regrese y finja que esta guía nunca existió](/guide/Español/1-particiones-es.md)*)

- [Recovery](../../../../releases/tag/1.0)

- [ADB y Fastboot](https://developer.android.com/studio/releases/platform-tools)


### Inicia el recovery para formatear Windows y las particiones de arranque

``` cmd
fastboot boot <recovery.img>
```
### Formatear las particiones


``` cmd
adb shell format
```

### Instalar

- Continuar la guía desde [aquí](2-instalacion-es.md#Ejecutar-el-msc)
