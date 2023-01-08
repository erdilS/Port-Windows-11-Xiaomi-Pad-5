## Dual Boot gereksinimleri

- Beyin

- Sadece A slotunda çalışmaktadır!

- Rootlanmış Android ve rootlanmış Android boot bölümü yedeği

- [Download Files](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/dualboot) 

### Dual Boot işleminin Windows tarafı

- [Cygwin](https://www.cygwin.com/setup-x86_64.exe) uygulamasını coreutils ile beraber yükleyin (varsayılan olarak yüklenecektir)

- Boot yedeğinizin adını boot.img yapın

- Android boot yedeğinizi C:\ dizinine kopyalayın (C:\boot.img)

- .bat dosyasını yönetici olarak çalıştırın, bu cihaza Android yedeğini yükleyip yeniden başlatacaktır. Dilerseniz bunun için yönetici haklarıyla çalışan bir kısayol da oluşturabilirsiniz.

### Dual Boot işleminin Android tarafı

- switchtowin.apk dosyasını cihaza kurun.

- UEFI dosyasının adını boot.img olarak adlandırın.

- UEFI dosyasını /sdcard/windows konumuna kopyalayın (/sdcard/windows/boot.img)

- Uygulamayı başlatın ve root izni verin.

- "Switch to Windows" butonuna bastığınızda cihaz yeniden başlatılacak ve Windows'a giriş yapacaktır.

