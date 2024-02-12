<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Running Windows on the Xiaomi Pad 5

## ルートを取得 
> [!NOTE]
> **すでに root を持っている場合は、このステップをスキップして次のページに進んでください。**

### 前提条件
- ```脳```
  
- [```Android ブートのバックアップ```](/guide/English/1-partition-en.md#Make-a-backup-of-your-existing-boot-image) (最初のガイドページでバックアップしたもの)


## パッチブート

- をコピーします ```normal_boot.img``` からのファイル ```platform tools``` タブレットへのフォルダー


- ダウンロードしてインストールします [Magisk app](https://github.com/topjohnwu/Magisk/releases/latest) タブレットに
  
-  Magisk アプリを開き、 ```Install``` ボタン。 選択する ```Select and Patch a File``` オプションを見つけて、 ```normal_boot.img``` タブレットにコピーしたファイル。 クリック ```Let's Go``` ボタンを押して、パッチ適用プロセスが完了するまで待ちます。
  
- をコピーします ```magisk_patched....img``` からのファイル ```Downloads``` タブレット上のフォルダーに ```platform tools``` コンピューター上のフォルダー。
  
- 再起動して、fastboot
  
- コマンドプロンプトを開きます platform tools フォルダ 

 ## フラッシュパッチが適用されたブート
 > 交換する `<magisk_patched.img>` 実際の ```magisk_patched.img``` 名前/パス.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [次のステップ: Windows のインストール](/guide/Japanese/3-install-ja.md)

