# Phantom

[English](README_EN.md) | [简体中文](README.md)

Phantom is a native macOS privacy protection and file concealment management utility. Built upon macOS low-level filesystem attributes and access control mechanisms, it delivers lightweight, instantaneous, and non-destructive privacy protection for personal documents and sensitive project data.

---

## Overview and Motivation

In daily collaborative environments—such as office work, multi-display presentations, remote screen sharing, or shared Mac workstations—personal files, private photo albums, financial documentation, or proprietary code repositories can easily be exposed through Finder searches, recent item lists, Spotlight queries, or AirDrop discoveries.

Conventional solutions often come with distinct compromises:
- **Cumbersome Container Packaging**: Relying on archive formats or virtual disk images requires full data read-and-write cycles. Concealing or accessing large files can take significant time and carries the risk of data corruption if interrupted;
- **Lack of Credential Decoupling**: Many utilities rely directly on the macOS login password. Once family members, borrowing colleagues, or service technicians know the device unlock code, privacy protection is effectively bypassed;
- **Excessive Privileges and Network Telemetry**: Numerous third-party tools request invasive Full Disk Access for continuous background scanning and bundle analytics modules, expanding the surface for potential data exposure.

**The Design Motivation Behind Phantom**: To build a privacy tool that integrates seamlessly into macOS workflows—leaving original file structures intact, eliminating slow data duplication, and maintaining a credential hierarchy independent of the system password, all while delivering protection in an ultra-lightweight form factor.

---

## Core Advantages

- **In-Place Instant Response**: Leverages native macOS access controls and filesystem attributes directly at the file's original location. Whether handling standard documents or large files, items are concealed or revealed instantly with zero extra disk consumption and no risk of write-interruption corruption.
- **Independent Credentials and Biometric Isolation**: Establishes a dedicated master password decoupled from the macOS login password. Even if someone knows your device unlock password, they cannot access Phantom. Deep Touch ID integration enables instant, friction-free biometric authentication.
- **100% Local Offline Architecture**: Contains zero network communication routines, zero telemetry, and zero cloud uploads. Critical credentials reside strictly within the hardware-backed macOS Keychain.
- **Dual-Layer Fluid Interface**: Features a lightweight Liquid Glass status bar popover for rapid access alongside a structured, dual-column management center, catering to both quick single-item access and organized batch management.
- **Minimal Resource Footprint**: Built purely with native AppKit and SwiftUI without third-party runtime frameworks. The entire application package is approximately 450KB, ensuring minimal memory and background CPU usage.

---

## Feature Tour and Visual Overview

### 1. Independent Credential System and Biometric Unlock

To eliminate the risks associated with shared device passwords, Phantom enforces an independent authentication boundary.

| Figure 1: First-Time Setup & Password Configuration | Figure 2: Lock Screen Auth & Touch ID Trigger |
| :---: | :---: |
| ![Setup Master Password](docs/screenshots/en/1.png) | ![Lock Screen Authentication](docs/screenshots/en/2.png) |

- **Dedicated Master Password**: Initial configuration requires establishing a unique master password (at least 6 characters) with an optional password hint;
- **Touch ID Fast Path**: On Touch ID-enabled Mac hardware and Magic Keyboards, biometric authentication is deeply integrated into the prompt, avoiding the need for repeated keyboard entry;
- **Brute-Force Rate Limiting**: Repeated incorrect password attempts trigger progressive lockouts, extending waiting intervals to safeguard against close-range guessing attempts.

---

### 2. User Notice and Operational Guidelines

Data integrity depends on clear operational awareness. Before accessing the management center for the first time, users are presented with comprehensive usage guidelines.

![User Notice & Guidelines](docs/screenshots/en/3.png)

- **Offline and Zero-Intrusive Principles**: Clarifies that the application operates strictly offline without network access or invasive background disk roaming;
- **In-Place Response Model**: Outlines the technical boundaries of system-level concealment directly on original storage paths;
- **Collaboration Best Practices**: Advises users against targeting active cloud synchronization folders (e.g. iCloud Drive, OneDrive) or download directories directly into locked folders, and recommends unhiding all protected assets prior to application uninstallation.

