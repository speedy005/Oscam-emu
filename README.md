# 🚀 OSCam-Emu | Open Source CAM with Emulator

<p align="center">
  <img src="https://img.shields.io/badge/OSCam--Emu-Open%20Source-00ADD8?style=for-the-badge&logo=github" alt="OSCam-Emu Open Source">
  <img src="https://img.shields.io/badge/Platform-Multi--Architecture-6C5CE7?style=for-the-badge" alt="Multi Architecture">
  <img src="https://img.shields.io/badge/License-GPL--3.0%2B-2EA44F?style=for-the-badge" alt="GPL License">
</p>

<p align="center">
  <strong>Powerful. Flexible. Open Source.</strong>
  <br>
  <strong>Leistungsstark. Flexibel. Open Source.</strong>
  <br><br>
  An open-source CAM project with emulator support, flexible build options and cross-compilation capabilities.
  <br>
  Ein Open-Source-CAM-Projekt mit Emulator-Unterstützung, flexiblen Build-Optionen und Cross-Compilation.
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
</p>

<p align="center">
  <a href="https://github.com/speedy005/Oscam-emu">📦 Repository</a> •
  <a href="https://github.com/speedy005/Oscam-emu/commits">🕘 History</a> •
  <a href="https://github.com/speedy005/Oscam-emu/issues">🐛 Issues</a> •
  <a href="https://github.com/speedy005/Oscam-emu/discussions">💬 Discussions</a>
</p>

---

## 📚 Table of Contents

