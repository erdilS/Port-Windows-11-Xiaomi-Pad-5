<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 En La Xiaomi Pad 5">

# Windows 11 En La Xiaomi Pad 5

## Solución de problemas


## El dispositivo puede iniciarse en Android pero no en el gestor de arranque

### Requisitos previos:

- [ADB y Fastboot](https://developer.android.com/studio/releases/platform-tools)

> [!WARNING]\
> Probablemente estos pasos no te ayuden porque la Xiaomi Pad 5 no tiene un recovery personalizado completamente funcional para actualizarlo en el dispositivo. Además, como la mayoría de los dispositivos A/B más nuevos, no tenemos un zip del instalador TWRP, etc. y no puede iniciar la imagen de recuperación existente debido a un inicio rápido roto. Si ya ha instalado la rom AOSP, probablemente tenga un recovery AOSP preinstalada y pueda iniciarla directamente, por lo que puede seguir estos pasos. Si ha desrooteado MIUI, estos pasos no le ayudarán.
>
> Por lo tanto, evite usar etiquetas de disco que contengan espacios y caracteres especiales, y si es posible, use etiquetas ESPNABU y WINNABU que se probaron un millón de veces. Si bloquea el fastboot con etiquetas de disco y ha desrooteado MIUI, debe flashear la rom a través de EDL con una cuenta autorizada y debe pagar por ello.


Esto es causado por particiones con nombres de volumen que el cargador de arranque no puede manejar, para arreglar esto:

- Arranque el recovery

- Conectar el teléfono al PC

- Abrir cmd en PC

- Ejecutar ```adb shell```

- Ejecutar ```parted```

- Ejecute ```print``` para listar todas las particiones

- Busque particiones que tengan espacios en los nombres, por ejemplo, "Basic Data Partition" y anote su número de volumen

- Ahora ejecute ```rm <número de volumen>```, por ejemplo, ```rm 99```


## fsa4480.sys BSOD en el arranque

- Abrir carpeta de drivers

- Elimine la carpeta ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB```

- Reinstalar el controlador

- Arranque la UEFI

- Después de que arranque, lea el driver y vuelva a instalarlo

## Habilitar la carga rápida y habilitar el modo de host USB

> [!WARNING]\
> Enchufe el cargador antes de iniciar, de lo contrario, la tablet no se cargará en Windows, tampoco desconecte el cargador o el dispositivo no se cargará a menos que reinicie y tenga el cargador enchufado.
>
> [!NOTE]
> Se ha confirmado que la carga de C a C con un dispositivo compatible con PD funciona y también se confirma que funciona el cargador de 33 W proporcionado por xiaomi


- Flashea este [UEFI](https://github.com/kmille36/TempStorage/blob/main/xiaomi-nabu.img?raw=true) usando ```fastboot flash boot xiaomi-nabu.img```

- Actualizar a los [Drivers] más recientes (https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/blob/main/guide/driver-updating-selection.md)

- Modificando el siguiente valor en regedit ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters\RoleSwitchMode``` cambie el valor de 3 a 1

- ¡Reinicia Windows!

## He deshabilitado el modo de prueba y ahora mi tableta no arranca en Windows

> [!IMPORTANT]\
> Asegúrate de ver [Este video](https://youtu.be/oHg5SJYRHA0) antes de intentar hacer algo para evitar más problemas después de completar todo lo que se indica a continuación.

- Mírate bien

- Date cuenta de lo decepcionante que eres.

- Sigue lo que está abajo

- Inicie el recovery con ```fastboot boot <recovery.img>```

- Pase el script de Mass Storage con ```adb push msc.sh /sbin/```

- Ejecute el script de Mass Storage con ```adb shell sh /sbin/msc.sh```

- Abrir cmd como administrador

- Escriba ```diskpart``` para iniciar diskpart

- Encuentra el Volumen ESP con ```list volume```, debería ser el que se llama ESPNABU

- Selecciona el volumen ESP con ```select volume <number>```

- Asignar la letra con ```assign letter=y```

- Salir de diskpart con ```exit```

- Ejecute este comando para volver a habilitar el modo de prueba ```bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on```

- Reinicie la tablet al gestor de arranque y arranque su imagen UEFI y Windows debería arrancar
