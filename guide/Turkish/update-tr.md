<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows çalıştırma

## Sürücüleri Güncelleme

### Gerekli Dosyalar
- [```Recovery imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [```Sürücüler (driverlar)```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Recovery modunu bilgisayar aracılığıyla başlatın
```cmd
fastboot boot <recovery.img>
```

#### Yığın depolama (mass storage) modunu etkinleştirin
> Eğer komutu bir kez daha çalıştırmanıza dair uyarı gelirse, bunu yapın
```cmd
adb shell msc
```
  
#### Diskpart'ı (Windows disk yönetimini) başlatın
```cmd
diskpart
```

#### Tabletinizdeki Windows volümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, **WINNABU** isimli volümdür.
```diskpart
select volume <volume numarası>
```

#### X harfini atayın
```diskpart
assign letter x
```

#### Diskpart arayüzünden çıkın.
```diskpart
exit
```

### Sürücü kurulumu
> `"Automatic WINNABU detection failed! Enter Drive Letter manually"` diye bir uyarı verirse, **`X`** yazın   
```cmd
Sürücülerün bulunduğu klasörü açın ve OfflineUpdater.cmd dosyasını çalıştırın
```
  
### UEFI'yi flashlamak için fastboot'a reboot edin
> WOA Helper uygulamasını da kullanabilirsiniz, bu durumda ```adb reboot``` ile yeniden başlatabilirsiniz 
>
> En güncel UEFI'yi kullandığınızdan emin olun, çünkü UEFI'yi güncellemeden sürücüleri güncellerseniz Windows açılmayabilir
```cmd
adb reboot bootloader
```

#### Boot edilebilir Windows UEFI imajıyla boot edin
> Komutun <uefi.img> kısmını UEFI imajının bulunduğu gerçek yol ile değiştirin
```
fastboot flash boot <uefi.img>
```

## İşlem tamamlandı!
