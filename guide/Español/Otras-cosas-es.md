## Requisitos para el Dual Boot

- Cerebro

- ¡Solo funciona en el slot A!

- Tener Android rooteado y un backup del boot de Android rooteado.

- [Descargar archivos necesarios](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Configurar Windows para el Dual Boot

- Instalar [Cygwin](https://www.cygwin.com/setup-x86_64.exe) con coreutils (se instalarán por defecto)

- Renombra el archivo de arranque de Android a boot.img

- Coloca el archivo de arranque en C:\ (C:\boot.img)

- Ejecuta el archivo .bat como administrador o crea un acceso directo con permisos de administrador.

### Configurar Android para el Dual Boot

- Instala switchtowin.apk al dispositivo.

- Renombra tu archivo UEFI a boot.img

- Coloca el archivo UEFI en /sdcard/windows (/sdcard/windows/boot.img).

- Inicia la app y dale permisos root.

- Toca "Switch to Windows" si quieres reiniciar a Windows.

# Arreglar la GPU en Windows

- Ve al Administrador de dispositivos (Mantén pulsado el logo de Windows y toca Administrador de dispositivos).
- Busca adaptadores de pantalla y expándelo.
- Mantén pulsado "Microsoft Basic Display Adapter".
- Selecciona actualizar driver.
- Selecciona "Examinar mi PC en busca de controladores".
- Selecciona "Elegir en una lista de controladores disponibles en el equipo".
- Selecciona "Mi Pad 5 Adreno 640 GPU" y pulsa siguiente.
- La pantalla parpadeará mientras se instala el driver.
- ¡Hecho!
