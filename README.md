# STM32 Project Template

## Overview

This is a simple template for STM32F407 projects using CubeMX and HAL. It includes VS Code and CubeIDE support.

## Project Structure

```
STM32_Template/
├─ .vscode/       # VS Code settings
├─ build/         # Compiled .elf, .bin, .hex files
├─ Core/          # Source and header files
├─ Drivers/       # HAL and CMSIS drivers
├─ flash.bat      # Windows flash script
├─ flash.sh       # Linux flash script
├─ Makefile       # Build instructions
└─ README.md      # This file
```

## Getting Started

### 1. Clone Template

```bash
git clone https://github.com/yourusername/stm32-template.git
cd stm32-template
```

### 2. Build

```bash
make all
```

Generates `.elf` and `.bin` in `build/`.

### 3. Flashing (DFU Mode)

1. Set **BOOT0 = 1**.
2. Connect board via USB.
3. Open **STM32CubeProgrammer GUI** → select **USB Device (DFU)** → Connect.
4. Select `.bin` from `build/`, address `0x08000000`, and Start.
5. Remove **BOOT0**, press **RESET**.

> Optional: use `flash.bat` or `flash.sh` if CLI works.

### 5. Notes

* Keep `.vscode/` for IntelliSense.
* `.bin` files are generated in `build/`.
* ST-LINK can be used later for faster flashing.
