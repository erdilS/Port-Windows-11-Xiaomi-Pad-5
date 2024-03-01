<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Obtener root 
> [!NOTE]
> **Si ya tienes root, omite este paso y ve a la página siguiente.**

### Requisitos previos
- ```Cerebro```
  
- [```Copia de seguridad de arranque de Android```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (que hizo una copia de seguridad en la primera página de la guía)


## Patch boot 

- Copia el ```normal_boot.img``` archivo de la ```platform tools``` carpeta en la tableta


- Descargue e instale el [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) en la tableta
  
-  Abra la aplicación Magisk y haga clic en ```Install``` botón. Seleccionar ```Select and Patch a File``` opción y busque el ```normal_boot.img``` archivo que copiaste en la tableta. Haga clic en el ```Let's Go``` y espere a que se complete el proceso de parcheo.
  
- Copia el ```magisk_patched....img``` archivo de la ```Downloads``` carpeta en la tableta a la ```platform tools``` carpeta en su computadora.

- Reiniciar a fastboot
  
- Abra el símbolo del sistema en el platform tools carpeta 

 ## Arranque parcheado con flash 
 > Reemplazar `<magisk_patched.img>` con el real ```magisk_patched.img``` nombre/ruta.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Siguiente paso: instalar Windows](/guide/Español/3-install-es.md)
