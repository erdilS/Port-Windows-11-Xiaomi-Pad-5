<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows en la Xiaomi Pad 5">


# Windows en la Xiaomi Pad 5

## Dualboot de Android y Windows sin problemas

### Requisitos previos

- Cerebro

- Android rooteado y copia de seguridad de arranque de Android rooteado

- [Descargar archivos](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot)

### Parte de Windows del dualboot

- Instale [Cygwin](https://www.cygwin.com/setup-x86_64.exe) con coreutils (se instalará por defecto)

- Cambie el nombre de su archivo de arranque a boot.img

- Coloque su arranque de Android en C:\ (C:\boot.img)

- Inicie el archivo bat como administrador o haga un acceso directo con privilegios de administrador

### Parte de Android del dualboot

- Instale switchtowin.apk en el dispositivo.

- Cambie el nombre de su archivo UEFI a boot.img

- Coloque su archivo UEFI en /sdcard/windows (/sdcard/windows/boot.img)

- Inicie la aplicación y otorgue privilegios de root.

- Haga clic en "Cambiar a Windows" si desea cambiar de Windows.