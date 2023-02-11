<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 çalıştıran bir Xiaomi Pad 5">


# Xiaomi Pad 5 üzerinde Windows çalıştırma

## Windows ve Android'in tek bir slotta dual-boot olarak yüklenmesi

### Gereksinimler

- Beyin

- Rootlu Android ve rootlu Android boot.img yedeği

- [DualBoot dosyaları](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Dualboot işleminin Windows tarafı

- [Cygwin](https://www.cygwin.com/setup-x86_64.exe) uygulamasını coreutils ile beraber yükleyin (varsayılan olarak yüklenecektir)

- Boot yedeğinizin adını boot.img yapın

- Android boot yedeğinizi C:\ dizinine kopyalayın (C:\boot.img)

- .bat dosyasını yönetici olarak çalıştırın, bu cihaza Android yedeğini yükleyip yeniden başlatacaktır. Dilerseniz bunun için yönetici haklarıyla çalışan bir kısayol da oluşturabilirsiniz.

### Dualboot işleminin Android tarafı

- switchtowin.apk dosyasını cihaza kurun.

- UEFI dosyasının adını boot.img olarak adlandırın.

- UEFI dosyasını /sdcard/windows konumuna kopyalayın (/sdcard/windows/boot.img)

- Uygulamayı başlatın ve root izni verin.

- "Switch to Windows" butonuna bastığınızda cihaz yeniden başlatılacak ve Windows'a giriş yapacaktır.

