<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 Üzerinde Windows Çalıştırma

## Secureboot'u Devre Dışı Bırakma
> [!Important]
> Secureboot'u devre dışı bırakmak istiyorsanız bu kılavuzu takip edin.

### Gereksinimler
- ```Beyin```

- [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools)

- [```Kurtarma Görüntüsü```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```UEFI görüntüsü (Secureboot kapalı)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/XXXnabu-NoSecureboot-v4.img)

## Secureboot'un Artıları ve Eksileri
> Varsayılan olarak, bu kılavuzda secureboot etkindir.

##### Secureboot'un Açık Olmasının Artıları ve Eksileri
- √ Ana ekranda filigran yok
- √ Test Modu ile çalışmayan uygulamalar çalışacak
- √ Windows güncellemesinde büyük sürümleri doğrudan güncelleyebilirsiniz (örn. 22h2'den 23h2'ye)
- × İmzalanmamış sürücüleri yükleyemezsiniz

##### Secureboot'un Devre Dışı Bırakılmasının Artıları ve Eksileri
- √ İmzalanmamış sürücüleri yükleyebilirsiniz
- × Ana ekranda test modu filigranı
- × Anti-hile yazılımı olan bazı uygulamalar/oyunlar çalışmayabilir
- × Windows Güncellemesi ile büyük sürümleri (örn. 22h2'den 23h2'ye) güncelleyemezsiniz

## Secureboot'u Devre Dışı Bırakma

#### Rootlu Önyükleme Görüntünüzün Yedeğini Alın
> Android'e geri dönmek için buna ihtiyacınız olacak, ancak zaten bir yedek aldıysanız bu adımı atlayabilirsiniz

WOA Helper uygulamasındaki `Android önyükleme yedeği` işlevini kullanın veya modifiye edilmiş kurtarma moduna önyükleme yapın ve şu komutu çalıştırın:
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Kurtarma Moduna Önyükleme Yapın
> <path\to\recovery> ile kurtarma görüntüsünün gerçek yolunu değiştirin
```cmd
fastboot boot <path\to\recovery.img>
```

#### Kütle Depolama Modunu Etkinleştirin
> Xiaomi Pad 5 modifiye edilmiş kurtarma modunda önyüklediğinde
```cmd
adb shell msc
```

#### Windows Disk Yöneticisini Başlatın
> Xiaomi Pad 5 disk olarak algılandığında
```cmd
diskpart
```

#### Tabletin ESP Hacmini Seçin
> `list volume` kullanarak bulun, "ESPNABU" adını taşıyan
```diskpart
select volume <number>
```

#### Y Harfi Atayın
```diskpart
assign letter y
```

#### Diskpart'tan Çıkın
```diskpart
exit
```

#### Önyükleyici Dosyalarını Değiştirin
> Test imzalamayı etkinleştirmek için
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### SiPolicy'i Kaldırma
> Secureboot'u mevcut bir kurulumda devre dışı bırakıyorsanız, bu dosyayı silmeniz gerekir yoksa sistem önyükleme yapmaz
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### ESPNABU için Sürücü Harfini Kaldırın
> Bu işe yaramazsa, görmezden gelin ve bir sonraki komuta geçin. Bu hayalet sürücü, PC'nizi bir sonraki yeniden başlatmanızda kaybolacaktır.
```cmd
mountvol y: /d
```

#### Fastboot Moduna Yeniden Başlatın
```cmd
adb reboot bootloader
```

#### UEFI'yi Flashlama
> Bu sayfadaki secureboot kapalı UEFI'yi kullandığınızdan emin olun, <path\to\uefi-NoSecureboot-v3.img> ile UEFI görüntüsünün gerçek yolunu değiştirin
```cmd
fastboot flash boot <path\to\uefi-NoSecureboot-v3.img>
```

> [!Önemli]
> Android'in dahili depolamasındaki UEFI klasörünüzde eski UEFI'nizi de değiştirmeniz gerektiğinden emin olun, böylece Android'den Windows'a geçmeye çalıştığınızda yanlışlıkla onu flashlamazsınız.

#### Windows'a Yeniden Başlatın
```cmd
fastboot reboot
```

## Tamamlandı!
