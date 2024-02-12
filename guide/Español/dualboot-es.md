<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Arranque dual de Android y Windows sin problemas 

### Requisitos previos 
- Cerebro 
- Una tableta rooteada 
- Windows instalado en la tableta. 
- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img)
- [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [StA Installer](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## Configurar la aplicación de arranque dual 
> Esta guía asume que usted está rooteado; si no lo está, siga las instrucciones [guía raíz](2-rootguide-en.md) primero.

### Configuración - Android
> [!NOTE]
> Si no puede mover archivos a la carpeta de Windows, significa que cerró Windows en lugar de reiniciarlo. Para solucionar este problema, reinicie Windows y use reiniciar, luego, cuando se reinicie, inicie fastboot y utilícelo para regresar a Android.

- Descargue e instale el [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), luego ábrelo y concédele acceso de root. 
- Descargar el [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img) and colóquelo dentro de la carpeta llamada `UEFI` en su almacenamiento interno, si esta carpeta no existe, créela. 
- Volver a la WOA Helper app y presione el `Back up Android boot` botón. Seleccione tanto el `Windows` y `Android` opciones.
- presione el `Mount Windows` botón, luego descargar y mover [StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) a la recién creada `Windows` carpeta en su almacenamiento interno. 
- Volver a la WOA Helper app y presione `Quickboot to Windows`.

### Configuración - Windows
- Navegar a C:\StA_Installer_nabu.exe y ejecutarlo. Si no funciona, asegúrese de que el software antivirus esté desactivado, ya que probablemente no permitirá que la aplicación se ejecute. 

##### Arrancando a android
  - Ejecute el nuevo acceso directo en su escritorio (también puede fijarlo en su menú de inicio/barra de tareas para facilitar el acceso) 

##### Arrancando a windows
  - Prensa "Quickboot to Windows" dentro de la aplicación, o use la palanca recién creada en su panel de configuración rápida 
  
## Finalizado!

