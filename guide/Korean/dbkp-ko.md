<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 듀얼부팅 가이드 (DualbootKernelPatcher)
> There are two methods listed below, the first one requires root, the second one does not. Use whichever method suits you the most, as they both do the same.

### 준비물 (방법 1: 루트 권한 필요)
- [WOA Helper 앱](https://github.com/n00b69/woa-helper/releases/tag/APK)

### 설정 - 안드로이드
- **WOA Helper** 앱을 다운로드 및 설치하시고, 앱을 열고 루트 권한을 허용하세요.
- **WOA 도구** 를 열고, then press the **듀얼부팅 커널 패치** 버튼을 클릭하세요.
- 끝날 떄까지 기다리시고, 장치를 재부팅하세요.

#### 윈도우로 부팅하려면
- **마그네틱 케이스** 를 닫고 장치를 재부팅합니다. (또는 전원을 켭니다)

#### 안드로이드로 부팅하려면
- **마그네틱 케이스** 를 열고 장치를 재부팅합니다. (또는 전원을 켭니다)

## 끝!


### 준비물 (방법 2: 루트 권한 불필요)
- [맞춤화된 리커버리 이미지](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [Magiskboot](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/magiskboot.exe)

- [DualBoot Kernel Patcher](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/DualBootKernelPatcher.zip)

- [.fd 파일](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/nabu.fd)

### 명령 프롬프트를 관리자 권한으로 실행
> 명령 프롬프트를 **관리자 권한** 으로 실행하고, 아래의 명령어를 실행합니다. 이때 `path\to\platform-tools`를 platform-tools 폴더의 실제 경로로 변경하세요. (예시: **C:\platform-tools**)
>
> 창을 닫지 마세요. 전체 가이드를 이용하는 동안 이 창을 계속 유지해야 합니다.
```cmd
cd path\to\platform-tools
```

### 맞춤화된 리커버리로 부팅
> fastboot 모드에서, 경로 `path\to\recovery.img`를 리커버리 이미지의 실제 경로로 변경하세요
```cmd
fastboot boot path\to\recovery.img
```

#### boot 이미지를 백업합니다
> This will back up your boot image in the current directory (for example `C:\platform-tools`).
```cmd
adb pull /dev/block/by-name/boot_a boot.img
```

#### 필요한 파일들을 준비합니다
- **magiskboot.exe** 를 다운로드하고 `platform-tools` 폴더로 파일을 이동하세요.
- **DualBootKernelPatcher.zip** 를 다운로드하고 **DualBootKernelPatcher** 폴더를 `platform-tools` 폴더에 압축 해제하세요.
- **nabu.fd** 를 다운로드하고 `platform-tools` 폴더로 파일을 이동하세요.

### boot 이미지 언팩
> **boot.img** 가 `platform-tools` 폴더에 있는지 확인하세요.
```cmd
./magiskboot unpack boot.img
```

### boot 이미지 패치
```cmd
./DualBootKernelPatcher\bin\Windows\DualBootKernelPatcher-x86_64.exe ./kernel ./nabu.fd ./output ./DualBootKernelPatcher\Config\DualBoot.Sm8150.cfg ./DualBootKernelPatcher\ShellCode\ShellCode.Nabu.bin
```

### 커널 파일 이름 변경
- `platform-tools` 폴더에 있는 **kernel** 파일을 제거하거나 이름을 변경하고, **output** 파일을 `kernel` 로 이름을 변경합니다

### boot 이미지 리팩
> 이 과정을 통해 패치된 boot 이미지를 새로운 파일 **new_boot.img** 로 리팩합니다
```cmd
./magiskboot repack boot.img
```

### fastboot로 재부팅
```cmd
adb reboot bootloader
```

### 패치된 boot 이미지 설치
> `path\to\new_boot.img` 를 이미지의 실제 경로로 변경하세요
```cmd
fastboot flash boot_a path\to\new_boot.img
```
```cmd
fastboot flash boot_b path\to\new_boot.img
```

#### 장치를 재부팅합니다
```cmd
fastboot reboot
```

#### 윈도우로 부팅하려면
- **마그네틱 케이스** 를 닫고 장치를 재부팅합니다. (또는 전원을 켭니다)

#### 안드로이드로 부팅하려면
- **마그네틱 케이스** 를 열고 장치를 재부팅합니다. (또는 전원을 켭니다)

## 끝!

















