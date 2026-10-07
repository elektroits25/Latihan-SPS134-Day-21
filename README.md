# Portal Validasi Presensi

Portal frontend untuk menampilkan dan merekap data presensi kegiatan dari Google Apps Script.

## Konfigurasi

Konfigurasi kegiatan berada di `config.js`, sehingga informasi event tidak perlu diubah langsung di `index.html`.

```js
const APP_CONFIG = {
  portalTitle: "Portal Validasi Presensi",

  event: {
    name: "Latihan SPS 134 - Day 21",
    participantCount: 284,
  },

  api: {
    url: "GOOGLE_APPS_SCRIPT_WEB_APP_URL",
  },

  attendanceCategories: [
    { id: "HADIR", label: "Hadir" },
    { id: "SAKIT", label: "Sakit" },
    { id: "KEAGAMAAN", label: "Agama" },
    { id: "BERDUKA", label: "Duka" },
    { id: "AKADEMIK", label: "Akademik" },
  ],

  unsubmittedCategory: {
    id: "BELUM PRESENSI",
    label: "Belum Presensi",
  },
};
```

Untuk menggunakan portal pada kegiatan lain, sesuaikan konfigurasi event, URL API, dan kategori presensi di `config.js`.

## Sinkronisasi Data

Portal menggunakan cache singkat untuk mengurangi request berulang ke Google Apps Script.

- Cache berlaku selama 30 detik.
- Data disinkronkan otomatis setiap 30 detik selama tab browser aktif.
- Tombol **Refresh** dapat digunakan untuk memaksa pengambilan data terbaru.
- Perpindahan tab dapat menggunakan cache selama data masih baru.
- Waktu sinkronisasi terakhir ditampilkan pada halaman.

> "Terakhir disinkronkan" menunjukkan waktu browser terakhir berhasil mengambil data, bukan waktu Google Sheet terakhir diedit.

## Struktur Project

```text
.
├── index.html
├── config.js
├── README.md
└── Logo Angkatan Elektro ITS 2025.jpeg
```