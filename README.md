
# ploopy-nano2-qmk

Ploopy Nano 2 Trackball(QMK)용 개인 커스텀 키맵입니다.
이 repo는 **QMK 전체 소스가 아니라 `keymap.c` 한 파일만** 포함합니다.

This repository contains **only one `keymap.c`** for Ploopy Nano 2 (not the full QMK firmware tree).

---

## 대상(Target)

- **Keyboard**: `ploopyco/nano_2/rev2_003`
- **Keymap name**: `korenl137`

---

## 사용 방법(How to use)

### 1) QMK 펌웨어 트리에 keymap 설치(Install into your QMK tree)

QMK 펌웨어(`qmk_firmware`)가 준비되어 있다는 전제입니다.

1. 아래 폴더를 생성합니다.

   `keyboards/ploopyco/nano_2/keymaps/korenl137/`

2. 이 repo의 `keymap.c`를 위 폴더에 복사합니다.

최종 경로는 아래가 됩니다.

`qmk_firmware/keyboards/ploopyco/nano_2/keymaps/korenl137/keymap.c`

English:

1. Create this folder in your `qmk_firmware` tree:

   `keyboards/ploopyco/nano_2/keymaps/korenl137/`

2. Copy this repository's `keymap.c` into that folder.

---

### 2) 빌드(Build)

QMK MSYS(Windows)에서 아래 명령을 실행합니다.

```sh
qmk compile -kb ploopyco/nano_2/rev2_003 -km korenl137
```

빌드 성공 시 `.uf2` 파일이 생성되며, 보통 `qmk_firmware` 루트로도 복사됩니다.

Example output file:

- `ploopyco_nano_2_rev2_003_korenl137.uf2`

---

### 3) 플래시(Flash)

Ploopy Nano 2를 부트로더 모드로 진입한 뒤 `.uf2` 파일을 장치에 복사합니다.

English:

Enter bootloader mode and copy the generated `.uf2` file to the mounted device.

---

## 제스처(Features / Gestures)

현재 `BTN_SMART` 단일 버튼으로 아래 동작을 제공합니다.

- **단일 클릭(1-click tap)**: Left click
- **단일 클릭 홀드(무이동, 400ms)**: Right click (tap)
- **1-click hold + move**: Left drag (momentary)
- **2-click hold + move**: Scroll mode (momentary)

스크롤 모드에서는 트랙볼 이동이 스크롤(`h/v`)로 변환되며, 커서 이동(`x/y`)은 억제됩니다.

---

## 튜닝 파라미터(Tuning)

`keymap.c` 상단 `#define` 값으로 체감 조절이 가능합니다.

- `RIGHTCLICK_HOLD_THRESHOLD` (default: `400` ms)
- `SCROLL_ARM_THRESHOLD` (default: `120` ms)
- `DOUBLECLICK_THRESHOLD` (default: `250` ms)
- `DRAG_ARM_THRESHOLD` (default: `70` ms)
- `MOVE_THRESHOLD_DRAG` (default: `2`)
- `MOVE_THRESHOLD_SCROLL` (default: `3`)
- `SCROLL_DIVISOR_H / SCROLL_DIVISOR_V` (default: `17`)

