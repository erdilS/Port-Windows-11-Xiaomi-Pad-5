# Project status

- Current **Driver** version: **[v2611.21](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases/tag/2611.21)**
- Current **UEFI** version: **[v2611.21](https://github.com/remtrik-stuff/MiPad5-Windows-Releases/releases/tag/2611.21)**

# Simple status

| Feature                | Notes                                           | Status         |
|------------------------|-------------------------------------------------|----------------|
| 🔊 Audio               |                                                 | ✅            |
| 🔋 Battery             |                                                 | ✅            |
| 🎆 GPU                 |                                                 | ✅            |
| 👆 Touch               | 10-point Multi-touch                            | ✅            |
| 🪵 USB                 |                                                 | ✅            |
| 🔌 Charging            | Works with most chargers; limited to 18 W       | ⚠️            |
| 🔵 Bluetooth           |                                                 | ✅            |
| 🛜 Wi-Fi               |                                                 | ✅            |
| ⌨️ Side buttons        |                                                 | ✅            |
| 🖊 Accessories          | Mostly working, with some limitations           | ⚠️            |
| 🛡️ Security            | Partial                                         | ⚠️            |
| 🛰️ Location            |                                                 | ✅            |
| 🧭 Sensors             |                                                 | ✅            |
| 🔦 Flashlight          | Partial                                         | ⚠️            |
| 💽 Virtualization      | Only WSL 1                                      | ❌            |
| 📷 Camera              | Working, but image quality is currently below Android quality; requires [additional setup](Additional-materials-en.md#camera-drivers) | ⚠️            |


# Detailed status

## 🔊 Audio

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🔉 Bottom speakers     |                                             | ✅            |
| 🔉 Top speakers        |                                             | ✅            |
| 🎙️ Internal top mic    |                                             | ✅            |
| 🎙️ Internal bottom mic |                                             | ✅            |


## 🎆 GPU

| Feature                | Notes                               | Status         |
|------------------------|-------------------------------------|----------------|
| 🔆 Brightness control  |                                     | ✅            |
| 🎆 x64 emulation       |  Only in Windows 11                 | ✅            |


## 🪵 USB & Charging

> [!Note]
> Driver and UEFI v2611.21 improve USB-C OTG and dual-role operation; manually switching between USB device and host modes is generally no longer needed.

| Feature                        | Notes                                                            | Status         |
|--------------------------------|------------------------------------------------------------------|----------------|
| 🪵 USB-Fn (Charging & MTP)     | Device role                                                     | ✅             |
| 🪵 USB-Host (OTG)              | Host role; dual-role operation works without manual switching    | ✅             |
| 🔌 Charging (USB)              | Works with most chargers; limited to 18 W, compatibility varies  | ⚠️             |


## 🌐 Wi-Fi

| Feature                | Notes                               | Status         |
|------------------------|-------------------------------------|----------------|
| 🌐 Wi-Fi (2.4 Ghz)     |                                      | ✅            |
| 🌐 Wi-Fi (5 Ghz)       |                                      | ✅            |
| 📡 Wi-Fi Direct        |                                      | ✅            |
| 🖥 Miracast             |                                      | ✅            |


## ⌨️ Side buttons

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| ⌨️ Volume up button    |                                             | ✅            |
| ⌨️ Volume down button  |                                             | ✅            |
| ⌨️ Power button        |                                             | ✅            |


## 🖊 Accessories

| Feature                | Notes                                                               | Status         |
|------------------------|---------------------------------------------------------------------|----------------|
| 🖋 Xiaomi Pen          |                                                                     | ✅             |
| 🖋 Xiaomi Pen buttons  |                                                                     | ✅             |
| 🔌 Xiaomi Pen charging |                                                                     | ❌             |
| 🖋 Third-party pens    | Only pens compatible with Wacom WGP digitizers will work properly   |    ⚠️          |
| 🖋 Third-party pen buttons   | Only if Bluetooth                                             | ⚠️             |
| ⌨️ Xiaomi Keyboard     |                                                                     | ✅             |
| 💻 Smart Cover         | Puts device to sleep when magnetic case is closed                   |  ✅            |



## 🛡️ Security

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🛡️ TPM                 |                                             | ❌            |
| 🛡️ Security processor  | Unavailable                                 | ❌              |
| 🔒 BitLocker           | Available but not recommended               | ✅            |
| 🛡️ Secure Boot         |                                             | ✅            |
| 🛡️ Windows Hello Biometrics      |   | ❌            |


## 🧭 Sensors

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🧭 Accelerometer       |                                             | ✅            |
| 🧭 Gyroscope           |                                             | ✅            |
| 🧭 Light sensor        |                                             | ✅            |
| 🧭 Magnetometer        |                                             | ✅            |
| 🧭 Proxymity           | Combined with light sensor                  | ✅            |


## 🔦 Flashlight

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🔦 Flashlight          | Accessible only from the Windows Camera app | ⚠️            |
| 📸 Camera flash        |                                             | ❌            |
