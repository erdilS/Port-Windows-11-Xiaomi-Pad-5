<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 で Windows を動かす

## Android と Windows をデュアルブートさせる

### 必要なもの

- 脳みそ

- タブレットのRoot化と、その boot イメージのバックアップ

### Windows 側の手順

- [STA](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) のインストール

- Android の boot イメージを `boot.img` にリネームする

- Cドライブ直下に配置する(C:\boot.img)

- デスクトップのショートカットを開くと、Androidが起動します

### Android 側の手順

- [switchtowin.apk](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/switchtowindows.apk) をインストールする
  
- タブレットの内部ストレージ直下に`Windows`フォルダを作成する

- Windows のUEFI イメージを `boot.img`にリネームする

- リネームしたUEFIイメージをWindowsフォルダ内に配置する(/Android storage/Windows/boot.img)

- アプリを起動し、root権限を与える

- "Switch to Windows" を押下すると、Windowsが起動します

