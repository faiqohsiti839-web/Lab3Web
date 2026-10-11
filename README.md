# Lab3Web
Tugas post test praktikum 3

# Lab3Web
Tugas Post Test Praktikum 3

# Praktikum 3: CSS Dasar – Pemrograman Web

Repository ini berisi hasil Praktikum 3 mata kuliah Pemrograman Web tentang dasar-dasar CSS (Cascading Style Sheets).

Identitas


| Nama | Siti Faiqoh Almarufi |
| NIM | 312510168 |
| Program Studi | Teknik Informatika |
| Universitas | Universitas Pelita Bangsa |
| Mata Kuliah | Pemrograman Web |

#Tujuan Praktikum

1. Memahami tiga cara penerapan CSS pada dokumen HTML: internal, inline, dan eksternal.
2. Memahami dan menggunakan CSS Selector: element (tag), ID, dan class.
3. Mampu mengatur tampilan dasar halaman web seperti warna, font, jarak (padding/margin), border, dan perataan teks.


#Struktur File

```
Lab3Web/
├── lab2_css_dasar.html     # Halaman utama (HTML + CSS internal + inline)
├── style_eksternal.css     # File CSS eksternal (navigasi & selector)
├── screenshots/            # Tangkapan layar hasil praktikum
└── README.md               # Dokumentasi praktikum
```

> Catatan: tautan navigasi pada halaman mengarah ke `lab2_css_eksternal.html` dan `lab1_tag_dasar.html`. Kedua file tersebut perlu berada di folder yang sama agar tautan berfungsi.

---

#Langkah-Langkah Praktikum

#Langkah 1 – Membuat Struktur Dasar HTML

Membuat file `lab2_css_dasar.html` dengan kerangka dokumen HTML5.

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Dasar</title>
</head>
<body>
    ...
</body>
</html>
```

Penjelasan:
- `<!DOCTYPE html>` memberi tahu browser bahwa dokumen menggunakan HTML5.
- `lang="id"` menandakan bahasa dokumen adalah Bahasa Indonesia.
- `<meta charset="UTF-8">` memastikan karakter (termasuk huruf khusus) tampil dengan benar.
- `<meta name="viewport">` membuat halaman responsif di berbagai ukuran layar.
- `<title>` menentukan judul yang tampil pada tab browser.

Pada bagian `<body>` dibuat tiga elemen utama: `<header>` (judul halaman), `<nav>` (menu navigasi), dan `<div id="intro">` (konten pengantar).

---

#Langkah 2 – CSS Internal

CSS internal ditulis di dalam tag `<style>` pada bagian `<head>` dokumen HTML.

```html
<style>
    body {
        font-family: 'Open Sans', sans-serif;
    }

    header {
        min-height: 80px;
        border-bottom: 1px solid #77CCEF;
    }

    h1 {
        font-size: 24px;
        color: #0F189F;
        text-align: center;
        padding: 20px 10px;
    }

    h1 i {
        color: #6d6a6b;
    }
</style>
```

Penjelasan:

| Selector | Fungsi |
|---|---|
| `body` | Mengatur jenis font seluruh halaman menjadi Open Sans, dengan cadangan `sans-serif` bila font tidak tersedia. |
| `header` | Memberi tinggi minimal 80px dan garis bawah berwarna biru muda sebagai pemisah. |
| `h1` | Mengatur ukuran font 24px, warna biru tua, teks rata tengah, serta padding agar tidak terlalu rapat. |
| `h1 i` | *Descendant selector*: hanya memengaruhi tag `<i>` yang berada di dalam `<h1>`, sehingga teks miring berwarna abu-abu. |

Kapan digunakan:cocok untuk styling yang hanya berlaku pada **satu halaman**.

---

#Langkah 3 – Inline CSS

Inline CSS ditulis langsung pada atribut `style` di dalam tag HTML.

```html
<p style="text-align: center; color: #ccd8e4;">
    Kami sedang belajar HTML dan CSS dasar, pada mata kuliah
    <b>Pemrograman Web</b> di <i>Universitas Pelita Bangsa</i>.
    ...
</p>
```

Penjelasan:
- `text-align: center` membuat paragraf rata tengah.
- `color: #ccd8e4` memberi warna teks abu-abu kebiruan terang.
- Style ini hanya berlaku pada satu elemen tersebut.
- Inline CSS memiliki prioritas tertinggi dibanding CSS internal dan eksternal.

