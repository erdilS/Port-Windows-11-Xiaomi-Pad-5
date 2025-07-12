<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# 在小米平板 5 上安装 Windows

## 重装系统
如果你对当前的 Windows 版本不满意，或者你的 Windows 安装损坏，或者遇到其他问题，你可能会选择重装 Windows。幸运的是，这个过程非常简单。

> [!重要]
> 很明显，这将会清除你所有的 Windows 文件。如果你想备份其中的任何文件，你可以使用 [WOA Helper](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk) 应用挂载 Windows，并手动复制你想保留的文件。

#### 先决条件

- ```现有的 Windows 和启动分区``` (*如果未满足条件，[返回并假装这个指南从未存在过](/guide/Simplified%20Chinese/1-partition-cn.md)*)

- [```恢复镜像```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

#### 重启到 Fastboot 模式
- 重启时按住 **`音量下`** 键以进入 **fastboot** 模式

- 使用数据线把平板连接到电脑

#### 启动恢复镜像以格式化 Windows 和启动分区

```cmd
fastboot boot <recovery.img>
```

#### 格式化分区
> 如果脚本提示“请再次运行”，那么就照它说的再次运行
```cmd
adb shell format
```
## [下一步：安装 Windows](/guide/Simplified%20Chinese/3-install-cn.md#进入-MSC-(大容量存储)-模式)
