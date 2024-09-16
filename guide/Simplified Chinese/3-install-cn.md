<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows
> [!WARNING]
> **请不要遵照 YouTube、哔哩哔哩或其他平台上的那些严重过时的视频指南操作！使用过时的安装方法可能导致你的设备出现问题，甚至变砖。如果你实在是需要看着视频操作，请看这份由 [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) 制作的 [视频指南](https://youtu.be/BbgTbTGbXYg)**。

## 刷入 Windows

#### 先决条件

- ```大脑```
- [```DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)
- [```ARM Windows ESD```](https://arkt-7.github.io/woawin/)
- [```驱动包```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

#### 启动修改后的 recovery
> 将 **path\to\recovery.img** 替换为你下载的 recovery 镜像的实际路径
```cmd
fastboot boot path\to\recovery.img
```

#### 进入 MSC (大容量存储) 模式
> 如果脚本提示“请再次运行”，那么就照它说的再次运行
```cmd
adb shell msc
```

#### 给 WINNABU 和 ESPNABU 分配盘符
> 打开 **DriveLetterAssigner** 脚本，之后在提示窗口按下键盘 Y 键，之后脚本将给 **WINNABU** 和 **ESPNABU** 分别分配 **X** 和 **Y** 盘符

#### 刷入 Windows
> [!Important]
> 确保你的命令提示符 / PowerShell 为 **管理员** 权限

> 将 `path\to\install.esd` 替换为你实际下载的 ESD 镜像，文件名可能为 22631.2861.XXXXXXX.esd

```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

> 如果报错 `Error 87`，使用 `dism /get-imageinfo /ImageFile:path\to\install.esd` 命令查看镜像中的系统索引编号，之后把命令中的 6 号替换为你下载的镜像中 **Windows 11 专业版** 的实际索引编号

#### 将 boot 镜像复制到 Windows 中

- 将 **root.img** 从 **platform-tools** 文件夹拖放到 Windows 资源管理器中的 **WINNABU** 磁盘中，然后将其重命名为 **boot.img**。

#### 安装驱动
- 解压驱动包，打开 `OfflineUpdater.cmd`（如果报错，则使用 `OfflineUpdaterFix.cmd`）

> 如果驱动安装程序需要输入盘符，那么就输入 **WINNABU** 的实际盘符（刚才分配的是 **X**），并按下回车

#### 创建 Windows 引导器文件

> 如果复制引导文件时出现错误，请再次运行 **DriveLetterAssigner**，然后再次运行以下命令，将 **Y** 替换为 **U**
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

#### 移除 ESPNABU 的盘符
> 如果不起作用，请跳过这条命令。下次重新启动电脑时，ESPNABU 的盘符将会自己消失。
```cmd
mountvol y: /d
```


#### 重启到安卓
在安装完成后，长按电源键重启回到安卓。

## [最后一步: 配置双系统](/guide/Simplified%20Chinese/4-dualboot-cn.md)



















