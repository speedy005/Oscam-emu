# 🚀 OSCam-Emu — Open Source CAM with Emulator

<p align="center">
  <strong>An open-source Conditional Access Module with emulator support.</strong>
  <br>
  <em>Ein Open-Source-Conditional-Access-Modul mit Emulator-Unterstützung.</em>
</p>

<p align="center">
  <a href="https://github.com/speedy005/Oscam-emu/actions/workflows/build-oscam.yml">
    <img src="https://github.com/speedy005/Oscam-emu/actions/workflows/build-oscam.yml/badge.svg" alt="Build Status">
  </a>
  <a href="https://github.com/speedy005/Oscam-emu/actions/workflows/sync-gitlab.yml">
    <img src="https://github.com/speedy005/Oscam-emu/actions/workflows/sync-gitlab.yml/badge.svg" alt="GitLab Sync">
  </a>
  <a href="https://github.com/speedy005/Oscam-emu/actions/workflows/create-patch.yml">
    <img src="https://github.com/speedy005/Oscam-emu/actions/workflows/create-patch.yml/badge.svg" alt="Patch Workflow">
  </a>
  <br>
  <a href="https://github.com/speedy005/Oscam-emu">
    <img src="https://img.shields.io/badge/GitHub-Project-181717?style=flat&logo=github" alt="Project Repository">
  </a>
  <a href="https://www.gnu.org/licenses/gpl-3.0.html">
    <img src="https://img.shields.io/badge/License-GPL--3.0--or--later-blue.svg" alt="GPL License">
  </a>
</p>

---

## 📑 Quick Navigation

