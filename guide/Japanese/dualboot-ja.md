<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## Android と Windows をシームレスにデュアルブートする

### 前提条件
- 脳
- root化されたタブレット
- タブレットにインストールされている Windows
- [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img)
- [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk)
- [StA Installer](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe)

## デュアルブート アプリのセットアップ
> このガイドは root 化されていることを前提としています。root化されていない場合は、次の手順に従ってください。 [root guide](2-rootguide-ja.md) 初め.

### 設定 - Android
> [!NOTE]
> Windows フォルダーにファイルを移動できない場合は、Windows を再起動せずにシャットダウンしたことを意味します。この問題を解決するには、Windows に戻って起動し、再起動を使用します。次に、再起動時に fastboot を起動し、それを使用して Android に戻ります。

- ダウンロードしてインストールします [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), 次に、それを開いて root アクセスを許可します.
- ダウンロード [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v2.img) and 内部ストレージの `UEFI` という名前のフォルダー内に置きます。このフォルダーが存在しない場合は、作成します。
- に戻る WOA Helper アプリを選択し、 `Back up Android boot` ボタン. 両方を選択します `Windows` そして `Android` オプション.
- を押します。 `Mount Windows` ボタンをクリックしてダウンロードして移動します.[StA_Installer_nabu.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) 新しく作られたものに `Windows` 内部ストレージ内のフォルダー.
- に戻る WOA Helper アプリを押して `Quickboot to Windows`.

### 設定 - Windows
- `C:\StA_Installer_nabu.exe` に移動して実行します。動作しない場合は、ウイルス対策ソフトウェアがオフになっていることを確認してください。ウイルス対策ソフトウェアを使用するとアプリが実行できなくなる可能性があります.

##### 起動中 Android
  - デスクトップ上で新しいショートカットを実行します (アクセスしやすくするために、スタート メニュー/タスクバーにピン留めすることもできます)

##### 起動中 Windows
  - プレス `Quickboot to Windows` アプリ内で、またはクイック設定パネルで新しく作成されたトグルを使用します
  
## 終了した!
