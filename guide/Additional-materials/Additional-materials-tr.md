<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi pad 5'te Windows için faydalı uygulamalar ve talimatlar

## USB Host modunu devre dışı bırakma
> [!Warning]
> Güç verilmeyen USB aygıtları çalışmayı durduracaktır.

[restore_default_usb.reg](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/USBHost/restore_default_usb.reg) dosyasını çalıştırın, sonrasında tableti yeniden başlatın.

USB host modunu yeniden aktif etmek için [force_usb_host.reg](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/USBHost/force_usb_host.reg) dosyasını çalıştırın, ardından tableti yeniden başlatın.

## Secureboot'u devre dışı bırakma
> Sürücüleri bilgisayar olmadan güncelleyebilmek istiyorsanız

[Secureboot'u devre dışı bırakma rehberi](/guide/Turkish/disable-secureboot-tr.md)

## ```Microsoft Office``` / ```Microsoft 365``` kurulumu

- Bu dosyayı [dosya](https://mega.nz/file/Q7p1XK6L#J-KPp_-MNJ8iXGqEwwZ3_sfv2tMiq_AJjUiiaX6TBrI) tablete indirin
  
### Office'i iso dosyasından kurma
  
- iso dosyasına sağ tıklayın ve Explorer'da açmak için Bağla'yı seçin

- Kurulum sihirbazını başlatmak için ```Office Tool Plus.exe``` dosyasına çift tıklayın
  
- Açılan pencerede `Evet` seçeneğine tıklayın
  
- Kurulumun tamamlanmasını bekleyin

 ### Office aktivasyonunu yapma

- massgrave script dosyasını kullanarak etkinleştirin:

> `PowerShell`'i açın ve şunu yazın: 

```powershell 
irm https://massgrave.dev/get | iex 
```

- Bir pencere açılacak, burada `2`yi seçin

- Sonraki sayfada `1`i seçin

- Etkinleştirmenin tamamlanmasını bekleyin

- Office'i kullanmanın keyfini çıkarın!

 ## Windows aktivasyonunu yapma

> PowerShell'i açın ve şunu yazın: 

```powershell 
irm https://massgrave.dev/get | iex 
```
> Bir pencere açılacak, burada 1'i seçin

 ## El feneri nasıl kullanılır

 - [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) arşiv dosyasını indirin ve herhangi bir klasöre çıkartın

> El fenerini açmak için flashlight.exe'yi çalıştın

> Kapatmak için ise herhangi bir tuşa basın
