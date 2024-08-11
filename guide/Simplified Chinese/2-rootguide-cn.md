<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在小米平板 5 上安装 Windows

## root 你的平板
> [!NOTE]
> **如果你的平板已经 root 了，那么请跳过这步，前往下一页**

#### 先决条件
- ```大脑```
  
- 在上一页中备份出来的 [```安卓 boot 分区镜像```](/guide/Simplified%20Chinese/1-partition-cn.md#备份当前的-boot-分区) 

#### 给 boot 镜像打补丁

- 从 `platform tools` 文件夹找到 `normal_boot.img` 并将其发送到平板上

- 在平板上下载并安装 [Magisk](https://github.com/topjohnwu/Magisk/releases/latest) app
  
-  打开 Magisk app 并点击“安装”。点击“选择并修补一个文件”，并选择刚才传到平板上的 `normal_boot.img`。点击开始修补，并等待修补完成
  
- 将平板 `Downloads` 文件夹中以 `magisk_patched` 开头的 img 镜像文件传回到电脑上的 `platform tools` 文件夹中

#### 重启到 fastboot

- 在重启时按住音量减，把你的平板重启到 fastboot 模式

- 使用数据线把平板连接到电脑

- 返回到先前打开的命令窗口

#### 刷入修补后的 boot 镜像
> 将 `magisk_patched.img` 替换为实际的修补后的镜像文件名 / 路径。
```cmd
fastboot flash boot magisk_patched.img
```

#### 重启到安卓
```cmd
fastboot reboot
```

#### 完成安装

- 再次打开 Magisk app
- Magisk 会提示需要进行一些额外步骤，跟着提示走，平板将再次自动重启

#### 提取 root 后的 boot 镜像
> 在平板重启完毕后

- 如果平板的屏幕上出现超级用户权限申请，那么就允许权限。
```cmd
adb shell "su -c cp dev/block/by-name/boot /sdcard/root.img" & adb pull /sdcard/root.img
```

### [下一步：刷入 Windows](/guide/Simplified%20Chinese/3-install-cn.md)











