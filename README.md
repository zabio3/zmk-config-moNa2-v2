# moNa2 Keymap Configuration

Personal customized ZMK firmware configuration for moNa2 split keyboard.

## Table of Contents

- [About moNa2](#about-mona2)
- [About This Repository](#about-this-repository)
- [Keymap](#keymap)
  - [Layer 0: Default](#layer-0-default)
  - [Layer 1: Numbers & Symbols](#layer-1-numbers--symbols)
  - [Layer 3: Navigation](#layer-3-navigation)
  - [Layer 4: Bluetooth & System](#layer-4-bluetooth--system)
- [Combo Keys](#combo-keys)
- [Encoder Functions](#encoder-functions)
- [Trackball Settings](#trackball-settings)
- [Building Firmware](#building-firmware)
- [References](#references)

## About moNa2

moNa2 is a split wireless keyboard designed by [sayu](https://x.com/Pooh_pol0).

### Key Features

- **Split Design**: Ergonomic left-right separated layout
- **Right Hand Trackball**: PMW3610 sensor
- **Left Hand Encoder**: Rotary encoder support
- **Wireless Connection**: Bluetooth 5.0 (ZMK firmware)
- **Microcontroller**: Seeeduino XIAO BLE (nRF52840)

> For details, see [moNa2 Introduction Page](https://note.com/pooh_polo/n/ncfce62c909f5) (Japanese)

## About This Repository

This repository is a fork of [sayu-hub/zmk-config-moNa2-v2](https://github.com/sayu-hub/zmk-config-moNa2-v2) with personal keymap customizations.

### File Structure

```
config/
├── mona2.keymap      # Keymap definitions
├── mona2.json        # ZMK Studio layout
├── mona2_l.conf      # Left side configuration
├── mona2_r.conf      # Right side configuration
└── west.yml          # Module dependencies
```

## Keymap

### Layer 0: Default

Standard QWERTY layout with mouse buttons on right side. Hold-tap for layer switching.

```
Left Hand                                    Right Hand
┌─────┬─────┬─────┬─────┬─────┐               ┌─────┬─────┬─────┬─────┬─────┐
│  Q  │  W  │  E  │  R  │  T  │               │  Y  │  U  │  I  │  O  │  P  │
├─────┼─────┼─────┼─────┼─────┤         ┌─────┼─────┼─────┼─────┼─────┼─────┤
│  A  │  S  │  D  │  F  │  G  │         │  @  │  H  │  J  │  K  │  L  │  ;  │
├─────┼─────┼─────┼─────┼─────┼─────┐   ├─────┼─────┼─────┼─────┼─────┼─────┤
│  Z  │  X  │  C  │  V  │  B  │  ,  │   │  .  │  N  │  M  │ MB1 │ MB2 │ MB1 │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┴─────┴─────┼─────┤
│ ESC │SHIFT│ GUI │ BS  │ENTER│LANG2│   │LANG1│L1+SP│                 │ ALT │
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────────────────┴─────┘
  ⟲ Scroll                                          ● Trackball
```

**Legend:**
| Symbol | Description |
|--------|-------------|
| SHIFT | Sticky Shift (tap for one-shot, hold for normal shift) |
| LANG2 | Hold for Layer 2, tap for Japanese input |
| LANG1 | Hold for Layer 0, tap for English input |
| L1+SP | Hold for Layer 1, tap for Space |
| MB1/MB2 | Left click / Right click |
| GUI | Command (⌘) |
| BS | Backspace |

### Layer 1: Numbers & Symbols

Numbers and various symbols. Access by holding Space on Layer 0.

```
Left Hand                                    Right Hand
┌─────┬─────┬─────┬─────┬─────┐               ┌─────┬─────┬─────┬─────┬─────┐
│  1  │  2  │  3  │  4  │  5  │               │  6  │  7  │  8  │  9  │  0  │
├─────┼─────┼─────┼─────┼─────┤         ┌─────┼─────┼─────┼─────┼─────┼─────┤
│  `  │  [  │  ]  │  (  │  )  │         │  ?  │CTRL │  &  │  *  │  -  │  _  │
├─────┼─────┼─────┼─────┼─────┼─────┐   ├─────┼─────┼─────┼─────┼─────┼─────┤
│  !  │  @  │  #  │  $  │  %  │  ~  │   │     │     │     │     │     │  \  │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┴─────┴─────┼─────┤
│     │     │     │     │     │     │   │     │     │                 │  |  │
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────────────────┴─────┘
  ⟲ Volume Control
```

### Layer 3: Navigation

Arrow keys, page navigation, Mac operations. Access via ALT + MB1 combo.

```
Left Hand                                    Right Hand
┌─────┬─────┬─────┬─────┬─────┐               ┌─────┬─────┬─────┬─────┬─────┐
│ ESC │C+S+T│ S↑  │C+TAB│     │               │     │HOME │  ↑  │ END │     │
├─────┼─────┼─────┼─────┼─────┤         ┌─────┼─────┼─────┼─────┼─────┼─────┤
│ GUI │ S←  │ S↓  │ S→  │C+G+→│         │     │     │  ←  │  ↓  │  →  │     │
├─────┼─────┼─────┼─────┼─────┼─────┐   ├─────┼─────┼─────┼─────┼─────┼─────┤
│SHIFT│ ⌘+F │⌘+TAB│ ⌘+` │     │     │   │     │     │ DEL │PGUP │PGDN │     │
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┴─────┴─────┼─────┤
│     │     │     │     │     │     │   │     │     │                 │     │
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────────────────┴─────┘
  ⟲ Horizontal Scroll                               ● Scroll Mode
```

**Legend:**
| Symbol | Description |
|--------|-------------|
| C+S+T | Ctrl+Shift+Tab (previous tab) |
| C+TAB | Ctrl+Tab (next tab) |
| C+G+→ | Ctrl+Cmd+→ (desktop switch) |
| S↑↓←→ | Scroll up/down/left/right |
| ⌘+F | Spotlight search |
| ⌘+TAB | App switch |
| ⌘+` | Window switch within app |
| PGUP/PGDN | Page Up / Page Down |

### Layer 4: Bluetooth & System

Bluetooth profile switching, bootloader, screenshots.

```
Left Hand                                    Right Hand
┌─────┬─────┬─────┬─────┬─────┐               ┌─────┬─────┬─────┬─────┬─────┐
│     │⌘S+4 │⌘S+5 │⌘C+N │     │               │ BT0 │ BT1 │ BT2 │ BT3 │ BT4 │
├─────┼─────┼─────┼─────┼─────┤         ┌─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │         │     │     │     │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┐   ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │   │BOOT │     │     │     │     │BTCLR│
├─────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┴─────┴─────┼─────┤
│     │     │     │     │     │     │   │     │     │                 │CLRAL│
└─────┴─────┴─────┴─────┴─────┴─────┘   └─────┴─────┴─────────────────┴─────┘
  ⟲ Brightness Control
```

**Legend:**
| Symbol | Description |
|--------|-------------|
| ⌘S+4 | Cmd+Shift+4 (screenshot selection) |
| ⌘S+5 | Cmd+Shift+5 (screenshot menu) |
| ⌘C+N | Cmd+Ctrl+N (notification center) |
| BT0-4 | Bluetooth profile 0-4 |
| BOOT | Bootloader mode |
| BTCLR | Clear current profile pairing |
| CLRAL | Clear all pairings |

## Combo Keys

Special keys triggered by pressing two keys simultaneously.

| Keys | Output | Position |
|------|--------|----------|
| Q + W | ` (backtick) | Left hand row 1 |
| S + D | TAB | Left hand row 2 |
| D + F | Shift+TAB | Left hand row 2 |
| U + I | - (minus) | Right hand row 1 |
| I + O | = (equal) | Right hand row 1 |
| K + L | " (double quote) | Right hand row 2 |
| L + ; | ' (single quote) | Right hand row 2 |
| ALT + MB1 | ESC + Layer 3 | Right thumb |

## Encoder Functions

The left-hand rotary encoder has different functions per layer.

| Layer | Clockwise | Counter-clockwise |
|-------|-----------|-------------------|
| Layer 0 (Default) | Scroll Down | Scroll Up |
| Layer 1 (Numbers) | Volume Up | Volume Down |
| Layer 3 (Navigation) | Scroll Right | Scroll Left |
| Layer 4 (Bluetooth) | Brightness Up | Brightness Down |

## Trackball Settings

Right side features a trackball using PMW3610 sensor.

- **CPI (Sensitivity)**: 600
- **Sensor**: PMW3610
- **Trackball**: [COROPIT](https://booth.pm/ja/items/6830658)

### Scroll Mode

In Layer 3, the trackball switches to scroll mode.

## Building Firmware

### Automatic Build via GitHub Actions

1. Edit `config/mona2.keymap`
2. Commit & Push
3. GitHub Actions builds automatically
4. Download firmware (.uf2) from Actions tab

### Build Artifacts

- `mona2_l-seeeduino_xiao_ble-zmk.uf2` - Left side
- `mona2_r-seeeduino_xiao_ble-zmk.uf2` - Right side

### Flashing Firmware

1. Connect keyboard via USB
2. Double-press reset button quickly to enter bootloader mode
3. Copy .uf2 file to mounted `XIAO-SENSE` drive
4. Automatic restart completes the flash

## References

### Official Resources

- [moNa2 Introduction Page](https://note.com/pooh_polo/n/ncfce62c909f5) (Japanese)
- [moNa2 Official Firmware (sayu-hub)](https://github.com/sayu-hub/zmk-config-moNa2-v2)
- [ZMK Firmware Documentation](https://zmk.dev/docs)
- [moNa Support & Development Server (Discord)](https://discord.gg/kJjDBDHGer)

### Libraries Used

- [zmk-pmw3610-driver](https://github.com/badjeff/zmk-pmw3610-driver) - Trackball driver
- [zmk-rgbled-widget](https://github.com/caksoylar/zmk-rgbled-widget) - RGB LED control
- [zmk-input-processor-keybind](https://github.com/zettaface/zmk-input-processor-keybind) - Input processor

### Tools

- [ZMK Studio](https://zmk.studio/) - Real-time keymap editing
- [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) - Visual keymap editor
