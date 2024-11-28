<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 配置双系统

### 先决条件
- `大脑`

- `Root 后的平板`

- `平板上已经刷入 Windows`

- [```UEFI 镜像```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```WoA Helper app```](https://github.com/n00b69/woa-helper/releases/tag/APK)

## 配置双系统
本指南需要 root 权限。如果尚未 root，请先按照 [本指南之前的步骤](2-rootguide-en.md) 进行操作。

### 安卓侧的配置
- 下载并安装 **WOA Helper** app，打开并授予超级用户权限。
- 下载 **UEFI 镜像**，将其置于平板内部存储中名为 `UEFI` 的文件夹（如果没有，就自行建立）。
- 再次打开 WOA Helper，在 **WOA TOOLBOX** （WOA 工具箱）中运行 **STA CREATOR**（创建安卓切换工具）。
> [!Important]
> 如果 `/sdcard/Windows` 文件夹是空的，或 WOA Helper 提示无法挂载 Windows 分区，那么你的 ROM 不支持挂载 NTFS 分区。你需要自己把内部存储中的 STA 工具复制到其他设备（比如 U 盘或电脑），之后再启动到 Windows，然后把它传回平板里。
>
> 如果这个文件夹为只读，那么也需要这样操作。
- 点击 WOA Helper 中的 **QUICKBOOT TO WINDOWS**（快速启动到 Windows）按钮，稍后将重启到 Windows。

### Windows 侧的配置
> [!Tip]
> 如果这是你第一次启动 Windows，并且希望跳过微软帐户登录，在 WiFi 页面按下 **“我没有 Internet 连接”** 按钮，然后在出现提示时，按下 **“继续使用有限设置”** 按钮。
>
> 在新版 Windows 11 中如果“我没有 Internet 连接”按钮没有出现，那么按下键盘 Shift+F10，输入 `oobe\bypassnro.cmd` 并回车，重启后此按钮将出现。

#### 从 Windows 启动到安卓

- 运行桌面上的切换工具快捷方式（你也可以将其固定到开始菜单或任务栏以便于访问）。

#### 从安卓启动到 Windows

- 在 WOA Helper 内按下 **“快速启动到Windows”**，或者也可以使用安卓操作中心的系统切换按钮。

## 大功告成!

















