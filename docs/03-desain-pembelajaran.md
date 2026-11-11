# 03 — Desain Pembelajaran Berbasis Teori Beban Kognitif

## 1. Kerangka singkat
Menurut Teori Beban Kognitif (Sweller), kapasitas memori kerja terbatas. Beban total terdiri dari:
- **Beban intrinsik (IL)** — kerumitan materi itu sendiri (banyaknya elemen yang harus diproses bersamaan). *Tidak bisa dihilangkan, tetapi bisa dikelola* dengan memecah dan mengurutkan materi.
- **Beban ekstrinsik (EL)** — beban akibat cara penyajian yang kurang baik. *Harus ditekan seminimal mungkin.*
- **Beban relevan (GL)** — usaha mental untuk membangun skema. *Didorong*, memakai kapasitas yang dibebaskan dari EL.

Prinsip multimedia Mayer dipakai sebagai turunan praktisnya.

## 2. Prinsip → aturan desain yang wajib dipatuhi

| Prinsip | Aturan desain di aplikasi | Data wawancara |
|---|---|---|
| **Segmentasi** | Satu unsur baru per layar; siswa menekan "Berikutnya" sendiri | DS02, DS03, EL02 |
| **Pra-latihan (pre-training)** | Unsur dasar (titik pusat, jari-jari, diameter) dipelajari dulu sebagai "bahan bangunan" sebelum unsur berupa daerah | IL02, IL03, IL07 |
| **Penanda (signaling)** | Unsur aktif berwarna + garis tebal; unsur lain abu-abu tipis; setiap unsur punya satu warna tetap di seluruh aplikasi | EL07, GL07 |
| **Koherensi** | Tidak ada hiasan, maskot bergerak, musik latar, atau teks yang tidak perlu | DS07, EL07 |
| **Kedekatan ruang** (mencegah *split-attention*) | Label ditulis menempel pada unsurnya; definisi tepat di bawah gambar, tidak di halaman lain | EL06, GL02 |
| **Kedekatan waktu** | Animasi dan teks penjelas muncul bersamaan | DS01 |
| **Redundansi** | Jika ada narasi suara (P2), teks layar hanya kata kunci, bukan kalimat yang sama | — |
| **Modalitas** | (P2) Penjelasan berupa suara + gambar, bukan teks panjang + gambar | EL05 |
| **Kasus kontras** | Mode Bandingkan untuk pasangan mirip, pada gambar yang sama dengan sakelar A ⇄ B | IL01, IL04–IL06 |
| **Contoh lengkap → memudar** (*worked example → fading*) | Level Sulit: contoh dikerjakan lengkap → soal setengah dikerjakan → soal mandiri | DS04, DS06 |
| **Sederhana → kompleks** | Gambar 1 unsur → 2–3 unsur → gambar lengkap | GL06 |
| **Aktivitas generatif** | Eksplorasi geser titik, konstruksi terbimbing, ketuk-pada-gambar | GL01, EL04 |
| **Umpan balik elaboratif** | Petunjuk bertingkat lalu pembahasan "mengapa" | DS05, DS06 |
| **Efek pembalikan keahlian** | Siswa yang sudah menguasai boleh langsung ke Latihan | — |

## 3. Batasan kuantitatif ("aturan keras" saat membangun)
- Maksimal **1 unsur baru** disorot per layar materi.
- Maksimal **3 unsur** tampil bersamaan pada soal level Mudah–Sedang (di luar lingkaran dasar).
- Definisi ≤ **20 kata**; ciri kunci ≤ **10 kata**; perintah soal ≤ **15 kata**; teks per layar ≤ **40 kata**.
- Maksimal **4 pilihan** jawaban.
- Animasi ≤ **8 detik**, diputar sekali, bisa diulang.
- Gambar lengkap 8 unsur hanya muncul di **Ringkasan** dan **level Sulit**.

## 4. Alur belajar

```
Beranda
  │
  ├─► Belajar (urut 1→8)
  │     tiap unsur: Gambar+label → Animasi → Ciri kunci → Cek cepat (1 soal)
  │     setelah unsur 5 (busur)     ► "Bandingkan: busur vs tali busur"
  │     setelah unsur 8 (tembereng) ► "Bandingkan: juring vs tembereng"
  │
  ├─► Bandingkan (3 pasangan)
  ├─► Eksplorasi (geser titik + tantangan)
  ├─► Latihan  Mudah ──(≥70%)──► Sedang ──(≥70%)──► Sulit
  │              └ salah → Petunjuk 1 → Petunjuk 2 → Pembahasan
  │              └ akhir sesi → "Ulangi materi: <unsur yang salah>"
  └─► Ringkasan (8 kartu unsur + gambar lengkap)
```

Perbandingan disisipkan **tepat setelah** unsur kedua dari pasangan dipelajari, karena di situlah
kebingungan muncul (IL05: tertukar karena "keduanya menghubungkan dua titik").

## 5. Contoh rancangan satu layar unsur: Tembereng
1. **Gambar**: lingkaran abu-abu; daerah tembereng diarsir warna tembereng.
2. **Animasi "telusuri batas"**: tali busur muncul (label "tali busur") → busur muncul (label "busur") → daerah di antaranya terisi warna (label "tembereng").
3. **Definisi**: "Tembereng adalah daerah yang dibatasi oleh tali busur dan busur."
4. **Ciri kunci**: "Batasnya: 1 garis lurus + 1 garis lengkung."
5. **Pengingat kontras** (kecil): "Bukan juring — juring dibatasi 2 jari-jari."
6. **Cek cepat**: "Ketuk daerah yang merupakan tembereng." (gambar berisi 1 juring dan 1 tembereng)

## 6. Strategi menangani miskonsepsi
| Miskonsepsi yang mungkin | Strategi di aplikasi |
|---|---|
| Juring dan tembereng dianggap sama ("sama-sama daerah") | Fokus pada **batas**: juring selalu menyentuh titik pusat (dibatasi 2 jari-jari), tembereng dibatasi tali busur |
| Busur dianggap garis lurus / tali busur dianggap lengkung | Ciri kunci "lengkung = busur, lurus = tali busur"; animasi busur "ditarik lurus" menjadi tali busur |
| Diameter tidak dianggap tali busur | Eksplorasi: geser tali busur hingga melewati pusat → "Tali busur ini juga diameter (tali busur terpanjang)" |
| Apotema dianggap jari-jari | Tunjukkan apotema tidak sampai ke keliling dan tegak lurus tali busur (tanda siku) |
| Juring hanya yang kecil | Tampilkan juring kecil dan juring besar dari dua jari-jari yang sama |
| Jari-jari hanya yang mengarah ke kanan | Tampilkan beberapa jari-jari ke berbagai arah, semuanya sama panjang |

## 7. Pola penulisan umpan balik
- **Petunjuk 1 (umum)** — mengarahkan perhatian tanpa memberi jawaban. *"Perhatikan batas daerahnya. Ada jari-jarinya atau tidak?"*
- **Petunjuk 2 (spesifik)** — gambar menyorot bagian penting. *Batas daerah berkedip; "Daerah ini dibatasi garis lurus yang tidak melewati titik pusat."*
- **Pembahasan** — 1–2 kalimat mengapa jawaban benar + 1 kalimat mengapa pilihan siswa keliru.
- Nada positif dan netral: "Belum tepat, coba lagi ya" — hindari tulisan "SALAH!" merah besar.
