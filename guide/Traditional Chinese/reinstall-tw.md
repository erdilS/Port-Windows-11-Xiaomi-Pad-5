<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# 在 Xiaomi Pad 5 上執行 Windows

## 重新安裝

### 若發生錯誤，您可重新安裝 Windows

- 如果您不喜歡您的 Windows 版本，或者您的平板電腦在 Windows 安裝時變磚，或者其他的原因，您可能會直接重新安裝 Windows。，這個程序非常簡單。

- 如果您尚未還原您的磁碟分割表格，您可以使用現有的分割區來使用本指南。

### 先決條件

- 包含 Windows 和 Boot 分割區 (*若不符合要求，[回到過去，就當這個指南不存在吧](/guide/Traditional%20Chinese/1-partition-tw.md)*)

- [Recovery 映像](../../../../releases/tag/1.0)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [大型存放模式指令碼](../../../../releases/tag/1.0)

### 開機至 Recovery 以格式化 Windows 和 Boot 分割區

```cmd
fastboot boot <recovery.img>
```
### 格式化分割區

```cmd
adb shell format
```

#### 執行 msc 指令碼

```cmd
adb shell msc
```

### 指派代號至磁碟…再做一次
  

#### 啟動 Windows 磁碟管理員

> 一旦 Xiaomi Pad 5 被偵測為一個磁碟

```cmd
diskpart
```

- 「WINNABU」分割區應該已經顯示為字母 X。若這樣，跳轉至 `指派 Y 至 ESP 磁碟區`

#### 指派 `X` 至 Windows 磁碟區

#### 選取平板電腦的 Windows 磁碟區
> 使用 `list volume` 以找到它，其名為「WINNABU」

```diskpart
select volume <number>
```

#### 指派代號 X
```diskpart
assign letter=x
```

### 指派 `Y` 至 ESP 磁碟區

#### 選取平板電腦的 ESP 磁碟區
> 使用 `list volume` 以找到它，其名為「ESPNABU」

```diskpart
select volume <number>
```

#### 指派代號 Y

```diskpart
assign letter=y
```

- 如果您遇到錯誤「指定的磁碟機代號已在使用中，因此無法指定」，僅需重新啟動您的電腦並從 Diskpart 再試一次。先不要觸碰您的平板電腦。

#### 離開 Diskpart
```diskpart
exit
```


### 安裝

- 繼續來自[這裡](/guide/Traditional%20Chinese/2-install-tw.md#install)的指南
