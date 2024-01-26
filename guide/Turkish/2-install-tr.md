<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows Çalıştırma
> [!WARNING]
> **LÜTFEN YOUTUBE'DA VEYA BAŞKA BİR platformda güncel olmayan VİDEO kılavuzları kullanmayın! BU VİDEOLAR MODASI GEÇMİŞ VE CİHAZINIZI KULLANARAK TUĞLALAYABİLİRSİNİZ! BİR VİDEO KILAVUZUNA İHTİYACINIZ VARSA, BUNU KULLANIN [YENİ VİDEO REHBERİ](https://www.youtube.com/watch?v=rGPbdFq7gKs) -den [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)**


## Aşama 2: Windows Kurulumu

### Gerekli Dosyalar

- [ARM64 Mimaride Çalışabilen Windows ISO imajı](https://uupdump.net/)
  
- [UEFI imajı](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
  
- [Sürücüler](https://github.com/map220v/MiPad5-Drivers/releases/latest)


### Windows'u yüklemeye başlamak için ilk olarak recovery modunda cihazı başlatın.

```cmd
fastboot boot <recovery.img>
```

### msc çalıştırın
> Sizden bir kez daha çalıştırmanızı isterse, bunu yapın
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

> [!NOTE]
> **Şimdi komut istemini yönetici olarak çalıştırın**

> Komuttaki `<sources/install.wim>` kısmını install.wim dosyanızın konumuyla değişin.

> `install.wim` dosyası ISO'nun içindeki sources klasöründedir.
> Bu dosyayı ISO'yu bağlayarak ya da ayrıştırarak elde edebilirsiniz.

> Sırasıyla Yolu değiştir **install.esd** olarak da adlandırılabilir.

```cmd
dism /apply-image /ImageFile:<sources/install.wim> /index:1 /ApplyDir:X:\
```

# Sürücü kurulumu

> Sürücüleri indirebilirsiniz [burada](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Size sorduğunda "Sürücü harfini girin..." tür **X:**

> Yönetici olarak çalıştırmayın, gerektiğinde yönetici hakları isteyecektir.

```cmd
Sürücülerle klasörü açın ve çalıştırın OfflineUpdater.cmd
```
  

# EFI için Windows önyükleme yöneticisi dosyalarını oluşturun
> Bu aşamayı muhakkak yönetici yetkileriyle başlatılmış Komut İstemi (cmd.exe) ile yapın. Windows Terminal ya da PowerShell kullanmak komutta hata almanıza yol açacaktır.

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```
 ## Hayalet sürücü harfinin görünmesini önlemek için ESPNABU için sürücü harfini çıkarın
```cmd
mountvol y: /d
```

# Windows'u başlatın

### Mevcut boot bölümünün bir yedeğini alın
> [!NOTE]
> **Şimdi platform araçları komut istemine geri dönün**


```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

##### Bu yedeği bilgisayarınıza kopyalayın

```cmd
adb pull /tmp/boot.img
```

### Bootloader moduna geçiş yapın

```cmd
adb reboot bootloader
```

### UEFI görüntüsünü indirin ve flaşlayın
> İndir [UEFI görüntüsü](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
```cmd
fastboot flash boot <path to image>
```
> Bu aşamadan itibaren cihazınızı başlatıp Windows'u kullanabilirsiniz.

## Windows'a yeniden başlat
```cmd
fastboot reboot
```

> [!NOTE]
> İlk Windows açılışında herhangi bir Wi-Fi ağı görmeyecek, sadece güç düğmesini basılı tutarak yeniden başlatın ve yeniden başlattıktan sonra yuor ağına bağlanmayı denediğinizde ve "dondurma" gördüğünüzde 7 kez "tekrar dene" ye tıklayın


# Android'e geri dönüş yapmak
> Yedeklediğiniz boot yedeğini Fastboot aracılığıyla geri yükleyin.

```cmd
fastboot flash boot boot.img
```

# İşlem tamamlandı!
> Bize katılabilirsiniz [Telegram sohbeti](https://t.me/nabuwoa) projeyle ilgili en son haberleri almak için
### [Son adım: Çift önyüklemeyi ayarlama](dualboot-tr.md)
