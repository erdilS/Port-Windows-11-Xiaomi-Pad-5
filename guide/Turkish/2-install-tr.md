<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows Çalıştırma

## Aşama 2: Windows Kurulumu

### Gerekli Dosyalar

- [ARM64 Mimaride Çalışabilen Windows ISO imajı](https://uupdump.net/)
- [UEFI imajı](../../../../releases/tag/1.0)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Sürücüler](https://github.com/map220v/MiPad5-Drivers/releases/latest)


### Windows'u yüklemeye başlamak için ilk olarak recovery modunda cihazı başlatın.

```cmd
fastboot boot <recovery.img>
```

### msc betiğini çalıştırın

```cmd
adb shell msc
```
> Bu aşamadan sonra tabletinizdeki tüm bölümler bilgisayarınızda taşınabilir sabit disk olarak görünecektir. İlk aşamada uyarıldığı gibi diskpart üzerinden silme işlemi yapmamaya dikkat edin.

## Disklere harf atayın
  

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

### ESP bölümüne `Y` harfini atayın

#### Tabletteki ESP bölümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, genellikle en sondaki bölüm olur.

```diskpart
select volume <number>
```

#### Y harfini atayın

```diskpart
assign letter=y
```

### diskpart arayüzünden çıkın.
```diskpart
exit
```

  
  

## Kurulum işlemi

> Komuttaki `<sources/install.wim>` kısmını install.wim dosyanızın konumuyla değişin.

> `install.wim` dosyası ISO'nun içindeki sources klasöründedir.
> Bu dosyayı ISO'yu bağlayarak ya da ayrıştırarak elde edebilirsiniz.

```cmd
dism /apply-image /ImageFile:<sources/install.wim> /index:1 /ApplyDir:X:\
```

# Sürücü kurulumu

> Komuttaki `<nabusurucuklasoru>` kısmını sürücülerin bulunduğu konum ile değişin.

```cmd
driverupdater.exe -d <nabusurucuklasoru>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabusurucuklasoru> -p X:
```

  

# EFI için Windows önyükleme yöneticisi dosyalarını oluşturun
> Bu aşamayı muhakkak yönetici yetkileriyle başlatılmış Komut İstemi (cmd.exe) ile yapın. Windows Terminal ya da PowerShell kullanmak komutta hata almanıza yol açacaktır.

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

# İmzasız sürücülere izin verin

> Bunu yapmazsanız önyükleme esnasında mavi ekranla karşılaşacaksınız.

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

# Windows'u başlatın

### Mevcut boot bölümünün bir yedeğini alın

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Bu yedeği bilgisayarınıza kopyalayın

```cmd
adb pull /tmp/boot.img
```
### Panelinizi tanımlayın

```cmd
adb shell panel
```


### Bootloader moduna geçiş yapın

```cmd
adb reboot bootloader
```

### UEFI görüntüsünü indirin ve flaşlayın
> İçin resmi indirin [Huaxing](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_huaxing.img) veya [Tianma](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_tianma.img) panel

```cmd
fastboot flash boot <path to image>
```
> Bu aşamadan itibaren cihazınızı başlatıp Windows'u kullanabilirsiniz.

# Android'e geri dönüş yapmak
> Yedeklediğiniz boot yedeğini Fastboot aracılığıyla geri yükleyin.

```cmd
fastboot flash boot boot.img
```

# İşlem tamamlandı!
