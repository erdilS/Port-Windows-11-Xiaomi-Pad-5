<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 在 Xiaomi Pad 5 上安装 Windows

## 恢复原厂分区表并删除 Windows

### 在什么时候需要这样做 ?

如果您想要删除 Windows, 请参考本篇而不是手动尝试恢复分区表, 这样可以避免人为错误, *本篇仅用于删除 Windows*
> 如果您需要重新锁定 Bootloader, 您的磁盘分区必须为原厂状态, 且需要回到原厂固件

### 需要的文件
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)

### 还原 GPT 分区表
> 使用 gpt_both0.bin 路径取代下面命令里的 ```<gpt_both0.bin>```。
```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### 格式化 Userdata 分区以避免在启动画面卡住, 并还原 FS 大小
```cmd
fastboot -w
```