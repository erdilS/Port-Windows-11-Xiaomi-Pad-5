<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5'te Windows için faydalı uygulamalar ve talimatlar

## Çalıştığı bilinen uygulamalar/oyunlar
Bu kapsamlı bir liste değildir, sadece topluluğun test etmiş olduğu uygulamaları/oyunları listeler
[Linki burada bulabilirsiniz](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

Ayrıca [bu linkte](https://armrepo.ver.lt/) ARM'a özel yazılımların bir listesini bulabilirsiniz

#### Bitti!

## D sürücüsünü gizleme (modem bölümü)
> [!NOTE]
> Bu işlemi yapmanız önerilir çünkü sürücüde herhangi bir değişiklik yapılmaması gerekmektedir, ayrıca sürücü gizlenmezse bazı uygulamaların bu sürücüye dosya yazma ihtimali her daim olacaktır.

- [ModemHide.vbs](https://github.com/Misha803/My-Scripts/releases/tag/ModemHide) dosyasını cihaza indirin ce çalıştırın
- `Evet`e tıklayarak bütün Kullanıcı Hesabı Denetimi uyarılarını onaylayın


## USB Host modunu devre dışı bırakma
> [!Warning]
> Ek güç verilmemiş USB aygıtlar çalışmayı durduracaktır.

> [!Important]
> Linkteki adımları Mi Pad 5'in Windows tarafında yapınız, bilgisayarınız üzerinde değil. 

Run [USB Host Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) to enable/disable USB host mode and confirm that you want to disable/enable USB host mode 


## Secureboot'u devre dışı bırakma
> [!Warning]
> Sadece gerekliyse bu işlemi yapın!

[Secureboot'u devre dışı bırakma rehberi](/guide/Turkish/disable-secureboot-tr.md)


## ```Microsoft Office``` / ```Microsoft 365``` kurulumu

- Bu [ISO dosyasını](https://drive.google.com/file/d/10FTyC0XBccj0BkxdIa_W_haixQz-d3to/view?usp=drivesdk) tablete indirin
- iso dosyasına sağ tıklayın ve windows gezgininde (explorer) açmak için bağlayın (mount edin)
- Kurulum sihirbazını başlatmak için ```Office Tool Plus.exe``` dosyasını çift tıklayın
- Tüm UAC uyarılarını onaylayın 
- Açılan pencerede `Evet (Yes)`i seçin
- Kurulumun bitmesini bekleyin


 ### Windows / Office aktivasyonunu yapma

[Buradan](https://github.com/massgravel/Microsoft-Activation-Scripts) Massgravel'ın talimatlarını takip edin


 ## ~El feneri (flashlight) nasıl kullanılır~

- [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) arşiv dosyasını indirin ve herhangi bir klasöre çıkartın
> El fenerini açmak için flashlight.exe'yi çalıştın
> Kapatmak için ise herhangi bir tuşa basın


## Factory reset Windows 11
> [!Warning]
> Bu adımları tamamladıktan sonra dosyalar, ayarlar ve uygulamalar dahil olmak üzere Windows'taki tüm verileriniz silinecektir
- Ayarlar uygulamasını açın
- Sistem'e tıklayın
- Kurtarma sekmesine tıklayın
- **Kurtarma seçenekleri** bölümünün altında, **Bu bilgisayarı sıfırla** ayarındaki ```Bilgisayarı sıfırla``` düğmesine tıklayın
- ```Her Şeyi Kaldır``` seçeneğine tıklayın
- ```Yerel yeniden yükleme``` seçeneğini seçin
- `Sonraki` düğmesine tıklayın
- `Sıfırla` düğmesine tıklayın
> Yeniden başlattıktan sonra temiz bir Windows elde edeceksiniz
