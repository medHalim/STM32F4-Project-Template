# STM32 Project Template

## Overview

This is a simple STM32F407 template project using CubeMX and HAL.
It is designed to work **inside Windows**, with **Windows Subsystem for Linux (WSL2)** used for building via Makefiles.

## Project Structure

```
STM32_Template/
├─ .vscode/       # VS Code configuration files
├─ App/           # Application source and header files
├─ Board_supp/    # Other boards source and header files
├─ build/         # Compiled binaries (.elf, .bin, .hex)
├─ Core/          # STM32 core source and header files
├─ Debug          # Debug files  
├─ Drivers/       # HAL and CMSIS drivers
├─ flash.bat      # Windows DFU flash script
├─ flash.sh       # Linux / WSL2 DFU flash script
├─ Makefile       # Build instructions (used inside WSL2)
├─ Middleware     # Middleware source and header files
└─ README.md      # This file
```

## Getting Started

### 1. Clone Template

```bash
git clone https://github.com/medHalim/STM32F4-Project-Template.git
cd STM32F4-Project-Template-main
```
### 2. Configure pins in STM32CubeMX

Rename `template.ioc` to your liking, open and modify it to generate code.

### 3. Edit code

VS Code is recommended.

### 4. Build inside WSL2

```bash
make all
```

* `.elf` and `.bin` files will appear in `build/`

### 3. Flashing (DFU Mode)

1. Set **BOOT0 = 1**.
2. Connect board via USB.
3. Open **STM32CubeProgrammer GUI** → select **USB Device (DFU)** → Connect.
4. Select `.bin` from `build/`, address `0x08000000`, and Start.
5. Remove **BOOT0**, press **RESET** to run the program.

> Optional: use `flash.bat` (Windows) or `flash.sh` (Linux/WSL2) if CLI flashing is configured.

### Notes

* `.vscode/` is included for IntelliSense and task configurations.
* This template is set up for **Windows + WSL2 workflow**, allowing cross-platform building.
* ST-LINK can be used later for faster flashing.
