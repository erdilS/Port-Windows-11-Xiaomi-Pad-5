<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동

## secureboot 비활성화
> [!Important]
> secureboot를 비활성화하려는 경우에만 이 가이드를 이용하십시오.

### 준비물
- ```뇌```

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Secureboot가 비활성화된 UEFI 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-NoSecureboot-v3.img)

## secureboot의 장단점
> 기본적으로, 이 가이드에서 secureboot는 활성화되어 있습니다

##### secureboot의 장단점
- √ 홈화면에 워터마크가 없습니다
- √ 테스트 모드에서 작동하지 않는 앱이 작동합니다
- √ 윈도우에서의 대규모 업데이트가 직접적으로 가능합니다 (예: 22h2 에서 23h2)
- × PC 없이 드라이버 업데이트가 불가능합니다

##### 비활성화된 secureboot의 장단점
- √ 태블릿에서 직접적으로 드라이버 업데이트가 가능합니다; PC가 필요하지 않습니다
- × 홈화면에 테스트 모드 워터마크가 있습니다
- × 몇몇 안티 치트 소프트웨어를 탑재한 앱/게임이 실행되지 않을 수 있습니다
- × 윈도우 업데이트를 통한 대규모 업데이트가 불가능합니다 (예: 22h2 에서 23h2)

## secureboot 비활성화

#### 루팅 boot 이미지를 백업합니다
> 안드로이드로 돌아오기 위해 이 파일이 필요하지만, 이미 백업했다면 이 단계를 건너뛸 수 있습니다

WOA Helper 앱에서 `Backup Android boot` 기능을 사용하거나, 커스텀 리커버리로 부팅하여 아래의 명령어를 입력하십시오
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/rooted_boot.img" && adb pull /tmp/rooted_boot.img
```

#### 리커버리로 부팅합니다다
> <path\to\recovery.img>를 실제 리커버리 이미지 파일의 경로로 변경하십시오
```cmd
fastboot boot <path\to\recovery.img>
```

#### mass storage 모드를 활성화합니다
> 샤오미 패드 5가 커스텀 리커버리로 부팅되면 아래의 명령어를 입력하십시오
```cmd
adb shell msc
```

#### 윈도우 디스크 관리자를 시작합니다
> 샤오미 패드 5가 디스크로 인식되면 아래의 명령어를 입력하십시오
```cmd
diskpart
```

#### 태블릿의 esp 볼륨을 선택합니다
> `list volume` 명령어를 사용하여 볼륨을 찾으십시오. 볼륨의 이름은 "ESPNABU" 입니다.
```diskpart
select volume <number>
```

#### 문자 Y를 할당합니다
```diskpart
assign letter y
```

#### diskpart를 종료합니다
```diskpart
exit
```

#### 부트로더 파일을 수정합니다
> test signing을 활성화합니다
```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set "{default}" testsigning on
```

#### SiPolicy을 제거합니다
> 기존 설치에서 secureboot를 비활성화하는 경우, 이 파일을 삭제해야 합니다. 그렇지 않으면 시스템이 부팅되지 않습니다.
```cmd
del Y:\EFI\Microsoft\Boot\SiPolicy.p7b
```

## ESPNABU에 대한 드라이브 문자 제거
> 이 명령어가 작동하지 않더라도, 무시하고 다음에 입력할 명령어로 건너뛰십시오. 이 드라이브는 PC를 재부팅하면 자동으로 제거됩니다.
```cmd
mountvol y: /d
```

#### fastboot로 재부팅합니다
```cmd
adb reboot bootloader
```

#### UEFI를 플래시 합니다
> 이 페이지에서 secureboot 비활성화 UEFI를 사용하고 있는지 확인하시고, <path\to\uefi-NoSecureboot-v3.img>를 실제 UEFI 이미지 파일의 경로로 변경하십시오
```cmd
fastboot flash boot <path\to\uefi-NoSecureboot-v3.img>
```

> [!Important]
> 안드로이드 내부 저장소의 UEFI 폴더 내의 구버전 UEFI도 교체했는지 확인하십시오. 그러면 다음번에 안드로이드에서 윈도우르 전환하려고 할 때 실수로 구버전 UEFI를 플래시 하지 않게 됩니다

#### 윈도우로 재부팅합니다
```cmd
fastboot reboot
```

## 끝!



















