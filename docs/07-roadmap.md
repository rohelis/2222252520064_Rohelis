# 07 — Roadmap & Milestone

Setiap milestone kecil dan bisa diperiksa. Kerjakan berurutan. Centang `[x]` jika selesai.

## Milestone 0 — Persiapan proyek
- [ ] Inisialisasi Vite + React + TypeScript, ESLint, Prettier, Vitest
- [ ] Token warna & tipografi (`src/styles/tokens.css`) sesuai 05
- [ ] Routing kosong untuk semua layar
- [ ] Inisialisasi git + repositori
- **Selesai jika:** `npm run dev` menampilkan Beranda kosong; `npm run test` lulus.

## Milestone 1 — Mesin gambar lingkaran
- [ ] `geometry/circle.ts` & `paths.ts` + uji unit (titik pada lingkaran, busur kecil/besar, juring, tembereng, kaki apotema)
- [ ] Komponen `<CircleCanvas>` dan 8 komponen unsur, mendukung status *sorot / redup*
- [ ] Label menempel pada unsur
- [ ] Halaman uji internal (`/#/dev/figur`) menampilkan semua unsur
- **Selesai jika:** semua unsur tampil benar di 360 px dan 1280 px; uji geometri lulus.

## Milestone 2 — Mode Belajar (P0)
- [ ] `content/unsur.ts` berisi 8 unsur dari 04
- [ ] Layar Unsur + animasi langkah + tombol Sebelumnya/Berikutnya
- [ ] Cek cepat per unsur
- [ ] Progres tersimpan (`localStorage`)
- **Selesai jika:** siswa bisa belajar 1→8; tidak ada layar dengan > 1 unsur baru disorot.

## Milestone 3 — Mode Bandingkan (P0)
- [ ] 3 pasangan dengan sakelar A ⇄ B dan tabel pembeda
- [ ] Animasi "telusuri batas"
- [ ] Sisipan otomatis setelah unsur 5 dan 8
- **Selesai jika:** pembeda tiap pasangan tampil di gambar yang sama.
- **Sebelum lanjut:** uji cepat ke 2–3 siswa kelas VIII (lihat 08, uji perorangan).

## Milestone 4 — Mode Latihan (P0)
- [ ] Komponen soal: pilihan ganda, benar/salah, ketuk-gambar, isian angka
- [ ] Alur petunjuk 1 → petunjuk 2 → pembahasan
- [ ] 3 level, buka level ≥ 70%
- [ ] Layar Hasil + tautan "ulangi materi"
- [ ] Minimal 8 soal per level
- **Selesai jika:** semua soal punya 2 petunjuk & pembahasan (dicek otomatis oleh uji unit konten).

## Milestone 5 — Ringkasan, Pengaturan, PWA (P0)
- [ ] 8 kartu ringkasan + gambar lengkap
- [ ] Pengaturan: teks besar, suara, kontras tinggi, reset progres
- [ ] PWA: manifest, ikon, offline
- **Selesai jika:** aplikasi berjalan dalam mode pesawat setelah dibuka sekali; skor Lighthouse PWA lulus.

## Milestone 6 — Android (P0)
- [ ] Capacitor, ikon & splash Android
- [ ] Tombol kembali Android, safe area
- [ ] APK diuji di minimal 1 HP Android kelas bawah
- **Selesai jika:** APK terpasang dan semua alur berjalan.

## Milestone 7 — Eksplorasi (P1)
- [ ] Titik geser menempel di keliling
- [ ] 4–6 tantangan terbimbing (mis. "jadikan tali busur sebagai diameter", "buat juring besar", "ubah tembereng menjadi setengah lingkaran")
- **Selesai jika:** dapat digeser lancar dengan jari di layar 360 px.

## Milestone 8 — Validasi & revisi
- [ ] Validasi ahli materi & ahli media → revisi
- [ ] Uji perorangan & kelompok kecil → revisi
- [ ] Uji lapangan
- [ ] Rilis v1.0 (web + APK)

## Milestone 9 — Opsional (P2)
- [ ] Narasi suara
- [ ] Ekspor hasil untuk guru
- [ ] Mode gelap
- [ ] Materi lanjutan (keliling & luas, sudut pusat)

## Perkiraan waktu (bisa disesuaikan)
| Milestone | Perkiraan |
|---|---|
| 0–1 | 1 minggu |
| 2–3 | 1–2 minggu |
| 4 | 1–2 minggu |
| 5–6 | 1 minggu |
| 7 | 1 minggu |
| 8 | mengikuti jadwal penelitian |