- [🇩🇪 Deutsch](#-deutsch)
  - [✨ Projektübersicht](#-projektübersicht)
  - [⚡ Schnellstart](#-schnellstart)
  - [🔧 Cross-Compilation](#-cross-compilation-1)
  - [🧰 Abhängigkeiten](#-abhängigkeiten)
  - [📖 Dokumentation und Support](#-dokumentation-und-support)
- [🇬🇧 English](#-english)
  - [✨ Project Overview](#-project-overview)
  - [⚡ Quick Start](#-quick-start)
  - [🔧 Cross-Compilation](#-cross-compilation-2)
  - [🧰 Dependencies](#-dependencies)
  - [📖 Documentation and Support](#-documentation-and-support)
- [📜 License](#-license)

---

# 🇩🇪 Deutsch

## ✨ Projektübersicht

**OSCam-Emu** ist ein Open-Source-CAM-Projekt mit Emulator-Unterstützung. Es basiert auf dem Streamboard mp-cardserver 0.9d von dukat und wurde über viele Jahre von zahlreichen Entwicklern erweitert und weiterentwickelt.

Das Projekt bietet ein flexibles Build-System, Unterstützung für unterschiedliche Prozessorarchitekturen sowie optionale Schnittstellen und externe Bibliotheken.

### 🌟 Highlights

- 🧩 Erweiterbares Build-System
- 🖥️ Unterstützung unterschiedlicher Zielarchitekturen
- 🔧 Flexible Kompilierungsoptionen
- 🌐 Cross-Compilation für geeignete Embedded-Plattformen
- 📦 Optionale Bibliotheken und Hardware-Schnittstellen
- 📖 Dokumentation und Community-Support

## ⚡ Schnellstart

### Voraussetzungen

Stelle sicher, dass Git, GNU Make, ein geeigneter C-Compiler und die erforderlichen Build-Werkzeuge installiert sind.

### 1. Repository klonen

```bash
git clone https://github.com/speedy005/Oscam-emu.git
cd Oscam-emu
```

### 2. Kompilieren

```bash
make
```

### 3. Build-Optionen anzeigen

```bash
make help
```

Weitere Build- und Konfigurationshinweise findest du in `README.build` und `README.config`, sofern diese Dateien im Repository vorhanden sind.

## 🔧 Cross-Compilation

Mit einer passenden Toolchain lässt sich OSCam-Emu für unterstützte Zielarchitekturen kompilieren.

**Beispiel: SH4**

```bash
make CROSS=sh4-linux-
```

Wenn die Toolchain nicht im `PATH` liegt, kann das Compiler-Präfix mit vollständigem Pfad angegeben werden:

```bash
make CROSS=/opt/STM/STLinux-2.3/devkit/sh4/bin/sh4-linux-
```

Passe den Pfad und das Compiler-Präfix an deine installierte Toolchain an.

📘 [Cross-Compilation-Dokumentation](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling)

## 🧰 Abhängigkeiten

Standardmäßig benötigt OSCam-Emu keine zusätzlichen externen Bibliotheken, sofern keine optionalen Funktionen aktiviert werden. Für SSL-Unterstützung wird beispielsweise OpenSSL beziehungsweise libcrypto benötigt.

| Funktion | Build-Option |
|---|---|
| OpenSSL / libcrypto | `make USE_LIBCRYPTO=1` |
| USB-Unterstützung | `make USE_LIBUSB=1` |
| PC/SC-Unterstützung | `make USE_PCSC=1` |
| SH4 STAPI | `make USE_STAPI=1` |
| SH4 STAPI5 | `make USE_STAPI5=1` |
| Coolapi | `make USE_COOLAPI=1` |
| AZBOX | `make USE_AZBOX=1` |

### Zusätzliche STAPI-Bibliotheken

Für STAPI wird `liboscam_stapi.a` im Verzeichnis `stapi` unterhalb des Quellverzeichnisses benötigt.

Für STAPI5 wird entsprechend `liboscam_stapi5.a` in diesem Verzeichnis benötigt.

Bitte beachte die jeweiligen Anforderungen und Lizenzbedingungen der externen Bibliotheken.

## 📖 Dokumentation und Support

| Ressource | Beschreibung |
|---|---|
| [OSCam Wiki](https://git.streamboard.tv/common/oscam/-/wikis/home) | Allgemeine Dokumentation |
| [Building OSCam](https://git.streamboard.tv/common/oscam/-/wikis/BuildingOscam) | Build-Anleitung |
| [CrossCompiling](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling) | Toolchains und Cross-Compilation |
| [Konfigurationswiki](https://wiki.streamboard.tv/wiki/OSCam/de/Config/oscam.conf) | Konfigurationsreferenz |
| [GitHub Issues](https://github.com/speedy005/Oscam-emu/issues) | Fehler und Verbesserungsvorschläge |
| [GitHub Discussions](https://github.com/speedy005/Oscam-emu/discussions) | Fragen und Diskussionen |

Handbuchseiten und Konfigurationsbeispiele können sich außerdem im Verzeichnis `Distribution/doc` befinden.

### 🤝 Mitwirken

Fehlerberichte, konstruktive Rückmeldungen und technische Verbesserungsvorschläge sind willkommen. Bitte gib bei Fehlern möglichst genaue Schritte zur Reproduktion, relevante Build-Ausgaben und Informationen zur Zielplattform an.

---

# 🇬🇧 English

## ✨ Project Overview

**OSCam-Emu** is an open-source CAM project with emulator support. It is based on the Streamboard mp-cardserver 0.9d by dukat and has been extended and developed by numerous contributors over the years.

The project provides a flexible build system, support for different CPU architectures, and optional interfaces and external libraries.

### 🌟 Highlights

- 🧩 Extensible build system
- 🖥️ Support for different target architectures
- 🔧 Flexible compilation options
- 🌐 Cross-compilation for supported embedded platforms
- 📦 Optional libraries and hardware interfaces
- 📖 Documentation and community support

## ⚡ Quick Start

### Requirements

Make sure Git, GNU Make, a suitable C compiler, and the required build tools are installed.

### 1. Clone the repository

```bash
git clone https://github.com/speedy005/Oscam-emu.git
cd Oscam-emu
```

### 2. Compile

```bash
make
```

### 3. Explore build options

```bash
make help
```

For additional build and configuration guidance, consult `README.build` and `README.config`, if these files are present in the repository.

## 🔧 Cross-Compilation

With a suitable toolchain, OSCam-Emu can be compiled for supported target architectures.

**Example: SH4**

```bash
make CROSS=sh4-linux-
```

If the toolchain is not available in your `PATH`, specify the compiler prefix using its full path:

```bash
make CROSS=/opt/STM/STLinux-2.3/devkit/sh4/bin/sh4-linux-
```

Adjust the path and compiler prefix to match your installed toolchain.

📘 [Cross-compilation documentation](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling)

## 🧰 Dependencies

By default, OSCam-Emu does not require additional external libraries unless optional features are enabled. For example, SSL support requires OpenSSL or libcrypto.

| Feature | Build option |
|---|---|
| OpenSSL / libcrypto | `make USE_LIBCRYPTO=1` |
| USB support | `make USE_LIBUSB=1` |
| PC/SC support | `make USE_PCSC=1` |
| SH4 STAPI | `make USE_STAPI=1` |
| SH4 STAPI5 | `make USE_STAPI5=1` |
| Coolapi | `make USE_COOLAPI=1` |
| AZBOX | `make USE_AZBOX=1` |

### Additional STAPI Libraries

For STAPI support, `liboscam_stapi.a` is required in the `stapi` directory under the source tree.

For STAPI5 support, place `liboscam_stapi5.a` in the same directory.

Please review the requirements and licensing terms for the respective external libraries.

## 📖 Documentation and Support

| Resource | Description |
|---|---|
| [OSCam Wiki](https://git.streamboard.tv/common/oscam/-/wikis/home) | General documentation |
| [Building OSCam](https://git.streamboard.tv/common/oscam/-/wikis/BuildingOscam) | Build instructions |
| [CrossCompiling](https://git.streamboard.tv/common/oscam/-/wikis/CrossCompiling) | Toolchains and cross-compilation |
| [Configuration Wiki](https://wiki.streamboard.tv/wiki/OSCam/de/Config/oscam.conf) | Configuration reference |
| [GitHub Issues](https://github.com/speedy005/Oscam-emu/issues) | Bugs and feature requests |
| [GitHub Discussions](https://github.com/speedy005/Oscam-emu/discussions) | Questions and discussions |

Manual pages and configuration examples may also be available in the `Distribution/doc` directory.

### 🤝 Contributing

Bug reports, constructive feedback, and technical improvement suggestions are welcome. When reporting an issue, please include reproduction steps, relevant build output, and details about your target platform.

---

# 📜 License

**OSCam-Emu — Open Source CAM with Emulator**

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
  <em>Open Source • Flexible Builds • Community Driven</em>
  <br><br>
  <a href="https://github.com/speedy005/Oscam-emu">📦 Repository</a> ·
  <a href="https://github.com/speedy005/Oscam-emu/issues">🐛 Issues</a> ·
  <a href="https://github.com/speedy005/Oscam-emu/discussions">💬 Discussions</a>
</p>
