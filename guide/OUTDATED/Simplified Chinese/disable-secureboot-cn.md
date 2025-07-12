<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 禁用安全启动
> [!Important]
> 请在操作前确认你是否**真的**想要禁用安全启动。

### 先决条件
- ```大脑```

- [```DriveLetterAssigner```](https://github.com/Misha803/My-Scripts/releases/tag/DriveLetterAssigner)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Recovery 镜像```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```无安全启动的 UEFI 镜像```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/XXXnabu-NoSecureboot-v4.img)

## 安全启动的利弊
> 默认情况下，本指南中启用了安全启动

##### Pros and cons of secureboot
- √ 桌面上没有测试模式水印
- √ 强制要求安全启动的软件和游戏可以运行
- √ 可以在 Windows Update 中直接升级大版本（如 22H2 到 23H2）
- × 不能安装未签名的驱动

##### 禁用安全启动
- √ 可以安装未签名的驱动
- × 桌面上没有测试模式水印
- × 有一些软件和带反作弊的游戏需要安全启动，禁用后将不能运行
- × 不能在 Windows Update 中升级大版本

## 禁用安全启动

#### 提取 root 后的 boot 镜像
> 需要提取 boot 镜像才能从 Windows 重启到安卓，但如果在先前的指南中已经进行了此步，则可以跳过

在 WOA Helper 中可以提取 boot 镜像。也可以启动修改后的 recovery 镜像然后运行下面的命令：
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### 启动修改后的 recovery
> 将 **path\to\recovery.img** 替换为你下载的 recovery 镜像的实际路径
```cmd
fastboot boot <path\to\recovery.img>
```

#### 让平板进入 MSC (大容量存储) 模式

> 在启动 recovery 之后
```cmd
adb shell msc
```

#### 给 WINNABU 和 ESPNABU 分配盘符

> 打开 **DriveLetterAssigner V2.0** 脚本，之后在提示窗口按下键盘 Y 键，之后脚本将给 **ESPNABU** 分配 **Y** 盘符

#### 修改引导文件
> 启用测试签名
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### 移除 SiPolicy
> 要禁用安全启动则必须删除这个文件，否则平板将无法开机
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

#### 移除 ESPNABU 的盘符
> 如果不起作用，请跳过这条命令。下次重新启动电脑时，ESPNABU 的盘符将会自己消失。
```cmd
mountvol y: /d
```

#### 重启到 fastboot
```cmd
adb reboot bootloader
```

#### 刷入无安全启动的 UEFI
> 确保使用从本页下载的无安全启动 UEFI。将 <path\to\uefi-NoSecureboot-v3.img> 替换为 UEFI 镜像的实际路径。
```cmd
fastboot flash boot <path\to\uefi-NoSecureboot-v3.img>
```

> [!Important]
> 确保同时替换安卓内部存储中 UEFI 文件夹中的旧 UEFI，这样下次尝试从安卓切换到 Windows 时，这个禁用安全启动的 UEFI 就不会被误覆盖。

#### Reboot to Windows
```cmd
fastboot reboot
```

## 大功告成!

















