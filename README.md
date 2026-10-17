<div align="center">
  <h1>⌨️ AspirersCMD</h1>
  <p><b>The Intelligent Windows Terminal. Reimagined.</b></p>

  <a href="https://github.com/yourusername/AspirersCMD/releases">
    <img src="https://img.shields.io/badge/Download-AspirersCMD.exe-success?style=for-the-badge&logo=windows" alt="Download EXE">
  </a>
  <br><br>
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Platform-Windows-lightgrey?style=flat-square&logo=windows" alt="Platform">
  <img src="https://img.shields.io/badge/Release-v1.0.0-informational?style=flat-square" alt="Release">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">
</div>

---

**AspirersCMD** is a standalone Windows executable (`.exe`) that completely reinvents the classic Command Prompt. It bridges the gap between a traditional shell and a modern IDE by introducing a powerful, context-aware autocompletion engine. 

Gone are the days of memorizing obscure command flags or syntax. AspirersCMD brings a "Minecraft-style" or VS Code-like experience to the Windows CLI, wrapped in a sleek, dark-themed, hacker-inspired interface.

## 📸 Preview

*(Add a screenshot or a GIF of your terminal here! People love seeing the UI in action. Just drag and drop an image right into this file on GitHub).*

---

## ✨ Why AspirersCMD?

### 🧠 Context-Aware Autocompletion (The Core)
This isn't just a simple text search. The engine analyzes the syntax of your command in real-time.
*   **Command Prediction:** Type `net` and it immediately suggests `user`, `share`, `start`, `stop`, or `use`.
*   **Flag/Parameter Prediction:** Type `ipconfig /` and the engine knows you need flags, instantly suggesting `/all`, `/release`, `/renew`, or `/flushdns`.
*   **Smart Floating UI:** The suggestion box calculates the cursor's absolute position on your screen and dynamically chooses to render *above* or *below* your text. It will never be cut off by the window edge.

### ⚡ Asynchronous System Profiling
You don't have to wait for the terminal to load. 
*   The UI appears instantly.
*   In the background, invisible threads silently execute `wmic` and `ipconfig /all`.
*   It extracts your CPU model, RAM size, OS build, IPv4, MAC address, and Gateway.
*   The data is seamlessly injected into the ASCII splash screen without freezing the interface for a single millisecond.

### 🎨 Generative ASCII Splash Screen
Instead of a boring text dump, AspirersCMD greets you with a mathematically generated, 3D-like ASCII art logo. The characters are color-graded (using Tkinter text tags) to simulate lighting and depth, and the layout adapts dynamically to your window size.

### 🛡️ True CMD Emulation
*   **Locked Cursor:** You cannot click back and edit or delete previous commands. The cursor is strictly locked to the active prompt line.
*   **Native History:** Use the `↑` and `↓` arrow keys to cycle through your previously executed commands, just like in a real terminal.
*   **Silent Execution:** Commands are executed using Python's `subprocess` module with hidden window flags (`creationflags`), completely preventing ugly black CMD windows from flashing on your screen.

---

## 🚀 Quick Start (For End Users)

Since this project is compiled into a portable executable, **you do not need to install Python to use it.**

1. Go to the **[Releases]** tab on the right side of this GitHub repository.
2. Download the latest `AspirersCMD.exe`.
3. Double-click to run. 

> ⚠️ **Note on Windows Defender / SmartScreen:**
> Because the `.exe` is compiled with PyInstaller and lacks an expensive corporate digital signature, Windows Defender or SmartScreen might flag it as an unknown application. **This is a standard false positive.** 
> Click **"More info"** and then **"Run anyway"** to launch the terminal.

---

## 🕹️ Usage Guide

Using AspirersCMD feels like a cheat code for Windows. Here is how to master it:

1. **Just start typing:** Let's say you want to check your IP configuration. Just type `ipc`.
2. **Autocomplete:** A green suggestion box appears. Press `Tab` to auto-complete it to `ipconfig`.
3. **Add Flags:** Type a space and a forward slash: `ipconfig /`. The box appears again with `/all` and `/flushdns`. Press `Tab` to select, then `Enter` to execute.
4. **Navigate History:** Press `↑` to recall your last command.

---

## 💻 Building from Source (For Developers)

If you want to modify the code, add new commands to the dictionary, or tweak the aesthetics, follow these steps:

### Prerequisites
*   **Python 3.8+**
*   No external libraries required! (Uses standard `tkinter`, `subprocess`, `threading`, `os`, `sys`, `re`).

### Run Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/AspirersCMD.git
