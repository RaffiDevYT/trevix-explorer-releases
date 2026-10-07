<div align="center">

# ⚡ Trevix Explorer Releases

**The standalone desktop test automation & E2E recording studio.**

[![Latest Release](https://img.shields.io/github/v/release/RaffiDevYT/trevix-explorer-releases?style=flat-square)](https://github.com/RaffiDevYT/trevix-explorer-releases/releases/latest)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-blue.svg?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078d4.svg?style=flat-square&logo=windows)](https://github.com/RaffiDevYT/trevix-explorer-releases/releases/latest)

[🌐 Official Website](https://trevix-explorer.vercel.app/) • [📖 Manual Book](MANUAL_BOOK.md) • [📋 Changelog](CHANGELOG.md) • [🐞 Report Issue](https://github.com/RaffiDevYT/trevix-landing-page/issues)

---

</div>

## 📥 Official Download Mirrors

Choose the official standalone binary for your operating system (currently Windows 10/11 only):

| Platform    | Type                     | Architecture   | Download                                                                                      | Verification     |
| :---------- | :----------------------- | :------------- | :-------------------------------------------------------------------------------------------- | :--------------- |
| **Windows** | Setup Installer (`.exe`) | `x64` (64-bit) | [**Download Latest**](https://github.com/RaffiDevYT/trevix-explorer-releases/releases/latest) | SHA-256 Included |

> 💡 **Auto-Update**: Trevix Explorer checks for updates automatically and notifies you when a new version is available. The download starts only after you confirm.

---

## 🚀 Perubahan Penting di 1.0.7

Versi **1.0.7** membawa pembaruan stabilitas dan peningkatan keamanan penting, antara lain:

- **Validasi Kegagalan Eksplisit**: Langkah upload file dan pemilihan dropdown yang tidak ditemukan kini langsung berstatus _Failed_ dengan pesan deskriptif.
- **Pengamanan Popup & Tab Baru Bawaan**: Proteksi popup otomatis memblokir pembukaan tab jebakan secara default, dengan opsi izin per-langkah (opsi "Buka tab baru").
- **Deteksi & Penyamaran Nilai Rahasia**: Deteksi pintar kata sandi/token pada skenario dan isolasi variabel lingkungan pada skrip ekspor Playwright.
- **Peningkatan Presisi Asersi & Polling**: Mode pencocokan URL (`exact`, `contains`, `regex`) serta evaluasi nilai input yang lebih ketat.

Untuk detail lengkap dan catatan migrasi skenario lama, silakan baca [CHANGELOG.md](CHANGELOG.md).

---

## ⚡ Core Capabilities

- **Deep Multi-Frame Recording**: Record multi-step user journeys inside nested iframes and Shadow DOM trees without extra configuration.
- **Smart Self-Healing**: when a form rejects duplicate data, Trevix Explorer generates fresh unique values, refills the fields, and resubmits automatically. You can turn it off for negative testing.
- **Visual Scenario Matrix**: Generate a test scenario matrix from your steps and export it to Excel and standalone HTML reports.
- **Zero Cloud Lock-in**: 100% offline-first architecture. All test definitions, credentials, and artifacts stay strictly on your local machine.
- **Multi-Framework Exporter**: Export captured journeys directly to clean Playwright (TypeScript/JavaScript).

---

## 🛡️ Security & Integrity Verification

Untuk memastikan keaslian dan integritas berkas unduhan, lakukan verifikasi checksum SHA-256 sebelum menjalankan installer:

### PowerShell (Windows)

```powershell
Get-FileHash .\trevix-explorer-*-setup.exe -Algorithm SHA256
```

### Command Prompt (Windows)

```cmd
certutil -hashfile trevix-explorer-*-setup.exe SHA256
```

Bandingkan nilai hash yang dihasilkan dengan berkas SHA256SUMS.txt pada [halaman rilis](https://github.com/RaffiDevYT/trevix-explorer-releases/releases).

---

## ⚠️ Peringatan Windows SmartScreen

Karena installer Trevix Explorer belum memiliki sertifikat tanda tangan digital berbayar (_digitally signed_), Windows Defender SmartScreen mungkin akan menampilkan dialog peringatan:

> **"Windows protected your PC"**  
> _Microsoft Defender SmartScreen prevented an unrecognized app from starting._

### Cara Melanjutkan Instalasi:

1. Pastikan Anda telah melakukan **verifikasi checksum SHA-256** (lihat bagian verifikasi di atas) sesuai dengan berkas SHA256SUMS.txt pada halaman rilis.
2. Pada jendela dialog SmartScreen, klik tautan teks **"More info"**.
3. Klik tombol **"Run anyway"** untuk memulai instalasi.

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

- **Landing Page**: [https://trevix-explorer.vercel.app/](https://trevix-explorer.vercel.app/)
- **Manual Book**: [MANUAL_BOOK.md](MANUAL_BOOK.md)
- **Changelog**: [CHANGELOG.md](CHANGELOG.md)
- **Organization**: [Raffi Studio](https://github.com/RaffiDevYT)
- **Community & Issues**: [GitHub Discussions & Issue Tracker](https://github.com/RaffiDevYT/trevix-landing-page/issues)

<br />

<div align="center">
  <sub>© 2026 Raffi Studio. All rights reserved. Trevix Explorer is developed by Raffi Studio.</sub>
</div>