---

### 3. Structured Dual-Column Management Center

The management window utilizes macOS Liquid Glass materials to present protected assets in an organized, dual-column layout.

| Figure 4: Empty Initial Management State | Figure 5: Populated Asset Index |
| :---: | :---: |
| ![Empty State](docs/screenshots/en/4.png) | ![Populated State](docs/screenshots/en/5.png) |

- **Dedicated Column Partitioning**: The left pane aggregates folders while the right pane organizes individual files, showing item sizes, concealment states, and storage locations at a glance;
- **Live Search Filtering**: A centered search bar dynamically filters items across both columns with instant keystroke response;
- **Direct Drag-and-Drop Ingestion**: Files and folders can be dragged directly from Finder into the window for immediate concealment and registration.

---

### 4. Adaptive Batch Operations and Granular Row Actions

Whether performing quick single-item reveals or reorganizing large collections, Phantom provides responsive controls suited to both scenarios.

| Figure 6: Adaptive Batch Action Bar | Figure 7: Row Actions and Finder Reveal |
| :---: | :---: |
| ![Batch Action Bar](docs/screenshots/en/6.png) | ![Row Actions and Finder Reveal](docs/screenshots/en/7.png) |

- **Adaptive Batch Toolbar**: Select all or toggle custom subsets with a single click. The top bar intelligently adapts its buttons based on the selection state: "Batch Unlock" when all items are locked, "Batch Lock" when all items are revealed, and segmented counters in mixed states;
- **Granular Row Controls**: Each row includes dedicated lock/unlock toggles. When an item is revealed, a "Finder" button opens the directory and highlights the target file;
- **Confirmation Safeguards**: Removing protection requires confirmation via a dedicated modal card to prevent accidental unregistration.

---

### 5. Menu Bar Floating Panel for Rapid Workflow

For routine tasks during focused work sessions, there is no need to keep the full management window open.

![Status Bar Floating Panel](docs/screenshots/en/8.png)

- **Menu Bar Presence**: A discreet keyhole icon indicates current system status, switching to an amber indicator if any protected assets remain unlocked;
- **Recent Items Overview**: The popover displays recently accessed folders and files, allowing immediate in-place unlocking or Finder reveal without interrupting your active workspace;
- **Focus-Loss Auto Dismissal**: Clicking anywhere outside the panel instantly closes and unloads the view to maintain privacy against nearby onlookers.

---

### 6. Preferences and Dedicated Recovery Key Protection

Phantom places complete data control and recovery authority in the user's hands.

![Preferences & Security Spec](docs/screenshots/en/9.png)

- **Interface Language Selection**: Supports instant switching between English and 简体中文;
- **Credential Management**: Facilitates updating the master password and hints at any time;
- **Unique Recovery Key**: During initial setup, a high-entropy Recovery Key is generated. Because Phantom maintains no cloud infrastructure or remote accounts, this key is your sole credential to reset your password and restore access in the event of forgotten credentials. Users should store it securely offline.

---

## System Requirements

- **Operating System**: macOS 14.0 (Sonoma) or later (fully compatible with macOS 15 Sequoia and newer)
- **Hardware Architecture**: Apple Silicon (M1, M2, M3, and M4 series chips)
- **Recommended Peripherals**: Mac models or Magic Keyboards equipped with Touch ID

---

## Installation and Quick Start

1. Download the latest `Phantom-v0.1.0-Beta-en.dmg` from the Releases section;
2. Mount the disk image and drag **Phantom** into your `Applications` folder;
3. Launch Phantom, complete the setup wizard to create your master password, and securely archive your Recovery Key;
4. Click the ghost keyhole icon in the menu bar, or drag target files directly into the management window to begin protection.

---

## Intellectual Property and Licensing

- **Copyright © 2026 Phantom Team. All rights reserved.**
- This software is protected under applicable intellectual property laws and commercial regulations.
- Unauthorized reverse engineering, modification, tampering, or redistribution of any portion of this application is strictly prohibited without explicit written permission.
