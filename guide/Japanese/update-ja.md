<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomiパッド5でWindowsを実行する

## ドライバの更新

### 前提条件


- [```UEFIイメージ```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```Recovery```](../../../../releases/tag/1.0)

- [```ドライバー```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

#### 次のコマンドを使用してPCから回復を開始します

```cmd
fastboot boot <recovery.img>
```


#### 実行 msc
> もう一度実行するように求められた場合は、実行してください
```cmd
adb shell msc
```

### ディスクへの文字の割り当て

#### Windowsディスクマネージャを起動します

> パッド5がディスクとして検出されると

```cmd
diskpart
```


### Windowsボリュームに`X`を割り当てる

#### タブレットのWindowsボリュームを選択します
> 使用 `list volume` それを見つけるために、それは名前の一つです "WINNABU"

```diskpart
select volume <number>
```

#### 手紙を割り当てる X
```diskpart
assign letter=x
```

#### Diskpartを終了します
```diskpart
exit
```


### ドライバのインストール

> ドライバをダウンロードすることができます[ここ](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> `"Automatic WINNABU detection failed! Enter Drive Letter manually"` と書き込まれた場合は、 **`X`** と入力します

```cmd
ドライバでフォルダを開き、実行します OfflineUpdater.cmd
```
### UEFIをフラッシュするためにfastbootに再起動します
> または、UEFIがすでにフラッシュされている場合は、`adb reboot`で再起動するだけです
```cmd
adb reboot bootloader
```

### Windowsブート可能なUEFIイメージで起動する
> <uefi.img> を UEFI イメージの実際のパスに置き換えます
```
fastboot flash boot <uefi.img>
```

## 終了しました！
