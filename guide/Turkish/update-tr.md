<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">

# Xiaomi Pad 5 üzerinde Windows çalıştırma

### Prerequisites

- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)
  
- [Recovery imajı](../../../../releases/tag/1.0)
  
- [Sürücüler](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### Recovery modunu bilgisayar aracılığıyla başlatın

```cmd
fastboot boot <recovery.img>
```


### Betiği çalıştırın
> Sizden bir kez daha çalıştırmanızı isterse, bunu yapın
```cmd
adb shell msc
```
> Bu aşamadan sonra tabletinizdeki tüm bölümler bilgisayarınızda taşınabilir sabit disk olarak görünecektir. İlk aşamada uyarıldığı gibi diskpart üzerinden silme işlemi yapmamaya dikkat edin.

## Disklere harfleri atayın

#### Diskpart'ı başlatın

```cmd
diskpart
```


### Windows bölümüne `X` harfini atayın

#### Tabletinizdeki Windows bölümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, "WINNABU" etiketini içeren bölümün numarasını komutta kullanın. Genellikle sondan bir önceki bölüm olur.

```diskpart
select volume <number>
```

#### X harfini atayın
```diskpart
assign letter=x
```

### diskpart arayüzünden çıkın.
```diskpart
exit
```



# Sürücü kurulumu

> Sürücüleri indirebilirsiniz [burada](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> `"Automatic WINNABU detection failed! Enter Drive Letter manually"` yazıyorsa, **`X`** yazın   

```cmd
Sürücülerle klasörü açın ve çalıştırın OfflineUpdater.cmd
```
  
### UEFI'yi flaş etmek için fastboot'u yeniden başlatın
> Veya UEFI'niz zaten yanıp sönmüşse, ```adb reboot``` ile yeniden başlatmanız yeterlidir.
```cmd
adb reboot bootloader
```

#### UEFI imajını yükleyerek Windows'u başlatın #####
> <uefi.img> dosyasını UEFI görüntüsünün gerçek yolu ile değiştirin
```
fastboot flash boot <uefi.img>
```


# İşlem tamamlandı!
