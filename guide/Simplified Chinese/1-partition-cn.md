<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 安装

### 先决条件
- ```Bootloader 已经解锁``` - (如果你的 bootloader 是上锁状态并且不知道如何解锁，请看[这篇指南](unlock-bootloader.md))

-  ```大脑```
  
- [```Recovery 镜像```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

### 注意:
>[!NOTE]
> 你可以使用任何安卓版本进行双系统启动 —— MIUI，HyperOS 或者任何第三方 ROM

> [!Warning]
> 你的所有数据都将被删除！如果需要，请立即备份。
> 
> 如果你认为自己犯了错误，不要重新启动你的平板，请在 [Telegram 群组](https://t.me/nabuwoa) 中寻求帮助。
>
> **请不要遵照 YouTube、哔哩哔哩或其他平台上的那些严重过时的视频指南操作！使用过时的安装方法可能导致你的设备出现问题，甚至变砖。如果你实在是需要看着视频操作，请看这份由 [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) 制作的 [视频指南](https://youtu.be/BbgTbTGbXYg)**。

### 给 Windows 分区并备份 boot 分区
> [!NOTE]
> 不知道从何开始? 首先解压下载好的 [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)，之后以管理员权限打开 ```命令提示符``` 或 ```PowerShell```，并运行提到的命令。注意把其中的 `"path\to\platform-tools"`  替换为你自己解压 platform tools 的实际路径。
```cmd
cd "path\to\platform-tools"
```
> 在整个安装过程中，一直都需要使用这个命令窗口。不要关掉它。

#### 重启到 fastboot
- 在重启时按住音量减，把你的平板重启到 fastboot 模式

- 使用数据线把平板连接到电脑

#### 启动修改后的 recovery
> 将 **path\to\recovery.img** 替换为你下载的 recovery 镜像的实际路径
```cmd
fastboot boot path\to\recovery.img
```

#### 给平板进行分区
> 将 **$** 替换为你想给 Windows 分配的存储大小，单位为 GB。（不要把 GB 二字打上去，只写数字即可）
> 
> 如果脚本提示“请再次运行”，那么就照它说的再次运行
```sh
adb shell partition $
```

#### 备份当前的 boot 分区
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### 检查安卓是否仍能正常启动
> 重启以检查安卓是否仍能正常启动。如果无法启动，请在原厂 recovery 中清除所有数据，并再次尝试。

```cmd
adb reboot
```


### [下一步：获取 root 权限](/guide/Simplified Chinese/2-rootguide-cn.md)
