# Corne Xiao Direct Logic

This folder contains the ZMK configuration for a "Corne Xiao" keyboard using **Direct Wiring** (no shift registers).

## Hardware Configuration (CRITICAL)

The firmware is configured for the following pinout on the **Seeed XIAO BLE (nRF52840)**:

| Matrix Function | Pin Count | XIAO Pins (ZMK Ref) | Physical Pin |
| :--- | :--- | :--- | :--- |
| **Rows** | 4 | `D0` `D1` `D2` `D3` | P0.02, P0.03, P0.28, P0.29 |
| **Columns** | 6 | `D4` `D5` `D6` `D7` `D8` `D9` | P0.04, P0.05, P1.11, P1.12, P1.13, P1.14 |

**Note**: `D10` is unused.

## Application

To build this firmware, you need a ZMK environment.

### Build Command (West)

```bash
# For Left Side
west build -b xiao_ble -- -DSHIELD=corne_xiao_direct_left

# For Right Side
west build -b xiao_ble -- -DSHIELD=corne_xiao_direct_right
```

### Flashing

1. Enter bootloader mode on the XIAO (Double-click Reset).
2. Copy the `build/zephyr/zmk.uf2` file to the `XIAO-SENSE` drive.

## Directory Structure

Copy the `config` folder into your ZMK repository (e.g., `zmk-config/config`).
