# SIDALI – Sistem Digitalisasi Kecamatan Kabupaten Tapanuli Selatan

Web single-file elegan bernuansa putih–emas–hijau, siap deploy di **GitHub Pages**.

## Fitur
- **Deskripsi Wilayah**: statistik + grafik (Chart.js) dan ringkasan editable
- **Kegiatan Kecamatan**: form unggah (nama, tanggal, kecamatan, deskripsi, lampiran) → kirim ke Google Drive via **Apps Script**
- **Pengumuman**: menampilkan hasil unggahan (via endpoint `?action=list` pada Apps Script) — fallback **localStorage**
- **Data Camat, Lurah & Kepling**: menampilkan Google Spreadsheet (read-only)

## Cara Deploy ke GitHub Pages
1. Buat repo baru, misalnya: `sidali-tapsel`.
2. Upload file `index.html` dan folder `.github/workflows/deploy.yml` (sudah disediakan di paket ini).
3. Masuk ke **Settings → Pages**: 
   - **Build and deployment**: *GitHub Actions*
4. Commit/push ke branch `main`. Workflow akan otomatis publish.
5. Akses situs: `https://<username>.github.io/sidali-tapsel/`

## Setel Endpoint Apps Script (Drive + Sheet)
- Di situs, buka tab **Kegiatan Kecamatan → Setel** lalu tempel **URL Web App** dari Apps Script.
- Contoh struktur Apps Script ada di tab **Bantuan** halaman ini. Ganti:
  - `FOLDER_ID_DRIVE` (folder target di Google Drive)
  - `SHEET_ID` (ID Google Sheet ber-sheet `Data`)

## Ganti Logo
Ubah `src` logo di **index.html** menjadi `https://drive.google.com/uc?export=view&id=<ID_LOGO>`.

## Kustomisasi
- Sesuaikan angka default (luas, penduduk, dst.) di `dataWilayah` pada `index.html`.
- Jika ingin domain kustom, tambahkan file `CNAME` berisi domain Anda di root repo.