Kapan digunakan: untuk perubahan cepat pada satu elemen. Tidak disarankan untuk dipakai berlebihan karena menyulitkan perawatan kode.

---

#Langkah 4 – CSS Eksternal

CSS eksternal ditulis pada file terpisah (`style_eksternal.css`) lalu dihubungkan ke HTML menggunakan tag `<link>`.

Menghubungkan di HTML:

```html
<link rel="stylesheet" href="style_eksternal.css" type="text/css">
```

Isi `style_eksternal.css` (bagian navigasi):

```css
nav {
    background: #20A759;
    color: #fff;
    padding: 10px;
}

nav a {
    color: #fff;
    text-decoration: none;
    padding: 10px 20px;
}

nav .active,
nav a:hover {
    background: #0B6B3A;
}
```

Penjelasan:

Aturan Fungsi 
| `nav` | Memberi latar hijau, teks putih, dan padding 10px pada menu navigasi. |
| `nav a` | Mengubah link menjadi putih, menghilangkan garis bawah, dan menambah ruang klik (padding 10px 20px). |
| `nav .active, nav a:hover` | Memberi warna hijau lebih gelap pada menu yang aktif atau saat kursor diarahkan (hover) ke link. Tanda koma (`,`) berarti dua selector memakai aturan yang sama. |

Pada HTML, menu navigasi dibuat sebagai berikut:

```html
<nav>
    <a href="lab2_css_dasar.html">CSS Dasar</a>
    <a href="lab2_css_eksternal.html">CSS Eksternal</a>
    <a href="lab1_tag_dasar.html">HTML Dasar</a>
</nav>
```

Kapan digunakan: paling direkomendasikan untuk proyek nyata karena satu file CSS bisa dipakai oleh banyak halaman sekaligus dan kode lebih rapi.

---

#Langkah 5 – CSS Selector (ID dan Class)

Selector menentukan elemen HTML mana yang akan diberi style.

a. ID Selector (`#`)

```css
#intro {
    background: #418fb1;
    border: 1px solid #099249;
    min-height: 100px;
    padding: 10px;
}

#intro h1 {
    text-align: left;
    border: 0;
    color: #fff;
}
```

```html
<div id="intro">
    <h1>Hello World</h1>
    ...
</div>
```

Penjelasan:
- `#intro` menargetkan elemen dengan `id="intro"`. ID bersifat unik, hanya boleh dipakai satu kali per halaman.
- Elemen diberi latar biru, border hijau, tinggi minimal 100px, dan padding 10px.
- `#intro h1` mengubah `<h1>` di dalam `#intro` menjadi rata kiri, tanpa border, dan berwarna putih. Aturan ini menimpa style `h1` dari CSS internal karena selector-nya lebih spesifik.

b. Class Selector (`.`)

```css
.button {
    padding: 15px 20px;
    background: #bebcbd;
    color: #fff;
    display: inline-block;
    margin: 10px;
    text-decoration: none;
}

.btn-primary {
    background: #E42A42;
}
```

```html
<a class="button btn-primary" href="#intro">Informasi selengkapnya.</a>
```

Penjelasan:
- `.button` menargetkan semua elemen ber-`class="button"`. Class boleh dipakai berulang pada banyak elemen.
- `display: inline-block` membuat link bisa diberi padding dan margin layaknya kotak, namun tetap sejajar dengan teks.
- `.btn-primary` hanya mengubah warna latar menjadi merah (`#E42A42`).
- Satu elemen dapat memiliki lebih dari satu class (`button btn-primary`), sehingga tampilan dasar tombol dan variasi warnanya bisa digabung.

---

#Langkah 6 – Menjalankan dan Menguji

1. Simpan `lab2_css_dasar.html` dan `style_eksternal.css` dalam satu folder.
2. Buka file HTML di browser (klik dua kali atau gunakan Live Server di VS Code).
3. Periksa hasil: header, navigasi hijau (cek efek hover), kotak `#intro` berwarna biru, dan tombol merah.
4. Ambil tangkapan layar dan simpan di folder `screenshots/`.

#Ringkasan Perbandingan Jenis CSS

