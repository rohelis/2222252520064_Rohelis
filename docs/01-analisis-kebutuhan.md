# 01 — Analisis Kebutuhan (Hasil Wawancara)

## 1. Ringkasan wawancara

| Keterangan | Isi |
|---|---|
| Responden | S01 (kelas XI, sudah pernah belajar unsur-unsur lingkaran) |
| Pewawancara | Rohelis |
| Tanggal | 08 November 2026 |
| Durasi | 25 menit, direkam dengan persetujuan |
| Artefak pemicu | Gambar lingkaran berisi titik pusat, jari-jari, diameter, busur, tali busur, juring, tembereng, apotema |
| Kategori kode | K (konteks belajar), IL (*intrinsic load*), EL (*extraneous load*), GL (*germane load*), DS (desain/saran) |

> **Catatan metodologis.** Responden saat ini kelas XI, sedangkan sasaran aplikasi adalah siswa SMP.
> Data S01 bersifat *retrospektif* (mengingat pengalaman belajar materi kelas VIII). Ini wajar untuk
> studi pendahuluan, tetapi sebaiknya ditambah 2–4 wawancara/observasi siswa SMP kelas VIII
> (lihat [08-rencana-evaluasi.md](08-rencana-evaluasi.md)) agar kebutuhan tidak hanya bersumber dari satu orang.
> Selain itu, baris EL04 belum diberi kode awal — sebaiknya dilengkapi "EL".

## 2. Temuan per kategori

### K — Konteks belajar sebelumnya
- Siswa hanya **mengingat sebagian** materi (K01, K04): titik pusat, jari-jari, diameter, busur, tali busur, juring. **Tembereng dan apotema tidak disebut** saat recall bebas.
- Guru mengajar dengan gambar di papan tulis dan memberi nama tiap bagian (K02); latihan berupa menunjuk bagian pada gambar (K03).

### IL — Beban intrinsik (kesulitan dari materi itu sendiri)
| Temuan | Bukti | Penjelasan kognitif |
|---|---|---|
| **Juring vs tembereng** paling sulit | IL01, IL06 | Keduanya *daerah*; pembedanya hanya batas (2 jari-jari + busur vs tali busur + busur). Siswa harus memproses beberapa elemen sekaligus → interaktivitas elemen tinggi. |
| **Busur vs tali busur** sering tertukar | IL04, IL05 | Keduanya menghubungkan dua titik pada lingkaran; pembeda: lengkung vs lurus. |
| Jari-jari, diameter, titik pusat sudah dipahami | IL02, IL03, IL07 | Siswa tahu d = 2r dan tali busur tidak harus melewati pusat → bisa dijadikan **jangkar** (*prior knowledge*). |

### EL — Beban ekstrinsik (kesulitan dari cara penyajian)
| Temuan | Bukti | Implikasi desain |
|---|---|---|
| Bingung maksud soal | EL01 | Kalimat soal pendek, satu perintah, kata kerja jelas ("Ketuk…", "Pilih…"). |
| Penjelasan guru kadang tidak dipahami di bagian tertentu | EL02 | Materi bisa diulang per bagian, kecepatan diatur siswa. |
| Gambar sangat membantu; teks saja sulit dibayangkan | EL03, EL05 | Setiap konsep wajib punya visual; teks melekat pada gambar. |
| Bingung saat diminta menggambar sendiri | EL04 | Sediakan konstruksi terbimbing, bukan kanvas kosong. |
| Gambar tanpa keterangan lengkap membingungkan | EL06 | Label langsung pada gambar (bukan legenda terpisah). |
| **Terlalu banyak garis dan nama dalam satu gambar** → sulit fokus | EL07 | Tampilkan unsur **satu per satu**; unsur lain diredupkan. Artefak pemicu sendiri (8 unsur sekaligus) adalah contoh masalah ini. |

### GL — Beban relevan (strategi yang membantu membangun skema)
- Menggambar/menyusun sendiri membantu (GL01) → fitur **eksplorasi interaktif** (geser titik).
- Nama + penjelasan pada gambar memudahkan (GL02).
- Strategi siswa: menghafal pengertian sambil melihat gambar dan ciri-ciri (GL03), mencocokkan gambar dengan pengertian (GL04) → fitur **ciri kunci** dan latihan **mencocokkan**.
- Siswa sudah bisa menyebut pembeda yang benar (GL05) namun masih ragu → perlu latihan **perbandingan** berulang.
- Belajar dari gambar sederhana ke kompleks (GL06) → urutan **sederhana → kompleks**.
- Gambar berwarna + keterangan + penjelasan singkat + latihan (GL07).

### DS — Saran desain dari siswa
| Kode | Permintaan | Diterjemahkan menjadi fitur |
|---|---|---|
| DS01 | Gambar interaktif, penjelasan tiap unsur, video/animasi, latihan | Kartu unsur interaktif + animasi singkat + latihan |
| DS02 | Unsur ditampilkan satu per satu | Mode "satu unsur per layar" |
| DS03 | Bertahap dengan contoh gambar | Alur belajar berurutan dengan contoh |
| DS04 | Soal mudah → sulit | Tiga level latihan |
| DS05 | Petunjuk jika salah | Petunjuk bertingkat |
| DS06 | Pembahasan alasan benar/salah | Pembahasan per soal |
| DS07 | Sederhana, tidak banyak tulisan, warna tidak mencolok, tombol mudah | Pedoman UI (lihat 05) |

## 3. Pernyataan masalah
Siswa mengalami beban kognitif berlebih saat belajar unsur-unsur lingkaran karena (a) beberapa pasangan
unsur memiliki kemiripan tinggi (juring–tembereng, busur–tali busur) dan (b) penyajian materi
menampilkan terlalu banyak unsur dan label dalam satu gambar, sering tanpa keterangan yang menempel
pada gambar. Siswa membutuhkan media yang menyajikan unsur secara bertahap, visual, interaktif,
dengan latihan berjenjang serta umpan balik yang menjelaskan.

## 4. Daftar kebutuhan (ditelusuri ke data)

| ID | Kebutuhan | Sumber |
|---|---|---|
| N1 | Satu unsur baru per layar; unsur lain diredupkan | EL07, DS02 |
| N2 | Label & penjelasan menempel langsung pada gambar | EL06, GL02 |
| N3 | Teks singkat; visual sebagai penyampai utama | EL05, DS07 |
| N4 | Mode perbandingan khusus juring–tembereng dan busur–tali busur | IL01, IL04–IL06, GL05 |
| N5 | Eksplorasi interaktif (geser titik, lihat perubahan) | GL01, DS01 |
| N6 | Konstruksi terbimbing (bukan menggambar bebas) | EL04, GL01 |
| N7 | Urutan materi dari yang sudah dikenal ke yang sulit | IL02–IL03, GL06, DS03 |
| N8 | Latihan bertingkat mudah → sedang → sulit | DS04 |
| N9 | Petunjuk bertingkat saat jawaban salah | DS05 |
| N10 | Pembahasan untuk setiap jawaban | DS06 |
| N11 | Kalimat soal pendek dan jelas | EL01 |
| N12 | Animasi singkat pembentukan unsur | DS01 |
| N13 | Tampilan sederhana, warna lembut, tombol besar | DS07 |
| N14 | Bisa diulang per bagian sesuai kecepatan siswa | EL02 |
