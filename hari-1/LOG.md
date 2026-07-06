# Log Hari 1 — Fitur Tarik (Pull) Gacha

Penjelasan santai soal apa yang barusan dibuat di `index.html`.

## Apa yang berubah?

Tampilan (HTML + CSS) tadinya sudah jadi, tapi tombol **TARIK** belum ada fungsinya.
Sekarang logikanya sudah diisi, jadi tombolnya benar-benar bisa "menarik" hadiah acak.

## Cara kerjanya (per bagian)

1. **Data hadiah** — ada 4 tingkat kelangkaan (rarity):
   - `common` (paling gampang keluar) → `rare` → `epic` → `ssr` (paling langka & keren).
   - Tiap hadiah punya nama + emoji.

2. **Sekali tarik (`rollSatu`)** — pakai angka acak `Math.random()`:
   - Peluang **SSR 3%**, **EPIC 10%**, **RARE 30%**, sisanya **COMMON**.

3. **Pity (biar nggak apes terus)** — ini yang bikin adil:
   - Tiap tarik, hitungan "pity" naik 1.
   - Kalau sampai tarikan **ke-10** belum dapat SSR, tarikan ke-10 itu **dijamin SSR**.
   - Begitu dapat SSR, pity balik ke 0.
   - Progress bar kuning di atas menunjukkan seberapa dekat kamu ke SSR gratis.

4. **Tampilan & animasi (`tampilkan`)** — kartu menampilkan hasil dengan efek "pop",
   dan khusus SSR ada efek getar + kilau emas.

5. **Riwayat & tombol** — hasil terakhir dicatat sebagai chip kecil (maks 12).
   - **TARIK 1x** → menarik sekali.
   - **TARIK 10x** → menarik 10 kali beruntun.

## Sudah dites?

Ya. Logikanya diuji pakai simulasi 100.000 tarikan:
- Sebaran rarity sesuai harapan (common paling banyak).
- **Rentetan tanpa SSR maksimal 9** → artinya pity bekerja, nggak pernah tembus 10.
- Setiap jendela 10 tarikan pasti menghasilkan minimal 1 SSR.

## Cara lihat hasilnya

Buka file `hari-1/index.html` di browser (dobel klik), lalu pencet tombol **TARIK**.

## Catatan

Semua perubahan sudah di-commit dengan pesan:
`feat: implement gacha pull feature with pity system in hari-1`
