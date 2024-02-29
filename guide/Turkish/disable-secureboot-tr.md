<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Disabling secureboot
> [!Important]
> Bu rehberi yalnızca secureboot'u devre dışı bırakmak istiyorsanız takip edin.

### Gerekli Dosyalar
- ```Brain```

- [```Android platform araçları```](https://developer.android.com/studio/releases/platform-tools)

- [```Recovery imajı```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```UEFI imajı (Secureboot kapalı)```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-NoSecureboot-v3.img)

## Secureboot'un artıları ve eksileri

##### Açık Secureboot'un artıları ve eksileri
- √ Ana ekranda filigran olmaz
- √ Test Modu ile çalışmayan uygulamalar çalışacaktır
- √ Büyük sürümleri (örneğin 22h2'den 23h2'ye) doğrudan Windows Update üzerinden güncelleyebilirsiniz
- × PC olmadan sürücüleri güncelleyemezsiniz

##### Kapatılmış Secureboot'un artıları ve eksileri
- √ Sürücüleri doğrudan tabletinizden güncelleyebilirsiniz; PC gerekmez
- × Ana ekranda test modu filigranı belirir
- × Anticheat yazılımına sahip bazı uygulamalar/oyunlar çalışmayabilir
- × Windows Update aracılığıyla büyük sürümleri (örneğin 22h2'den 23h2'ye) güncelleyemezsiniz

## Secureboot'u kapatma

####  Rootlu boot imajınızın yedeğini alın
> Android'e dönmek için buna ihtiyacınız olacak, ancak zaten bir yedekleme yaptıysanız bu adımı atlayabilirsiniz

WOA Helper uygulamasındaki `Backup Android boot` işlevini kullanın ya da modlu recovery'e boot edin ve alttaki komutu çalıştırın
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### Recovery'e boot edin
<gerçek\yol\recovery> kısmını recovery imajının bulunduğu gerçek yol ile değiştirin
```cmd
fastboot boot <gerçek\yol\recovery.img>
```

#### Yığın depolama (mass storage) modunu etkinleştir
> Xiaomi Pad 5 modlu recovery'e boot edildikten sonra
```cmd
adb shell msc
```

####  Diskpart'ı (Windows disk yönetimini) başlatın
```cmd
diskpart
```

### ESP volümüne `Y` harfini atayın

#### Tabletteki ESP bölümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, "ESPNABU" isimli volümdür.
```diskpart
select volume <volume numarası>
```

#### Y harfini atayın
```diskpart
assign letter y
```

### Diskpart arayüzünden çıkın.
```diskpart
exit
```

#### Bootloader dosyalarını modifiye edin
> Test imzalamayı etkinleştirmek için
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### SiPolicy'iyi kaldırın
> Mevcut bir kurulumda secureboot'u devre dışı bıraktığınızı varsayarsak, bu dosyayı silmeniz gerekir, aksi takdirde sistem boot yapmaz
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### ESPNABU'nun harfini kaldırın
> Eğer bu işe yaramazsa, bunu görmezden gelin ve bir sonraki komuta geçin. Bu hayalet sürücü bilgisayarınızı bir sonraki yeniden başlatışınızda kaybolacaktır.
```cmd
mountvol y: /d
```

#### Fastboot'a reboot edin
```cmd
adb reboot bootloader
```

#### UEFI flashlayın
> Bu sayfadaki secureboot'u kapalı UEFI'yi kullandığınızdan emin olun. <gerçek\yol\uefi-NoSecureboot-v3.img> yerine UEFI görüntüsünün bulunduğu gerçek yolu yazın
```cmd
fastboot flash boot <gerçek\yol\uefi-NoSecureboot-v3.img>
```

> [!Important]
> Android'in dahili depolama alanındaki UEFI klasöründeki eski UEFI'nizi de değiştirdiğinizden emin olun, böylece bir dahaki sefere Android'den Windows'a geçmeye çalıştığınızda yanlışlıkla flashlamazsınız

#### Reboot to Windows
```cmd
fastboot reboot
```

## Finished!



















