<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Cài đặt Windows 11 lên Xiaomi Mi Pad 5

## Hướng dẫn cài lại

### Hướng dẫn cài lại nếu lỡ không may có gì đó sai sai

- Nếu bạn không thích bản Windows này hoặc bị brick Windows Install, hoặc trời trăng mây biển gì khác, bạn sẽ cần tới việc này: Cài lại Windows. Ôi trời đất ơi, rất may là cái này dễeeeee ơi là dễ

- Nếu bạn chưa restore lại phân vùng của máy, bạn sẽ cần đến hướng dẫn này với phân vùng đã tồn tại.

### Điều kiện tiên quyết

- Đã có Windows và phân vùng boot (*Lỡ xui không có thì [quay lại và coi như hướng dẫn này chưa từng tồn tại nha](/guide/Vietnamese/1-partition-vi.md)*)

- [Recovery Image](../../../../releases/tag/1.0)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)


### Boot vào recovery để định dạng lại Windows và phân vùng boot

```cmd
fastboot boot <recovery.img>
```
### Định dạng phân vùng

```cmd
adb shell format
```


#### Thực thi msc script

```cmd
adb shell msc
```

### Gán lại kí tự cho ổ đĩa... một lần nữa dùm em nha
  

#### Khởi động Windows disk manager

> Rồi đó, Xiaomi Pad 5 sẽ xuất hiện ở đây một lần

```cmd
diskpart
```

- Phân vùng "WINNABU" sẽ được gán với kí tự X. Nếu có rồi, bỏ qua tới `Gán "Y" đến ESP volume`

#### Gán `X` cho ổ Windows

#### Chọn Windows volume của máy tính bảng
> Dùng `list volume` để kiếm, nó sẽ được đặt tên là "WINNABU"

```diskpart
select volume <số>
```

#### Gán kí tự X
```diskpart
assign letter=x
```

### Gán `Y` cho ổ ESP 

#### Chọn ổ esp của máy tính bảng
> Dùng lệnh `list volume` để kiếm, nó được đặt tên là  "ESPNABU"

```diskpart
select volume <number>
```

#### Gán kí tự Y

```diskpart
assign letter=y
```

- Nếu gặp lỗi `The specified drive letter is not free to be assigned`, hãy khởi động lại máy tính và thử lại từ đoạn diskpart ở trên, tuyệt đối không đụng vô máy tính bảng

#### Thoát diskpart
```diskpart
exit
```


### Cài đặt

- Tiếp tục hướng dẫn [ở đây](/guide/Vietnamese/2-install-vi.md#install)
