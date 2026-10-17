<div align="center">
  <h1><code>AspirersCMD</code></h1>
  <p><b>The Intelligent Windows Terminal. Reimagined.</b></p>

  <a href="https://github.com/Aspirstudios/Aspirers-Cmd/releases">
    <img src="https://img.shields.io/badge/⬇_Download-AspirersCMD.exe-00ff00?style=for-the-badge&logo=windows&logoColor=white&labelColor=000000" alt="Download EXE">
  </a>
  <br><br>
  <img src="https://img.shields.io/badge/Python-3.8+-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Platform-Windows-0078D4?style=flat-square&logo=windows&logoColor=white" alt="Platform">
  <img src="https://img.shields.io/badge/License-MIT-00ff00?style=flat-square&labelColor=000000" alt="License">
</div>

<br>

> **AspirersCMD** is a standalone Windows executable (`.exe`) that completely reinvents the classic Command Prompt. It bridges the gap between a traditional shell and a modern IDE by introducing a powerful, context-aware autocompletion engine.

Gone are the days of memorizing obscure command flags. AspirersCMD brings a "Minecraft-style" experience to the Windows CLI, wrapped in a sleek, dark-themed, hacker-inspired interface.

---

## ⚡ Core Features

### 🧠 Context-Aware Autocompletion
The engine analyzes your command syntax in real-time. It doesn't just guess the first word.
*   Type `net` ➔ Suggests `user`, `share`, `start`.
*   Type `ipconfig /` ➔ Suggests `/all`, `/release`, `/flushdns`.
*   **Controls:** Navigate suggestions with <kbd>↑</kbd> / <kbd>↓</kbd> and autocomplete with <kbd>Tab</kbd>.
*   **Smart Floating UI:** The suggestion box calculates the cursor's absolute position and renders *above* or *below* your text so it never gets cut off.

### ⚡ Asynchronous System Profiling
The UI appears instantly. While you type, background threads silently execute `wmic` and `ipconfig /all` to extract your CPU, RAM, OS build, MAC address, and Gateway. The data is seamlessly injected into the splash screen without freezing the interface.

### 🛡️ True CMD Emulation
*   **Locked Cursor:** You cannot click back and edit previous commands.
*   **Native History:** Use <kbd>↑</kbd> and <kbd>↓</kbd> to cycle through executed commands.
*   **Silent Execution:** Uses `subprocess` with hidden window flags so no ugly black CMD windows flash on your screen.

---

## 🚀 Quick Start

> [!IMPORTANT]  
> **You do not need Python installed to run this.** It is a portable `.exe`.

1. Go to the **[Releases](https://github.com/Aspirstudios/Aspirers-Cmd/releases)** tab.
2. Download the latest `AspirersCMD.exe`.
3. Double-click to run.

> [!WARNING]  
> **Windows Defender / SmartScreen Warning:**  
> Because the `.exe` is compiled with PyInstaller and lacks an expensive corporate digital signature, Windows might flag it as an unknown app. **This is a standard false positive.** Click **"More info"** ➔ **"Run anyway"**.

---

## 🕹️ Usage Guide

1. Start typing a command, e.g., `ipc`.
2. A box appears. Press <kbd>Tab</kbd> to auto-complete it to `ipconfig`.
3. Type a space and a forward slash: `ipconfig /`.
4. The box appears again with `/all` and `/flushdns`. Press <kbd>Tab</kbd> to select.
5. Hit <kbd>Enter</kbd> to execute.

---

<details>
<summary><b>💻 Click here to see Developer / Build Instructions</b></summary>
<br>

**Prerequisites:** Python 3.8+

**Run Locally:**
```bash
git clone https://github.com/Aspirstudios/Aspirers-Cmd.git
cd Aspirers-Cmd
python main.py
