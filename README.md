# Layanan Akademik Fakultas Universitas Pattimura – Pertemuan 5 (Responsive & Accessible Web Client)

Satu halaman web client statis (HTML + CSS, tanpa JavaScript) untuk layanan akademik fakultas di Universitas Pattimura (Unpatti), Ambon.

## Struktur proyek
```
index.html
css/styles.css
img/            (tidak ada gambar informatif)
evidence/       (taruh screenshot bukti DevTools di sini)
README.md
```

## Keputusan desain
- **Semantik**: `header`, `nav`, `main`, `section`, `article` (tiap kartu), `form`, `footer`. Heading: satu `h1`, `h2` per section, `h3` per kartu.
- **Mobile-first**: CSS dasar satu kolom; breakpoint `40em` (kartu 2 kolom, saat satu kolom mulai terlalu lebar) dan `64em` (4 kolom, saat ruang cukup).
- **Layout**: CSS Grid untuk kartu, Flexbox untuk header, nav, dan isi kartu.
- **Form**: label terasosiasi (`for`/`id`), `fieldset`+`legend`, tipe `text`/`email`/`select`/`textarea`/`checkbox`, atribut `required`, `minlength`, `maxlength`, `pattern`, serta petunjuk lewat `aria-describedby`. Tombol memakai `<button type="submit">`.
- **Aksesibilitas**: skip link, fokus terlihat (`:focus-visible`), target sentuh ≥ 44px, kontras tinggi, `prefers-reduced-motion`, ARIA hanya `aria-label` pada nav dan `aria-describedby` (elemen native didahulukan).
- **Gambar**: tidak ada gambar informatif. Ikon topi toga di header adalah SVG dekoratif dengan `aria-hidden="true"` karena nama portal sudah ada dalam teks.
- **Tanpa overflow**: `box-sizing: border-box`, `min-width: 0` pada item grid, `overflow-wrap: anywhere`, `max-width: 100%` pada media.

## Hasil pemeriksaan DevTools (isi setelah Anda menguji)
Simpan screenshot di folder `evidence/` dengan nama seperti di tabel.

| Pemeriksaan | Cara | Hasil | Bukti |
|---|---|---|---|
| Elements/Inspector | Periksa landmark, heading, label–input | ☐ | `evidence/01-elements.png` |
| Responsive 360 px | F12 → Ctrl+Shift+M → 360 | ☐ tanpa scroll horizontal | `evidence/02-360.png` |
| Responsive 768 px | lebar 768 | ☐ 2 kolom kartu | `evidence/03-768.png` |
| Responsive 1280 px | lebar 1280 | ☐ 4 kolom kartu | `evidence/04-1280.png` |
| Network | Reload (Ctrl+R), cek status 200, tak ada resource gagal | ☐ | `evidence/05-network.png` |
| Accessibility | Tab Accessibility tree / Lighthouse Accessibility | ☐ | `evidence/06-a11y.png` |
| Keyboard | Tab melalui semua kontrol, fokus terlihat | ☐ | `evidence/07-focus.png` |
| Validasi email | Isi `abc` lalu kirim, pesan error muncul | ☐ | `evidence/08-validasi.png` |

### Catatan temuan debugging
Tulis 2–3 temuan nyata Anda di sini (masalah → penyebab → perbaikan).

## Cara menjalankan
Buka `index.html` di browser, atau gunakan ekstensi Live Server di VS Code.

## Deploy ke GitHub Pages (untuk URL aplikasi)
1. Buat repo baru di GitHub, unggah semua isi folder ini.
2. Settings → Pages → Source: `main` / root → Save.
3. URL: `https://<username>.github.io/<nama-repo>/`
