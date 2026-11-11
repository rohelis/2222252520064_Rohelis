# LingkarKu — Aplikasi Belajar Unsur-Unsur Lingkaran (SMP)

> Nama kerja "LingkarKu" bisa diganti kapan saja.

Aplikasi pembelajaran interaktif untuk siswa SMP (Fase D, kelas VIII) tentang **unsur-unsur lingkaran**:
titik pusat, jari-jari, diameter, busur, tali busur, juring, tembereng, dan apotema.
Desainnya berlandaskan **Teori Beban Kognitif (Cognitive Load Theory)** dan temuan wawancara siswa.
Aplikasi berjalan di **web (PWA)** dan **Android** (dibungkus dengan Capacitor).

## Isi folder perencanaan

| File | Isi | Untuk siapa |
|---|---|---|
| [CLAUDE.md](CLAUDE.md) | Aturan & konteks proyek untuk Claude Code saat membangun aplikasi | Claude Code / developer |
| [docs/01-analisis-kebutuhan.md](docs/01-analisis-kebutuhan.md) | Analisis hasil wawancara S01 → temuan → kebutuhan | Peneliti, dosen |
| [docs/02-PRD.md](docs/02-PRD.md) | Product Requirements Document: tujuan, pengguna, fitur, kriteria terima | Semua |
| [docs/03-desain-pembelajaran.md](docs/03-desain-pembelajaran.md) | Prinsip beban kognitif → aturan desain konkret, alur belajar | Peneliti, desainer |
| [docs/04-konten-materi.md](docs/04-konten-materi.md) | Definisi baku 8 unsur, urutan materi, bank soal awal + petunjuk + pembahasan | Ahli materi, developer |
| [docs/05-desain-ui-ux.md](docs/05-desain-ui-ux.md) | Peta layar, wireframe, warna, tipografi, aksesibilitas | Desainer, developer |
| [docs/06-arsitektur-teknis.md](docs/06-arsitektur-teknis.md) | Tech stack, struktur folder, model data, offline, build Android | Developer |
| [docs/07-roadmap.md](docs/07-roadmap.md) | Tahapan kerja (milestone) & checklist | Semua |
| [docs/08-rencana-evaluasi.md](docs/08-rencana-evaluasi.md) | Validasi ahli, uji kepraktisan, uji efektivitas, instrumen beban kognitif | Peneliti, dosen |

## Urutan membaca yang disarankan
1. `01-analisis-kebutuhan.md` → memahami *mengapa* aplikasi ini dibuat.
2. `02-PRD.md` → memahami *apa* yang dibuat.
3. `03` dan `04` → memahami *bagaimana* materi disajikan.
4. `05`, `06`, `07` → mulai membangun.
5. `08` → menyiapkan penelitian/uji coba.

## Cara memulai pembangunan dengan Claude Code
Buka folder ini di VS Code, lalu minta Claude Code, misalnya:
> "Baca CLAUDE.md dan docs/07-roadmap.md, lalu kerjakan Milestone 0 (setup proyek)."

Kerjakan satu milestone per sesi agar mudah diperiksa.
