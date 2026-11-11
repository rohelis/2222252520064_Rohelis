# 02 — Product Requirements Document (PRD)

| | |
|---|---|
| Produk | LingkarKu — media belajar unsur-unsur lingkaran |
| Versi dokumen | 0.1 (draf) |
| Penyusun | Rohelis (S1 Pendidikan Matematika) |
| Tanggal | 11 November 2026 |
| Status | Draf untuk ditinjau dosen pembimbing |

## 1. Latar belakang
Hasil wawancara (lihat [01-analisis-kebutuhan.md](01-analisis-kebutuhan.md)) menunjukkan siswa kesulitan
membedakan juring–tembereng dan busur–tali busur, serta mudah kehilangan fokus jika satu gambar memuat
terlalu banyak garis dan label. Siswa meminta gambar interaktif, penyajian satu per satu, latihan
bertingkat, petunjuk saat salah, dan pembahasan.

## 2. Tujuan
**Tujuan produk**
1. Siswa dapat **mengidentifikasi** 8 unsur lingkaran pada gambar.
2. Siswa dapat **membedakan** pasangan unsur yang mirip (juring–tembereng, busur–tali busur, diameter–tali busur).
3. Siswa dapat **menjelaskan hubungan** antarunsur (d = 2r, apotema ⟂ tali busur, diameter adalah tali busur terpanjang).

**Tujuan desain:** menekan beban ekstrinsik, mengelola beban intrinsik dengan segmentasi, dan mendorong beban relevan melalui eksplorasi dan perbandingan.

**Capaian Pembelajaran terkait:** Kurikulum Merdeka, Fase D (SMP kelas VII–IX), elemen Geometri — unsur-unsur lingkaran (umumnya diajarkan di kelas VIII). *Cocokkan dengan dokumen CP/ATP resmi sekolah sasaran.*

## 3. Pengguna

**Persona utama — "Sinta", siswa kelas VIII**
- Memakai HP Android kelas menengah ke bawah, layar ±6 inci, kuota terbatas.
- Sudah mengenal titik pusat, jari-jari, diameter dari SD/awal SMP.
- Mudah bingung jika banyak tulisan; lebih paham lewat gambar.
- Belajar mandiri di rumah atau dipandu guru di kelas.

**Pengguna sekunder — guru matematika**
- Memakai aplikasi sebagai media tayang di kelas (proyektor/laptop, versi web).
- (Fase lanjut) melihat rekap hasil latihan.

## 4. Ruang lingkup

### Termasuk (versi 1.0 / MVP)
- 8 unsur: titik pusat, jari-jari, diameter, busur, tali busur, apotema, juring, tembereng.
- Mode Belajar bertahap, Mode Bandingkan, Mode Eksplorasi, Mode Latihan 3 level, Ringkasan.
- Berjalan offline setelah dibuka pertama kali.
- Web (PWA) + APK Android.

### Tidak termasuk (versi 1.0)
- Keliling, luas, sudut pusat/keliling, garis singgung (kandidat versi berikutnya).
- Akun/login, server, papan peringkat, chat.
- Video berukuran besar (diganti animasi SVG ringan; video opsional di fase lanjut).

## 5. Fitur dan kebutuhan fungsional

Prioritas: **P0** = wajib MVP, **P1** = sebaiknya ada, **P2** = nanti.

### F1. Beranda (P0)
- Menampilkan 4 menu besar: **Belajar**, **Bandingkan**, **Latihan**, **Ringkasan**; plus **Eksplorasi** (P1).
- Menampilkan progres sederhana (mis. "5 dari 8 unsur selesai").
- **Kriteria terima:** setiap menu dapat dicapai dalam 1 ketukan; teks beranda ≤ 25 kata.

### F2. Mode Belajar bertahap (P0) — N1, N2, N3, N7, N12, N14
- Satu unsur per layar, urutan sesuai [04-konten-materi.md](04-konten-materi.md).
- Setiap layar unsur berisi: lingkaran dasar, unsur yang sedang dipelajari **disorot berwarna**, unsur sebelumnya **diredupkan (abu-abu tipis)**, label menempel pada gambar, definisi ≤ 20 kata, satu "ciri kunci", tombol **Putar animasi**.
- Tombol **Sebelumnya / Berikutnya** besar; siswa mengatur kecepatan sendiri.
- Di akhir setiap unsur ada **1 soal cek cepat** (mudah) sebelum lanjut.
- **Kriteria terima:**
  - Tidak ada layar yang menyorot lebih dari 1 unsur baru.
  - Tidak ada label yang diletakkan di legenda terpisah.
  - Animasi ≤ 8 detik, dapat diputar ulang, tidak berputar otomatis berulang.

### F3. Mode Bandingkan (P0) — N4
- Tiga pasangan: **busur vs tali busur**, **juring vs tembereng**, **diameter vs tali busur**.
- Satu lingkaran yang sama; tombol sakelar (toggle) A ⇄ B mengganti sorotan di tempat yang sama, sehingga siswa melihat perbedaan tanpa memindahkan pandangan.
- Tabel pembeda 2 baris ("Batasnya…", "Bentuknya…") di bawah gambar.
- Untuk juring–tembereng: batas daerah dianimasikan ("telusuri batas") — garis batas digambar satu per satu dengan nama batas.
- **Kriteria terima:** pembeda inti tiap pasangan dinyatakan dalam ≤ 2 kalimat; transisi A ⇄ B mempertahankan posisi lingkaran.

