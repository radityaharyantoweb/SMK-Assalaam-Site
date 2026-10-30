# PROJECT_CONTEXT.md

## 1. Ringkasan proyek

**Nama proyek:** Website Profil SMK ASSALAAM  
**Tujuan:** Membuat website profil sekolah yang responsif, rapi, mudah dinavigasi, dan menggunakan Bootstrap dari source files serta Sass/SCSS. Website ini merupakan tugas/studi kasus Gamelab yang nantinya juga akan dipresentasikan.

**Sekolah yang benar:** SMK ASSALAAM, bukan SMKN 4 Banjarmasin. Brief awal yang menyebut SMKN 4 Banjarmasin kemudian dikoreksi oleh pengguna setelah trainer menjelaskan bahwa isi sekolah boleh disesuaikan dengan sekolah yang dikenal atau sekolah sendiri.

**Program keahlian:** Teknik Komputer dan Jaringan (TKJ) saja, menurut informasi pengguna.

**Lokasi:** Pengguna memberikan tautan Google Maps berikut: https://maps.app.goo.gl/K5ogmkAw2ahFsY8n6

## 2. Status dan tingkat kepastian

Penting untuk membedakan riwayat percakapan dari kondisi file lokal saat ini:

- Pengguna sebelumnya sudah mengerjakan versi website SMK ASSALAAM dan menguji beberapa bagian di browser.
- Pengguna melaporkan pernah mengalami perbedaan font pada `jurusan.html`; kemudian diketahui bahwa SCSS saat itu belum dikompilasi ulang.
- Pengguna merasa folder proyek lama mungkin bermasalah dan memutuskan ingin memulai ulang dengan struktur yang lebih bersih.
- Setelah keputusan memulai ulang, template `index.html` dan sebagian styling SCSS diberikan dalam percakapan. **Belum ada konfirmasi bahwa semua template itu sudah disimpan, dibangun, dan diuji dalam folder baru.**
- Folder proyek aktual tidak tersedia untuk diperiksa dalam sesi ini. Yang tersedia di runtime hanya beberapa gambar tangkapan layar dari percakapan, bukan source project lengkap. Karena itu, nama file, keberadaan aset, isi final, dan hasil build saat ini belum dapat diverifikasi secara langsung.

Jangan menganggap kode yang pernah diberikan di percakapan pasti sama dengan kode yang sekarang tersimpan di PC pengguna. Periksa folder proyek dan baca file yang ada sebelum melakukan perubahan.

## 3. Teknologi dan tools

- **HTML5** untuk struktur halaman semantik.
- **Bootstrap 5.3.0 source files**; instruksi tugas meminta penggunaan source files, bukan Bootstrap CSS melalui CDN.
- **Sass/SCSS** untuk styling dan pengelolaan variabel/partial.
- **Node.js dan npm** untuk instalasi Sass; pengguna sebelumnya sudah berhasil melihat versi Sass dan pernah menjalankan compile lewat Windows CMD.
- **Visual Studio Code** sebagai editor.
- **Windows PC** sebagai lingkungan kerja.
- **Google Fonts:** rancangan memakai Montserrat untuk heading dan Poppins untuk teks isi. Keduanya dipanggil melalui Google Fonts pada HTML.
- **Bootstrap JavaScript bundle** untuk komponen interaktif seperti navbar collapse dan carousel.
- **Instagram embed** pernah dipakai untuk menampilkan video profil/kegiatan. Embed bergantung pada koneksi internet, konten publik, dan script Instagram.
- **Google Maps embed/link** untuk lokasi sekolah.

## 4. Halaman yang direncanakan

Website direncanakan memiliki empat halaman HTML:

1. `index.html` — Beranda.
2. `about.html` — Tentang sekolah.
3. `jurusan.html` — Halaman khusus jurusan TKJ.
4. `contact.html` — Kontak, lokasi, dan tautan pendaftaran SIPENWARU.

Brief awal menyebut maksimal tiga halaman utama, tetapi percakapan berikutnya memutuskan menambah halaman `jurusan.html` agar informasi TKJ terpisah dari halaman lain. Pastikan jumlah halaman dan keputusan tersebut tetap sesuai dengan instruksi trainer terbaru jika ada perubahan.

## 5. Struktur folder yang direncanakan

```text
RafiRaditya_XI-TKJ_WebProfilSMKAssalaam/
├── index.html
├── about.html
├── jurusan.html
├── contact.html
├── package.json                 # opsional; belum dipastikan ada/dibutuhkan
├── bootstrap/                   # Bootstrap source files hasil unduh
│   ├── scss/
│   └── dist/
│       ├── css/
│       └── js/
├── scss/
│   ├── _variables.scss
│   ├── _mixins.scss
│   ├── _components.scss
│   └── style.scss
├── css/
│   └── style.css                # hasil compile SCSS
└── assets/
    ├── images/
    └── logo/
```

