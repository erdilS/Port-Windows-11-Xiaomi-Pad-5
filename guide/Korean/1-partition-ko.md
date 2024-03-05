<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Xiaomi Pad 5 에서 윈도우 구동

## 설치



### 준비물
-  ```뇌```
  
- [```리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

### 메모:
> [!NOTE]
> 어디서부터 시작해야 할지 잘 모르십니까? 다운로드된 [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools) 을 원하는 경로에 압축해제 하십시오. 경로의 예시는 다음과 같습니다. ```"C:\platform-tools"``` 그런 다음 ```명령 프롬프트``` 또는 `Windows Powershell` 을 관리자 권한으로 열고 아래의 명령어를 입력하십시오:
```cmd
cd "path\to\platform-tools"
```
> 경로  `"path\to\platform-tools"` 를 플랫폼 도구 폴더의 실제 경로로 변경하십시오


> [!Warning]\
> 만약 지금 또는 나중에 diskpart 를 통해 파티션을 삭제한다면, windows 가 잘못된 ufs 명령어를 전송할 것이며 이것은 모든 ufs 데이터를 삭제시킬 것입니다
> 
> 모든 데이터가 초기화됩니다! 필요하다면 지금 백업하십시오.
> 
> 가이드에서 사용되는 명령어들은 모두 테스트되었습니다.
> 
> 만약 실수한 것 같다면 태블릿을 재부팅하지 마시고, [Telegram chat](https://t.me/nabuwoa) 에 도움을 요청하십시오
>
> **유튜브 또는 다른 플랫폼에 있는 최신 상태가 아닌 동영상 가이드를 보지 마시기 바랍니다! 이러한 동영상들은 최신 상태가 아니므로 따라 하다가 장치를 벽돌로 만들 수 있습니다! 만약 정말 동영상 가이드가 필요하다면, [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA) 의 [동영상 가이드](https://youtu.be/BbgTbTGbXYg) 를 보십시오**


### 리파티션 및 boot 이미지 백업

#### PC에서 아래의 명령어를 입력하여 리커버리로 부팅합니다
```cmd
fastboot boot <recovery.img>
```
#### 리파티션을 진행합니다

> 만약 한번 더 실행하라는 문구가 출력되면, 명령어를 한번 더 입력하십시오

> **선택사항**이지만, **파티션 크기를 직접 설정 (기본적으로는, 내부 저장소 용량의 절반을 사용합니다)** 할 수도 있습니다.

> 파티션 크기를 직접 설정하려면 ```adb shell partition [윈도우 파티션 크기를 GB 단위로 입력]``` 명령어를 입력하십시오

> 명령어의 끝 부분에 GB를 추가하지 마시고, 숫자만을 입력하십시오

```cmd
adb shell partition
```

### 기존 boot 이미지 백업
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### 안드로이드가 작동되는지 다시 확인합니다
> 안드로이드가 작동하는지 확인하기 위해 재부팅하십시오. 만약 부팅되지 않는다면, 리커버리에서 초기화를 진행하고 다시 시도하십시오.

```cmd
adb reboot
```


### [다음 단계: 루팅](/guide/Korean/2-rootguide-ko.md)
