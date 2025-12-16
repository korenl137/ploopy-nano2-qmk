# ploopy-nano2-qmk

This repository contains a custom QMK keymap for the Ploopy Nano 2 trackball.

It includes **only a single `keymap.c` file** (not the full QMK firmware tree).

---

## Target

- **Keyboard**: `ploopyco/nano_2/rev2_003`
- **Keymap name**: e.g. `my_keymap`

---

## How to use

1. Clone or download the official QMK firmware repository.
2. Copy this repository’s `keymap.c` into the appropriate keymap directory, for example:

   ```
   qmk_firmware/keyboards/ploopyco/nano_2/rev2_003/keymaps/my_keymap/keymap.c
   ```

3. Configure QMK environment and build the firmware:

   ```
   qmk compile -kb ploopyco/nano_2/rev2_003 -km my_keymap
   ```

4. Flash the resulting firmware to your Ploopy Nano 2 following the usual QMK / Ploopy flashing instructions.

---

## AI assistance

This keymap was created with the assistance of AI-based coding tools (Windsurf, ChatGPT 5.2, Claude Opus 4.5).  
All generated code was reviewed and modified by the author before being committed.

Some parts of the layer behavior and helper logic were initially suggested by these AI tools and then adapted for this specific device.

---

## Upstream projects

This keymap is intended to be used with:

- **QMK Firmware** – https://qmk.fm  
- **Ploopy Nano 2 firmware tree** inside the official QMK repository (the `ploopyco/nano_2` target).

This repository only contains a single `keymap.c` file and does *not* include the full QMK source tree.

The initial behavior is loosely based on the default Nano 2 keymap provided by Ploopy / QMK, then customized for this workflow.

---

## License and warranty

This repository is distributed under the terms of the **GPL-2.0** license (see `LICENSE`).  

The keymap is provided **“as is”**, without any warranty of any kind.  
Flashing this firmware to your device is done entirely at your own risk.