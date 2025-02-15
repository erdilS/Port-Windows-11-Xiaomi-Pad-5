<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 故障排除

## 在安卓中，我无法向 Windows 文件夹中移动文件

如果你无法将文件移动到 Windows 文件夹，这意味着你启用了 Windows 的快速启动功能，并且是关机而不是重启了 Windows。要解决这个问题，重新启动 Windows，然后使用“重启”选项。在重启时进入 fastboot 模式，并刷入安卓 boot 镜像以回到安卓。

##### 完成！

## Windows 中无法充电
> [!WARNING]
> 在启用 USB 主机模式期间，不要使用带供电的 USB Hub，这可能会烧坏平板的尾插。如果你使用带供电的 USB Hub，请参考 [禁用 USB 主机模式指南](/guide/Simplified%20Chinese/Additional-materials-cn.md#禁用-USB-主机模式)。

在 Windows 中，充电仅在特定的数据线上有效。已知可用的数据线包括小米原装充电线（USB-A 公头中有额外的橙色/红色引脚）和 Nimaso 100W USB-C 到 USB-C 快速充电电缆。

##### 完成！

## 我的电脑无法检测到 Fastboot 模式下的米板 5，我该怎么办？
- 下载 [**`QUD.zip`**](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip) 并解压。
- 打开设备管理器，找到一个未知设备或可能被称为 Android 或 QUSB_BULK 的有错误的设备。
- 右键点击它，选择 **```更新驱动程序```** → **`浏览文件`**，然后选择你之前解压的 QUD 文件夹。

##### 完成！

## 设备可以启动到安卓，但无法进入 bootloader

### 先决条件：
- [Android 平台工具](https://developer.android.com/studio/releases/platform-tools)

- [SHRP 恢复镜像](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/SHRP.img)

> [!IMPORTANT]
> 这只有在你已经获得 root 权限的情况下才有效。如果没有，唯一的恢复方法是使用 [MrAuthTool](https://mrauthtool.com/) 通过 EDL (9008) 深刷。

- 从内部存储的 **UEFI** 文件夹中删除 **UEFI** 镜像，然后将 **SHRP 恢复镜像** 放入此处。
- 在 WOA Helper 应用中按下 `QUICKBOOT TO WINDOWS`。
- 启动到恢复模式后，将设备连接到 PC，并运行以下命令：
```cmd
adb shell parted /dev/block/sda
```
- 运行 ```print``` 列出所有分区。
- 查找名称超过 16 个字符的分区，例如 "Basic Data Partition"，并记录它们的卷编号。
- 使用 ```name $ test``` 重命名此分区，将 **$** 替换为分区编号，将 **test** 替换为你想要的分区名称。
- 运行 ```quit``` 退出。
- 运行 ```adb reboot bootloader```，当你在屏幕上看到 **FASTBOOT** 标志时，使用 ```fastboot flash boot_a path\to\boot.img``` 刷写你的安卓启动镜像。
- 如果设备无法启动，或者进入了 recovery，你可能需要对 **boot_b** 执行相同操作。

> [!NOTE]
> 请确保再次将 UEFI 文件夹中的恢复镜像替换为 UEFI 文件。

##### 完成！

## 启动 Windows 时出现 fsa4480.sys 蓝屏报错
- 打开驱动程序文件夹。

- 从 NABU.xml 中删除 ```<DriverPackageFile Path="$(mspackageroot)\components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB" Name="fsa4480.inf" ID="fsa4480"/>``` 这一行。

- 重新安装驱动程序。

- 启动 UEFI。
> [!NOTE]
> 如果你仍然遇到蓝屏死机，请按照 `重新安装` 指南并使用指南随附的驱动包。

##### 完成！

## 尝试切换到安卓时进入重启死循环
- 启动到 Fastboot 模式。

- 运行 ```fastboot set_active other```。

- 运行 ```fastboot flash boot <boot.img>```。

- 运行 ```fastboot reboot```。

##### 完成！















