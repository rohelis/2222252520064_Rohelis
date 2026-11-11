# 05 — Desain UI/UX

## 1. Prinsip tampilan (dari DS07, EL06, EL07)
1. **Sederhana** — satu fokus per layar, banyak ruang kosong.
2. **Sedikit tulisan** — gambar menyampaikan, teks menegaskan.
3. **Warna lembut** — latar terang netral; warna hanya untuk menandai unsur.
4. **Tombol mudah** — besar, di bagian bawah layar (terjangkau ibu jari), berlabel kata, bukan ikon saja.

## 2. Peta layar

```
Splash (≤1 dtk)
└─ Beranda
   ├─ Belajar ──► Daftar 8 unsur (tanda ✓ jika selesai)
   │               └─ Layar Unsur (1..8) ──► Cek Cepat ──► [Bandingkan sisipan] ──► Unsur berikutnya
   ├─ Bandingkan ──► Pilih pasangan (3) ──► Layar Bandingkan
   ├─ Eksplorasi ──► Kanvas interaktif + daftar tantangan
   ├─ Latihan ──► Pilih level (Mudah/Sedang/Sulit) ──► Soal 1..n ──► Hasil Sesi
   ├─ Ringkasan ──► 8 kartu ──► (ketuk) Layar Unsur
   └─ ⚙ Pengaturan (ukuran teks, suara, kontras tinggi, reset progres, tentang aplikasi)
```

## 3. Wireframe (potret, 360 × 740)

**Beranda**
```
┌──────────────────────────────┐
│ LingkarKu                ⚙   │
│ Unsur-Unsur Lingkaran        │
│ ▓▓▓▓▓░░░  5 dari 8 unsur     │
│ ┌──────────┐ ┌──────────┐    │
│ │  ◯ Belajar│ │ ⇄ Banding-│   │
│ │          │ │    kan    │    │
│ └──────────┘ └──────────┘    │
│ ┌──────────┐ ┌──────────┐    │
│ │ ✎ Latihan│ │ ▤ Ringkas-│   │
│ │          │ │    an     │    │
│ └──────────┘ └──────────┘    │
│ ┌──────────────────────────┐ │
│ │ ✋ Eksplorasi             │ │
│ └──────────────────────────┘ │
└──────────────────────────────┘
```

**Layar Unsur**
```
┌──────────────────────────────┐
│ ←  Unsur 4 dari 8            │
│ Tali Busur                   │
│                              │
│        .-~~~~~-.             │
│      /           \           │
│     A━━━━━━━━━━━━B  ← tali   │
│     |      ·O     |    busur │
│      \           /           │
│        '-.___.-'             │
│                              │
│ Ruas garis yang menghubungkan│
│ dua titik pada lingkaran.    │
│ 🔑 Lurus; tidak harus lewat  │
│    titik pusat.              │
│        [ ▶ Putar animasi ]   │
│ [ ‹ Sebelumnya ][ Berikutnya ›]│
└──────────────────────────────┘
```

**Layar Bandingkan**
```
┌──────────────────────────────┐
│ ←  Juring vs Tembereng       │
│  [ Juring ]|[ Tembereng ]    │  ← sakelar
│        (gambar sama,         │
│     sorotan berganti)        │
│ ┌────────┬─────────┬────────┐│
│ │        │ Juring  │Tembere.││
│ │ Batas  │2 jari2  │tali bsr││
│ │        │+ busur  │+ busur ││
│ │ Pusat? │menyentuh│ tidak  ││
│ └────────┴─────────┴────────┘│
│      [ ▶ Telusuri batas ]    │
└──────────────────────────────┘
```

**Layar Soal (setelah salah sekali)**
```
┌──────────────────────────────┐
│ ←  Latihan Sedang   3/8      │
│ Ketuk daerah tembereng.      │
│        (gambar)              │
│ ┌──────────────────────────┐ │
│ │ 💡 Petunjuk: Tembereng    │ │
│ │ tidak dibatasi jari-jari.│ │
│ └──────────────────────────┘ │
│                [ Periksa ]   │
└──────────────────────────────┘
```

## 4. Warna

Latar dan teks:
| Token | Nilai | Pemakaian |
|---|---|---|
| `--bg` | `#F7F8FA` | Latar aplikasi |
| `--surface` | `#FFFFFF` | Kartu |
| `--text` | `#1F2937` | Teks utama |
| `--text-muted` | `#6B7280` | Teks sekunder |
| `--circle` | `#374151` | Garis lingkaran dasar |
| `--inactive` | `#D1D5DB` | Unsur yang tidak sedang dibahas |
| `--primary` | `#2F6FB5` | Tombol utama |
| `--correct` | `#2E7D5B` | Umpan balik benar |
| `--retry` | `#B7791F` | Umpan balik "coba lagi" (oranye lembut, bukan merah) |

Warna unsur (tetap di seluruh aplikasi, saturasi sedang):
| Unsur | Warna | Gaya garis/isi (pembeda selain warna) |
|---|---|---|
| Titik pusat | `#1F2937` | titik tebal + huruf O |
| Jari-jari | `#2F6FB5` biru | garis penuh |
| Diameter | `#2E7D5B` hijau | garis putus-panjang |
| Tali busur | `#8B5CF6` ungu | garis penuh tebal |
| Busur | `#C2410C` jingga tua | garis lengkung tebal |
| Apotema | `#BE185D` magenta | garis putus-putus + tanda siku |
| Juring | `#F2C94C` @ 45% | isi + arsir diagonal |
| Tembereng | `#7FB8D9` @ 45% | isi + arsir titik |

> Warna wajib diuji dengan simulator buta warna. Pembeda juga dinyatakan lewat **label teks** dan **pola**,
> sehingga tidak bergantung pada warna saja.
> Mode gelap: tidak diwajibkan di MVP (P2), tetapi semua warna sudah ditaruh di token CSS agar mudah ditambah.

## 5. Tipografi
- Font: **Nunito** atau **Lexend** (ramah pembaca muda), cadangan `system-ui`.
- Ukuran: judul 22 px, isi 17 px, label gambar 15 px, minimal 14 px.
- Mode teks besar: semua × 1,2.
- Istilah matematika ditulis **tebal** saat pertama muncul di layar.

## 6. Interaksi
- Target sentuh ≥ 48 × 48 px; titik geser di Eksplorasi punya area sentuh 44 px walau tampil 14 px.
- Ketuk-pada-gambar: daerah yang diketuk memberi sorotan tipis sebelum "Periksa" (siswa bisa mengubah pilihan).
- Animasi: `ease-in-out`, 300–800 ms per langkah; hormati pengaturan `prefers-reduced-motion` (tampilkan langkah statis).
- Getar/suara efek pendek hanya jika diaktifkan.
- Tidak ada batas waktu pada soal (mengurangi beban & kecemasan).

## 7. Aksesibilitas
- Kontras teks ≥ 4,5 : 1.
- Semua SVG memiliki `role="img"` dan `aria-label` (mis. "Lingkaran dengan tali busur AB disorot").
- Semua tombol bisa dioperasikan keyboard (untuk versi web/proyektor).
- Bahasa halaman `lang="id"`.

## 8. Tata letak lanskap / proyektor
- Gambar di kiri (60%), teks & tombol di kanan (40%), agar teks tetap dekat dengan gambar.
