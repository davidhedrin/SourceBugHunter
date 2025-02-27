1. Persiapkan Alat:
Gunakan browser seperti Google Chrome dan Burp Suite untuk memonitor traffic web. Kamu juga bisa menggunakan alat lain seperti OWASP ZAP jika lebih nyaman.

2. Pilih Situs untuk Pengujian:
Pilih situs yang memiliki program bug bounty yang mengizinkan pengujian, atau coba di platform seperti Hack The Box atau TryHackMe yang menyediakan lingkungan yang aman untuk belajar.

3. Cari Formulir Input yang Dapat Diserang:
Pencarian di situs web atau formulir pendaftaran sering menjadi titik di mana skrip bisa disuntikkan. Misalnya:
  - Kolom pencarian
  - Formulir login atau pendaftaran
  - Kolom komentar atau input teks lainnya
Untuk percobaan ini, kita akan menggunakan kolom pencarian sebagai contoh.

4. Cobalah Menyuntikkan Skrip JavaScript di Kolom Input: Cobalah memasukkan input berikut ke dalam kolom pencarian atau form input:
<script>alert('XSS Vulnerability!');</script>
Jika situs web tersebut rentan terhadap XSS, maka saat kamu mengirimkan input tersebut, browser akan mengeksekusi skrip ini dan menampilkan alert box dengan pesan "XSS Vulnerability!".

5. Perhatikan Respon Situs:
- Jika setelah mengirimkan input kamu melihat pop-up dengan pesan “XSS Vulnerability!” maka situs tersebut rentan terhadap XSS Reflected.
- Jika pesan ini muncul setiap kali kamu melakukan pencarian atau mengirimkan data ke situs, itu artinya skrip tidak disaring dengan baik oleh situs tersebut.

6. Cek Variasi XSS Lainnya: Tergantung pada situsnya, kamu bisa mencoba berbagai variasi input untuk melihat apakah ada celah lainnya. Misalnya:
  - Menyisipkan skrip dalam atribut HTML seperti onerror atau onload.
  - Cobalah menyisipkan input lain seperti:
    <img src="x" onerror="alert('XSS!')">
    Jika gambar gagal dimuat, browser akan mengeksekusi skrip yang ada di onerror dan menampilkan pesan.