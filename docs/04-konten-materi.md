# 04 — Konten Materi & Bank Soal

> Semua definisi di sini adalah **sumber kebenaran** untuk aplikasi. Jika diubah, ubah di sini dulu,
> lalu di file data aplikasi (`src/content/`). Wajib divalidasi ahli materi sebelum rilis.

## 1. Urutan materi dan alasannya

| No | Unsur | Jenis | Prasyarat | Alasan urutan |
|---|---|---|---|---|
| 1 | Titik pusat | titik | — | Acuan semua unsur |
| 2 | Jari-jari | ruas garis | 1 | Sudah dikuasai siswa (IL02) → membangun rasa mampu |
| 3 | Diameter | ruas garis | 1, 2 | d = 2r (IL07) |
| 4 | Tali busur | ruas garis | 3 | Dikontraskan dengan diameter: "tidak harus lewat pusat" |
| 5 | Busur | garis lengkung | 4 | Dikontraskan dengan tali busur → **Bandingkan #1** |
| 6 | Apotema | ruas garis | 1, 4 | Butuh tali busur |
| 7 | Juring | daerah | 2, 5 | Dibangun dari 2 jari-jari + busur |
| 8 | Tembereng | daerah | 4, 5 | Dibangun dari tali busur + busur → **Bandingkan #2** |

Pola besar: **titik → garis lurus → garis lengkung → daerah** (dari elemen sedikit ke elemen banyak).

## 2. Kartu unsur

Warna mengacu pada token di [05-desain-ui-ux.md](05-desain-ui-ux.md).

### 1. Titik pusat
- **Definisi:** Titik yang jaraknya sama ke semua titik pada lingkaran.
- **Ciri kunci:** Tepat di tengah lingkaran, biasanya diberi nama O.
- **Animasi:** beberapa ruas garis sama panjang muncul dari O ke keliling.

### 2. Jari-jari (r)
- **Definisi:** Ruas garis yang menghubungkan titik pusat dengan satu titik pada lingkaran.
- **Ciri kunci:** Dari titik pusat ke tepi; semua sama panjang.
- **Animasi:** jari-jari berputar mengelilingi pusat, ujungnya membentuk lingkaran.

### 3. Diameter (d)
- **Definisi:** Ruas garis yang menghubungkan dua titik pada lingkaran dan melewati titik pusat.
- **Ciri kunci:** Lewat titik pusat; panjangnya 2 × jari-jari.
- **Animasi:** dua jari-jari berlawanan arah menyatu menjadi satu diameter.
- **Catatan:** fakta "diameter adalah tali busur terpanjang" baru disampaikan di layar 4 (tali busur), karena tali busur belum dikenalkan di layar ini.

### 4. Tali busur
- **Definisi:** Ruas garis yang menghubungkan dua titik pada lingkaran.
- **Ciri kunci:** Garis lurus; tidak harus lewat titik pusat.
- **Animasi:** tali busur bergeser sejajar hingga melewati pusat → menjadi diameter (tali busur terpanjang).

### 5. Busur
- **Definisi:** Bagian dari lingkaran (garis lengkung) di antara dua titik pada lingkaran.
- **Ciri kunci:** Garis lengkung, menempel pada lingkaran.
- **Tambahan:** busur kecil (lebih pendek dari setengah lingkaran) dan busur besar.
- **Animasi:** dua titik pada lingkaran; lengkungan di antaranya menyala.

### 6. Apotema
- **Definisi:** Ruas garis terpendek dari titik pusat ke tali busur, tegak lurus tali busur.
- **Ciri kunci:** Dari pusat, tegak lurus (siku) ke tali busur.
- **Tambahan:** apotema membagi tali busur menjadi dua bagian sama panjang.
- **Animasi:** dari O, garis "turun" ke tali busur; tanda siku muncul.

### 7. Juring
- **Definisi:** Daerah yang dibatasi oleh dua jari-jari dan sebuah busur.
- **Ciri kunci:** Seperti potongan pizza; ujungnya di titik pusat.
- **Tambahan:** juring kecil dan juring besar.
- **Animasi:** jari-jari 1 → jari-jari 2 → busur → daerah terisi.

### 8. Tembereng
- **Definisi:** Daerah yang dibatasi oleh tali busur dan busur.
- **Ciri kunci:** Batasnya 1 garis lurus + 1 garis lengkung; tidak menyentuh pusat.
- **Catatan:** jika tali busurnya diameter, tembereng = setengah lingkaran (kasus khusus, cukup di level Sulit).
- **Animasi:** tali busur → busur → daerah terisi.

