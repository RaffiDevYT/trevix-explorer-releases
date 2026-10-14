# 📘 Trevix Explorer — Official Manual Book

> **Platform**: Windows 10 / 11 (Current official installer supports Windows 10/11)  
> **Repository**: [https://github.com/RaffiDevYT/trevix-explorer-releases](https://github.com/RaffiDevYT/trevix-explorer-releases)  
> **License**: Proprietary - see LICENSE file

---

## 📑 Table of Contents

1. [About Trevix Explorer](#1-about-trevix-explorer)
2. [Architecture & Technology](#2-architecture--technology)
3. [Installation & Update Guide](#3-installation--update-guide)
4. [Key Features Overview](#4-key-features-overview)
   - [A. Project & Workspace Management](#a-project--workspace-management)
   - [B. Smart Multi-Frame Test Recorder](#b-smart-multi-frame-test-recorder)
   - [C. Visual Test Editor & Interactive Debugger](#c-visual-test-editor--interactive-debugger)
   - [D. Real-time Test Runner & Console Logger](#d-real-time-test-runner--console-logger)
   - [E. Test Scenario Matrix & Export (Excel & HTML)](#e-test-scenario-matrix--export-excel--html)
   - [F. Integrated Auto-Updater](#f-integrated-auto-updater)
   - [G. Trevix API Studio & Testing](#g-trevix-api-studio--testing)
   - [H. Automated API Collection Runner](#h-automated-api-collection-runner)
   - [I. Local API Mock Server & Dynamic Interpolation](#i-local-api-mock-server--dynamic-interpolation)
5. [Action Steps Reference Table](#5-action-steps-reference-table)
6. [Dynamic Variables](#6-dynamic-variables)
7. [Testing Mechanics & Behaviors](#7-testing-mechanics--behaviors)
8. [Smart Self-Healing](#8-smart-self-healing)
9. [System Requirements & Security](#9-system-requirements--security)
10. [Troubleshooting & FAQ](#10-troubleshooting--faq)

---

## 1. About Trevix Explorer

**Trevix Explorer** is a standalone visual desktop application designed specifically for **Visual End-to-End (E2E) Test Automation**, **API Testing**, and **QA Matrix Documentation**.

It empowers QA Engineers, Testers, and Developers to:

- Record web test flows interactively without writing code (_No-Code Recording_).
- Perform live step-by-step test debugging (_Pause_, _Resume_, _Step Next_) via the Desktop Toolbar or the browser's _Floating In-Page HUD_.
- Customize, reorder, and add assertions or validations visually.
- Convert test scenarios into clean native **Playwright TypeScript (`.spec.ts`)** scripts.
- Test REST/HTTP APIs (including `form-data` and `x-www-form-urlencoded` payloads), run Automated Collection Runners, and utilize Local Mock Servers.
- Generate professional test matrix reports in **Microsoft Excel (`.xlsx`)** and standalone **HTML** formats.

---

## 2. Architecture & Technology

Built with Electron and Playwright.

---

## 3. Installation & Update Guide

### A. New Installation

1. Download the official installer from the [GitHub Releases](https://github.com/RaffiDevYT/trevix-explorer-releases/releases) page.
2. Run the installer (`trevix-explorer-<version>-setup.exe`).
3. Follow the installation wizard and launch the application.

### B. Auto-Update

1. When a new release is available, the update indicator in the app header will light up.
2. Click the update button to view release notes and start background downloading.
3. Click **"Update & Restart"** to apply the latest version.

---

## 4. Key Features Overview

### A. Project & Workspace Management

- **Automatic Folder Isolation**: Sets up `tests/`, `apis/`, and `reports/` folders automatically.
- **Workspace Lock (`.trevix.lock`)**: Secures active sessions.
- **File Action Menu**: Download, Duplicate, Rename, and Delete test specs.

### B. Smart Multi-Frame Test Recorder

- **One-Code Recording**: Captures user interactions across frames, iframes, Select2 dropdowns, and Rich Text Editors.
- **Smart Locator Generator**: Generates stable selectors using IDs, data-testid, attributes (`title`/`aria-label`), and CSS hierarchies.

### C. Visual Test Editor & Interactive Debugger

- Interactive step tables with real-time Playwright TypeScript script previews and live debugger controls (_Pause_, _Resume_, _Step Next_).

### D. API Studio & Collection Runner

- Complete HTTP method support, environment variables, mock servers, and batch execution runners.

---

## 5. Action Steps Quick Reference

| Action        | Description                                                                       |
| :------------ | :-------------------------------------------------------------------------------- |
| `navigate`    | Opens target URL                                                                  |
| `click`       | Clicks target element with optional `allowPopup` support                          |
| `fill`        | Fills form input fields (supports `isSecret` and programmatic fill on `readonly`) |
| `select`      | Selects standard `<select>` or Select2 dropdown options                           |
| `assert`      | Asserts visibility, text, values, or URLs with an 8-second polling retry          |
| `upload_file` | Uploads files with optional dummy fallback                                        |
| `api_request` | Executes HTTP/REST API test requests                                              |

---

## 6. Dynamic Variables

Supported dynamic variables for `fill`, URLs, and API bodies:

- `{{$timestamp}}`
- `{{$randomEmail}}`
- `{{$randomUUID}}`
- `{{$randomPhone}}`
- `{{$randomInt}}`
- `{{$randomName}}`

---

## 7. Security & Privacy

- **100% Local Storage**: All test definitions, credentials, and artifacts remain strictly on your local machine.
- **No Telemetry**: Zero user tracking or analytics.

---

_© 2026 Trevix Explorer — Developed by Rafi Athallah._