Ini adalah **struktur target**, bukan hasil inspeksi folder lokal yang sudah terverifikasi. Cocokkan dengan folder aktual sebelum mengubah path.

## 6. Fungsi file utama

- `index.html`: beranda, navbar, hero carousel, profil singkat, video profil/kegiatan, kegiatan siswa, prestasi, dan footer.
- `about.html`: profil/sejarah sekolah, visi dan misi, sambutan kepala sekolah, serta informasi fasilitas jika datanya tersedia.
- `jurusan.html`: penjelasan TKJ, kompetensi yang dipelajari, perangkat/software yang relevan, peluang karier, partner/program, dan galeri praktik.
- `contact.html`: detail kontak yang sudah diverifikasi, Google Maps, serta tombol menuju SIPENWARU.
- `scss/_variables.scss`: variabel warna, font, dan nilai desain yang dipakai bersama.
- `scss/_mixins.scss`: mixin yang dapat digunakan ulang, misalnya transisi dan hover.
- `scss/_components.scss`: styling komponen khusus proyek seperti navbar, hero carousel, cards, tombol, galeri, dan footer.
- `scss/style.scss`: entry point SCSS yang mengatur variabel Bootstrap, memuat Bootstrap SCSS dan custom styling sesuai urutan yang tepat.
- `css/style.css`: output kompilasi yang diload oleh halaman HTML. Jangan mengedit file output ini sebagai sumber utama styling.
- `bootstrap/dist/js/bootstrap.bundle.min.js`: JavaScript Bootstrap lokal untuk carousel dan navbar collapse.
- `assets/images/` dan `assets/logo/`: aset gambar dan logo lokal.

## 7. Desain dan keputusan visual

- Palet yang digunakan sebagai rancangan berdasarkan identitas visual sekolah: hijau dan kuning.
  - Hijau utama: `#0B7A3E`
  - Hijau gelap: `#075A2E`
  - Kuning aksen: `#FBC02D`
  - Latar terang: `#F8F9FA`
  - Teks gelap: `#222222`
- Palet ini adalah nilai rancangan dari percakapan, bukan hasil sampling warna resmi dari file logo. Jika logo resmi tersedia, warna dapat dicocokkan lagi.
- Font rancangan: Montserrat untuk heading dan Poppins untuk body.
- Navbar memiliki efek hover dengan teks/garis bawah kuning.
- Hero dirancang menggunakan carousel foto lokal dengan overlay gelap agar teks mudah terbaca.
- Tombol `btn-warning` dirancang dengan glow kuning lembut; `btn-primary` dengan glow hijau lembut.
- Gambar kartu kegiatan dan prestasi perlu mempunyai tinggi yang konsisten dengan `object-fit: cover`.
- Semua halaman seharusnya memakai stylesheet dan navbar/footer yang konsisten.
- Tampilan harus responsif pada desktop, tablet, dan mobile.

## 8. Fitur yang pernah dirancang atau dibuat dalam kode percakapan

Daftar ini berarti fitur pernah dibahas atau kodenya pernah disusun di percakapan; **bukan konfirmasi bahwa semuanya ada dan bekerja di versi lokal saat ini**.

- Navbar dengan tautan Beranda, Tentang, Jurusan, dan Kontak.
- Hero carousel dengan tiga gambar lokal.
- Bagian profil singkat sekolah.
- Satu embed Instagram untuk video profil serta bagian video kegiatan.
- Kartu kegiatan siswa dengan foto.
- Kartu prestasi siswa dengan gambar bukti; ukuran gambar perlu diseragamkan.
- Sambutan kepala sekolah dengan foto.
- Daftar partner/program yang disebut pengguna: Gamelab, Cisco, Biznet, MikroTik, Telkom, dan Jo Computer.
- Halaman khusus TKJ.
- Halaman kontak dan Google Maps.
- Tautan/button ke SIPENWARU: https://sipenwaru.assalaam.or.id/
- Footer yang ingin digunakan di semua halaman.
- Styling hover navbar, overlay hero, dan efek glow pada tombol.

## 9. Aturan tugas/trainer dan akurasi konten

- Gunakan identitas **SMK ASSALAAM**, jurusan **TKJ**, dan lokasi dari tautan Google Maps yang diberikan pengguna.
- Jangan kembali menggunakan nama SMKN 4 Banjarmasin; itu berasal dari brief awal yang ternyata bukan sekolah pengguna.
- Utamakan data asli bila tersedia: nama kepala sekolah, sejarah, visi/misi, fasilitas, prestasi, kontak resmi, dan dokumentasi.
- Jangan mengarang prestasi, data statistik, sejarah, visi/misi resmi, nama pejabat sekolah, nomor telepon, atau email. Bila data belum tersedia, tandai sebagai placeholder atau tanyakan kepada pengguna.
- Nama partner/program berasal dari pengguna, tetapi status hubungan formal dengan masing-masing organisasi belum diverifikasi. Hindari klaim kerja sama resmi bila belum ada bukti.
- Tautan SIPENWARU yang diminta pengguna harus tersedia di halaman kontak/footer sesuai revisi.
- Website harus menggunakan Bootstrap source files, bukan Bootstrap CSS CDN, sesuai persyaratan proyek.
- Source SCSS harus disimpan di `scss/`, dan hasil kompilasinya disimpan di `css/style.css`.
- Semua halaman perlu terhubung lewat navigasi responsif dan memiliki footer konsisten.
- Uji visual dan fungsi di desktop, tablet, dan mobile; periksa Console browser untuk error.

