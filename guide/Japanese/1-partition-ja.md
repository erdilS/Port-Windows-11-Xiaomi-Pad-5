<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 で Windows を動かす

## インストール手順



### 必要なもの

- 脳みそ
- [Recovery Image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### ノート:
> [!Warning]\
> diskpart 経由でパーティションを削除した場合、Windows は ufs コマンドを送信しますが、これは誤って解釈され、すべての ufs が消去されます。
> 
> デバイスのデータは全て消去されます。必要ならばバックアップをしてください。
> 
> これらのコマンドはテスト済みです。
> 
> `udevadm` の警告は無視してください。
> 
> もし何かミスをした際、**絶対にタブレットを再起動しないで**、[Telegram chat](https://t.me/nabuwoa)で助けを求めてください。
>
> コマンドは一つずつ実行してください。
>
> YouTube などのビデオガイドは古いので、使わないでください。

### デバイスのパーティショニング

#### PCでコマンドを実行してリカバリーを起動する
```cmd
fastboot boot <recovery.img>
```
#### デバイスのパーティショニング

> もう一度実行するように指示されたら、実行してください。

> これは**オプション**ですが、このスクリプトを使って、Windowsパーティションの**カスタムサイズ**を設定できます。

> カスタムサイズを設定するには、``adb shell partition [Windowsパーティションのサイズ(GB)]`` を実行します。

>  最後にGBを付けず、数字だけ入力してください。

```cmd
adb shell partition
```

#### Android がまだ起動するか確認する
タブレットを再起動し、Androidがまだ動作するかどうかを確認します。
起動しない、ループする、またはアニメーションが表示されない場合は、MIUIリカバリまたはデータを消去するための他のリカバリーを使用します。


### [次の手順: Windowsをインストールする](/guide/Japanese/2-install-ja.md)
