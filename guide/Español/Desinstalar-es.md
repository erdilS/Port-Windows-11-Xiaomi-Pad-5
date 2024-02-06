<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Ejecutando Windows en el Xiaomi Pad 5

## Desinstalación

### ¿Por qué es necesario?

Si desea desinstalar Windows, esto se usa en lugar de eliminar particiones manualmente para evitar errores humanos + escribir una guía completa dedicada a la desinstalación.

Si desea volver a bloquear su gestor de arranque, necesitará que su tabla de particiones esté disponible.

### Requisitos Previos

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [gpt_both0.bin](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin)

# Restaurar el stock de la tabla de particiones

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Borrar userdata para evitar bootloop y restaurar el tamaño de FS
```cmd
fastboot -w
```
