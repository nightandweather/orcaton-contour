# Orcaton Contour

[한국어](#한국어) · [English](#english)

> **연구·교육용입니다. 진단이나 치료 계획에 사용할 수 없습니다.**
> **For research and education only. Not for diagnosis or treatment planning.**

---

## 한국어

CT를 비롯한 의료 영상(MR·PET·X선·초음파, 병리 슬라이드, 수술 영상)에 윤곽을 그리고 고치는 데스크톱 프로그램입니다(Windows, macOS). 영상은 컴퓨터 밖으로 나가지 않습니다.

### 할 수 있는 것

- **CT 열기**: NIfTI, DICOM 폴더(압축 포함), NRRD, MetaImage. 축상면·관상면·시상면과 3차원 보기.
- **윤곽 그리기**: 붓·지우개, 다각형, 가위, 영역 채우기, 임계값, 여백, 다듬기, 슬라이스 사이 보간. 실행 취소 200단계.
- **자동 윤곽**: 모델 파일을 설치하면 이 컴퓨터 안에서만 계산합니다. 임상 사용에 대해 검증되지 않았으며 결과는 반드시 검토해야 합니다.
- **윤곽 QA와 살펴볼 곳**: 이름 규칙, 빠진 슬라이스, 겹침, 떨어진 조각, 구멍 등을 항목별로 보여 주고 보고서(HTML·CSV·PDF)로 저장합니다.
- **읽기·쓰기**: DICOM RTSTRUCT, DICOM SEG, NIfTI 라벨 맵, Slicer `.seg.nrrd`. 표면은 STL·OBJ·PLY·VTK로 내보냅니다.
- **명령줄 도구** `orcaton-contour`: 변환, 통계, QA, 그림, 편집, 비교, 자동 윤곽, 일괄 처리. 결과를 JSON으로 냅니다.
- **컨투어 표시(0.7.2)**: 구조·클래스 목록 아래에서 채움·연하게·선만과 진하기를 고르고, C 키로 바꿉니다. CT·영상·슬라이드 모두.
- **여러 영상 종류(0.7.1)**: DICOM MR·PET(SUV)·X선·유방촬영·Enhanced 다중 프레임, 초음파·혈관조영 시네, 시상·관상 시리즈. MR은 공개 무릎 MR로 다른 프로그램과 비교했고, 공개 전신 FDG PET의 SUV는 따로 계산한 값과 0.005 이내, 흉부 X선과 유방촬영은 pydicom과 픽셀이 같음을 확인했습니다.
- **병리 슬라이드(0.7.1)**: SVS·타일 TIFF·DICOM WSI를 필요한 부분만 읽어 열고, 다각형·자유곡선·점으로 클래스별 주석을 달아 GeoJSON(QuPath 형식)으로 주고받습니다.
- **창과 터미널(0.7.1)**: 어느 도구에서든 우클릭한 채 끌어 창(밝기·대비)을 바꾸고 위쪽 막대에서 프리셋을 고릅니다. 위쪽 막대의 터미널 단추로 바로 셸을 엽니다.
- **수술 영상(0.7.0, 시험 단계)**: MP4/MOV를 프레임 단위로 넘기며 클래스별 마스크를 그리고, 사이를 보간으로 채우고, 수술 단계를 표시하고, 영상 QA 뒤 PNG 마스크·단계 CSV·manifest로 내보냅니다. 영상은 이 컴퓨터를 떠나지 않습니다.
- **어시스턴트(0.6.0)**: 직접 설정한 모델 API(OpenAI, Anthropic(Claude), OpenRouter 같은 호스팅 서비스, 또는 이 컴퓨터의 Ollama·LM Studio)에 한국어나 영어로 부탁하면 편집기의 기능으로 일하고, 고친 것은 미리보기로 보여 준 뒤 받아들일 때만 반영됩니다. 기본은 꺼짐.
- **에이전트와 함께 작업(0.6.0)**: 증례 폴더를 공유하고, 프로그램 안의 터미널에서 직접 설치한 AI 에이전트(Claude Code, Codex CLI 등)를 실행합니다. Windows·macOS.

### 처음 실행할 때 (orcaton.com 계정으로 로그인)

1. [orcaton.com](https://orcaton.com)에 구글 계정으로 가입합니다.
2. 프로그램을 설치하고 실행합니다. 로그인 화면에서 **브라우저로 로그인**을 누르고, 열린 orcaton.com 화면에서 **로그인**을 누릅니다(0.7.5부터). 또는 **토큰 페이지 열기**로 **Orcaton Contour 전용** 토큰을 만들어 붙여 넣습니다.
3. 로그인하면 프로그램이 열리고 **2주 무료 체험**이 시작됩니다(토큰의 유효 기간과는 따로입니다). 체험이 끝나면 받은 코드를 넣어 이어서 쓰거나, 프로그램의 **사용 신청**으로 메모와 함께 요청합니다. 구매는 준비 중입니다.

문의는 **kanghoun@orcaton.com** 으로 보내 주세요.

### 내려받기와 설치

[Releases](https://github.com/nightandweather/orcaton-contour/releases/latest)에서 내려받습니다.

| 운영체제 | 파일 |
| --- | --- |
| Windows 10/11 (64비트) | `Orcaton-Contour-Setup-<버전>-win-x64.exe` |
| macOS (Apple Silicon: M1 이후) | `Orcaton-Contour-<버전>-mac-arm64.dmg` |
| macOS (Intel) | `Orcaton-Contour-<버전>-mac-x64.dmg` |

각 파일의 SHA-256은 릴리스 설명에 있습니다. 릴리스의 .zip과 .yml 파일은 프로그램 안 업데이트용입니다. 0.7.4부터는 새 버전이 나오면 프로그램의 '업데이트' 단추로 받을 수 있고, 0.7.3 이전에서는 한 번 손으로 설치합니다.

macOS용은 Apple의 공증을 받은 서명 빌드입니다(Developer ID: kanghoun lee). **Windows용은 아직 서명되지 않은 빌드입니다.**

**Windows**
1. 내려받은 설치 파일을 실행합니다.
2. '전용(현재 사용자)'을 그대로 두고 다음 → 설치를 누릅니다. 관리자 권한은 필요 없습니다.
3. 시작 메뉴의 Orcaton Contour로 실행합니다.

Windows 11 Pro 시험 PC에서는 경고 없이 설치 마법사가 열렸습니다. PC 설정에 따라 'Windows의 PC 보호' 창이 먼저 뜰 수 있으며, 그 창에서의 절차는 확인하지 못했습니다.

**macOS**
1. 내려받은 .dmg를 열고 Orcaton Contour를 응용 프로그램 폴더로 옮깁니다.
2. 응용 프로그램 폴더에서 Orcaton Contour를 엽니다. 인터넷에서 받은 앱이라는 확인 창이 한 번 나오면 '열기'를 누릅니다.

이전에 받은 서명되지 않은 빌드에서 쓰던 xattr 명령은 더 이상 필요 없습니다. macOS 26(Apple Silicon)에서 확인했습니다. Intel Mac에서는 확인하지 못했습니다.

### 개인정보

- 영상과 파일 이름은 이 컴퓨터 밖으로 나가지 않습니다. 텔레메트리와 오류 보고가 없고, 묻지 않고 받는 업데이트도 없습니다.
- 기본으로 밖으로 나가는 요청은 계정 확인 하나뿐입니다: `GET https://orcaton.com/api/cli/v1/me`, 토큰과 앱 이름·버전만 보냅니다.
- 새 버전은 계정 확인의 답으로 알려 줍니다. '업데이트'를 누를 때만 이 저장소의 Releases(GitHub)에서 받고, 받은 파일의 해시를 확인한 뒤 다시 시작할 때 설치합니다(0.7.4부터).
- '브라우저로 로그인'을 누르면 그때만 orcaton.com 확인 화면을 브라우저로 열고, 확인한 뒤 일회용 코드와 확인값을 보내 토큰을 받습니다. 브라우저 주소에는 이 컴퓨터의 포트와 임시값만 들어갑니다(0.7.5부터).
- 사용 신청이나 코드 등록을 직접 누르면 그때 한 번 orcaton.com으로 보냅니다: 토큰과 적은 메모·앱 버전, 또는 코드만.
- 어시스턴트를 켜면, 켜 둔 동안 대화와 구조의 이름·수치(허용했을 때만 잘라 낸 CT 그림)가 직접 정한 주소 한 곳으로 갑니다. 환자 영상에는 클라우드 모델을 쓰지 마십시오.
- 내장 터미널에서 실행한 프로그램이 보내는 것은 그 프로그램이 하는 일입니다.
- 한 번 확인되면 인터넷 없이 30일 동안 쓸 수 있습니다.

### 알아 둘 점

- 연구·교육용이며 의료기기로 허가받지 않았습니다. 진단이나 치료 계획에 쓸 수 없습니다.
- 실제 치료계획시스템과의 왕복(내보낸 RTSTRUCT를 치료계획시스템에서 여는 것)과 병원 장비가 만든 DICOM은 아직 확인 중입니다. 문제가 있으면 위 메일로 알려 주세요.
- 이 저장소에는 설치 파일과 안내만 있습니다. 소스 코드는 공개하지 않습니다.

---

## English

A desktop program for drawing and correcting contours on CT and other medical images (MR, PET, X-ray, ultrasound, pathology slides, surgical video) (Windows, macOS). Images never leave the computer.

### What it does

- **Opens CT**: NIfTI, DICOM folders (compressed too), NRRD, MetaImage. Axial, coronal and sagittal views and a 3-D view.
- **Contouring**: brush and eraser, polygon, scissors, region fill, threshold, margin, smoothing, interpolation between slices. Undo up to 200 steps.
- **Automatic contouring**: install a model file and everything is computed on this computer. Not validated for clinical use; the results must be reviewed.
- **Contour QA and places to look at**: naming rules, missing slices, overlaps, detached pieces, holes and more, listed finding by finding, with reports as HTML, CSV and PDF.
- **In and out**: DICOM RTSTRUCT, DICOM SEG, NIfTI label maps, Slicer `.seg.nrrd`. Surfaces as STL, OBJ, PLY and VTK.
- **Command-line tool** `orcaton-contour`: conversion, statistics, QA, pictures, editing, comparison, automatic contouring, batches. JSON output.
- **Contour display (0.7.2)**: Filled, Faint or Outline with a strength slider under every structure or class list; the C key cycles them. In CT, video and slide modes.
- **More image kinds (0.7.1)**: DICOM MR, PET (SUV), X-ray, mammography, enhanced multi-frame, ultrasound and angiography cine, sagittal and coronal series. MR was checked against other software with a public knee MR; on public data, whole-body FDG PET SUV is within 0.005 of an independent calculation, and chest X-ray and mammogram pixels equal pydicom's.
- **Pathology slides (0.7.1)**: SVS, tiled TIFF and DICOM WSI, read only where you look; annotate with polygons, freehand outlines and points in classes and exchange them as GeoJSON the way QuPath writes it.
- **Window and terminal (0.7.1)**: change the window (brightness/contrast) with a right-drag in any tool and pick presets in the top bar; a Terminal button in the top bar opens a shell at once.
- **Surgical video (0.7.0, early)**: step through MP4/MOV frame by frame, draw class masks, fill between, mark surgical phases, run the video QA and export PNG masks, phase CSVs and a manifest. The video never leaves the computer.
- **Assistant (0.6.0)**: ask a model API you set up yourself (hosted such as OpenAI, Anthropic (Claude) or OpenRouter, or Ollama / LM Studio on this computer) in Korean or English; it works through the editor's functions and shows its changes as a preview that applies only when you accept. Off by default.
- **Working with an agent (0.6.0)**: share the case through a folder and run an AI agent you installed (Claude Code, Codex CLI …) in the terminal inside the program. Windows and macOS.

### The first time you run it (sign in with an orcaton.com account)

1. Sign up at [orcaton.com](https://orcaton.com) with a Google account.
2. Install the program and start it. Press **Sign in with the browser** on the sign-in screen and confirm on the orcaton.com page that opens (from 0.7.5). Or use **Open the token page** to create an **Orcaton Contour only** token and paste it into the program.
3. Once signed in, the program opens and a **two-week free trial** starts (separate from the token's own lifetime). After the trial, enter a code you received to keep using it, or send an **access request** with a note from the program. Purchase is not available yet.

Questions: **kanghoun@orcaton.com**

### Download and install

Download from [Releases](https://github.com/nightandweather/orcaton-contour/releases/latest).

| System | File |
| --- | --- |
| Windows 10/11 (64-bit) | `Orcaton-Contour-Setup-<version>-win-x64.exe` |
| macOS (Apple Silicon: M1 and later) | `Orcaton-Contour-<version>-mac-arm64.dmg` |
| macOS (Intel) | `Orcaton-Contour-<version>-mac-x64.dmg` |

The SHA-256 of every file is in the release notes. The release's .zip and .yml files are for in-program updates. From 0.7.4 on, a new version can be installed with the program's Update button; from 0.7.3 or older, install 0.7.4 by hand once.

The macOS builds are signed and notarised by Apple (Developer ID: kanghoun lee). **The Windows build is not signed yet.**

**Windows**
1. Run the downloaded installer.
2. Keep "Only for me (current user)" and press Next → Install. No administrator rights are needed.
3. Start Orcaton Contour from the Start menu.

On the Windows 11 Pro test PC the setup wizard opened without a warning. Depending on the PC's settings a "Windows protected your PC" window may appear first; the steps in that window were not checked.

**macOS**
1. Open the downloaded .dmg and move Orcaton Contour to the Applications folder.
2. Open Orcaton Contour from the Applications folder. If macOS asks once because it was downloaded from the internet, press Open.

The xattr command that earlier unsigned builds needed is no longer needed. Checked on macOS 26 (Apple Silicon); not checked on an Intel Mac.

### Privacy

- Images and file names never leave this computer. No telemetry, no error reports, and nothing is updated without you asking.
- By default the only outgoing request is the account check: `GET https://orcaton.com/api/cli/v1/me`, carrying the token and the app's name and version only.
- A new version is announced in the answer to the account check. Only when you press Update is it fetched from this repository's Releases (GitHub), its hash checked, and installed when the program restarts (from 0.7.4).
- Only when you press Sign in with the browser does the program open the orcaton.com confirmation page in your browser; after you confirm, it sends a one-time code and its check value to get a token. The browser address carries only a local port and one-time values (from 0.7.5).
- An access request or code you send yourself goes to orcaton.com once: the token with your note and the app's version, or the code.
- With the assistant turned on, the conversation and the structures' names and figures (cropped CT pictures only if allowed) go to the one address you set. Do not use cloud models with patient images.
- What a program you start in the built-in terminal sends is that program's doing.
- After one successful check the program works offline for 30 days.

### Good to know

- For research and education only; not cleared as a medical device. Not for diagnosis or treatment planning.
- The round trip with treatment planning systems (opening exported RTSTRUCT there) and DICOM from hospital scanners are still being checked. Please report problems to the address above.
- This repository holds the installers and this guide only. The source code is not published.

© 2026 Orcaton. All rights reserved.
