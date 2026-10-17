# Jawaban Praktikum: [Ade Sopi Fauzan] ([10224041])

## Bagian 1: Pemanasan

1. Pada `nav a.active:hover { color: red; }`:
   - Selector: `nav a.active:hover`
   - Deklarasi: `color: red;`
   - Property: `color`
   - Value: `red`
   - Pseudo-class: `:hover`
2. Default block: `p`, `li`, `h2`. Default inline: `span`, `a`, `strong`.
3. Paragraf yang hijau: **A dan B**. Keduanya merupakan elemen `p` yang berada di dalam elemen dengan class `box`. C memiliki class `box` sendiri tetapi bukan keturunan dari elemen `.box`; D tidak berada di dalam `.box`.
4. Warnanya **merah**, karena selector ID `#title` memiliki specificity lebih tinggi daripada selector class `.heading` dan selector elemen `h1`.
5. Tag bersarang tidak ditutup dalam urutan yang benar. Seharusnya `<p>Hello <strong>world</strong></p>`.

## Bagian 3: Prediksi Selector Golf

P1.
- (a) `Weekly hack nights.`: hijau, karena cocok dengan `p` dan `section p`; `section p` lebih spesifik.
- (b) `Bring your own laptop.`: oranye, karena `.note` lebih spesifik daripada `section p`.
- (c) `© 2026 Student Affairs`: biru, karena hanya cocok dengan `p`.

P2. Specificity tertinggi ke terendah:
1. `#tech p`
2. `.club p`
3. `main section p`
4. `p`

Setelah diuji (hasil sebenarnya):
- (a) hijau
- (b) oranye
- (c) biru
- Urutan specificity sesuai daftar P2 di atas.

## Bagian 4: Box model

Q1 (content-box):
- Lebar terlihat dari tepi border ke tepi border = content + padding kiri/kanan + border kiri/kanan.
- `300px + 16px + 16px + 1px + 1px = 334px`.
- Margin 24px tidak termasuk lebar dari tepi border ke tepi border. Jika menghitung ruang total termasuk margin kiri dan kanan, hasilnya 382px.

Q2 (border-box):
- Dengan `box-sizing: border-box`, lebar yang ditetapkan 300px sudah mencakup content, padding, dan border. Jadi lebar dari tepi border ke tepi border adalah 300px.
- Dengan margin kiri dan kanan masing-masing 24px, ruang total menjadi 348px.

Pengecekan DevTools:
- Buka `profile.html` di browser.
- Klik kanan salah satu kartu bagian → Inspect.
- Buka panel Computed dan bagian Box Model.
- Catat nilai content, padding, border, dan margin yang tampil pada browser kamu.

## Bagian 5: Tabel debug

| # | Baris/area | Bug | Perbaikan | Cara menemukannya |
|---|---|---|---|---|
| 1 | CSS body | `colour` bukan property CSS yang benar | `color` | Membaca kode/DevTools |
| 2 | CSS header | Kurang titik koma setelah `background: #dbe7f3` | Tambahkan `;` | Membaca kode/DevTools |
| 3 | Selector kartu | HTML memakai `class="card"` tetapi CSS `.Card` | Samakan menjadi `.card` | Membandingkan HTML dan CSS |
| 4 | CSS #news-list | `18 px` memiliki spasi yang tidak valid | `18px` | Validator/DevTools |
| 5 | CSS footer | Nilai `centre` tidak valid | `center` | Validator/DevTools |
| 6 | Heading | `<h1>` ditutup dengan `</h2>` | Gunakan `</h1>` | Validator |
| 7 | Link About | Kutip atribut href tidak ditutup | `href="about.html"` | Validator/membaca kode |
| 8 | ID daftar berita | HTML `newsList`, CSS `news-list` tidak cocok | Samakan menjadi `newsList` | Membandingkan HTML dan CSS |
| 9 | Gambar | Elemen img tidak memiliki atribut `alt` | Tambahkan `alt` bermakna | Validator/aksesibilitas |

Catatan: kesalahan titik koma pada CSS dapat membuat deklarasi berikutnya tidak terbaca dengan benar. Kode `debug.html` yang sudah diperbaiki tersedia di file proyek.

## Bagian 6: Tabel Code Review

