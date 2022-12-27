## Windows'u kaldırmak


> Komuttaki <gpt_both0.bin> kısmını gpt_both0.bin dosyasının konumuyla değiştirin. Dosyayı [releases sayfasından](../../../../releases/) indirebilirsiniz.


# Varsayılan bölüm tablosunu geri yükleyin

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

# Bootloop yaşamamak ve bölüm boyutunu geri yüklemek için Userdata bölümünü biçimlendirin
```cmd
fastboot -w
```
