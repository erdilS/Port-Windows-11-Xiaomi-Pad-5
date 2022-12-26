## Uninstalling Windows


> Replace <gpt_both0.bin> with the path to the gpt_both0.bin file. you can find it on the [releases page](../../../../releases/)


# Restore stock partition table

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Erase userdata to avoid bootloop and restore FS size
```cmd
fastboot -w
```
