Este paso es necesario para que hagamos las particiones donde estará nuestra instalación de Windows

## Notas:
> **Advertencia**: si elimina cualquier partición a través de diskpart más adelante o ahora, Windows enviará un comando ufs que se malinterpretará y borrará toda su ufs.
- ¡Todos tus datos serán eliminados! Haz un backup si lo necesitas.
- Estos comandos han sido probados.
- Ignora las advertencias de `udevadm` .
- No ejecutes el mismo comando dos veces.
- En el recovery, la pantalla no funciona.
- No reinicies tu teléfono si crees que has cometido un error, busca ayuda en el [chat de Telegram](https://t.me/nabuwoa)

#### Inicia el recovery desde el PC con el siguiente comando
```cmd
fastboot boot <recovery.img>
```
> Si ya tienes TWRP instalado, solo pulsa el botón de encendido y vol+ para iniciarlo

#### Desmontar las particiones
```cmd
adb shell twrp unmount /data
```

## Pasar parted a /tmp/
> Para reparticionar las particiones
```cmd
adb push parted /tmp/
```

## Inicia ADB shell
```cmd
adb shell
```

### Redimensionar la tabla de particiones
> Para que entren las particiones de Windows
```sh
sgdisk --resize-table 64 /dev/block/sda
```

### Darle los permisos a parted
```sh
chmod 755 /tmp/parted
```

### Iniciar parted
```sh
/tmp/parted /dev/block/sda
```


### Borra la partición `userdata` 
> Puedes estar seguro de que es la partición 31 poniendo
>  `print all`
```sh
rm 31
```

### Crear particiones
> si recibes cualquier mensaje diciendote `ignore or cancel`, solo escribe i y dale a enter

#### Para los modelos de 128Gb:

- Crea la partición ESP (almacena datos del gestor de arranque de Windows y archivos EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

- Crea la partición principal donde instalaremos Windows
```sh
mkpart win ntfs 11.4GB 70.2GB
```

- Crea la partición de datos de Android
```sh
mkpart userdata ext4 70.2GB 126GB
```

#### Para los modelos de 256Gb:

- Crea la partición ESP (almacena datos del gestor de arranque de Windows y archivos EFI)
```sh
mkpart esp fat32 10.9GB 11.4GB
```

-  Crea la partición principal donde instalaremos Windows
```sh
mkpart win ntfs 11.4GB 120.8GB
```

-  Crea la partición de datos de Android
```sh
mkpart userdata ext4 120.8GB 254GB
```


### Marca la partición ESP como partición de arranque para que la imagen EFI pueda detectarla
```sh
set 31 esp on
```

### Salir de parted
```sh
quit
```

### Reinicia a TWRP

### Inicia ADB shell de nuevo en tu PC
```cmd
adb shell
```

### Formatear particiones
-  Formatear la partición ESP en FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/bootdevice/by-name/esp -n ESPNABU
```

-  Formatear la partición Windows en NTFS
```sh
mkfs.ntfs -f /dev/block/bootdevice/by-name/win -L WINNABU
```

-  Formatea userdata
```sh
mke2fs -t ext4 /dev/block/bootdevice/by-name/userdata
```

### Comprobar si Android inicia
Solo reinicia y comprueba que Android sigue funcionando.
Si no arranca o se reinicia constantemente solo limpia los datos con cualquier recovery.

## [Siguiente paso: Instalar Windows](/guide/Español/2-instalacion-es.md)
