## Désinstaller Windows

> Remplacer <gpt_both0.bin> par le chemin du fichier "gpt_both0.bin". Vous pouvez trouver ce fichier [sur la page suivante](../../../../releases/)

# Restaurez la table initiale des partitions

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Effacez les données utilisateurs (userdata) afin d'éviter un bootloop and restaurez la taille des Fichiers Système (FS)

```cmd
fastboot -w
```
