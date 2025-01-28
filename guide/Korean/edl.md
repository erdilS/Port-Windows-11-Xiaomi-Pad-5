<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# Xiaomi Pad 5 에서 윈도우 구동

## EDL 모드의 장치 복구
> 이 가이드에는 장치를 복구하는 두 가지 방법이 포함되어 있습니다. 방법 1이 안되면, 방법 2를 이용해보세요

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
  <summary><strong>방법 1: 무료 방법</strong></summary>

## 방법 1: 무료 방법

### 준비물
- [`패치된 MiFlash 도구`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/MiFlashPatched.zip)

- [`패치된 firehose (.elf) 파일`](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/prog_ufs_firehose_sm7150_ddr.elf)

- `추출된` [`Nabu의 fastboot 롬`](http://xmfirmwareupdater.com/miui/nabu/) 

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

<details>
  <summary><strong>방법 2: 유료 EDL 방법</strong></summary>

## 방법 2: HXRU Tool을 통한 유료 복구

### 준비물 
- `$3 USDT` 및 크레딧을 위한 암호화폐 지갑 (일부 러시아 은행 계좌 가능)

- HXRU 지원 소통을 위한 `텔레그램 계정`

- [`MiFlash HXRU 도구`](https://hxrutool.net/tool/Xiaomi_Auth_Tool_v9.0.0.5_mtk.zip)
 
- [`Nabu의 순정 fastboot 롬`](http://xmfirmwareupdater.com/miui/nabu/)  
### HXRU Tool 설정  
- **[HXRU dashboard](https://dashboard.hxrutool.com/Register)** 에서 계정을 생성합니다.
- **MiFlash HXRU** 도구를 다운로드 및 압축 해제합니다.

#### 크레딧을 구매합니다 
- 텔레그램에서 **@hxruofficial** 님께 연락하여 **5 크레딧** (대략 **$3**)을 구매합니다. 장치를 복구하려면 이 크레딧이 필요합니다.

### 장치 복구
- **XiaoMiFlash.exe** 를 열고 관리자 권한을 부여합니다.
- 기기의 순정 fastboot 롬을 다운로드하고 엽니다. (.tgz 확장의 파일입니다) 내부에 .tar 파일이 있을 것입니다. 이 .tar 파일을 아무 폴더에 압축 해제하세요.
- **XiaoMiFlash** 에서 **select** 버튼을 클릭하고 압축 해제한 폴더를 선택합니다.
- **flash** 를 선택합니다.
- `write time out` 오류가 발생한 경우, **전원** + **볼륨 아래** 버튼을 30초 정도 누른 상태를 유지하여 EDL로 재부팅하세요. 이후 **flash** 버튼을 다시 선택하세요.
- 몇 초 후 로그인 팝업이 나타날 것입니다. HRXU 계정 정보를 이곳에 작성하고 **Request Auth Flashing** 를 선택하세요.

#### 장치를 재부팅합니다
- **flash done** 이 표시되면, **전원** 을 14초 정도 누른 상태를 유지하여 장치를 재부팅합니다.

</details>

### MiFlash로 롬 재설치
> [!Warning]
> 이러한 도구들은 한 쪽 슬롯에만 롬을 설치합니다. 장치가 부팅 슬롯을 변경할 경우 다시 EDL로 부팅될 것입니다.
- fastboot 모드로 재부팅합니다.
- **MiFlash**를 사용하거나 롬에 있는 **flash_all.bat** 파일을 사용하여 fastboot 롬을 두 번 설치합니다.
- 플래시가 끝나면 장치를 재부팅합니다.

#### 성공!
이제 Xiaomi Pad 5가 원래대로 성공적으로 복구되었을 것입니다!
































