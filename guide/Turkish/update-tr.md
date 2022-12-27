#### Recovery modunu bilgisayar aracılığıyla başlatın

```cmd
fastboot boot <recovery.img>
```

## msc betiğini cihaza kopyalayın

```cmd
adb push msc.sh /sbin/
```

### Betiği çalıştırın

```cmd
adb shell sh /sbin/msc.sh
```
> Bu aşamadan sonra tabletinizdeki tüm bölümler bilgisayarınızda taşınabilir sabit disk olarak görünecektir. İlk aşamada uyarıldığı gibi diskpart üzerinden silme işlemi yapmamaya dikkat edin.

## Disklere harfleri atayın

#### Diskpart'ı başlatın

```cmd
diskpart
```


### Windows bölümüne `X` harfini atayın

#### Tabletinizdeki Windows bölümünü seçin
> Bunu bulmak için `list volume` komutunu kullanabilirsiniz, "WINNABU" etiketini içeren bölümün numarasını komutta kullanın. Genellikle sondan bir önceki bölüm olur.

```diskpart
select volume <number>
```

#### X harfini atayın
```diskpart
assign letter=x
```

### diskpart arayüzünden çıkın.
```diskpart
exit
```


# Sürücüleri yükleyin

> Replace `<nabusurucuklasoru>` with the location of the drivers folder

> Komut istemini yönetici olarak başlatın.

```cmd
driverupdater.exe -d <nabusurucuklasoru>\definitions\Desktop\ARM64\Internal\nabu.txt -r <nabusurucuklasoru> -p X:
```


##### UEFI imajını yükleyerek Windows'u başlatın #####

```
fastboot flash boot <uefi.img>
```


# İşlem tamamlandı!
