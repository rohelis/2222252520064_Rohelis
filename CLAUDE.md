# CLAUDE.md — Panduan untuk Claude Code

## Proyek
**LingkarKu**: aplikasi belajar *unsur-unsur lingkaran* untuk siswa SMP kelas VIII (Kurikulum Merdeka, Fase D).
Dibangun oleh mahasiswa S1 Pendidikan Matematika sebagai produk penelitian pengembangan berbasis
**Teori Beban Kognitif**. Berjalan di web (PWA) dan Android (Capacitor).

Dokumen acuan (baca sesuai kebutuhan, jangan mengarang di luar isinya):
- Kebutuhan & fitur: `docs/02-PRD.md`
- Aturan desain pembelajaran: `docs/03-desain-pembelajaran.md`
- Definisi & soal (sumber kebenaran isi): `docs/04-konten-materi.md`
- UI, warna, wireframe: `docs/05-desain-ui-ux.md`
- Stack, struktur folder, model data: `docs/06-arsitektur-teknis.md`
- Urutan kerja: `docs/07-roadmap.md`

## Stack
React 18 + TypeScript + Vite · SVG untuk semua gambar geometri · React Router (HashRouter) ·
Context + useReducer · localStorage · vite-plugin-pwa · Capacitor (Android) · Vitest · Playwright.
Jangan menambah library besar (UI kit, state manager, canvas engine) tanpa bertanya dulu.

## Perintah
```
npm run dev        # pengembangan
npm run build      # build produksi
npm run test       # uji unit
npm run test:e2e   # uji end-to-end (viewport 360x740)
npm run lint
npm run android    # build + cap sync android
```

## Aturan WAJIB (berasal dari data wawancara siswa — jangan dilanggar)
1. **Satu unsur baru per layar materi.** Unsur lain diredupkan (`--inactive`), bukan disembunyikan semuanya dan bukan ditampilkan penuh warna.
2. **Label menempel pada gambar.** Tidak ada legenda terpisah.
3. **Teks pendek:** definisi ≤ 20 kata, ciri kunci ≤ 10 kata, perintah soal ≤ 15 kata, total teks per layar ≤ 40 kata.
4. **Soal level Mudah/Sedang maksimal 3 unsur dalam gambar.** Gambar lengkap 8 unsur hanya di Ringkasan dan level Sulit.
5. **Setiap soal wajib punya** `petunjuk1`, `petunjuk2`, `pembahasan`, `unsurTerkait`. Tambahkan uji unit yang memeriksa ini.
6. **Warna unsur tetap** di seluruh aplikasi (token di `src/styles/tokens.css`), saturasi sedang, dan selalu disertai label/pola (tidak hanya warna).
7. **Tanpa dekorasi** yang tidak mengajar: tidak ada maskot animasi, musik latar, confetti berlebihan, atau teks motivasi panjang.
8. **Umpan balik bernada netral:** "Belum tepat, coba lagi ya" — jangan "SALAH!" merah besar. Warna coba-lagi = `--retry` (oranye lembut).
9. **Animasi** ≤ 8 detik, tidak berulang otomatis, hormati `prefers-reduced-motion`.
10. **Tanpa batas waktu** pada soal.

## Aturan isi matematika
- Semua teks materi & soal hanya di `src/content/`. Komponen tidak boleh berisi teks materi yang di-hardcode.
- Definisi harus **sama persis** dengan `docs/04-konten-materi.md`. Jika menemukan definisi yang tampak keliru, **jangan ubah diam-diam** — laporkan ke pengguna.
- Istilah baku: *titik pusat, jari-jari, diameter, tali busur, busur, apotema, juring, tembereng*. Pakai "ruas garis" untuk segmen. Jangan pakai istilah Inggris di UI (sector, chord, arc, apothem).
- Gambar dibangun dari **sudut pada lingkaran** (`FigurSpec`), bukan koordinat bebas, agar geometrinya selalu benar (apotema tegak lurus & jatuh di titik tengah tali busur, diameter melewati O, dst.).

## Konvensi kode
- Bahasa UI: Bahasa Indonesia. Nama variabel/fungsi kode: boleh Indonesia untuk domain (`unsur`, `soal`, `petunjuk`), Inggris untuk teknis (`useProgress`, `Button`). Konsisten dalam satu file.
- Komponen fungsional + hooks; TypeScript `strict`.
- Fungsi geometri murni di `src/geometry/` dan **wajib diuji unit**.
- Akses `localStorage` selalu lewat `src/state/storage.ts` (try/catch, ada nilai default).
- Target sentuh ≥ 48 px; SVG punya `role="img"` + `aria-label` berbahasa Indonesia.
- Mobile-first: rancang untuk 360 px dulu, lalu lanskap/proyektor.
- Tidak ada permintaan jaringan saat runtime (harus berjalan offline); font di-bundle lokal.
- Tidak ada analytics, iklan, login, atau pengumpulan data pribadi.

## Cara bekerja
- Kerjakan **satu milestone** dari `docs/07-roadmap.md` per sesi; centang checklist yang selesai.
- Sebelum menyatakan selesai: jalankan `npm run lint`, `npm run test`, dan cek tampilan di 360 px.
- Jika permintaan pengguna bertentangan dengan Aturan WAJIB, sampaikan dulu konflik tersebut dan alasannya (data wawancara), lalu ikuti keputusan pengguna.
- Pengguna adalah mahasiswa pendidikan matematika, bukan programmer profesional: jelaskan langkah teknis dengan bahasa sederhana dan sebutkan perintah yang perlu dijalankan.
