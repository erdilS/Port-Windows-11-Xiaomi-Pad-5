<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## 제거

### 왜 이 과정이 필요합니까?
> 윈도우 제거를 원할 경우 수동으로 파티션을 제거하지 않고 이 과정이 사용되며 이를 통해 실수 또한 방지합니다.

> [!Warning]
> **모든 데이터가 삭제됩니다! 필요한 경우 백업하세요.**

#### Android로 전환합니다
> 마지막으로 부팅한 운영체제가 Windows인 경우, 제거 과정을 진행하기 전에 먼저 Android로 전환하세요

#### fastboot 모드로 재부팅합니다
- USB 케이블이 연결된 상태에서 재부팅할 때 **`볼륨 아래`** 버튼을 누른 상태를 유지하여 NABU를 **fastboot**로 재부팅하세요
- 또는, USB 디버깅이 활성화했다면, Android로 부팅되어 있는 상태에서 아래의 명령어를 입력하세요.
```cmd
adb reboot bootloader
```

> [!NOTE]
>
> ▶️ 클릭하여 메뉴를 확장하세요.

<details>
  <summary><strong>방법 1 - adb shell restore 명령어를 사용하여 제거</strong></summary>

### 준비물
- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)
  
- [```맞춤화된 리커버리 이미지```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

#### 맞춤화된 리커버리로 부팅합니다
> platform-tools 폴더에서 CMD 창을 열고, 아래의 명령어를 실행합니다 (fastboot 모드에 진입하면 실행하세요)
```cmd
fastboot boot path\to\recovery.img
```

#### 파티션 레이아웃을 복원합니다
> [!Warning]
> 안드로이드 파일이 모두 초기화됩니다. 필요한 경우 미리 백업하세요.

```cmd
adb shell restore
```

### 안드로이드로 재부팅
```cmd
adb reboot 
```

## 끝!

</details>

<details>
  <summary><strong>방법 2 - fastboot에서 제거</strong></summary>

### 준비물물
- [```안드로이드 플랫폼 도구```](https://developer.android.com/studio/releases/platform-tools)

- [```gpt_both0.bin```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/gpt_both0.bin) 

### 파티션 테이블 복원
> ```path\to\gpt_both0.bin```를 gpt_both0.bin 파일의 경로로 교체하세요.
```cmd
fastboot flash partition:0 path\to\gpt_both0.bin
```

#### userdata 초기화
> To avoid a bootloop and restore FS size
```cmd
fastboot -w
```

#### Android로 재부팅
```cmd
fastboot reboot
```

## 끝!

</details>

<details>
  <summary><strong>방법 3 - "Nabu Fastboot Tool"을 이용하여 제거</strong></summary>

### 준비물
 **`Xiaomi Pad 5`**`를 `**`다른 장치`**`로 연결할 `**`케이블`**

 **`다른 장치 (Android, Windows, Mac 또는 Linux)`**

### Fastboot Tool 웹사이트 연결
- **[Nabu Fastboot Tool](https://arkt-7.github.io/nabu/)** 를 다른 장치의 브라우저에서 엽니다.
- **`Connect Device Fastboot`** 버튼을 클릭합니다.
- 리스트에서 **`Android`** 를 선택하고 **`allow`** 를 선택하여 권한을 허용합니다.

### 초기화 및 파티션 순정화
- **`Format/wipe make Partition Stock`** 부분까지 화면을 스크롤하여 내립니다.
- 입력 상자에 **`format`** 을 입력합니다.
- 마지막으로, **`Format/Wipe`** 버튼을 클릭하고 경고 메시지가 나타나면 **`OK`** 를 선택합니다.
- 초기화가 끝나면, 성공 메시지가 나타납니다. **`OK`** 를 클릭하여 메시지 창을 닫습니다.
- 화면을 스크롤하여 올리고 **`Reboot Device`** 버튼을 클릭핳여 장치를 다시 시작합니다.

## 끝!

</details>

> [!NOTE]
> MIUI 리커버리로 부팅된 경우 다음 작업을 수행하세요:
> 1. Wipe Data를 선택합니다
> 2. 모든 데이터를 삭제합니다
> 3. 데이터가 성공적으로 삭제되면, Back To Main Menu를 선택합니다
> 4. Reboot를 선택합니다
> 5. 시스템으로 재부팅합니다





