Jenis Lokasi Penulisan Cakupan Prioritas

| Inline | Atribut `style` pada tag | Satu elemen | Tertinggi |
| Internal | Tag `<style>` di `<head>` | Satu halaman | Menengah |
| Eksternal | File `.css` terpisah via `<link>` | Banyak halaman | Terendah* |

\ Jika selector sama-sama setara, aturan yang ditulis paling akhir akan menang. Pada praktikum ini, `<link>` ditempatkan sebelum `<style>`, sehingga CSS internal dapat menimpa CSS eksternal untuk selector yang sama.

#Ringkasan Selector yang Dipelajari

Selector Contoh Menargetkan

| Element | `h1`, `nav`, `header` | Semua tag dengan nama tersebut |
| Descendant | `h1 i`, `nav a`, `#intro h1` | Elemen di dalam elemen lain |
| ID | `#intro` | Satu elemen dengan `id` tertentu |
| Class | `.button`, `.btn-primary` | Semua elemen dengan `class` tertentu |
| Pseudo-class | `a:hover` | Elemen pada kondisi tertentu (kursor di atasnya) |

#Hasil Tampilan

Tambahkan tangkapan layar hasil praktikum di sini:

#Bukti Verifikasi

<img width="1365" height="767" alt="verifikasi" src="https://github.com/user-attachments/assets/ef868ab5-7ea6-470c-8313-8b57cddd7a4f" />


<img width="794" height="595" alt="WhatsApp Image 2026-10-11 at 12 31 15 (1)" src="https://github.com/user-attachments/assets/46d808dc-22a1-4b88-97fc-6d5dea390b56" />

<img width="792" height="56" alt="WhatsApp Image 2026-10-11 at 12 31 15" src="https://github.com/user-attachments/assets/e56ea5cf-622d-40ce-888d-f1f2a7fe5fc7" />

<img width="789" height="537" alt="WhatsApp Image 2026-10-11 at 12 31 16" src="https://github.com/user-attachments/assets/3181e530-ca84-46dd-8930-0ac9a5eba9f9" />

<img width="811" height="556" alt="WhatsApp Image 2026-10-11 at 12 31 14" src="https://github.com/user-attachments/assets/2e2b5a04-53a1-4f1f-a03e-f405751fc4ef" />

<img width="792" height="373" alt="WhatsApp Image 2026-10-11 at 12 31 14 (1)" src="https://github.com/user-attachments/assets/230420bc-f960-4fc9-92df-b54f8840cc4b" />


<img width="1365" height="767" alt="WhatsApp Image 2026-10-11 at 12 31 32" src="https://github.com/user-attachments/assets/4d1cba58-4a44-4da1-9c41-b7d8b345cce7" />

<img width="1365" height="767" alt="WhatsApp Image 2026-10-11 at 12 31 32" src="https://github.com/user-attachments/assets/f9b13f33-79f1-4b5d-b9a8-3a9b68f5befc" />

<img width="1365" height="767" alt="WhatsApp Image 2026-10-11 at 12 31 32 (1)" src="https://github.com/user-attachments/assets/a2e392ba-c487-4fb4-b81f-998bad57f023" />

<img width="1365" height="767" alt="WhatsApp Image 2026-10-11 at 12 31 32 (2)" src="https://github.com/user-attachments/assets/d025da58-376d-476e-9edd-146a1e338f3a" />

#Eksperimen
<img width="1365" height="767" alt="WhatsApp Image 2026-10-11 at 12 31 38" src="https://github.com/user-attachments/assets/e63b7081-2b98-4444-a01f-9abe6393eab3" />



#Kesimpulan

Dari praktikum ini dapat disimpulkan bahwa:

1. CSS dapat diterapkan dengan tiga cara: inline, internal, dan eksternal. Cara eksternal paling efisien dan mudah dirawat untuk proyek berskala besar.
2. Selector (element, ID, class) memungkinkan pengaturan tampilan secara tepat sasaran.
3. Pemisahan antara struktur (HTML) dan tampilan (CSS) membuat kode lebih rapi, terstruktur, dan mudah dikembangkan.
4. Properti dasar seperti `color`, `background`, `padding`, `margin`, `border`, `text-align`, dan `display` merupakan fondasi dalam mendesain halaman web.