## 10. Aset yang pernah disebut dalam kode

Nama berikut pernah muncul dalam potongan kode yang ditempel pengguna atau template di percakapan. **Keberadaan fisik dan ejaan aktualnya belum diverifikasi di folder proyek saat ini.**

- Logo: `assets/logo/logo SMK assalaam.png`
- Foto hero/sekolah: `assets/images/gedung.png`
- Foto kelas: `assets/images/fotokelas.jpg`
- Foto laboratorium: `assets/images/Laboratorium.jpg`
- Foto ekstrakurikuler: `assets/images/ekstra.png`
- Foto kegiatan: `assets/images/ftd pi.jpg`
- Foto bukti prestasi: `assets/images/lemon.jpg-1.jpeg`, `assets/images/prestasi2.png`, `assets/images/ibrahim.png`

Perhatikan kapitalisasi, spasi, dan ekstensi nama file. Jika memungkinkan, rapikan nama aset tanpa spasi dan gunakan path yang konsisten setelah memastikan semua referensi HTML/SCSS diperbarui.

## 11. Cara menjalankan dan compile

### Menjalankan website

1. Buka folder proyek di VS Code.
2. Buka `index.html` dengan browser atau Live Server jika extension tersedia.
3. Pastikan koneksi internet tersedia untuk Google Fonts dan Instagram embed. Bootstrap CSS/JS sendiri seharusnya lokal.

### Compile SCSS

Pengguna pernah berhasil melakukan compile dari **Windows CMD**. PowerShell di terminal VS Code pernah memblokir `sass.ps1` karena Execution Policy.

Jalankan CMD pada root proyek, lalu:

```cmd
sass scss/style.scss css/style.css
```

Untuk mode otomatis:

```cmd
sass --watch scss/style.scss css/style.css
```

Hentikan mode watch menggunakan `Ctrl+C`.

Di PowerShell, error yang pernah muncul:

```text
sass.ps1 cannot be loaded because running scripts is disabled on this system
```

Ini berkaitan dengan PowerShell Execution Policy, bukan bukti bahwa Sass rusak. Gunakan CMD, atau dari PowerShell jalankan `cmd /c "sass scss/style.scss css/style.css"`.

## 12. Catatan teknis penting tentang Bootstrap dan Sass

- Pada percobaan sebelumnya, `@use "variables";` digunakan lalu Bootstrap diimpor. Variabel Sass dengan namespace tidak otomatis menjadi variabel global untuk Bootstrap.
- Warna navbar/footer tetap biru karena Bootstrap CSS siap pakai `bootstrap/dist/css/bootstrap.min.css` masih dimuat, sementara custom Bootstrap SCSS belum berhasil terintegrasi secara benar. Pada percakapan berikutnya upaya debugging berlanjut, tetapi tidak ada inspeksi akhir terhadap file lokal yang membuktikan konfigurasi warna final.
- Sass pernah mengeluarkan `Deprecation Warning [import]` karena penggunaan `@import`; warning tersebut berbeda dari compile error. Bootstrap 5.3 source SCSS menggunakan pola import legacy, jadi jangan mengganti seluruh import Bootstrap secara membabi buta dengan `@use` tanpa memeriksa kebutuhan internal Bootstrap.
- Pastikan hanya ada satu sumber Bootstrap CSS yang aktif. Jika `css/style.css` sudah berisi Bootstrap hasil compile SCSS, jangan sekaligus memuat `bootstrap/dist/css/bootstrap.min.css`, kecuali memang sengaja memisahkan CSS vendor dan custom serta tidak mengira bahwa variabel SCSS akan mengubah vendor CSS siap pakai.
- Sebelum mengubah konfigurasi SCSS, periksa versi/folder Bootstrap aktual dan `style.scss` saat ini. Compile setelah perubahan dan pastikan output CSS yang ditautkan HTML adalah output yang baru.

## 13. Proyek lain dalam percakapan

Percakapan terbaru juga membahas latihan JavaScript/jQuery Gamelab seperti Kuis #6, #7, dan #8. Itu adalah latihan terpisah, bukan bagian dari website profil sekolah, kecuali pengguna secara eksplisit ingin menggabungkannya. Jangan mencampur folder/berkas latihan kuis ke dalam source website profil tanpa instruksi.
