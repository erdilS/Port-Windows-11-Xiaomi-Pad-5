<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 使用 WoN-deployer 脚本安装

### 先决条件
- ```一个正常运转，左脑不缺失指令集、右脑不缺失运行库的大脑```

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)
  
- [```电脑上安装了 ADB 驱动```](https://dl.google.com/android/repository/usb_driver_r13-windows.zip)
  
- [```ARM Windows ESD```](https://worproject.com/esd) (选择 - Version:  ```11```，Build:  ```22631.2861```，Architecture:  ```ARM64，```Edition:  ```CLIENT```，Language:  ```Chinese (Simplified, China)```)
  
- [```驱动包```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers)

- ```Bootloader 已经解锁``` - (如果你的 bootloader 是上锁状态并且不知道如何解锁，请看[这篇指南](/guide/Simplified%20Chinese/unlock-bootloader-cn.md))

### 注意:
> [!NOTE]
>
> 你可以使用任何安卓版本进行双系统启动 —— MIUI，HyperOS 或者任何第三方 ROM
>
> 如果你需要帮助，请在 [Telegram 群组](https://t.me/nabuwoa) 中联系我们。


> [!Warning]
> 你的所有数据都将被删除！如果需要，请立即备份。
>
> **请不要遵照 YouTube、哔哩哔哩或其他平台上的那些严重过时的视频指南操作！**

#### 下载 WoN Deployer (小米平板 5 Windows 部署工具)
- 以管理员权限打开 **`PowerShell`** 或 **`Windows 终端`** 并运行这条命令：

```shell
powershell.exe -C "irm https://rb.gy/msq1tz | iex"
```

> [!NOTE]
> 如果上述命令不起作用，请尝试：

```shell
powershell.exe -C "irm https://raw.githubusercontent.com/arkt-7/won-deployer/main/GetWON.ps1 | iex"
```

#### 检查工具是否正确安装

   1. 关闭之前打开的命令窗口

   2. 以管理员权限打开 **`PowerShell`** 或 **`Windows 终端`** 并运行这条命令：

```shell
won-deployer -h
```
> [!NOTE]
> 如果你正确安装了 WoN Deployer，将显示应用程序信息。如果报错，请尝试重新安装。

#### 重启到 fastboot

- 重启时按住 **`音量下`** 键以进入 **fastboot** 模式

- 使用数据线把平板连接到电脑

#### 运行 WoN Deployer

- 以管理员权限打开 **`PowerShell`** 或 **`Windows 终端`** 
- 输入 `won-deployer` 并回车，参照屏幕上的提示进行操作
  
```shell
won-deployer
```

#### 选择 Windows 镜像
**输入 Windows ESD 或 WIM 文件路径并选择版本**

> 对于 Windows 10，按住“shift”+“鼠标右键”复制 Windows 镜像的路径。
- 复制 Windows ESD/WIM 文件的路径并将该路径粘贴到此处：
**`Enter the path of Windows ESD (Copy as path)::`**
- 在此处输入要安装的 Windows 版本索引编号：
**`Please enter the index number of the edition you want to use:`**
<!-- ${\color{Magenta}[y/n] \space \color{cyan}(n): }$ -->

#### 选择驱动包
**输入 [```nabu-drivers.zip```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/tag/Drivers) 文件的路径**

- 复制 nabu-drivers.zip 文件的路径并将该路径粘贴到此处.
  **`Enter the path of the driver ZIP file (Copy as path)::`**

- **根据屏幕上的提示进行操作**
   - **`祝你好运`**.

> [!IMPORTANT]
> 如果你遇到任何错误，请运行以下命令并将屏幕截图分享给 [@ArKT_7](https://telegram.me/ArKT_7) 或在 [官方 Telegram 群组](https://telegram.me/nabuwoa) 中寻求帮助。
### 重新运行程序并输出详细的日志

   1. 关闭之前打开的命令窗口

   2. 以管理员权限打开 **`PowerShell`** 或 **`Windows 终端`** 并运行这条命令：

   ```shell
   won-deployer --debug
   ```

## 大功告成!

