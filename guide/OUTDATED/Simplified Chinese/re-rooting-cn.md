<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## 重新 root 安卓系统
在 MIUI / HyperOS 系统更新后，root 将被去除。本指南将引导你重新取得 root 权限。

### 先决条件
- [```Recovery 镜像```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

#### 重启到 fastboot

- 重启时按住 **`音量下`** 键以进入 **fastboot** 模式

- 使用数据线把平板连接到电脑

#### 启动修改后的 recovery
> 将 **path\to\recovery.img** 替换为你下载的 recovery 镜像的实际路径
```cmd
fastboot boot path\to\recovery.img
```

#### 备份当前的 boot 分区
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```

#### 重启到安卓
```cmd
adb reboot
```

#### 修补 boot 镜像
- 从 `platform tools` 文件夹找到 `normal_boot.img` 并将其发送到平板上

- 在平板上下载并安装 [Magisk](https://github.com/topjohnwu/Magisk/releases/latest) app
  
-  打开 Magisk app 并点击“安装”。点击“选择并修补一个文件”，并选择刚才传到平板上的 `normal_boot.img`。点击开始修补，并等待修补完成
  
- 将平板 `Downloads` 文件夹中以 `magisk_patched` 开头的 img 镜像文件传回到电脑上的 `platform tools` 文件夹中
- 重启到 fastboot
- 在刚才的 platform tools 文件夹中打开命令窗口

#### 刷入修补后的 boot 镜像
> 将 `magisk_patched.img` 替换为实际的修补后的镜像文件名 / 路径。
```cmd
fastboot flash boot magisk_patched.img
```

#### 更新 Windows C 盘中的 boot.img
- 重启到安卓
- 在 WOA Helper 中挂载 Windows
- 在文件管理器中进入内部存储的 Windows 文件夹
- 删除之前的 ```boot.img```

> [!NOTE]
> **下次重新启动时，更新后的 boot.img 将在 C 盘中自动生成**

## 大功告成!















