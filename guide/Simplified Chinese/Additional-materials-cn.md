<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 适用于小米平板 5 Windows 的有用应用程序和说明

### 软件 / 游戏支持列表
[这个列表](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)记录了社区测试的软件 / 游戏在小米平板 5 Windows 的支持情况，覆盖面可能不会那么全面。

你也可以在 [这里](https://armrepo.ver.lt/) 找到一些 Windows on ARM 专版的软件。

## 隐藏 D 盘盘符 (基带分区)
> [!NOTE]
> 极为推荐进行这个操作，因为基带分区被错误挂载到了 D 盘，其中的内容绝不应该被修改，而某些软件可能会尝试写入 D 盘。

- 在平板上下载 [`ModemHide.vbs`](https://github.com/Misha803/My-Scripts/releases/tag/ModemHide) 
- 运行它
- 同意可能出现的 UAC 对话框 
- 在对话框中点击 `是`


#### 大功告成!


## 禁用 USB 主机模式
> [!Warning]
> 未通电的 USB 设备将停止工作

> [!Important]
> 以下步骤必须在运行着 Windows 的米板 5 上操作，而不是在你的电脑上操作。

下载并运行 [USB Host Mode Control](https://github.com/Misha803/My-Scripts/releases/tag/USB-Host-Mode-Control) 以启用 / 禁用 USB 主机模式。启用时米板 5 的 Type-C 接口将自主供电，适用于插入 U 盘和手机等。使用外接电源的 USB Hub 时请务必禁用 USB 主机模式，否则会烧坏尾插。

#### 大功告成!

## 我可以使用 Windows Update 或 ISO 镜像更新我的 Windows 吗？
- ✅ **可以！** 你可以安装 Windows Update 中出现的任何更新，也可以使用 ISO 镜像更新系统。

## 刷入 Windows 后可以更新安卓系统吗？
- ✅ **可以！** 你仍然可以更新安卓系统，只需要在更新之后 [重新 Root 你的平板](re-rooting-cn.md) 即可。

## 禁用安全启动
> [!Warning]
> 仅在必要时才这样做！

> [**`禁用安全启动指南`**](/guide/Simplified Chinese/disable-secureboot-cn.md)


## 安装 Microsoft Office / Microsoft 365
- 下载此 [ISO 文件](https://drive.google.com/file/d/10FTyC0XBccj0BkxdIa_W_haixQz-d3to/view?usp=drivesdk) 到平板电脑上。
- 右键点击ISO文件并选择“挂载”以在资源管理器中打开它。
- 双击 ```Office Tool Plus.exe``` 启动安装向导。
- 通过任何用户账户控制（UAC）对话框。
- 在出现的窗口中，点击 `是` 以开始安装。
- 等待安装完成。

#### 大功告成!


## 激活 Windows / Office
使用[Massgravel 的激活脚本](https://github.com/massgravel/Microsoft-Activation-Scripts)。

#### 大功告成!


## ~~如何使用闪光灯~~
 - 下载 [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) 并解压到任意文件夹
> 运行 flashlight.exe 点亮闪光灯
> 按任意键将其禁用

#### 大功告成!

## 给 Windows 恢复出厂设置
> [!Warning]
> 完成这些步骤后，Windows 中的所有数据都将被删除，包括文件、设置和应用程序。

- 打开“设置”应用程序。
- 点击“系统”。
- 点击“恢复”选项卡。
- 在“**恢复选项**”部分下，单击“**重置此电脑**”设置中的“重置电脑”按钮。
- 单击“删除所有内容”选项。
- 选择“本地重新安装”选项。
- 单击“下一步”按钮。
- 单击“重置”按钮。
> 重新启动后，您将得到一个干净的 Windows。


#### 大功告成!


## 禁用自动亮度

- 按 **`Win + I`** 打开 Windows 11 设置，或右键点击“开始”按钮并选择“设置”。

- 从左侧边栏导航到 **`系统`** 部分。

- 在系统设置中选择 **`显示`**。

- 在 **`亮度`** 部分，你会看到两个选项：

**```1. 当光线变化时自动调整亮度：```**

> 通过切换开关到 **`关闭`** 位置来关闭此选项。

**```2. 根据内容调整亮度：```**

> 从下拉菜单中选择 **`关闭`** 以关闭此选项。

>[!注意]
> 进行这些更改后，设备上的自适应亮度和内容自适应亮度将被禁用。

 #### 大功告成!













