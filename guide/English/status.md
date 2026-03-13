# Project status

- Current **Driver** version: **v2601.19**
- Current **UEFI** version: **v2601.19**

# Simple status

| Feature                | Notes                                           | Status         |
|------------------------|-------------------------------------------------|----------------|
| 🔊 Audio               |                                                 | ✅            |
| 🔋 Battery             |                                                 | ✅            |
| 🎆 GPU                 |                                                 | ✅            |
| 👆 Touch               | 10-point Multi-touch                                                | ✅            |
| 🪵 USB                 |                                                 | ✅            |
| 🔌 Charging              | Slow charging only                            | ✅            |
| 🔵 Bluetooth           |                                                 | ✅            |
| 🛜 Wi-Fi                |                                                 | ✅            |
| ⌨️ Side buttons        |                                                 | ✅            |
| 🖊 Accessories        | Mostly working, with some limitations                       | ⚠️            |
| 🛡️ Security                 | Partial                                    | ⚠️            |
| 🛰️ Location                 |                                                 | ✅            |
| 🧭 Sensors              |                                                 | ✅            |
| 📳 Vibration motor     |                                                 | ❌            |
| 🔦 Flashlight          | Partial         | ⚠️            |
| 💽 Virtualization              | Only WSL 1                                                | ❌            |
| 📷 Camera              |                                                 | ❌            |


# Detailed status

## 🔊 Audio

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🔉 Bottom speakers       |                                             | ✅            |
| 🔉 Top speakers    |                                             | ✅            |
| 🎙️ Internal top mic    |                                             | ✅            |
| 🎙️ Internal bottom mic |                                             | ✅            |


## 🎆 GPU

| Feature                | Notes                               | Status         |
|------------------------|-------------------------------------|----------------|
| 🔆 Brightness control  |                                                     | ✅            |
| 🎆 x64 emulation      |  Only in Windows 11                          | ✅            |


## 🪵 USB & Charging

> [!Note]
> On **SM8150** devices, the device is incapable of switching the USB-mode in Windows, and a [USB Host Mode Switch tool](https://github.com/n00b69/usbhostmode) is required to do so

| Feature                         | Notes                                                            | Status         |
|---------------------------------|------------------------------------------------------------------|----------------|
| 🪵 USB-Fn (Charging & MTP)   | **[Default]**                                                     | ✅            |
| 🪵 USB-Host (OTG)              | Some of the features are work in progress (USB Powerless Dongles) | ⚠️            |
| 🔌 Charging (USB)             | Slow charging only, only in USB-Fn mode                           | ✅            |
| 🔌 Charging (Wireless)             | Slow charging only, only in USB-Fn mode                           | ✅            |


## 🌐 Wi-Fi

| Feature                | Notes                               | Status         |
|------------------------|-------------------------------------|----------------|
| 🌐 Wi-Fi (2.4 Ghz)   |                             | ✅            |
| 🌐 Wi-Fi (5 Ghz)     |                             | ✅            |
| 📡 Wi-Fi Direct      |                             | ✅            |
| 🖥 Miracast           |                            | ✅            |


## ⌨️ Side buttons

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| ⌨️ Volume up button       |                                                 | ✅            |
| ⌨️ Volume down button  |                                                 | ✅            |
| ⌨️ Power button               |                                                 | ✅            |


## 🖊 Accessories

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🖋 Xiaomi Pen       |                                             | ✅            |
| 🖋 Xiaomi Pen buttons   |                                             | ✅            |
| 🔌 Xiaomi Pen charging           |                                             | ❌            |
| 🖋 Third-party pens        | Only pens compatible with Wacom WGP digitizers will work properly        | ⚠️            |
| 🖋 Third-party pen buttons    | Only if Bluetooth             | ⚠️            |
| ⌨️ Xiaomi Keyboard        |                                             | ✅            |
| 💻 Smart Cover Mode           | Puts device to sleep when magnetic case is closed      | ✅            |



## 🛡️ Security

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🛡️ TPM                 |  | ❌            |
| 🛡️ Security processor      | Unavailable                          |             |
| 🔒 BitLocker      | Available but not recommended                              | ✅            |
| 🛡️ Secure Boot      |                           | ✅            |
| 🛡️ Windows Hello Biometrics      | Requires working fingerprint scanner                          | ❌            |


## 🧭 Sensors

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🧭 Accelerometer       |                                             | ✅            |
| 🧭 Gyroscope           |                                             | ✅            |
| 🧭 Light sensor        |                                             | ✅            |
| 🧭 Magnetometer        |                                             | ✅            |
| 🧭 Proximity           |                                             | ✅            |


## 🔦 Flashlight

| Feature                | Notes                                       | Status         |
|------------------------|---------------------------------------------|----------------|
| 🔦 Flashlight          | Accessible only from the Windows Camera app         | ⚠️            |
| 📸 Camera flash          |                | ❌            |
