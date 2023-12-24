
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Aplicaciones útiles e instrucciones para Windows en Xiaomi pad 5

## Oficina de Microsoft

- Descargue este [archivo](https://drive.google.com/file/d/1st8xVpxtJbe2GVTEZrC_RNumKllR97Hp/view?usp=sharing) a la tableta
  
- Apague Windows Defender para evitar interferencias con la instalación
  
- Haga clic derecho en el archivo iso y seleccione Montar para abrirlo en el explorador

- Haga doble clic en AUTORUN.exe para iniciar el asistente de instalación
  
- Elija el idioma y los componentes que desea instalar y, a continuación, haga clic en Iniciar instalación.
  
- Espere a que se complete la instalación y activación

- Vuelva a activar Windows Defender

- ¡Disfruta usando Office!

 ## Activar Windows

> Abra PowerShell y escriba: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> Cuando aparezca una ventana, seleccione 1

 ## Cómo usar la linterna

 - Descargar [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) y descomprima en cualquier carpeta

> Enciende la linterna.exe para habilitar la linterna

> Presione cualquier tecla para desactivarlo

## Enabling charging and USB host mode

> [!WARNING]
>  Make sure any registry edits are done on the Mi Pad 5 itself

> [!NOTE]
> C to C charging with a PD supported device has been confirmed working and the 33W charger provided by Xiaomi is also confirmed to be working

- Download  [Script from Misha803](https://t.me/droidscripts/22) to easy enable it
 
- Or use traditional method - In the registry editor, change the value of the parameter ```RoleSwitchMode``` from ```3``` to ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

