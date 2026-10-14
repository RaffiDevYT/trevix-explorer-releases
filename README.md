<div align="center">

# ⚡ Trevix Explorer

**The standalone desktop test automation & E2E recording studio.**

[![Latest Release](https://img.shields.io/github/v/release/RaffiDevYT/trevix-explorer-releases?style=flat-square)](https://github.com/RaffiDevYT/trevix-explorer-releases/releases/latest)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-blue.svg?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078d4.svg?style=flat-square&logo=windows)](https://github.com/RaffiDevYT/trevix-explorer-releases/releases/latest)

[🌐 Official Website](https://trevix.cnplus.id/) • [📋 Changelog](CHANGELOG.md) • [🐞 Report Issue](https://github.com/RaffiDevYT/trevix-landing-page/issues)

**Documentation / Manual Book:**  
[🇮🇩 Bahasa Indonesia (MANUAL_BOOK.md)](MANUAL_BOOK.md) • [🇬🇧 English (MANUAL_BOOK_EN.md)](MANUAL_BOOK_EN.md)

---

</div>

## 📥 Official Download Mirrors

Choose the official standalone binary for your operating system (currently Windows 10/11 only):

| Platform    | Type                     | Architecture   | Download                                                                                      | Verification     |
| :---------- | :----------------------- | :------------- | :-------------------------------------------------------------------------------------------- | :--------------- |
| **Windows** | Setup Installer (`.exe`) | `x64` (64-bit) | [**Download Latest**](https://github.com/RaffiDevYT/trevix-explorer-releases/releases/latest) | SHA-256 Included |

> 💡 **Auto-Update**: Trevix Explorer checks for updates automatically and notifies you when a new version is available. The download starts only after you confirm.

---

## 📖 About Trevix Explorer

**Trevix Explorer** adalah aplikasi desktop visual mandiri yang dirancang khusus untuk kebutuhan **Visual End-to-End (E2E) Test Automation**, **API Testing**, dan **Dokumentasi Matriks QA**.

Aplikasi ini memungkinkan QA Engineer, Tester, dan Developer untuk merekam interaksi browser tanpa menulis kode, mengelola langkah pengujian secara visual, melakukan _debugging_ eksekusi secara langsung, menguji API REST dengan mock server, serta menghasilkan laporan Excel atau HTML profesional secara instan.

---

## ⚡ Core Features & Capabilities

- **Interactive Test Debugger**: Kendalikan eksekusi pengujian secara dinamis dengan tombol _Pause_, _Resume_, dan _Step Next_ langsung dari Toolbar Desktop atau _Floating In-Page HUD_ di dalam browser.
- **Deep Multi-Frame Recording**: Merekam alur pengguna multi-langkah di dalam _nested iframe_, _Shadow DOM trees_, _dropdown_ Select2, dan _Rich Text Editor_ tanpa konfigurasi tambahan.
- **Smart Self-Healing & LocatorResolver**: Menyelesaikan elemen secara otomatis di dalam modal aktif, menangani UUID dinamis, memperbaiki selector yang rusak, serta mengisi ulang data formulir unik saat terjadi penolakan data ganda.
- **Visual Scenario Matrix & Reports**: Menghasilkan matriks skenario pengujian terstruktur dan mengekspornya langsung ke Microsoft Excel (`.xlsx`) ber-styling rapi atau laporan HTML interaktif mandiri.
- **API Studio & Collection Runner**: Dukungan penuh metode HTTP, variabel lingkungan, _mock server_, eksekusi koleksi otomatis, serta dukungan _body request_ untuk `x-www-form-urlencoded` dan `form-data`.
- **Zero Cloud Lock-in**: Arsitektur _100% offline-first_. Seluruh definisi pengujian, kredensial, dan artefak tersimpan secara ketat di perangkat lokal Anda.

---

## 🛡️ Security & Integrity Verification

To ensure the authenticity and integrity of downloaded binaries, verify the SHA-256 checksum before running the installer:

### PowerShell (Windows)

```powershell
Get-FileHash .\trevix-explorer-*-setup.exe -Algorithm SHA256
```

### Command Prompt (Windows)

```cmd
certutil -hashfile trevix-explorer-*-setup.exe SHA256
```

Compare the resulting hash value with the `SHA256SUMS.txt` file on the [Releases page](https://github.com/RaffiDevYT/trevix-explorer-releases/releases).

---

## ⚠️ Windows SmartScreen Warning

Because the Trevix Explorer installer does not yet feature a paid digital code-signing certificate, Windows Defender SmartScreen may display a warning dialog:

> **"Windows protected your PC"**  
> _Microsoft Defender SmartScreen prevented an unrecognized app from starting._

### How to Proceed with Installation:

1. Ensure you have performed the **SHA-256 checksum verification** against `SHA256SUMS.txt` from the release page.
2. On the SmartScreen popup dialog, click the **"More info"** text link.
3. Click the **"Run anyway"** button to start the installation wizard.

---

## 💻 System Requirements

- **Operating System**: Windows 10 (Build 19041+) or Windows 11 (64-bit).
- **Processor**: Intel Core i3 / AMD Ryzen 3 or higher (64-bit).
- **RAM**: 4 GB minimum (8 GB+ recommended for parallel browser automation).
- **Storage**: ~250 MB free disk space.

---

## 📄 License

Trevix Explorer is proprietary software. Please see the [LICENSE](LICENSE) file for terms and conditions.

---

## 🔗 Official Links & Documentation

- **Landing Page**: [https://trevix.cnplus.id/](https://trevix.cnplus.id/)
- **Manual Book (ID)**: [MANUAL_BOOK.md](MANUAL_BOOK.md)
- **Manual Book (EN)**: [MANUAL_BOOK_EN.md](MANUAL_BOOK_EN.md)
- **Changelog**: [CHANGELOG.md](CHANGELOG.md)
- **Developer**: [Rafi Athallah](https://github.com/RaffiDevYT)
- **Community & Issues**: [GitHub Discussions & Issue Tracker](https://github.com/RaffiDevYT/trevix-landing-page/issues)

<br />

<div align="center">
  <sub>© 2026 Trevix Explorer. All rights reserved. Trevix Explorer is developed by Rafi Athallah.</sub>
</div>
