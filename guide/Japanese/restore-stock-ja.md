<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomiパッド5でWindowsを実行する

## アンインストール

### なぜこれが必要なのですか？

あなたがwindowsをアンインストールしたい場合、これは人為的なエラーを避けるために手動でパーティションを削除する代わりに使用されます+ただアンイ

ブートローダを再ロックしたい場合は、パーティションテーブルを在庫にする必要があります。

### 前提条件 

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [gpt_both0.bin](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin)

### GPTを復元する
> 置換 ```<gpt_both0.bin>``` へのパスを持つ gpt_both0.bin ファイル。

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Bootloopを回避し、FSサイズを復元するためにuserdataを消去します
```cmd
fastboot -w
```
