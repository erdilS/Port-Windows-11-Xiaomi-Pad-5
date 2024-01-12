
<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Aplicaciones útiles e instrucciones para Windows en Xiaomi pad 5

## Oficina de Microsoft

- Descargue este [archivo](https://mega.nz/file/Q7p1XK6L#J-KPp_-MNJ8iXGqEwwZ3_sfv2tMiq_AJjUiiaX6TBrI) a la tableta
  
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

## Habilitación del modo de carga y host USB

> [!WARNING]
>  Asegúrese de que las ediciones del registro se realicen en el propio Mi Pad 5

> [!NOTE]
> Se ha confirmado que la carga de C a C con un dispositivo compatible con PD funciona y también se confirma que el cargador de 33 W proporcionado por Xiaomi funciona

- Descargar [Script de Misha803](https://t.me/droidscripts/52) para habilitarlo fácilmente
 
- O use el método tradicional: En el editor del registro, cambie el valor del parámetro ```RoleSwitchMode``` desde ```3``` para ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

