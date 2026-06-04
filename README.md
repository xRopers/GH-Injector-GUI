# Qt GH DLL Injector Graphical User Interface

This repository hosts a customized frontend for the official [Guided Hacking DLL Injector](https://guidedhacking.com). This specific version is fully compatible with MSVC 2019, MSVC 2022, MSVC 2026, and Qt version 6.11.1 and updated to DOTNet 10.

## 📌 Project History & Evolution
The original frontend for the GH Injector was built using AutoIt. In 2020, [Kage](https://guidedhacking.com) and [Multikill](https://github.com) developed the initial framework for this modern Qt-based interface. Over the subsequent five years, Broihon has continually updated, maintained, and enhanced the codebase.

## 🖼️ Interface Preview
![Project Interface Image](https://github.com)

## 🎓 Official Guided Hacking Educational Resources
*   [The Game Hacking Bible](https://guidedhacking.com) – Comprehensive 70-chapter game hacking course.
*   [Computer Science 420](https://guidedhacking.com) – 8-chapter curriculum covering Computer Science, Data Types, and Assembly.
*   [Binary Exploit Development](https://guidedhacking.com) – 9-chapter exploit development series curated by a certified OSED.
*   [Game Hacking Shenanigans](https://guidedhacking.com) – 20-lesson instructional course utilizing Cheat Engine.
*   [Python Game Hacking Course](https://guidedhacking.com) – 7-chapter guide on internal and external Python manipulation.
*   [Python App Reverse Engineering](https://guidedhacking.com) – 5-part lesson series focused on reversing Python applications.
*   [Web Browser Game Hacking](https://guidedhacking.com) – 4-chapter introduction to hacking JavaScript-based web games.
*   [Roblox Exploiting Course](https://guidedhacking.com) – 7 premium scripting and exploitation lessons for the Roblox platform.
*   [Java Reverse Engineering Course](https://guidedhacking.com) – 5-chapter foundational blueprint for reversing Java software.
*   [Java Game Hacking Course](https://guidedhacking.com) – 6-chapter introduction to analyzing and modifying Java games.

## 🛠️ Compilation & Build Instructions

### 1. IDE Setup
*   Download and install [Visual Studio 2019, 2022, or 2026](https://microsoft.com).

### 2. Qt Framework Installation
*   Acquire the [Qt Online Installer](https://qt.io).
*   Add **Qt 5.15.2 -> MSVC 2019/2022/2026 32-bit** to your installation components.
*   Add **Qt 5.15.2 -> MSVC 2019/2022/2026 64-bit** to your installation components.

### 3. Visual Studio Integration
*   Download and integrate the [Qt VS Tools extension](https://visualstudio.com) compatible with your version of Visual Studio.

### 4. Static Qt Dependencies
*   Download the static binaries from the [Martin Rotter Minimalistic Build Releases](https://github.com).
*   Extract the contents to your local Qt build directory, ensuring the path mirrors your compiler version setup (e.g., `C:\Qt\5.15.2\qt-5.15.2-static-msvc2019-x86_64` or equivalent updated toolset path).

### 5. Configuring Visual Studio Environment
1.  Navigate via the top menu bar: **Qt VS Tools** -> **Qt Options** -> **Add**. Provide your compiler-specific installation paths:
    *   `C:\Qt\5.15.2\msvc2019` (or newer MSVC target folders)
    *   `C:\Qt\5.15.2\msvc2019_64`
    *   `C:\Qt\5.15.2\qt-5.15.2-static-msvc2019-x86_64`
2.  Open the project properties: **Project** -> **Properties** -> **Qt Project Settings** -> **Qt Installation**. Map the target architectures based on your active toolset:
    *   **x86** target -> Select your default MSVC environment
    *   **x64** target -> Select your 64-bit MSVC environment
    *   **x64_static** target -> Select your static MSVC build environment
3.  Restart your Visual Studio IDE instance to refresh IntelliSense.
4.  Compile and build the solution.

### 6. Linking the Injector Library
1.  Clone or download the [GH-Injector-Library](https://github.com).
2.  In the library project settings, update the C++ Language Standard compiler flag to `std:c++20` (or `std:c++latest` for newer compilers).
3.  Compile the library files and transfer the compiled binaries directly into this project's folder directory.

## ✨ Core Application Features
*   **Advanced Drag & Drop:** Custom drag-and-drop mechanism engineered to successfully bypass UIPI restrictions.
*   **CLI Functionality:** Native command-line interface for headless execution.
*   **Shortcut Utility:** Automated desktop and system shortcut generator.
*   **Automated Execution:** Built-in engine supporting automatic target process injection.

## 🤝 Project Credits & References
*   [Guided Hacking DLL Injector Core](https://guidedhacking.com)
*   [Jorgen-VikingGod / Qt-Frameless-Window-DarkStyle Framework](https://github.com)
*   [fpoussin / Qt5-MSVC-Static Build Script Patterns](https://github.com)


## License
All original licenses of all used components Qt are respected with the additional exception that compiling, linking or using is allowed. Go to Qt website and check for License.


GuidedHacking® - The Game Hacking Bible® - © 2025 Guided Hacking LLC. All Rights Reserved.
