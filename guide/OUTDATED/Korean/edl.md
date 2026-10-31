<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## EDL 모드의 장치 복구

### EDL 모드로 진입
> Xiaomi Pad 5를 **EDL 모드** 로 부팅하기 위한 두 가지 방법이 있습니다. 현재 상황에 맞는 것을 사용하세요.

> [!NOTE]
>
> ▶️ 클릭하여 메뉴를 확장하세요.

<details>
  <summary><strong>방법 1: 부트로더가 언락 상태일 때</strong></summary>

> 부트로더가 언락되어 있으면, **fastboot mode** 에서 아래의 명령어를 입력하세요
```cmd
fastboot oem edl
```

</details>

<details>
  <summary><strong>방법 2: 부트로더가 락 상태이거나 장치가 부팅 불가능할 때</strong></summary>

- **EDL 케이블** 이 있다면 장치에 이 케이블을 연결하고 케이블의 버튼을 눌러 **EDL mode** 로 부팅합니다.
> 온라인에서 찾을 수 있는 EDL 케이블은 이름에 V2가 포함되어 있어야 작동합니다. (예시: **Hydra V2 EDL Cable**)
- 또는, **테스트 포인트를 쇼트킵니다**. (장치의 뒷판을 열어야 합니다)

</details>

### 모든 것이 괜찮은지 확인
- PC에서 **장치 관리자** 를 열고 **Qualcomm HS-USB QDLoader 9008** 와 같은 새로운 장치를 찾습니다.
- **장치 관리자** 에서 장치 이름이 **QUSB_BULK_CID** 이거나 노란색 경고 ⚠️ 표시가 있는 경우, 드라이버를 설치/업데이트해야 합니다.
- 드라이버를 설치하기 위하여, **[QUD.zip](https://github.com/n00b69/woa-betalm/releases/download/Qfil/QUD.zip)** 파일을 다운로드 및 압축 해제하고, 장치 관리자에서 오류가 발생한 장치를 선택히고, **드라이버 업데이트** 선택하고, 압축 해제했던 **QUD 폴더** 를 선택하세요.

> [!NOTE]
>
> ▶️ 클릭하여 메뉴를 확장하세요.

<details>
  <summary><strong>MiFlash로 플래시</strong></summary>

## MiFlash로 플래시

### 준비물
- [`패치된 MiFlash 도구`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/MiFlashPatched.zip)

- [`패치된 firehose (.elf) 파일`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/Files/prog_ufs_firehose_sm7150_ddr.elf)

- `추출된` [`Nabu의 fastboot 롬`](https://xiaomifirmwareupdater.com/hyperos/nabu/) 

### 필요한 파일 준비
- Xiaomi Pad 5의 **fastboot 롬** 을 압축 해제합니다.
- 이전에 다운로드했던 **MiflashPatched.zip** 파일을 압축 해제합니다.
- **MiflashPatched.zip** 폴더에서 **firehose (.elf)** 파일을 압축 해제했던 **fastboot 롬** 의 **images** 폴더로 복사합니다. 파일이 이미 존재하면 덮어 씁니다.

#### MiFlash 도구를 엽니다 
- 압축 해제했던 **MiflashPatched.zip** 내부의 **MiFlash** 폴더로 이동합니다.
- **XiaoMiFlash.exe** 를 관리자 권한으로 실행합니다.

### 롬 플래시
- **MiFlash** 에서 **Select** 버튼을 클릭하고 **fastboot 롬** 을 압축 해제했던 폴더 (**firehose.elf** 파일을 교체했던 폴더)를 선택합니다.
- **MiFlash** 도구에서, **"Clean All"** 옵션이 선택되었는지 확인합니다.
- **MiFlash** 에서 **Refresh** 를 클릭하여 기기의 연결 상태를 확인합니다.
- 기기가 연결되었고 **"Clean All"** 옵션이 선택되었는지 확인했다면, **Flash** 를 클릭하여 플래시 과정을 시작합니다.

> [!Important]
> 2분 이상 동안 사라지지 않는 오류가 표시되는 경우, **EDL mode** 로 다시 재부팅하고, **Refresh** 및 **Flash** 를 클릭하여 다시 시도하세요.

#### 장치를 재부팅합니다
- 플래시가 완료되면, **Reboot** 버튼을 클릭하여 장치를 재부팅합니다.

</details>

#### 성공!
이제 Xiaomi Pad 5가 원래대로 성공적으로 복구되었을 것입니다!
































