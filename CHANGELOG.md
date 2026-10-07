# Changelog

Semua perubahan penting pada Trevix Explorer didokumentasikan di berkas ini.
Format ini mengacu pada [Keep a Changelog](https://keepachangelog.com/id/1.0.0/) dan mematuhi [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.7] - 2026-10-07

### ⚠️ Perubahan Perilaku (Perlu Perhatian)

- **Validasi Kegagalan Eksplisit Dropdown & Upload**: Langkah `upload_file` yang file fisiknya tidak ditemukan di disk lokal serta langkah `select` yang opsi targetnya tidak ada di halaman sekarang langsung berstatus **Failed** (sebelumnya lulus diam-diam).
  - _Yang harus dilakukan_: Pastikan path file upload valid di sistem lokal atau aktifkan opsi `allowDummyFile: true`. Untuk dropdown, pastikan label atau nilai opsi yang dipilih sesuai dengan elemen HTML/Select2 di halaman.
- **Asersi Elemen Kosong Diperketat**: Langkah `assert` pada elemen yang tidak ada di DOM sekarang akan gagal meskipun nilai yang diharapkan kosong (`""`).
  - _Yang harus dilakukan_: Pastikan elemen target sudah ter-render di halaman sebelum menjalankan validasi asersi.
- **Evaluasi Nilai Input Presisi (`toHaveValue`)**: Asersi `toHaveValue` tidak lagi menormalkan spasi berlebih.
  - _Yang harus dilakukan_: Pastikan string nilai input yang diuji cocok persis dengan atribut `value` elemen (termasuk spasi awal/akhir jika ada).
- **Pemblokiran Popup & Tab Baru Default**: Seluruh popup, popunder, dan link `target="_blank"` diblokir secara default oleh fitur pengaman popup kecuali langkah klik diberi izin eksplisit.
  - _Yang harus dilakukan_: Centang opsi **"Buka tab baru"** (`allowPopup: true`) pada langkah `click` yang memang ditujukan untuk membuka halaman/tab baru.
- **Eksekusi Klik Cepat Tanpa Menunggu Popup**: Aksi `click` biasa tidak lagi menunggu event popup secara pasif, sehingga durasi eksekusi langkah klik menjadi jauh lebih cepat.
  - _Yang harus dilakukan_: Jika sebuah tombol memerlukan pembukaan tab baru, selalu centang opsi **"Buka tab baru"**.
- **Prioritas Lokator Elemen Terdalam & Teks Persis**: Resolver lokator memprioritaskan elemen paling dalam dan mendahulukan pencocokan teks yang sama persis (_exact text match_).
  - _Yang harus dilakukan_: Jika skenario lama mengandalkan substring teks kontainer luar, sesuaikan selector ke elemen spesifik atau gunakan teks persis.
- **Isolasi Variabel Lingkungan Rahasia pada Skrip Ekspor**: Kode Playwright hasil ekspor melempar error runtime jika variabel lingkungan rahasia belum didefinisikan (`if (!authVar) throw new Error("Env AUTH_... belum diisi")`).
  - _Yang harus dilakukan_: Definisikan variabel lingkungan di terminal sebelum menjalankan tes Playwright mandiri (mis. `$env:AUTH_USER_PASSWORD="password_asli"` di PowerShell atau `export AUTH_USER_PASSWORD="password_asli"` di Bash).

> 💡 **Catatan Migrasi Skenario Lama**: Untuk file pengujian lama yang memiliki field token, kata sandi, password, apikey, atau sandi, silakan klik tombol **"Generate from Steps"** ulang di panel Scenario sebelum mengekspor ke Excel/HTML. Hal ini diperlukan karena deskripsi langkah tersimpan sebelumnya dibuat oleh generator lama yang hanya menyamarkan selector berisi kata kunci "pass" atau "secret".

### 🔒 Security

- **Pencegahan Path Traversal pada File Test & API**: Menutup celah keamanan _path traversal_ pada seluruh operasi berkas pengujian dan request API dengan memvalidasi direktori dasar dan menolak bypass path melalui folder dengan nama awalan serupa serta penyimpanan tes yang tidak tervalidasi.
- **Pengamanan Port Mock Server & Handler Window**: Mengikat listener mock server secara ketat ke antarmuka loopback lokal `127.0.0.1` (mencegah eksposur ke jaringan luar), membatasi pembukaan URL eksternal hanya untuk skema `http://` dan `https://`, serta menyematkan sanitasi path pada seluruh penanganan file request API.
- **Validasi Sanitasi Label Folder API**: Memvalidasi karakter label folder bertingkat pada penyimpanan request API dan menolak karakter ilegal/traversal.
- **Deteksi Field Rahasia Cerdas & Ekspor Env Var**:
  - Memperluas deteksi kata kunci rahasia mencakup `passcode`, `passphrase`, dan `passkey` selain `password`, `passwd`, `pwd`, `token`, `secret`, `apikey`, dan `sandi`, serta mencegah _false positive_ pada kata umum (`passport`, `bypass`, `tokenizer`).
  - Menghasilkan nama variabel lingkungan yang deskriptif dan konsisten (`AUTH_PASSWORD`, `AUTH_USER_PASSWORD`) berdasarkan prioritas atribut selector.
  - Mengisolasi variabel lokal skrip Playwright dengan prefiks aman `auth` (mis. `authUserPassword`) agar tidak menimpa variabel runtime bawaan.
- **Penyamaran Nilai Rahasia Menyeluruh**: Menyensor seluruh nilai input rahasia/kata sandi (`••••••`) di pratinjau live Scenario Matrix, metadata deskripsi langkah (`stepsDescription`), kolom `INPUT` ekspor Excel, tabel laporan HTML interaktif, dan log Smart Self-Healing.

### 🐛 Fixed

- **Kegagalan Eksplisit Dropdown & Upload**: Memastikan langkah `select` (baik elemen `<select>` native maupun Select2 jQuery) dan langkah `upload_file` gagal secara eksplisit dengan pesan error yang jelas jika opsi atau file fisik tidak ditemukan di sistem.
- **Peningkatan Polling & Mode Pencocokan URL Assert**:
  - Menambahkan retry polling hingga 8 detik dengan normalisasi whitespace pada asersi `toHaveText` dan `toContainText`.
  - Memperketat evaluasi `toHaveValue` (tanpa normalisasi spasi) dan menolak asersi pada elemen yang tidak ada meski nilai expected kosong.
  - Menambahkan dukungan mode pencocokan URL (`matchMode`: `exact`, `contains`, `regex`) pada asersi `toHaveURL`.
  - Menangkap dan menyertakan pesan detail error terakhir (_last error_) saat elemen teks tidak ditemukan.
- **Optimalisasi Eksekusi Klik & Lokator Presisi**:
  - Mempercepat aksi klik dengan memulai listener popup tepat sebelum klik dan memprioritaskan pencocokan teks persis (_exact text_).
  - Memilih elemen terdalam pada hierarki DOM dan menggunakan transisi `waitForURL` berbasis commit.
- **Sinkronisasi Izin Popup & Manajemen Tab**:
  - Menambahkan opsi opt-in izin popup per-langkah klik dan menyinkronkan izin popup antara halaman dan browser context.
  - Mempertahankan referensi tab aktif saat berpindah tab serta otomatis kembali ke tab terakhir yang masih terbuka jika tab aktif ditutup.
- **Penyalinan Clipboard Andal di Desktop**: Mengalihkan seluruh operasi penyalinan clipboard ke proses utama aplikasi untuk mengatasi kegagalan clipboard di lingkungan desktop.

### ✨ Added

- **Opsi Izin Popup Per-Step**: Menambahkan checkbox "Buka tab baru" (`allowPopup`) pada langkah `click` di UI Visual Editor.
- **Checkbox Rahasia Manual**: Menambahkan checkbox "Rahasia" pada modal penambahan dan pengeditan langkah form `fill` (`isSecret`).
- **Dukungan Template Dinamis Aman pada Ekspor**: Meng-escape karakter khusus (`\`, \`, `${...}`) pada template teks dinamis saat di-generate ke skrip Playwright serta mencegah deklarasi ganda variabel rahasia.

### 🔄 Changed

- **Pembaruan Generator Kode Ekspor**: Skrip ekspor Playwright kini menggunakan blok isolasi lingkup per-field rahasia, menyelaraskan evaluasi URL dengan runner, dan melempar error jika variabel lingkungan belum didefinisikan.
