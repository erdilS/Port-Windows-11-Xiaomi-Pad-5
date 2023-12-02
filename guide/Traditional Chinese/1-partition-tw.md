#在POCO X3Pro上运行Windows

##安装

##分区您的设备

###先决条件

-[修改TWRP]（。./../../释放/回收)

-[亚行&Fastboot](https://developer.android.com/studio/releases/platform-tools）

###注意事项
> [!警告]  
>如果您通过diskpart删除任何分区，Windows将发送一个UFS命令，该命令将擦除整个UFS存储！
> 
>您的所有数据将被删除！ 如果需要，现在备份。
> 
>不要运行两次相同的命令。
> 
>如果您认为自己犯了错误，请不要重新启动手机，请在[电报聊天]中寻求帮助（https://t.me/winonvayualt)。
> 
>
>不要一次运行所有命令，按顺序执行！
>
 如果你做错了,你可以用下面的命令打破你的设备!!!

> [!重要]
>确保您在整个教程中使用MODED TWRP恢复，因为我们提供工具来帮助此安装过程，并使其尽可能轻松。
> 
>如果你不使用它，你面临任何错误，认为这是你的错，并认为自己独自一人，如果你试图寻求支持，你已经从主指南推迟。

#####刷新修改后的TWRP恢复
"'cmd
fastboot闪存恢复路径\到\twrp。img
fastboot重启恢复
```

#####运行分区脚本

>如果它要求您再次运行它，请执行此操作

>这是**可选**但您可以使用此脚本**设置自定义大小**

>要设置自定义大小，请执行"'adb shell分区[以GB为单位的目标WINDOWS大小]"`

>确保你没有在最后添加GB，只是数字

"'cmd
adb shell分区
```

####检查Android是否仍然启动
只要重新启动手机，看看Android是否仍然有效

### [下一步：安裝 Windows](/guide/Traditional%20Chinese/2-install-tw.md)
