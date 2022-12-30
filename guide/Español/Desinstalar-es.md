## Desinstalar Windows


> Reemplaza <gpt_both0.bin> por la ruta del gpt_both0.bin file. Puedes encontrarlo en [releases page](../../../../releases/)


# Restaurar la tabla de particiones stock

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Borrar userdata para evitar bootloop y restaurar el tamaño de FS
```cmd
fastboot -w
```
