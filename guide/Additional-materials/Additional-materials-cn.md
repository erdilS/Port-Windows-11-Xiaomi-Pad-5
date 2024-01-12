<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# 小米pad5上Windows的有用应用程序和说明

## 安装Microsoft Office

- 下载这个 [档案](https://mega.nz/file/Q7p1XK6L#J-KPp_-MNJ8iXGqEwwZ3_sfv2tMiq_AJjUiiaX6TBrI) 到平板电脑
  
- 关闭Windows Defender以避免对安装造成任何干扰
  
- 右键单击iso文件并选择Mount以在资源管理器中打开它

- 双击自动运行。exe启动安装向导
  
- 选择要安装的语言和组件，然后单击开始安装
  
- 等待安装和激活完成

- 再次打开Windows Defender

- 享受使用Office！

 ## 激活Windows

> 打开PowerShell并键入: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> 出现窗口时，选择1

 ## 如何使用手电筒

 - 下载 [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) 并解压缩到任何文件夹

> 运行手电筒。exe启用手电筒

> 按任意键禁用它

## 启用充电和USB主机模式

> [!WARNING]
>  确保在Mi Pad5本身上完成任何注册表编辑

> [!NOTE]
> 使用PD支持的设备进行C到C充电已确认工作，小米提供的33w充电器也已确认工作

- 下载 [来自Misha803的剧本](https://t.me/droidscripts/52) 轻松启用它
 
- 或者使用传统方法-在注册表编辑器中，更改参数的值 ```RoleSwitchMode``` 从 ```3``` 到 ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

