# 06 — Arsitektur Teknis

## 1. Keputusan utama
**Satu kode untuk web dan Android**: dibangun sebagai **Progressive Web App (PWA)**, lalu dibungkus
menjadi APK Android dengan **Capacitor**.

| Alternatif | Alasan tidak dipilih |
|---|---|
| Flutter | Bahasa Dart baru dipelajari; ekosistem SVG/geometri interaktif lebih kaya di web |
| Android native (Kotlin) | Tidak bisa sekaligus untuk web |
| Unity / Godot | Terlalu berat untuk aplikasi materi; ukuran APK besar |
| Hanya PWA tanpa APK | Sebagian sekolah lebih mudah membagikan APK / ingin di Play Store |

## 2. Tech stack

| Lapisan | Pilihan | Catatan |
|---|---|---|
| Bahasa | TypeScript | Mencegah salah ketik data soal |
| UI | React 18 | |
| Build | Vite | Cepat, sederhana |
| Gambar & geometri | **SVG** dibuat lewat komponen React | Tajam di semua ukuran layar, ringan, bisa dianimasikan |
| Animasi | CSS transition + `stroke-dashoffset` untuk efek "menggambar garis"; Framer Motion bila perlu | |
| Routing | React Router (hash router agar aman di Capacitor) | |
| State | React Context + `useReducer` | Tidak perlu Redux |
| Penyimpanan | `localStorage` (dibungkus try/catch) | Progres & pengaturan |
| Offline | `vite-plugin-pwa` (Workbox) | Precache semua aset |
| Android | Capacitor 6 | `npx cap add android` |
| Styling | CSS Modules + CSS variables (token dari 05) | Tailwind boleh jika lebih nyaman |
| Uji unit | Vitest + Testing Library | Fungsi geometri & logika umpan balik |
| Uji E2E | Playwright (viewport 360 × 740) | Alur utama |
| Kualitas | ESLint + Prettier | |
| Hosting web | GitHub Pages / Netlify / Vercel (gratis) | |

## 3. Struktur folder

```
lingkarku/
├─ CLAUDE.md
├─ docs/                      # dokumen perencanaan ini
├─ public/
│  ├─ icons/                  # ikon PWA & Android
│  └─ manifest.webmanifest
├─ src/
│  ├─ main.tsx
│  ├─ App.tsx                 # routing
│  ├─ content/                # SEMUA teks materi & soal (tanpa logika)
│  │  ├─ unsur.ts             # 8 kartu unsur
│  │  ├─ bandingkan.ts        # 3 pasangan
│  │  ├─ soal/
│  │  │  ├─ mudah.ts
│  │  │  ├─ sedang.ts
│  │  │  └─ sulit.ts
│  │  └─ tantangan.ts         # tantangan eksplorasi
│  ├─ geometry/               # fungsi matematika murni (teruji)
│  │  ├─ circle.ts            # titikPadaLingkaran, jarak, sudut
│  │  └─ paths.ts             # path SVG busur, juring, tembereng
│  ├─ components/
│  │  ├─ circle/              # <CircleCanvas>, <Radius>, <Chord>, <Arc>, <Sector>, <Segment>, <Apothem>, <CenterPoint>, <Label>
│  │  ├─ ui/                  # <Button>, <Card>, <ProgressBar>, <HintBox>, <Toggle>
│  │  └─ quiz/                # <MultipleChoice>, <TapOnFigure>, <TrueFalse>, <NumberInput>
│  ├─ screens/                # Home, LearnList, LearnElement, Compare, Explore, PracticeLevel, Question, Result, Summary, Settings
│  ├─ state/                  # ProgressContext, SettingsContext, storage.ts
│  ├─ styles/                 # tokens.css, global.css
│  └─ types.ts
├─ tests/
│  ├─ unit/
│  └─ e2e/
├─ capacitor.config.ts
├─ vite.config.ts
└─ package.json
```

**Aturan penting:** isi materi di `src/content/` dipisah dari kode, sehingga ahli materi/peneliti bisa
merevisi teks tanpa menyentuh komponen.

## 4. Model data (TypeScript)

