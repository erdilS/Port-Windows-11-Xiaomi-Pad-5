<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Corriendo en una Xiaomi Pad 5">


# Ejecutando Windows en el Xiaomi Pad 5

## Reinstalar
Si no le gusta su versión de Windows o ha bloqueado su instalación de Windows, o cualquier otra cosa, probablemente simplemente reinstale Windows. Afortunadamente, este proceso es muy fácil.

> [!IMPORTANT]
> Obviamente, esto borrará todos sus archivos de Windows. Si desea hacer una copia de seguridad de alguno de ellos, puede hacerlo montando Windows usando el [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) aplicación y copiar manualmente cualquier archivo que desee conservar 

### Requisitos previos

- ```Windows existentes y particiones de arranque``` (*Si no se cumplen, [regrese y finja que esta guía nunca existió](/guide/Español/1-particiones-es.md)*)

- [```Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)


### Inicia el recovery para formatear Windows y las particiones de arranque

``` cmd
fastboot boot <recovery.img>
```
### Formatear las particiones
> Si le pide que lo ejecute una vez más, hágalo


``` cmd
adb shell format
```

### Instalar

- Continuar la guía desde [aquí](3-instalacion-es.md#Ejecutar-el-msc)