## 3. Konten Mode Bandingkan

| Pasangan | Pembeda 1 | Pembeda 2 |
|---|---|---|
| Busur vs tali busur | Busur **lengkung**, tali busur **lurus** | Busur ada **pada** lingkaran, tali busur **di dalam** lingkaran |
| Juring vs tembereng | Juring dibatasi **2 jari-jari + busur** | Tembereng dibatasi **tali busur + busur** |
| Diameter vs tali busur | Diameter **selalu** lewat titik pusat | Diameter adalah tali busur **terpanjang** |

Jembatan ingatan (opsional, divalidasi guru): **"Juring — Jari-jari"** (sama-sama berawal huruf J).

## 4. Bank soal awal

Format: **ID · Level · Tipe** — Soal — Jawaban — Petunjuk 1 — Petunjuk 2 — Pembahasan.
Target MVP: minimal **8 soal per level** (24 total). Berikut 15 contoh.

### Level Mudah (mengenali satu unsur yang disorot)

**M01 · pilihan ganda bergambar** — Gambar: ruas garis dari O ke tepi disorot.
- Soal: "Garis yang disorot disebut…" — A. Jari-jari ✅ B. Diameter C. Tali busur D. Busur
- P1: "Garis itu berawal dari mana?" · P2: (titik O berkedip) "Garis berawal dari titik pusat dan berhenti di tepi."
- Pembahasan: Ruas garis dari titik pusat ke lingkaran adalah jari-jari. Diameter melewati pusat dan menyentuh tepi di dua titik.

**M02 · pilihan ganda** — Gambar: garis lengkung pada tepi disorot.
- Soal: "Bagian yang disorot disebut…" — A. Tali busur B. Busur ✅ C. Juring D. Apotema
- P1: "Lurus atau lengkung?" · P2: "Garisnya lengkung dan menempel pada lingkaran."
- Pembahasan: Garis lengkung pada lingkaran adalah busur. Tali busur berupa garis lurus.

**M03 · ketuk pada gambar** — Gambar: lingkaran dengan titik O, A (di tepi), P (di dalam, bukan pusat).
- Soal: "Ketuk titik pusat."  — Jawaban: O
- P1: "Titik pusat berjarak sama ke semua tepi." · P2: "Titik pusat ada tepat di tengah."
- Pembahasan: O di tengah lingkaran sehingga jaraknya sama ke semua titik pada lingkaran.

**M04 · benar/salah** — Gambar: daerah berbentuk potongan pizza disorot.
- Soal: "Daerah yang disorot adalah juring." — Benar ✅
- P1: "Lihat batasnya. Ada jari-jari?" · P2: (dua jari-jari berkedip) "Dibatasi dua jari-jari dan busur."
- Pembahasan: Daerah yang dibatasi dua jari-jari dan sebuah busur adalah juring.

**M05 · pilihan ganda** — Gambar: garis lurus menghubungkan dua titik pada lingkaran, tidak lewat pusat.
- Soal: "Garis yang disorot disebut…" — A. Diameter B. Jari-jari C. Tali busur ✅ D. Busur
- P1: "Apakah garis ini melewati titik pusat?" · P2: "Garis lurus ini menghubungkan dua titik pada lingkaran tanpa lewat pusat."
- Pembahasan: Itu tali busur. Diameter juga tali busur, tetapi harus melewati titik pusat.

### Level Sedang (membedakan unsur mirip, 2–3 unsur dalam gambar)

**S01 · ketuk pada gambar** — Gambar: satu juring dan satu tembereng berwarna netral.
- Soal: "Ketuk daerah yang merupakan tembereng."
- P1: "Tembereng tidak dibatasi jari-jari." · P2: (tali busur berkedip) "Cari daerah yang dibatasi garis lurus tidak lewat pusat dan busur."
- Pembahasan: Tembereng dibatasi tali busur dan busur. Daerah lainnya juring, karena dibatasi dua jari-jari.

**S02 · ketuk pada gambar** — Gambar: busur AB dan tali busur AB pada titik yang sama.
- Soal: "Ketuk tali busur AB."
- P1: "Tali busur itu lurus atau lengkung?" · P2: "Pilih garis lurus antara A dan B."
- Pembahasan: Tali busur AB adalah ruas garis lurus AB. Garis lengkung AB adalah busur.