```ts
export type UnsurId =
  | 'titik-pusat' | 'jari-jari' | 'diameter' | 'tali-busur'
  | 'busur' | 'apotema' | 'juring' | 'tembereng';

export interface Unsur {
  id: UnsurId;
  urutan: number;               // 1..8
  nama: string;                 // "Tali Busur"
  jenis: 'titik' | 'ruas-garis' | 'garis-lengkung' | 'daerah';
  definisi: string;             // ≤ 20 kata
  ciriKunci: string;            // ≤ 10 kata
  tambahan?: string;
  pengingatKontras?: string;    // "Bukan juring — ..."
  warnaToken: string;           // "--el-tali-busur"
  figur: FigurSpec;             // apa yang digambar
  langkahAnimasi: LangkahAnimasi[];
  cekCepatId: string;           // id soal cek cepat
}

export interface FigurSpec {
  // sudut dalam derajat, 0° = kanan, berlawanan arah jarum jam
  tampil: Array<
    | { jenis: 'titik-pusat' }
    | { jenis: 'jari-jari'; sudut: number }
    | { jenis: 'diameter'; sudut: number }
    | { jenis: 'tali-busur'; sudutA: number; sudutB: number }
    | { jenis: 'busur'; sudutA: number; sudutB: number; besar?: boolean }
    | { jenis: 'apotema'; sudutA: number; sudutB: number }
    | { jenis: 'juring'; sudutA: number; sudutB: number; besar?: boolean }
    | { jenis: 'tembereng'; sudutA: number; sudutB: number; besar?: boolean }
  >;
  sorot?: number[];             // indeks elemen yang disorot; sisanya diredupkan
  label?: Record<number, string>;
  titikBernama?: Record<string, number>; // { A: 30, B: 150 } posisi sudut
}

export interface LangkahAnimasi { elemen: number; teks?: string; durasiMs: number; }

export type Level = 'mudah' | 'sedang' | 'sulit';

interface SoalDasar {
  id: string;                   // "M01"
  level: Level;
  perintah: string;             // ≤ 15 kata
  figur?: FigurSpec;
  petunjuk1: string;
  petunjuk2: string;
  sorotPetunjuk2?: number[];    // elemen yang berkedip saat petunjuk 2
  pembahasan: string;
  unsurTerkait: UnsurId[];
}

export type Soal =
  | (SoalDasar & { tipe: 'pilihan-ganda'; pilihan: string[]; kunci: number; alasanPengecoh?: Record<number, string> })
  | (SoalDasar & { tipe: 'benar-salah'; kunci: boolean })
  | (SoalDasar & { tipe: 'ketuk-gambar'; kunci: number[] })            // indeks elemen figur yang benar
  | (SoalDasar & { tipe: 'isian-angka'; kunci: number; satuan?: string; toleransi?: number });

export interface Progres {
  versi: 1;
  unsurSelesai: UnsurId[];
  latihan: Record<Level, { terbaik: number; jumlahSoal: number; terakhir?: string }>;
  levelTerbuka: Level[];
}
```

## 5. Komponen geometri inti
- `CircleCanvas` — `<svg viewBox="-120 -120 240 240">`, r = 100 unit; skala otomatis ke lebar layar.
- Semua unsur dihitung dari **sudut** pada lingkaran → mudah membuat soal baru dan konsisten.
- `paths.ts`:
  - busur: perintah SVG `A r r 0 largeArc sweep x y`;
  - juring: `M O → L A → A … B → Z`;
  - tembereng: `M A → A … B → Z` (tutup lewat tali busur);
  - apotema: titik kaki = proyeksi O ke AB (titik tengah AB).
- Hit-test ketuk: setiap elemen punya `pointer-events` sendiri + area sentuh yang diperbesar (stroke transparan lebar 24 px).
- Eksplorasi: Pointer Events (`pointerdown/move/up`), posisi jari dikonversi ke sudut `atan2`, titik "dikunci" ke keliling. Snap ±3° ke kondisi tantangan (mis. melewati pusat).

## 6. Offline & PWA
- `vite-plugin-pwa` mode `generateSW`, `registerType: 'autoUpdate'`, precache seluruh build.
- Tidak ada panggilan jaringan saat runtime; font di-bundle lokal (bukan Google Fonts) agar berjalan offline.
- Manifest: `name`, `short_name`, `lang: "id"`, `display: "standalone"`, `orientation: "portrait"`, ikon 192/512 + maskable.

## 7. Build Android (Capacitor)
```
npm run build
npx cap sync android
npx cap open android      # build APK di Android Studio
```
- `appId`: misal `id.ac.<kampus>.lingkarku` (sesuaikan).
- `minSdkVersion` 26 (Android 8.0).
- Tombol "kembali" Android dihubungkan ke navigasi aplikasi (`@capacitor/app` → `backButton`).
- Status bar/safe area: pakai `env(safe-area-inset-*)`.
- Untuk distribusi uji coba: APK debug/release yang ditandatangani dibagikan langsung; Play Store opsional.

## 8. Privasi & keamanan
- Tidak ada login, tidak ada server, tidak ada analytics pihak ketiga.
- Data hanya di perangkat siswa. Jika kelak perlu data penelitian, gunakan fitur **ekspor hasil** yang dibagikan siswa secara sadar (F9), bukan pelacakan diam-diam.

## 9. Skrip npm yang diharapkan
| Skrip | Fungsi |
|---|---|
| `npm run dev` | Server pengembangan |
| `npm run build` | Build produksi ke `dist/` |
| `npm run preview` | Pratinjau build |
| `npm run test` | Vitest |
| `npm run test:e2e` | Playwright |
| `npm run lint` | ESLint |
| `npm run android` | build + `cap sync android` |
