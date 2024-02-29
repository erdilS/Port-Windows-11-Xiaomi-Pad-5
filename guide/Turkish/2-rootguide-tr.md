<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5'te Windows çalıştırma

## Rootlamak (root yetkisi almak)
> [!NOTE]
> **Zaten rootunuz varsa, bu adımı atlayın ve bir sonraki sayfaya gidin**

### Gerekli Dosyalar
- ```Beyin```
  
- (bir önceki sayfada yedeğini aldığınız)[```Android boot yedeği```](/guide/Turkish/1-partition-tr.md#Mevcut boot imajınızın bir yedeğini alıne) 


## Boot patchleme (yamalama)

- ``platform tools`` klasöründeki ``normal_boot.img`` dosyasını tablete kopyalayın 

- [Magisk uygulamasını](https://github.com/topjohnwu/Magisk/releases/latest) tablete indirin ve kurun
  
- Magisk uygulamasını açın ve ```Install``` butonuna basın. ```Select and Patch a File``` seçeneğini seçin ve tablete kopyaladığınız ```normal_boot.img``` dosyasını bulun. ```Let's Go``` butonuna tıklayın ve işlemin tamamlanmasını bekleyin.
  
- Tabletin ```Downloads (/İndirilenler)``` klasöründeki ```magisk_patched....img``` dosyasını bilgisayarınızdaki ``platform tools`` klasörüne kopyalayın. 

- Fastboota reboot edin
  
- platform-tools klasöründe cmd açın

 ## Patchli boot flashlama
- <magisk_patched.img>` yerine ```magisk_patched.img``` dosyasının gerçek adını ve bulunduğu gerçek yolu yazın.
``cmd
fastboot flash boot <magisk_patched.img>
```

### [Sonraki adım: Windows'u kurma](/guide/Turkish/3-install-tr.md)
