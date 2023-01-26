## Come disinstallare Windows


> Sostituisci <gpt_both0.bin> con il percorso del file gpt_both0.bin . Puoi trovarlo su questa pagina [releases page](../../../../releases/)


# Ripristina la tabella delle partizioni al suo stato originale

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Formatta i dati per evitare il bootloop e ripristinare le dimensioni di FS
```cmd
fastboot -w
```
