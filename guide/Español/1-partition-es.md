<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 En La Xiaomi Pad 5">

# Windows 11 En La Xiaomi Pad 5


### Requisitos Previos
  
- [```Imagen de Recuperación```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

## Notas:

> [!NOTE]
> ¿No sabes por dónde empezar? Simplemente descomprima las [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools) descargadas, por ejemplo ```"C:\platform-tools"``` A continuación, abra ```símbolo del sistema``` o `powershell` como administradora y escriba:
```cmd
cd "camino\para\platform-tools"
```
> Reemplazar  `"camino\para\platform-tools"` con la ruta real de la carpeta Platform Tools

> [!WARNING]\
> si elimina cualquier partición a través de diskpart más adelante o ahora, Windows enviará un comando ufs que se malinterpretará y borrará toda su ufs.
> 
> ¡Todos tus datos serán eliminados! Haz un backup si lo necesitas.
> 
> Estos comandos han sido probados.
> 
> No reinicies tu teléfono si crees que has cometido un error, busca ayuda en el [chat de Telegram](https://t.me/nabuwoa)
>
> 
> ¡No ejecute todos los comandos a la vez, ejecútelos en orden!
>
> ¡¡¡ASEGÚRATE DE NO COMETER NINGÚN ERROR!!! ¡PUEDE ROMPER SU DISPOSITIVO CON LOS COMANDOS SI LO HACE MAL!

Este paso es necesario para que hagamos las particiones donde estará nuestra instalación de Windows

#### Inicia el recovery desde el PC con el siguiente comando
```cmd
fastboot boot <recovery.img>
```
##### Ejecute el script de particionamiento

> Si le pide que lo ejecute una vez más, hágalo

> Esto es **opcional** pero puede **establecer tamaños personalizados usando este script**

> Para establecer tamaños personalizados, haga partición de  ```adb shell partition [TAMAÑO DE WINDOWS DE DESTINO EN GB] ```

> Asegúrese de no agregar GB al final, solo el número

```cmd
adb shell partition
```

### Haga una copia de seguridad de su imagen de arranque existente

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Comprueba si Android aún se inicia
> Solo mira si Android todavía funciona
Si no está iniciando o haciendo un bucle en la animación, use la recuperación de MIUI u otras recuperaciones para borrar datos.

```cmd
adb reboot
```

## [Siguiente paso: Obtener root ](/guide/Español/2-rootguide-es.md)