### F4. Mode Eksplorasi (P1) — N5, N6
- Siswa menggeser titik pada lingkaran (A, B) dan melihat perubahan busur, tali busur, juring, tembereng secara langsung.
- Tantangan terbimbing, misal: "Geser titik B sampai tali busur menjadi diameter." Aplikasi memberi tanda saat tercapai.
- Panjang r, d, tali busur dan apotema ditampilkan (opsional dapat disembunyikan).
- **Kriteria terima:** titik selalu "menempel" pada keliling lingkaran; dapat dioperasikan dengan jari di layar 360 px.

### F5. Mode Latihan (P0) — N8, N9, N10, N11
- Tiga level: **Mudah** (mengenali satu unsur yang disorot), **Sedang** (membedakan unsur mirip / menemukan unsur pada gambar berisi 2–3 unsur), **Sulit** (hubungan antarunsur, gambar lengkap).
- Level berikutnya terbuka setelah benar ≥ 70% di level sebelumnya (tetap boleh dicoba ulang).
- Jenis soal: pilihan ganda bergambar, **ketuk pada gambar**, benar/salah, mencocokkan label ke gambar (P1).
- Umpan balik:
  - Salah ke-1 → **Petunjuk 1** (umum, mengarahkan perhatian).
  - Salah ke-2 → **Petunjuk 2** (spesifik, menyorot bagian gambar).
  - Benar, atau salah ke-3 → **Pembahasan** (mengapa jawaban benar, dan mengapa pilihan siswa keliru jika salah).
- Ringkasan hasil per sesi: jumlah benar, unsur yang masih perlu diulang + tautan langsung ke materi unsur tersebut.
- **Kriteria terima:** setiap soal memiliki 2 petunjuk dan 1 pembahasan; kalimat perintah soal ≤ 15 kata; 1 soal per layar.

### F6. Ringkasan / Kartu Unsur (P0) — GL03, GL04
- 8 kartu: gambar kecil + nama + ciri kunci. Ketuk kartu → buka materi unsur.
- Gambar lengkap (semua unsur) **hanya** ditampilkan di sini dan di level Sulit, setelah siswa mempelajari semuanya.

### F7. Progres lokal (P0)
- Menyimpan unsur yang sudah dipelajari dan skor latihan di perangkat (tanpa akun).
- Tombol "Mulai ulang progres" di Pengaturan.

### F8. Pengaturan (P1)
- Ukuran teks (normal/besar), suara efek (on/off), mode kontras tinggi.

### F9. Mode Guru / Rekap (P2)
- Ekspor hasil latihan sebagai gambar/teks untuk dikirim ke guru (tanpa server).

### F10. Narasi suara (P2)
- Penjelasan singkat dibacakan (prinsip modalitas) — mengurangi teks di layar.

## 6. Kebutuhan non-fungsional

| Kategori | Kebutuhan |
|---|---|
| Platform | Browser modern (Chrome Android, Chrome/Edge desktop) dan Android 8.0+ (APK via Capacitor) |
| Performa | Muat awal < 3 detik di 4G; ukuran unduh total < 5 MB; animasi 60 fps di HP menengah |
| Offline | Seluruh materi & latihan dapat dipakai tanpa internet setelah pemuatan pertama |
| Responsif | Layar 360 px – 1920 px; orientasi potret diutamakan, lanskap untuk proyektor |
| Aksesibilitas | Target sentuh ≥ 48 px; kontras teks ≥ 4.5:1; warna tidak menjadi satu-satunya pembeda (ada label/pola) |
| Bahasa | Bahasa Indonesia baku sederhana, istilah sesuai buku teks SMP |
| Privasi | Tidak mengumpulkan data pribadi; tidak ada iklan; tidak ada pelacakan pihak ketiga |
| Keakuratan | Semua definisi diverifikasi ahli materi sebelum rilis |

## 7. Metrik keberhasilan
| Metrik | Target | Cara ukur |
|---|---|---|
| Validitas | Rata-rata skor validasi ahli materi & media ≥ "valid" (mis. ≥ 3,26 dari 4) | Angket validasi |
| Kepraktisan | Skor angket respon siswa ≥ "praktis"; SUS ≥ 68 | Angket + SUS |
| Beban kognitif | Skor beban mental (skala Paas 1–9) lebih rendah dibanding pembelajaran biasa | Skala Paas setelah tiap sesi |
| Efektivitas | Peningkatan pretest–posttest (N-gain ≥ 0,3 / sedang) | Tes identifikasi & pembeda unsur |
| Kesulitan inti | ≥ 80% siswa benar pada soal pembeda juring–tembereng & busur–tali busur di posttest | Analisis butir |

Detail di [08-rencana-evaluasi.md](08-rencana-evaluasi.md).

## 8. Asumsi & risiko
| Risiko | Mitigasi |
|---|---|
| Kebutuhan hanya dari 1 responden kelas XI | Tambah wawancara/observasi siswa kelas VIII sebelum Milestone 3 |
| Siswa memakai HP spesifikasi rendah | SVG ringan, tanpa video besar, uji di HP murah |
| Interaksi geser sulit di layar kecil | Titik sentuh besar (≥ 44 px area), uji usabilitas |
| Definisi berbeda antarbuku | Kunci definisi di 04-konten-materi.md dan validasi ahli |
| Waktu pengembangan terbatas | Kerjakan P0 dulu; P1/P2 hanya jika waktu cukup |

## 9. Pertanyaan terbuka
1. Apakah perlu narasi suara di MVP? (memperkuat prinsip modalitas, tapi menambah pekerjaan rekaman)
2. Apakah perlu fitur rekap untuk guru di MVP penelitian?
3. Sekolah mana yang akan menjadi tempat uji coba, dan kelas berapa?
4. Model pengembangan penelitian: ADDIE, 4-D, atau Plomp? (memengaruhi struktur 08)