| # | Baris/area | Masalah | Mengapa penting | Perbaikan saya |
|---|---|---|---|---|
| 1 | Awal dokumen | Tidak ada `<!DOCTYPE html>` | Mencegah mode rendering standar tidak dinyatakan | Tambahkan doctype |
| 2 | Elemen html | Tidak ada atribut `lang` | Membantu teknologi bantu dan mesin pencari mengenali bahasa | Gunakan `<html lang="en">` |
| 3 | Head | Tidak ada meta charset dan viewport | Karakter dan tampilan mobile bisa kurang tepat | Tambahkan meta charset dan viewport |
| 4 | Judul | Judul halaman terlalu umum | Kurang deskriptif bagi pengguna tab browser | Gunakan judul yang jelas |
| 5 | Header/judul | Nama kampus menggunakan `div` dan `b`, bukan heading | Struktur dokumen dan aksesibilitas kurang baik | Gunakan `h1` |
| 6 | Isi halaman | Judul bagian dibuat dengan `div` | Heading tidak membentuk hierarki dokumen | Gunakan `h2` |
| 7 | Struktur | Banyak `div` digunakan untuk elemen semantik | Makna struktur dokumen kurang jelas | Gunakan `header`, `nav`, `main`, `section`, `footer` |
| 8 | CSS `.header` | Lebar tetap `1200px` | Dapat melebar keluar layar pada perangkat kecil | Gunakan `max-width: 960px; margin: 0 auto` |
| 9 | CSS navigasi | Menggunakan `!important` | Menyulitkan pengaturan ulang cascade CSS | Atur specificity dan urutan aturan dengan benar |
| 10 | CSS content | Warna `#bbbbbb` berkontras rendah pada latar putih | Teks sulit dibaca | Gunakan warna teks lebih gelap |
| 11 | CSS sidebar | `.sidebar` tidak digunakan | Menambah kode yang tidak diperlukan | Hapus jika tidak dipakai |
| 12 | CSS title | `.title` hanya dipakai sebagai pengganti heading | Struktur semantik tidak jelas | Gunakan `h1` |
| 13 | Konten | Menggunakan banyak `<br>` untuk membuat jarak | Jarak visual sebaiknya diatur melalui CSS | Gunakan margin/padding CSS |
| 14 | Gambar | Tidak memiliki `alt` | Pembaca layar tidak mendapat deskripsi gambar | Tambahkan `alt` |
| 15 | Form nama | Input tidak memiliki `label` | Sulit dipahami oleh pengguna pembaca layar | Tambahkan `label` dengan `for` dan `id` |
| 16 | Form email | Email memakai `type="text"` | Validasi email bawaan tidak tersedia | Gunakan `type="email"` |
| 17 | Form | Placeholder dipakai tanpa label | Placeholder hilang saat pengguna mengetik | Sediakan label yang terlihat |
| 18 | Tombol | `onclick="alert('Sent!')"` hanya menampilkan alert, bukan mengirim data | Memberi kesan pesan benar-benar terkirim | Gunakan form dan backend/layanan pengiriman yang nyata |

### Refleksi

1. Masalah yang paling sulit disadari hanya dari browser adalah masalah semantik dan aksesibilitas, seperti penggunaan `div` untuk heading atau gambar tanpa `alt`. Halaman mungkin tetap terlihat baik, tetapi struktur dokumennya tidak cukup jelas bagi pembaca layar dan alat pemeriksa.
2. Halaman yang terlihat berfungsi tetap perlu diperbaiki karena kualitas website juga mencakup aksesibilitas, responsivitas, validitas kode, keamanan, dan kemudahan pemeliharaan.
3. Sebelum mengumpulkan tugas, saya akan membuka halaman di browser, memeriksa tampilan mobile melalui DevTools, dan memvalidasi HTML menggunakan W3C Validator.

## Bagian 7: Exit ticket

1. Aturan CSS terdiri dari selector yang memilih elemen HTML dan blok deklarasi yang berisi property serta value untuk menentukan tampilannya.
2. Konsep yang masih ingin saya latih adalah specificity, khususnya ketika selector elemen, class, dan ID mengatur property yang sama.
3. Saya sekarang dapat membuat struktur HTML semantik, menghubungkan CSS eksternal, dan menggunakan selector dasar untuk mengatur tampilan halaman.
