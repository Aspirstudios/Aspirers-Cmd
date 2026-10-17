# AspirersCMD

**The Intelligent Windows Terminal. Reimagined.**

<a href="https://github.com/Aspirstudios/Aspirers-Cmd/releases">
  <img src="https://img.shields.io/badge/Download-AspirersCMD.exe-success?style=for-the-badge&logo=windows" alt="Download EXE">
</a>

<br>

<img src="https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python" alt="Python"> <img src="https://img.shields.io/badge/Platform-Windows-lightgrey?style=flat-square&logo=windows" alt="Platform"><img src="https://img.shields.io/badge/Release-v1.0.0-informational?style=flat-square" alt="Release"> <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">

---

**AspirersCMD** is a standalone Windows executable (`.exe`) that completely reinvents the classic Command Prompt. It bridges the gap between a traditional shell and a modern IDE by introducing a powerful, context-aware autocompletion engine. 

Gone are the days of memorizing obscure command flags. AspirersCMD brings a "Minecraft-style" experience to the Windows CLI, wrapped in a sleek, dark-themed interface, while maintaining the classic 80x25 CMD window proportions.

## Core Features

### Context-Aware Autocompletion
The engine analyzes your command syntax in real-time. It does not just guess the first word.
*   **Command Prediction:** Type `net` and it immediately suggests `user`, `share`, `start`, `stop`, or `use`.
*   **Flag/Parameter Prediction:** Type `ipconfig /` and the engine knows you need flags, instantly suggesting `/all`, `/release`, `/renew`, or `/flushdns`.
*   **Smart Floating UI:** The suggestion box calculates the cursor's absolute position on your screen and dynamically chooses to render above or below your text. It will never be cut off by the window edge.
*   **Controls:** Navigate suggestions with <kbd>Up</kbd> / <kbd>Down</kbd> and autocomplete with <kbd>Tab</kbd>.

### Asynchronous System Profiling
You do not have to wait for the terminal to load. 
*   The UI appears instantly.
*   In the background, invisible threads silently execute `wmic` and `ipconfig /all`.
*   It extracts your CPU model, RAM size, OS build, IPv4, MAC address, and Gateway.
*   The data is seamlessly aligned to the right side of the screen without freezing the interface for a single millisecond.

### True CMD Emulation
*   **Locked Cursor:** You cannot click back and edit or delete previous commands. The cursor is strictly locked to the active prompt line.
*   **Native History:** Use the <kbd>Up</kbd> and <kbd>Down</kbd> arrow keys to cycle through your previously executed commands.
*   **Silent Execution:** Commands are executed using Python's `subprocess` module with hidden window flags, completely preventing ugly black CMD windows from flashing on your screen.

---

## Quick Start (For End Users)

Since this project is compiled into a portable executable, **you do not need to install Python to use it.**

1. Go to the **[Releases](https://github.com/Aspirstudios/Aspirers-Cmd/releases)** tab on the right side of this GitHub repository.
2. Download the latest `AspirersCMD.exe`.
3. Double-click to run. 

> **Note on Windows Defender / SmartScreen:**
> Because the `.exe` is compiled with PyInstaller and lacks a corporate digital signature, Windows Defender might flag it as an unknown application. **This is a standard false positive.** 
> Click **"More info"** and then **"Run anyway"** to launch the terminal.

---

## Usage Guide

1. Start typing a command, e.g., `ipc`.
2. A box appears. Press <kbd>Tab</kbd> to auto-complete it to `ipconfig`.
3. Type a space and a forward slash: `ipconfig /`.
4. The box appears again with `/all` and `/flushdns`. Press <kbd>Tab</kbd> to select.
5. Hit <kbd>Enter</kbd> to execute.

---

## Building from Source (For Developers)

If you want to modify the code, add new commands to the dictionary, or tweak the aesthetics, follow these steps:

### Prerequisites
*   **Python 3.8+**
*   No external libraries required (Uses standard `tkinter`, `subprocess`, `threading`, `os`, `sys`, `re`).

### Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/Aspirstudios/Aspirers-Cmd.git

   
---

### 2. Release Notes (For the GitHub Release Tab)

Copy and paste this into the description box when you create your Release:

```markdown
# AspirersCMD v1.0.0

**The Intelligent Windows Terminal.**

---

Welcome to the very first official release of **AspirersCMD**. 

Forget everything you know about the classic, clunky Command Prompt. This release brings a sleek, dark-themed interface, real-time context-aware autocompletion, and zero-latency system profiling to your daily workflow, all while maintaining the classic CMD window size.

### What's New in v1.0.0?

*   **Context-Aware Autocomplete:** Type `ipconfig /` and watch the terminal instantly suggest flags like `/all` or `/flushdns`. Navigate with <kbd>Up</kbd>/<kbd>Down</kbd> and autocomplete with <kbd>Tab</kbd>.
*   **Asynchronous Profiling:** The app opens instantly. Background threads fetch your CPU, RAM, and Network data, displaying it cleanly on the right side of the splash screen.
*   **True CMD Emulation:** 
    *   **Locked Cursor:** You cannot edit or delete previous commands.
    *   **Silent Execution:** No annoying black CMD windows flashing on your screen.

---

### How to Install

1. Download the **`AspirersCMD.exe`** file attached below.
2. Put it in any folder you like (e.g., your Desktop).
3. Double-click to run. No Python installation required.

> **Windows Defender Notice:**  
> Because this executable is compiled using PyInstaller and does not have an expensive corporate digital signature, Windows SmartScreen might show a warning saying *"Windows protected your PC"*. 
> **This is a standard false positive.** Simply click on **"More info"** and then **"Run anyway"**.

---

**Built With:** Python 3, Tkinter, Threading, Subprocess.
**License:** MIT.

*Developed by Bruno  (Aspir Studio). If you like the project, consider giving it a star on the repository.*
