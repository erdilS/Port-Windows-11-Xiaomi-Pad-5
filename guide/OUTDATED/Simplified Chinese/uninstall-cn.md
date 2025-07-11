<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 卸载

如果你想卸载 Windows，则可以使用此方法，而不是手动删除分区，以避免操作失误。

如果你想重新锁定 bootloader，则需要保留分区表。

### 先决条件

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)
  
- [```Recovery 镜像```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)

#### 切换到安卓
> 在卸载流程前，请先切换到安卓

#### 重启到 fastboot
- 重启时按住 **`音量下`** 键以进入 **fastboot** 模式

- 使用数据线把平板连接到电脑

#### 启动修改后的 recovery
> 在 platform tools 文件夹中打开一个命令窗口
>
> 将 **path\to\recovery.img** 替换为你下载的 recovery 镜像的实际路径
```cmd
fastboot boot path\to\recovery.img
```

#### 重置分区表
> [!Warning]
> 安卓中的用户数据将被清除。请先备份！
```cmd
adb shell restore
```

#### 重启到安卓
```cmd
adb reboot 
```

> [!NOTE]
> 如果你重启后进入了 MIUI recovery，请执行以下操作：
>
> 1. 选择“清除数据”。
> 2. 选择“清除所有数据”。
> 3. 数据成功清除后，点击“返回主菜单”。
> 4. 点击“重启”。
> 5. 选择“重启到系统”。


## 大功告成!
