<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows için faydalı uygulamalar ve talimatlar

## Çalıştığı bilinen uygulamalar/oyunlar
Bu kapsamlı bir liste değildir, sadece topluluğun test etmiş olduğu uygulamaları/oyunları listeler
[Linki burada bulabilirsiniz](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

Ayrıca [bu linkte](https://armrepo.ver.lt/) ARM'a özel yazılımların bir listesini bulabilirsiniz

## D sürücüsünü gizleme (modem bölümü)
> [!NOTE]
> Bu sürücü ile oynanılmamalıdır. Bazı programlar bu sürücüde değişiklik yapabileceğinden bu işlemi yapmanızı öneriyoruz

- CMD açın ve ```diskpart``` komutunu çalıştırın
- Bütün mevcut bölümleri görmek için ```list volume``` komutunu çalıştırın
- D harfine sahip sürücüyü bulun. ```select volume $``` komutu ile sücüyü seçin ($ harfi yerine D sürücüsünün numarasını girmeyi unutmayın)
- ```remove letter d``` komutuyla sürücünün (d) harfini silin
- ```exit``` komutuyla çıkış yapın


## USB Host modunu devre dışı bırakma
> [!Warning]
> Ek güç verilmemiş USB aygıtlar çalışmayı durduracaktır.

Run [USB Host Control](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/USBHost) to enable/disable USB host mode and confirm that you want to disable/enable USB host mode 


## Secureboot'u devre dışı bırakma
> Sürücüleri bilgisayar olmadan güncelleyebilmek için secureboot kapatılmalıdır.

[Secureboot'u devre dışı bırakma rehberi](/guide/Turkish/disable-secureboot-tr.md)

## ```Microsoft Office``` / ```Microsoft 365``` kurulumu

- Bu [ISO dosyasını](https://drive.google.com/file/d/1-i-0RraTSgwxqQSWal3uYWCen1TjK6d3/view?usp=drivesdk) tablete indirin
- iso dosyasına sağ tıklayın ve windows gezgininde (explorer) açmak için bağlayın (mount edin)
- Kurulum sihirbazını başlatmak için ```Office Tool Plus.exe``` dosyasını çift tıklayın
- Açılan pencerede `Evet (Yes)`i seçin
- Kurulumun bitmesini bekleyin

 ### Windows / Office aktivasyonunu yapma

[Buradan](https://github.com/massgravel/Microsoft-Activation-Scripts) Massgravel'ın talimatlarını takip edin

 ## El feneri (flashlight) nasıl kullanılır

- [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) arşiv dosyasını indirin ve herhangi bir klasöre çıkartın
> El fenerini açmak için flashlight.exe'yi çalıştın
> Kapatmak için ise herhangi bir tuşa basın
