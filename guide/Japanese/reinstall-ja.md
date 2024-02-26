<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomiパッド5でWindowsを実行する

## 再インストール
あなたのwindowsのバージョンが気に入らない場合、またはあなたのwindowsのインストール、または何か他のものをレンガした場合は、おそらく単にWindowsを再インス ありがたいことに、このプロセスは非常に簡単です。


### 前提条件

- 既存のWindowsおよびブートパーティション (*満たされていない場合, [戻って、このガイドが存在しなかったふりをするだけです](1-partition-ja.md)*)

- [```Recovery Image```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)


### Windowsとブートパーティションをフォーマットするためのブートリカバリ

```cmd
fastboot boot <recovery.img>
```
### パーティションをフォーマットする
> もう一度実行するように求められた場合は、実行してください
```cmd
adb shell format
```
## [次のステップ：Windowsの再インストール](2-install-ja.md#msc-スクリプトを実行する)
