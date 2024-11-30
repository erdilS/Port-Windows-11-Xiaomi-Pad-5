<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 更新驱动程序

### 先决条件
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [修改过的 Recovery image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [UEFI 镜像](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [驱动包](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

### 启动到修改过的 Recovery

> 把 `path\to\recovery.img` 替换为你下载的 recovery 镜像的实际路径。

```cmd
fastboot boot path\to\recovery.img
```

#### 进入 MSC (大容量存储) 模式

> 如果脚本提示“请再次运行”，那么就照它说的再次运行

```cmd
adb shell msc
```

### 进入 Diskpart

```cmd
diskpart
```

#### 选择平板上的 Windows 分区

> 使用 `list volume` 找到 Windows 分区，把下面的 $ 替换为 **WINNABU** 分区的实际编号。

```diskpart
select volume $
```

#### 给其分配 X 盘符

```diskpart
assign letter x
```

#### 退出 diskpart

```diskpart
exit
```

### 安装驱动程序

> [!Note]
> 这个过程将会消耗大概 20 分钟。别急，这个速度很正常。

- 解压驱动包，打开 `OfflineUpdater.cmd`（如果报错，则使用 `OfflineUpdaterFix.cmd`）

> 如果驱动安装程序需要输入盘符，那么就输入 **WINNABU** 的实际盘符（刚才分配的是 **X**），并按下回车

### 重启设备

> 请确保也更新安卓系统中对应的 UEFI 镜像，否则，之后再重启到 Windows 时很可能会直接蓝屏。

```cmd
adb reboot
```

### 大功告成！