- [🇩🇪 Deutsch](#-deutsch)
- [🇬🇧 English](#-english)
- [🔨 Building from Source](#-building-from-source)
- [🧰 Dependencies](#-dependencies)
- [🌐 Cross-Compilation](#-cross-compilation)
- [📖 Wiki and Documentation](#-wiki-and-documentation)
- [🛠️ Help and Support](#️-help-and-support)
- [📜 License](#-license)

---

# 🇩🇪 Deutsch

## ✨ Überblick

**OSCam-Emu** ist ein Open-Source-CAM-Projekt mit Emulator-Unterstützung. Das Projekt basiert auf dem Streamboard mp-cardserver 0.9d von dukat und wurde seitdem von zahlreichen Entwicklern erweitert und weiterentwickelt.

Das Projekt bietet ein flexibles Build-System, Unterstützung für verschiedene Prozessorarchitekturen und optionale externe Bibliotheken.

## 📦 Repository

**Projekt:** [speedy005/Oscam-emu](https://github.com/speedy005/Oscam-emu)

Die ursprüngliche OSCam-Emu-Projekt- und CI-Referenz befindet sich unter [oscam-mirror/oscam-emu](https://github.com/speedy005/Oscam-emu).

## 🔨 OSCam-Emu aus dem Quellcode erstellen

### Voraussetzungen

- Git
- GNU Make
- Ein geeigneter C-Compiler und die erforderlichen Build-Werkzeuge
- Optional: zusätzliche Entwicklungsbibliotheken, abhängig von den aktivierten Funktionen

### Repository klonen

```bash
git clone https://github.com/speedy005/Oscam-emu.git
cd Oscam-emu
```

### Kompilieren

```bash
make
```

Für weitere Build-Optionen und Konfigurationsbeispiele stehen die Dateien `README.build` und `README.config` sowie die Make-Hilfe zur Verfügung:

```bash
make help
```

📖 **Build-Dokumentation:** [Building OSCam](https://git.streamboard.tv/common/oscam/-/wikis/BuildingOscam)

## 🌐 Cross-Compilation

OSCam-Emu kann mit einer passenden Toolchain für unterschiedliche Zielarchitekturen kompiliert werden.

### 1. Toolchain installieren

Installiere zunächst die passende Toolchain für deine Zielplattform. Vorbereitete Toolchains und weitere Hinweise findest du hier:

[Cross-Compiling – OSCam Wiki](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling)

### 2. Für eine Zielarchitektur kompilieren

Beispiel für eine SH4-Toolchain:

```bash
make CROSS=sh4-linux-
```

Wenn sich die Compiler nicht im `PATH` befinden, kann der vollständige Pfad angegeben werden:

```bash
make CROSS=/opt/STM/STLinux-2.3/devkit/sh4/bin/sh4-linux-
```

Passe den Toolchain-Pfad und das Compiler-Präfix an deine Umgebung an.

## 🧰 Abhängigkeiten

OSCam-Emu benötigt standardmäßig keine zusätzlichen externen Bibliotheken, sofern keine optionalen Funktionen aktiviert werden. Für SSL-Unterstützung wird beispielsweise OpenSSL benötigt.

| Funktion | Make-Option |
|---|---|
| OpenSSL / libcrypto | `make USE_LIBCRYPTO=1` |
| USB-Unterstützung | `make USE_LIBUSB=1` |
| PC/SC-Unterstützung | `make USE_PCSC=1` |
| SH4 STAPI | `make USE_STAPI=1` |
| SH4 STAPI5 | `make USE_STAPI5=1` |
| Coolapi | `make USE_COOLAPI=1` |
| AZBOX | `make USE_AZBOX=1` |

### Zusätzliche STAPI-Bibliotheken

Für STAPI-Unterstützung muss `liboscam_stapi.a` im Verzeichnis `stapi` unterhalb des OSCam-Quellverzeichnisses liegen.

Für STAPI5-Unterstützung wird entsprechend `liboscam_stapi5.a` im Verzeichnis `stapi` benötigt.

Bitte beachte die Dokumentation und Lizenzbedingungen der jeweiligen externen Bibliotheken.

## 📖 Wiki und Dokumentation

- **OSCam Wiki:** [Streamboard Wiki](https://git.streamboard.tv/common/oscam/-/wikis/home)
- **Build-Anleitung:** [Building OSCam](https://git.streamboard.tv/common/oscam/-/wikis/BuildingOscam)
- **Cross-Compilation:** [CrossCompiling](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling)
- **Konfigurationsreferenz:** [oscam.conf](https://wiki.streamboard.tv/wiki/OSCam/de/Config/oscam.conf)

Handbuchseiten und Konfigurationsbeispiele befinden sich außerdem im Verzeichnis `Distribution/doc`.

## 🛠️ Hilfe und Support

- 🐛 **Fehler melden:** [GitHub Issues](https://github.com/speedy005/Oscam-emu/issues/new)
- 💬 **Fragen und Diskussionen:** [GitHub Discussions](https://github.com/speedy005/Oscam-emu/discussions)
- 📖 **Konfigurationshilfe:** [OSCam-Konfigurationswiki](https://wiki.streamboard.tv/wiki/OSCam/de/Config/oscam.conf)

Bitte beschreibe Fehler möglichst nachvollziehbar und füge relevante Build-Ausgaben sowie Informationen zur verwendeten Plattform hinzu.

---

# 🇬🇧 English

## ✨ Overview

**OSCam-Emu** is an open-source CAM project with emulator support. It is based on the Streamboard mp-cardserver 0.9d by dukat and has been extended and maintained by many developers over the years.

The project provides a flexible build system, support for different CPU architectures, and optional external libraries.

## 📦 Repository

**Project:** [speedy005/Oscam-emu](https://github.com/speedy005/Oscam-emu)

The original OSCam-Emu project and CI reference can be found at [oscam-mirror/oscam-emu](https://github.com/speedy005/Oscam-emu).

## 🔨 Building from Source

### Requirements

- Git
- GNU Make
- A suitable C compiler and the required build tools
- Optional development libraries, depending on the features enabled

### Clone the Repository

```bash
git clone https://github.com/speedy005/Oscam-emu.git
cd Oscam-emu
```

### Compile

```bash
make
```

For additional build options and configuration examples, consult `README.build`, `README.config`, and the Make help:

```bash
make help
```

📖 **Build documentation:** [Building OSCam](https://git.streamboard.tv/common/oscam/-/wikis/BuildingOscam)

## 🌐 Cross-Compilation

OSCam-Emu can be compiled for different target architectures using an appropriate toolchain.

### 1. Install a Toolchain

Install the toolchain for your target platform. Prebuilt toolchains and further instructions are available here:

[Cross-Compiling – OSCam Wiki](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling)

### 2. Compile for a Target Architecture

Example using an SH4 toolchain:

```bash
make CROSS=sh4-linux-
```

If the compiler binaries are not available in your `PATH`, specify the full path:

```bash
make CROSS=/opt/STM/STLinux-2.3/devkit/sh4/bin/sh4-linux-
```

Adjust the toolchain path and compiler prefix to match your environment.

## 🧰 Dependencies

By default, OSCam-Emu does not require additional external libraries unless optional features are enabled. For example, OpenSSL is required when SSL support is requested.

| Feature | Make option |
|---|---|
| OpenSSL / libcrypto | `make USE_LIBCRYPTO=1` |
| USB support | `make USE_LIBUSB=1` |
| PC/SC support | `make USE_PCSC=1` |
| SH4 STAPI | `make USE_STAPI=1` |
| SH4 STAPI5 | `make USE_STAPI5=1` |
| Coolapi | `make USE_COOLAPI=1` |
| AZBOX | `make USE_AZBOX=1` |

### Additional STAPI Libraries

For STAPI support, place `liboscam_stapi.a` in the `stapi` directory under the OSCam source tree.

For STAPI5 support, place `liboscam_stapi5.a` in the same `stapi` directory.

Please consult the documentation and licensing terms for the respective external libraries.

## 📖 Wiki and Documentation

- **OSCam Wiki:** [Streamboard Wiki](https://git.streamboard.tv/common/oscam/-/wikis/home)
- **Build instructions:** [Building OSCam](https://git.streamboard.tv/common/oscam/-/wikis/BuildingOscam)
- **Cross-compilation:** [CrossCompiling](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling)
- **Configuration reference:** [oscam.conf](https://wiki.streamboard.tv/wiki/OSCam/de/Config/oscam.conf)

Manual pages and configuration examples are also available in the `Distribution/doc` directory.

## 🛠️ Help and Support

- 🐛 **Report a bug:** [GitHub Issues](https://github.com/speedy005/Oscam-emu/issues/new)
- 💬 **Questions and discussions:** [GitHub Discussions](https://github.com/speedy005/Oscam-emu/discussions)
- 📖 **Configuration help:** [OSCam Configuration Wiki](https://wiki.streamboard.tv/wiki/OSCam/de/Config/oscam.conf)

When reporting an issue, please include clear reproduction steps, relevant build output, and information about your target platform.

---

# 📜 License

**OSCam-Emu: Open Source CAM with Emulator**

Copyright (C) 2009–2026 OSCam-Emu developers.

OSCam-Emu is based on the Streamboard mp-cardserver 0.9d by dukat and has been extended and developed by many contributors.

This program is free software: you can redistribute it and/or modify it under the terms of the **GNU General Public License**, as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but **WITHOUT ANY WARRANTY**, without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see [gnu.org/licenses](https://www.gnu.org/licenses/).

For the complete license text, see the `COPYING` file in the root directory or visit the [GNU GPL v3 license page](https://www.gnu.org/licenses/gpl-3.0.html).

---

<p align="center">
  <strong>🚀 OSCam-Emu</strong>
  <br>
  <a href="https://github.com/speedy005/Oscam-emu">Project Repository</a>
  ·
  <a href="https://github.com/speedy005/Oscam-emu/issues">Issue Tracker</a>
  ·
  <a href="https://github.com/speedy005/Oscam-emu/discussions">Discussions</a>
</p>
