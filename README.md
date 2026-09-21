# Qt GH DLL Injector Graphical User Interface

This repository hosts a customized frontend for the official [Guided Hacking DLL Injector](https://guidedhacking.com). This version is updated to .NET 10. The project files use the **v145 toolset (Visual Studio 2026)**. The `Release | x64` configuration builds against **Qt 6.11.1**, while the `Debug`, `Release | x86` and `Static` configurations still reference **Qt 5.15.2** (see [Which Qt version do I need?](#which-qt-version-do-i-need)).

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
*   Download and install [Visual Studio 2026](https://visualstudio.microsoft.com) with the *Desktop development with C++* workload. The projects use `PlatformToolset` v145; to build with an older Visual Studio, retarget the toolset in the project properties first.
*   Clone with submodules (the injector library is a submodule): `git clone --recurse-submodules <repo-url>`, or run `git submodule update --init` in an existing clone.

### 2. Qt Framework Installation
*   Acquire the [Qt Online Installer](https://qt.io).
*   Add **Qt 6.11.1 -> MSVC 2022 64-bit** (installs to `C:\Qt\6.11.1\msvc2022_64`). Required for `Release | x64`; the post-build `windeployqt` step uses this exact path.
*   Add **Qt 5.15.2 -> MSVC 2019 32-bit** and **MSVC 2019 64-bit** if you want to build the `Debug`, `Release | x86` or `Static` configurations.

#### Which Qt version do I need?
| Configuration | Qt install name in the project | Qt version |
|---|---|---|
| Release \| x64 | `6.11.1_msvc2022_64` | 6.11.1 |
| Debug \| x64 | `5.15.2_x64` | 5.15.2 |
| Debug / Release \| x86 | `5.15.2_x86` | 5.15.2 |
| Static \| x64 / x86 | `5.15.2_static` | 5.15.2 (static build) |

### 3. Visual Studio Integration
*   Download and integrate the [Qt VS Tools extension](https://visualstudio.com) compatible with your version of Visual Studio.

### 4. Static Qt Dependencies
*   Download the static binaries from the [Martin Rotter Minimalistic Build Releases](https://github.com).
*   Extract the contents to your local Qt build directory, ensuring the path mirrors your compiler version setup (e.g., `C:\Qt\5.15.2\qt-5.15.2-static-msvc2019-x86_64` or equivalent updated toolset path).

### 5. Configuring Visual Studio Environment
1.  Navigate via the top menu bar: **Qt VS Tools** -> **Qt Options** -> **Add**. Provide your compiler-specific installation paths:
    *   `C:\Qt\6.11.1\msvc2022_64` (name it `6.11.1_msvc2022_64`)
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
1.  The library lives in the `GH Injector Library` submodule (your fork of [GuidedHacking-Injector](https://github.com/xRopers/GuidedHacking-Injector)); make sure it is checked out (see step 1). The library projects are part of this solution.
2.  The library projects already set the C++ language standard to `stdcpp20`; no change is needed.
3.  Build the library and place its binaries next to the GUI executable. The GUI loads the injection library at runtime with `LoadLibraryW`.

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