**S03 · pilihan ganda** — Gambar: garis dari O tegak lurus ke tali busur (ada tanda siku).
- Soal: "Garis dari O yang tegak lurus tali busur disebut…" — A. Jari-jari B. Apotema ✅ C. Diameter D. Busur
- P1: "Apakah garis itu sampai ke tepi lingkaran?" · P2: "Garis ini berhenti di tali busur dan membentuk siku."
- Pembahasan: Apotema berawal dari pusat dan tegak lurus tali busur. Jari-jari berhenti di tepi lingkaran.

**S04 · benar/salah**
- Soal: "Setiap diameter adalah tali busur." — Benar ✅
- P1: "Apa arti tali busur?" · P2: "Diameter juga menghubungkan dua titik pada lingkaran."
- Pembahasan: Tali busur menghubungkan dua titik pada lingkaran. Diameter melakukannya sambil melewati pusat, jadi diameter adalah tali busur terpanjang.

**S05 · benar/salah**
- Soal: "Setiap tali busur adalah diameter." — Salah ✅
- P1: "Apakah semua tali busur lewat titik pusat?" · P2: (tali busur yang tidak lewat pusat berkedip)
- Pembahasan: Hanya tali busur yang melewati pusat yang disebut diameter.

### Level Sulit (hubungan antarunsur, gambar lengkap)

**H01 · isian angka** — Gambar: lingkaran dengan r = 7 cm.
- Soal: "Jari-jari 7 cm. Berapa panjang diameternya?" — Jawaban: 14 (cm)
- P1: "Diameter terdiri dari berapa jari-jari?" · P2: "d = 2 × r."
- Pembahasan: d = 2 × 7 = 14 cm.

**H02 · isian angka**
- Soal: "Diameter 20 cm. Berapa panjang jari-jarinya?" — Jawaban: 10
- P1: "Jari-jari itu setengah dari…" · P2: "r = d : 2."
- Pembahasan: r = 20 : 2 = 10 cm.

**H03 · pilihan ganda** — Gambar lengkap berlabel huruf (O, A, B, C, D, E).
- Soal: "Daerah yang dibatasi OA, OB, dan busur AB disebut…" — A. Tembereng B. Juring ✅ C. Apotema D. Busur
- P1: "OA dan OB itu unsur apa?" · P2: "OA dan OB adalah jari-jari."
- Pembahasan: Dua jari-jari + busur membatasi juring.

**H04 · ketuk pada gambar** — Gambar lengkap berlabel.
- Soal: "Ketuk semua tali busur." (jawaban: tali busur CD **dan** diameter AB)
- P1: "Ada berapa garis lurus yang ujungnya pada lingkaran?" · P2: "Jangan lupa: diameter juga tali busur."
- Pembahasan: CD dan AB sama-sama menghubungkan dua titik pada lingkaran.

**H05 · isian angka (opsional, jika Pythagoras sudah dipelajari)** — Gambar: r = 5 cm, tali busur = 8 cm, apotema digambar.
- Soal: "Berapa panjang apotemanya?" — Jawaban: 3
- P1: "Apotema membagi tali busur menjadi dua sama panjang." · P2: "Segitiga siku-siku dengan sisi miring 5 dan alas 4."
- Pembahasan: Setengah tali busur = 4. Apotema = √(5² − 4²) = √9 = 3 cm.

**Contoh lengkap → memudar (untuk level Sulit)**
1. *Contoh lengkap:* "r = 6 cm → d = 2 × 6 = 12 cm." (ditampilkan, siswa membaca)
2. *Setengah:* "r = 9 cm → d = 2 × ___ = ___" (siswa mengisi)
3. *Mandiri:* "r = 11 cm. Berapa d?"

## 5. Panduan menulis soal baru
- Satu perintah per soal; kata kerja di awal: *Ketuk, Pilih, Tentukan*.
- Jangan pakai kalimat negatif ganda ("manakah yang bukan tidak…").
- Pengecoh (pilihan salah) diambil dari **pasangan yang sering tertukar**.
- Setiap soal wajib: `petunjuk1`, `petunjuk2`, `pembahasan`, `unsurTerkait` (untuk tautan "ulangi materi").
- Gambar soal level Mudah–Sedang maksimal 3 unsur.
