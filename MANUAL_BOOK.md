# 📘 Trevix Explorer — Official Manual Book

> **Platform**: Windows 10 / 11 (Installer resmi saat ini hanya untuk Windows 10/11)  
> **Repository**: [https://github.com/RaffiDevYT/trevix-explorer-releases](https://github.com/RaffiDevYT/trevix-explorer-releases)  
> **Lisensi**: Proprietary - lihat berkas LICENSE

---

## 📑 Daftar Isi

1. [Tentang Trevix Explorer](#1-tentang-trevix-explorer)
2. [Arsitektur & Teknologi](#2-arsitektur--teknologi)
3. [Panduan Instalasi & Update](#3-panduan-instalasi--update)
4. [Daftar Fitur Utama](#4-daftar-fitur-utama)
   - [A. Manajemen Project & Workspace](#a-manajemen-project--workspace)
   - [B. Smart Multi-Frame Test Recorder](#b-smart-multi-frame-test-recorder)
   - [C. Visual Test Editor & Multi-View](#c-visual-test-editor--multi-view)
   - [D. Real-time Test Runner, Debugger & Console Logger](#d-real-time-test-runner-debugger--console-logger)
   - [E. Test Scenario Matrix & Export (Excel & HTML)](#e-test-scenario-matrix--export-excel--html)
   - [F. Sistem Auto-Updater Terintegrasi](#f-sistem-auto-updater-terintegrasi)
   - [G. Trevix API Studio & Testing](#g-trevix-api-studio--testing)
   - [H. Automated API Collection Runner](#h-automated-api-collection-runner)
   - [I. Local API Mock Server & Dynamic Interpolation](#i-local-api-mock-server--dynamic-interpolation)
   - [J. Quick Command Palette](#j-quick-command-palette-ctrl--k--cmd--k)
   - [K. Daftar Pintasan Keyboard](#k-daftar-pintasan-keyboard-keyboard-shortcuts)
5. [Tabel Referensi Lengkap Action Steps](#5-tabel-referensi-lengkap-action-steps)
6. [Daftar Variabel Dinamis](#6-daftar-variabel-dinamis)
7. [Mekanisme & Perilaku Pengujian](#7-mekanisme--perilaku-pengujian)
8. [Smart Self-Healing](#8-smart-self-healing)
9. [Format Standar File Pengujian (.spec.json)](#9-format-standar-file-pengujian-specjson)
10. [Struktur Folder & File Output](#10-struktur-folder--file-output)
11. [Panduan Alur Penggunaan (Step-by-Step)](#11-panduan-alur-penggunaan-step-by-step)
12. [Batasan Sistem (Known Limitations)](#12-batasan-sistem-known-limitations)
13. [Kebijakan Keamanan & Privasi](#13-kebijakan-keamanan--privasi)
14. [Troubleshooting & FAQ](#14-troubleshooting--faq)

---

## 1. Tentang Trevix Explorer

**Trevix Explorer** adalah aplikasi desktop visual yang dirancang khusus untuk kebutuhan **Visual End-to-End (E2E) Test Automation**, **API Testing**, dan **Dokumentasi Matriks QA**.

Aplikasi ini memungkinkan QA Engineer, Software Tester, dan Developer untuk:

- Merekam alur pengujian web secara interaktif tanpa harus menulis baris kode dari awal (_No-Code Recording_).
- Melakukan _debugging_ langkah demi langkah secara interaktif (_Pause_, _Resume_, _Step Next_) melalui Toolbar desktop maupun _Floating In-Page HUD_ di browser.
- Menyesuaikan, menyusun ulang, dan menambahkan assertion/validasi pada setiap langkah pengujian secara visual.
- Mengonversi skenario pengujian ke skrip native **Playwright TypeScript (`.spec.ts`)** yang siap dijalankan mandiri.
- Menguji API REST/HTTP (termasuk dukungan payload `form-data` dan `x-www-form-urlencoded`), menjalankan Automated Collection Runner, dan Local Mock Server.
- Menghasilkan laporan matriks pengujian dalam format **Microsoft Excel (`.xlsx`)** dan laporan interaktif **HTML Standalone**.

---

## 2. Arsitektur & Teknologi

Dibangun dengan Electron dan Playwright.

---

## 3. Panduan Instalasi & Update

### A. Instalasi Baru

1. Unduh installer resmi dari halaman [GitHub Releases](https://github.com/RaffiDevYT/trevix-explorer-releases/releases).
2. Jalankan file installer (`trevix-explorer-<versi>-setup.exe`).
3. Ikuti wizard instalasi hingga selesai dan buka aplikasi.

### B. Pembaruan Otomatis (Auto-Update)

1. Saat rilis baru tersedia di GitHub Releases, indikator pembaruan di header aplikasi akan menyala.
2. Klik tombol pembaruan untuk melihat catatan rilis dan memulai pengunduhan di latar belakang.
3. Setelah selesai, klik **"Update & Restart"** untuk memasang versi terbaru.

---

## 4. Daftar Fitur Utama

### A. Manajemen Project & Workspace

- **Folder Isolasi Otomatis**: Menyiapkan struktur folder `tests/`, `apis/`, dan `reports/`.
- **Kunci Workspace (`.trevix.lock`)**: Melindungi sesi aktif workspace.
- **Menu Aksi File**: Download, Duplicate, Rename, dan Delete file spesifikasi.

### B. Smart Multi-Frame Test Recorder

- **One-Click Record**: Perekaman interaksi di seluruh frame, iframe, Select2 dropdown, dan Rich Text Editor.
- **Smart Locator Generator**: Menghasilkan selector stabil berbasis ID, data-testid, atribut `title`/`aria-label`, hingga hierarki CSS.
- **Proteksi Anti-Popup**: Memblokir iklan atau tab jebakan otomatis.

### C. Visual Test Editor, Multi-View & Interactive Debugger

1. **Visual & Script**: Tabel langkah interaktif dengan pratinjau kode Playwright TypeScript real-time.
2. **Interactive Debugger**: Kontrol eksekusi (_Pause_, _Resume_, _Step Next_) langsung dari Toolbar aplikasi atau _Floating In-Page HUD_ di browser.

### D. Real-time Test Runner & Console Logger

- Indikator warna status langkah real-time, tangkapan layar otomatis saat gagal, dan panel konsol interaktif.

### E. Test Scenario Matrix & Export (Excel & HTML)

- Eksekusi matriks skenario ke format Excel (`.xlsx`) ber-styling rapi dan laporan HTML interaktif mandiri.

---

## 5. Tabel Referensi Singkat Action Steps

| Action        | Deskripsi Utama                                                                   |
| :------------ | :-------------------------------------------------------------------------------- |
| `navigate`    | Membuka URL target                                                                |
| `click`       | Menклика elemen dengan dukungan `allowPopup`                                      |
| `fill`        | Mengisi teks input form (mendukung `isSecret` & pengisian programatik `readonly`) |
| `select`      | Memilih opsi dropdown HTML standar atau Select2                                   |
| `assert`      | Memeriksa visibilitas, teks, nilai, atau URL dengan polling 8 detik               |
| `upload_file` | Mengunggah berkas dengan opsi fallback dummy                                      |
| `api_request` | Menjalankan pengujian request HTTP/REST                                           |

---

## 6. Format Standar File Pengujian (.spec.json)

File disimpan dalam format terstruktur `.spec.json` di dalam folder `tests/` workspace lokal pengguna.

---

_© 2026 Trevix Explorer — Developed by Rafi Athallah._
