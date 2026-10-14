<p align="center">
  <img src="docs/assets/logo.png" width="96" height="96" alt="Phantom Logo" />
</p>

<h1 align="center">Phantom</h1>

<p align="center">
  <strong>Native macOS In-Place File Concealment & Privacy Guard</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-macOS%2014.0%2B-blue?style=flat-square" alt="Platform" />
  <img src="https://img.shields.io/badge/Architecture-Apple%20Silicon-success?style=flat-square" alt="Architecture" />
  <img src="https://img.shields.io/badge/Language-Swift%206-orange?style=flat-square" alt="Language" />
  <img src="https://img.shields.io/badge/Privacy-100%25%20Offline%20%7C%20No%20Telemetry-brightgreen?style=flat-square" alt="Privacy" />
  <img src="https://img.shields.io/badge/License-Proprietary-lightgrey?style=flat-square" alt="License" />
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#core-advantages">Advantages</a> •
  <a href="#feature-tour">Features</a> •
  <a href="#protection-scope">Protection Scope</a> •
  <a href="#system-requirements">Requirements</a> •
  <a href="#quick-start">Quick Start</a> •
  <a href="README_ZH.md">简体中文</a>
</p>

---

## Overview

In collaborative workspaces, presentations, screen shares, or shared-device environments, work files, personal folders, and staging assets can easily be exposed via Finder directory views, Recent Items, Spotlight searches, or AirDrop menus. Traditional encrypted disk containers can take significant time to create and carry data corruption risks on multi-gigabyte files, while relying purely on the macOS login password offers zero privacy isolation when lending a device.

**Phantom** provides native macOS in-place privacy protection: it conceals items instantaneously directly at their original storage paths without data duplication, while establishing an independent master credential to protect your workspace boundaries.

---

## Core Advantages

- **Instant In-Place Concealment**: Operates directly at original storage paths without copying, moving, or format re-encoding, eliminating write-interruption and data loss risks on large files.
- **Independent Credentials & Touch ID**: Dedicated master password paired with Touch ID authentication, decoupled from the macOS login password to protect privacy on shared hardware.
- **Proactive Leak Prevention & Visual Sentinel**: Dynamic visual sentinel in the menu bar displays an amber indicator during active editing and transitions to a conspicuous **red alert** if the management window is closed while items remain unlocked.
- **Local Offline Architecture**: Zero network permissions, zero telemetry, and zero remote communication. Master credentials reside safely in the local macOS Keychain (`ThisDeviceOnly`).
- **Native Lightweight Footprint**: Built purely with AppKit and SwiftUI for minimal system footprint and native macOS Liquid Glass aesthetics.

---

## Feature Tour

### 1. Independent Credentials & Biometric Unlock
Enforces a master password separate from system login, integrated with Touch ID for quick unlock.

| Figure 1: Master Password Setup | Figure 2: Lock Screen & Touch ID |
| :---: | :---: |
| <img src="docs/screenshots/en/1.png" width="420" alt="Master Password Setup" /> | <img src="docs/screenshots/en/2.png" width="420" alt="Lock Screen Authentication" /> |

---

### 2. Operational Notice & Security Guidelines
Presents essential operational rules before first use: clarifies local-only behavior and recommends avoiding targeting active sync drives or download paths directly into locked directories.

<p align="center">
  <img src="docs/screenshots/en/3.png" width="720" alt="User Notice & Guidelines" />
</p>

---

### 3. Structured Dual-Column Management Center
Liquid Glass interface partitioning folders and files into equal columns; features instant search filtering and direct Finder drag-and-drop ingestion.

| Figure 4: Empty Initial State | Figure 5: Populated Asset Index |
| :---: | :---: |
| <img src="docs/screenshots/en/4.png" width="420" alt="Empty Initial State" /> | <img src="docs/screenshots/en/5.png" width="420" alt="Populated Asset Index" /> |

---

### 4. Adaptive Batch Operations & Row Controls
The top toolbar dynamically switches between batch actions based on selection state. Rows provide direct unlock toggles, Finder reveals, and confirmation modals against accidental removal.

| Figure 6: Adaptive Batch Toolbar | Figure 7: Row Actions & Finder Reveal |
| :---: | :---: |
| <img src="docs/screenshots/en/6.png" width="420" alt="Adaptive Batch Toolbar" /> | <img src="docs/screenshots/en/7.png" width="420" alt="Row Actions & Finder Reveal" /> |

---

### 5. Menu Bar Floating Panel & Active Leak Prevention
Resides in the macOS menu bar with an intelligent visual sentinel: displays an amber indicator during active editing and transitions to an eye-catching **red alert** if the management window is closed while items remain unlocked and exposed in Finder.

<p align="center">
  <img src="docs/assets/sentinel_states_en.png" width="760" alt="Status Bar Sentinel States" />
</p>

<p align="center">
  <img src="docs/screenshots/en/8.png" width="440" alt="Status Bar Floating Panel" />
</p>

---

### 6. Preferences & Dedicated Recovery Key
Supports instant bilingual switching and password updates. The high-entropy Recovery Key generated at setup serves as the primary credential to regain access offline.

<p align="center">
  <img src="docs/screenshots/en/9.png" width="720" alt="Preferences & Security Spec" />
</p>

---

## Protection Scope

- **Intended Scenarios**: Built for workplace privacy protection, presentation shields, screen sharing deterrence, and preventing bystander snooping on shared Macs.
- **In-Place Architecture**: Prioritizes instantaneous response and zero data duplication overhead without modifying original file payloads.
- **Offline Assurance**: The binary operates strictly locally with zero network capabilities (`com.apple.security.network` permissions are strictly omitted).
- **Comprehensive Defense**: For high-threat environments requiring defense against physical hardware seizure or forensic analysis, users should combine Phantom with macOS FileVault full-disk encryption.

---

## System Requirements

- **Operating System**: macOS 14.0 (Sonoma) or later
- **Architecture**: Apple Silicon (M1 / M2 / M3 / M4 series chips)
- **Recommended Hardware**: Mac models or Magic Keyboards equipped with Touch ID

---

## Quick Start

1. Download `Phantom-v0.1.0-Beta-en.dmg` (or Chinese `-v0.1.0-Beta.dmg`) from Releases;
2. Mount the disk image and drag **Phantom** into your `Applications` folder;
3. Launch the app, configure your master password, and securely archive your Recovery Key;
4. Click the menu bar icon or drag files into the management window to begin protection.

---

## Licensing & Governance

- **Copyright © 2026 Phantom Team. All rights reserved.**
- Subject to the terms of the proprietary [LICENSE](LICENSE).
- Security policy and vulnerability reporting: [SECURITY.md](SECURITY.md).
- Privacy policy and offline commitments: [PRIVACY.md](PRIVACY.md).
