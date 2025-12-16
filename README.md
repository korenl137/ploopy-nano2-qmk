
# ploopy-nano2-qmk

This repository contains a custom QMK keymap for the Ploopy Nano 2 trackball.

It includes **only a single `keymap.c` file** (not the full QMK firmware tree).

---

## Target

- **Keyboard**: `ploopyco/nano_2/rev2_003`
- **Keymap name**: Example: `my_keymap`

---

## How to use

### 1) Install into your QMK tree

This assumes you already have a working `qmk_firmware` setup.

1. Create the following folder inside your `qmk_firmware` tree:

   `keyboards/ploopyco/nano_2/keymaps/my_keymap/`

2. Copy this repository's `keymap.c` into that folder.

Final path:

`qmk_firmware/keyboards/ploopyco/nano_2/keymaps/my_keymap/keymap.c`

---

### 2) Build

Run the following command (QMK MSYS on Windows):

```sh
qmk compile -kb ploopyco/nano_2/rev2_003 -km my_keymap
```

On success, a `.uf2` file is generated and usually copied to your `qmk_firmware` folder.

Example output filename:

- `ploopyco_nano_2_rev2_003_my_keymap.uf2`

---

### 3) Flash

Enter bootloader mode and copy the generated `.uf2` file to the mounted device.

---

## Features / Gestures

This keymap maps multiple actions onto a single `BTN_SMART` button:

- **1-click tap**: Left click
- **1-click hold (no move, 400ms)**: Right click (tap)
- **1-click hold + move**: Left drag (momentary)
- **2-click hold + move**: Scroll mode (momentary)

In scroll mode, trackball movement is converted into wheel scrolling (`h/v`) and cursor movement (`x/y`) is suppressed.

---

## Tuning

You can adjust the feel by changing these `#define` values near the top of `keymap.c`:

- `RIGHTCLICK_HOLD_THRESHOLD` (default: `400` ms)
- `SCROLL_ARM_THRESHOLD` (default: `120` ms)
- `DOUBLECLICK_THRESHOLD` (default: `250` ms)
- `DRAG_ARM_THRESHOLD` (default: `70` ms)
- `MOVE_THRESHOLD_DRAG` (default: `2`)
- `MOVE_THRESHOLD_SCROLL` (default: `3`)
- `SCROLL_DIVISOR_H / SCROLL_DIVISOR_V` (default: `17`)

---

## License

This project is distributed under the GPL-2.0 license. See `LICENSE`.

---

## Releases (UF2) and Source Matching

When publishing a prebuilt `.uf2` file, it is recommended to:

1. Create a git tag (example: `v0.1.0`).
2. Attach the `.uf2` file to the GitHub Release created from that tag.

This makes it clear which exact source revision produced the binary.

---

## QMK Firmware Version Used for Building

This keymap was built against the upstream QMK firmware repository.

- **QMK repo**: `https://github.com/qmk/qmk_firmware`
- **QMK commit**: `c1fedab4570a0b87b3422239a724681788727b09`

