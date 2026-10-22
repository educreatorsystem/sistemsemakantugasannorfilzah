# Sistem Semakan Penghantaran Tugasan Murid

Aplikasi web ringkas untuk guru merekod penghantaran buku kerja atau tugasan murid, mengira mata terkumpul, dan memaparkan dashboard rekod untuk analisis serta cetakan.

## Fungsi Utama

- Dropdown kelas dan nama murid diambil daripada Google Sheet.
- Dropdown subjek diambil daripada Google Sheet.
- Rekod penghantaran murid:
  - Hantar + Lengkap: 3 mata
  - Hantar + Tidak Lengkap: 1 mata
  - Tidak Hantar + Tidak Hadir: 0 mata
  - Tidak Hantar + Tiada Sebab: -2 mata
- Dashboard rekod dengan tapisan kelas, subjek, julat tarikh dan nama tugasan.
- Kolum tarikh dinamik berdasarkan rekod.
- Fungsi cetak laporan dashboard.
- Simpan dan baca semula rekod melalui Google Apps Script.

## Struktur Fail

```text
.
├── index.html
├── README.md
└── apps-script
    └── Code.gs
```

## Konfigurasi Semasa

Sheet ID:

```text
1XtZrC45ULx0IPeJpf2ik8Okk8JuDX7WCaYG6mvGUse4
```

URL Apps Script:

```text
https://script.google.com/macros/s/AKfycbxMKukVUwRhDZ6a4xq5VooAVp4o2e2GkXTeD785rdzuDU9QGyEWkqMGh0dJ42ffWG9a/exec
```

CSV Kelas & Nama Murid:

```text
https://docs.google.com/spreadsheets/d/e/2PACX-1vRvJrDNoxHmg72tqCX92ri4SZqY8f0PAL6KZXKHzt3O6svb84j4tP7uUQP99mCzT3paoagM7DjWqMNU/pub?gid=0&single=true&output=csv
```

CSV Subjek:

```text
https://docs.google.com/spreadsheets/d/e/2PACX-1vRvJrDNoxHmg72tqCX92ri4SZqY8f0PAL6KZXKHzt3O6svb84j4tP7uUQP99mCzT3paoagM7DjWqMNU/pub?gid=1262893420&single=true&output=csv
```

## Cara Publish Di GitHub Pages

1. Upload/replace fail `index.html`, `README.md`, dan folder `apps-script/Code.gs` ke repository GitHub.
2. Pergi ke `Settings > Pages`.
3. Pada bahagian `Build and deployment`, pilih:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
4. Klik `Save`.
5. Tunggu GitHub Pages update dan refresh laman web.

## Cara Setup Google Apps Script

1. Buka Google Sheet utama.
2. Pergi ke `Extensions > Apps Script`.
3. Padam kod sedia ada dan tampal kandungan daripada `apps-script/Code.gs`.
4. Klik `Save`.
5. Pergi ke `Deploy > Manage deployments`.
6. Klik `Edit`, pilih `New version`, kemudian `Deploy`.
7. Tetapan Web App:
   - Execute as: `Me`
   - Who has access: `Anyone`
8. Pastikan URL Web App yang digunakan ialah:

```text
https://script.google.com/macros/s/AKfycbxMKukVUwRhDZ6a4xq5VooAVp4o2e2GkXTeD785rdzuDU9QGyEWkqMGh0dJ42ffWG9a/exec
```

## Google Sheet Sumber Dropdown

Data kelas dan nama murid perlu berada dalam format:

```text
KELAS, NAMA MURID
```

Data subjek perlu berada dalam format:

```text
BIL, SUBJEK
```

## Nota Penting

- Selepas mengubah `Code.gs`, deploy Apps Script sebagai versi baharu.
- Jika dashboard tidak memaparkan data terkini, refresh laman web.
- Pastikan Google Sheet sumber dropdown telah dipublish sebagai CSV.

## Konfigurasi Terkini

Sheet ID:

```text
1XtZrC45ULx0IPeJpf2ik8Okk8JuDX7WCaYG6mvGUse4
```

URL Apps Script:

```text
https://script.google.com/macros/s/AKfycbxMKukVUwRhDZ6a4xq5VooAVp4o2e2GkXTeD785rdzuDU9QGyEWkqMGh0dJ42ffWG9a/exec
```

CSV Kelas & Nama Murid:

```text
https://docs.google.com/spreadsheets/d/e/2PACX-1vRvJrDNoxHmg72tqCX92ri4SZqY8f0PAL6KZXKHzt3O6svb84j4tP7uUQP99mCzT3paoagM7DjWqMNU/pub?gid=0&single=true&output=csv
```

CSV Subjek:

```text
https://docs.google.com/spreadsheets/d/e/2PACX-1vRvJrDNoxHmg72tqCX92ri4SZqY8f0PAL6KZXKHzt3O6svb84j4tP7uUQP99mCzT3paoagM7DjWqMNU/pub?gid=1262893420&single=true&output=csv
```


## Versi V45 — Jadual pengisian rekod
Tab Pengisian Rekod menggunakan jadual dengan lajur Bil., Nama Murid, Penghantaran, Status Tugasan, Sebab Tidak Hantar, Status Semasa dan Mata. Pilihan Lengkap / Tidak Lengkap automatik menandakan Hantar; pilihan Tidak Hadir / Tiada Sebab automatik menandakan Tidak Hantar. Semua fungsi Apps Script dan konfigurasi sambungan V44 dikekalkan.


## V46 — Paparan jadual murid
Paparan Pengisian Rekod ialah jadual satu baris bagi setiap murid, bukan kad. Selepas upload `index.html`, pastikan penanda `V46 · JADUAL` kelihatan pada header. Jika paparan masih kad, semak fail `index.html` pada GitHub Pages dan buat hard refresh (Ctrl+Shift+R / Cmd+Shift+R). Jika menggunakan Google Sites, pastikan iframe/embed memaparkan URL GitHub Pages terkini, bukan kod HTML lama yang ditampal.


## V47 – Pembetulan Jadual
- Header kolum dijadikan statik, bukan sticky.
- Lebar kolum diseragamkan menggunakan colgroup dan table-layout fixed.
- Jadual boleh ditatal mendatar pada skrin kecil; status dan fungsi sedia ada dikekalkan.
