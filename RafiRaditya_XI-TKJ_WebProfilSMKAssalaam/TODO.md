# TODO.md

Dokumen ini mencatat pekerjaan selanjutnya berdasarkan percakapan. Statusnya tidak mengasumsikan bahwa kode yang pernah dikirim lewat chat sudah tersimpan atau berjalan di PC.

## Status awal

- [x] Menetapkan target sekolah sebagai **SMK ASSALAAM**, bukan SMKN 4 Banjarmasin.
- [x] Mengonfirmasi jurusan yang dicantumkan: **TKJ saja**.
- [x] Mendapat tautan lokasi dari pengguna: https://maps.app.goo.gl/K5ogmkAw2ahFsY8n6
- [x] Menetapkan rencana empat halaman: `index.html`, `about.html`, `jurusan.html`, `contact.html`.
- [x] Menetapkan rancangan warna hijau-kuning dan font Montserrat/Poppins.
- [ ] Memeriksa folder proyek aktual dan isi semua file. Source project tidak tersedia dalam sesi ini sehingga status lokal belum diverifikasi.

## Prioritas 1: Verifikasi folder baru

1. Buka folder proyek yang sekarang digunakan di Windows, bukan folder lama yang dianggap mungkin rusak.
2. Konfirmasi apakah lokasi foldernya memang `D:\Documents\GAMELAB\RafiRaditya_XI-TKJ_WebProfilSMKAssalaam` atau lokasi lain.
3. Cocokkan isi folder dengan struktur target di `PROJECT_CONTEXT.md`.
4. Pastikan folder `bootstrap/scss/` berisi Bootstrap source files, termasuk entry point `bootstrap.scss`, dan folder `bootstrap/dist/js/` memiliki `bootstrap.bundle.min.js`.
5. Pastikan `css/`, `scss/`, dan folder aset memang ada. Jangan mengasumsikan file yang hanya disebut di chat pasti ada.
6. Simpan salinan/backup folder yang ada sebelum menghapus atau menimpa file.

## Prioritas 2: Bereskan build Sass dan Bootstrap

1. Buka `scss/style.scss`, `scss/_variables.scss`, dan `scss/_components.scss` yang benar-benar ada di folder proyek.
2. Tentukan satu alur yang konsisten untuk mengompilasi Bootstrap source SCSS dan styling custom.
3. Atur warna Bootstrap (`primary` hijau dan `warning/secondary` kuning) sebelum variabel Bootstrap dikonsumsi oleh source Bootstrap. Perhatikan urutan import dan kebutuhan fungsi/mixin Bootstrap.
4. Pastikan Bootstrap CSS tidak dimuat dobel. Tentukan apakah `css/style.css` berisi hasil compile Bootstrap + custom styling, atau CSS vendor lokal dan custom CSS digunakan terpisah dengan urutan yang sengaja diatur.
5. Hindari mengganti seluruh `@import` Bootstrap dengan `@use` tanpa menguji kompatibilitas source Bootstrap 5.3.0. Warning deprecation bukan sama dengan error, tetapi konfigurasi final harus dapat dibangun secara konsisten.
6. Compile dari Windows CMD pada root proyek:

   ```cmd
   sass scss/style.scss css/style.css
   ```

7. Pastikan command selesai tanpa error fatal dan waktu file `css/style.css` berubah sesuai compile terbaru.
8. Jangan menganggap warna hijau-kuning sudah berhasil sampai `bg-primary`, tombol, navbar, dan footer benar-benar diuji di browser.

## Prioritas 3: Selesaikan halaman Beranda

1. Pastikan `index.html` benar-benar tersimpan dengan struktur HTML lengkap.
2. Pastikan path logo, foto hero carousel, foto kegiatan, dan foto bukti prestasi sesuai dengan nama file yang tersedia.
3. Pastikan carousel memiliki tiga slide, hanya satu slide awal yang `active`, gambar memiliki `alt`, dan tombol previous/next bekerja.
4. Pertahankan section yang telah dirancang: profil singkat, video profil, kegiatan siswa, dan prestasi siswa.
5. Pastikan semua foto pada kartu prestasi dan kegiatan mempunyai tinggi konsisten, menggunakan `object-fit: cover` bila sesuai dengan kebutuhan pemotongan.
6. Pastikan teks prestasi benar-benar berdasarkan pencapaian yang valid dan bukti foto yang cocok. Jangan mengarang data prestasi bila belum dikonfirmasi.
7. Uji Instagram embed pada koneksi internet. Jika embed tidak tersedia, pastikan ada tautan fallback yang tetap dapat diklik.

## Prioritas 4: Samakan semua halaman

1. Buat/rapikan `about.html` untuk profil, sejarah, visi-misi, sambutan kepala sekolah, dan/atau fasilitas.
2. Buat/rapikan `jurusan.html` yang berfokus pada TKJ: kompetensi, praktik, alat/software yang relevan, galeri, dan prospek karier.
3. Buat/rapikan `contact.html` dengan informasi kontak yang sudah diverifikasi, tautan lokasi pengguna, Maps embed, dan tombol SIPENWARU.
4. Gunakan path stylesheet yang sama pada setiap halaman:

   ```html
   <link rel="stylesheet" href="css/style.css">
   ```

   Tambahkan CSS Bootstrap lokal hanya jika sesuai dengan strategi build yang dipilih pada Prioritas 2.
5. Gunakan navbar yang konsisten dan pastikan tautan ke `index.html`, `about.html`, `jurusan.html`, serta `contact.html` bekerja.
6. Gunakan footer yang konsisten di semua halaman, sesuai permintaan pengguna. Footer dapat berisi navigasi, kontak, tautan lokasi, dan SIPENWARU.
7. Periksa halaman Jurusan secara khusus karena sebelumnya font di halaman ini pernah berbeda; masalah saat itu diduga karena SCSS belum dikompilasi ulang.

## Prioritas 5: Validasi konten dan aset

1. Verifikasi nama resmi sekolah, alamat, logo, nama/jabatan kepala sekolah, sejarah, visi-misi, dan kontak melalui sumber sekolah yang dapat dipercaya.
2. Konfirmasi apakah semua organisasi yang disebutkan pengguna (Gamelab, Cisco, Biznet, MikroTik, Telkom, Jo Computer) boleh ditampilkan sebagai partner/program dan apakah hubungan formalnya boleh diklaim.
3. Ganti placeholder atau informasi contoh seperti nomor telepon, email, username media sosial, slogan, data statistik, sertifikasi, dan pencapaian dengan informasi terverifikasi. Beberapa nilai contoh pernah muncul di template sebelumnya dan tidak boleh dianggap sebagai informasi resmi.
4. Gunakan tautan lokasi yang diberikan pengguna sebagai sumber lokasi utama. Untuk iframe Google Maps, dapatkan embed URL yang tepat dari lokasi tersebut, bukan sekadar kueri teks umum jika akurasi pin penting.
5. Rapikan nama aset jika perlu (hindari spasi dan kapitalisasi yang membingungkan), lalu perbarui semua referensi HTML/SCSS sesuai nama file terbaru.

## Prioritas 6: Pengujian visual, fungsi, dan aksesibilitas

- [ ] Buka `index.html`, `about.html`, `jurusan.html`, dan `contact.html` di browser.
- [ ] Uji navigasi antarhalaman melalui navbar dan footer.
- [ ] Uji navbar collapse di mobile.
- [ ] Uji hero carousel: tombol, indikator, perpindahan otomatis, dan keterbacaan teks overlay.
- [ ] Uji video/Instagram embed dan tombol fallback jika tersedia.
- [ ] Pastikan gambar tidak broken dan `alt` deskriptif.
- [ ] Periksa konsistensi font, warna hijau-kuning, padding, card, dan footer di semua halaman.
- [ ] Uji lebar layar desktop sekitar 1280 px, tablet sekitar 768 px, dan mobile sekitar 375 px. Tambahkan 1024 px jika itu termasuk breakpoint yang bermasalah.
- [ ] Periksa bagian sambutan kepala sekolah agar teks tidak menutupi foto pada tablet/mobile.
- [ ] Periksa kartu Instagram pada tablet/mobile; embed Instagram dapat memiliki dimensi bawaan yang tidak sepenuhnya mengikuti layout Bootstrap.
- [ ] Buka Developer Tools > Console dan tangani error yang terkait kode/asset proyek.
- [ ] Periksa tab Network jika CSS, JavaScript, gambar, atau embed gagal dimuat.
- [ ] Lakukan hard refresh setelah compile (`Ctrl+F5` atau `Ctrl+Shift+R`).
- [ ] Pastikan halaman tidak bergantung pada CDN Bootstrap; Google Fonts dan Instagram embed masih memerlukan internet jika tetap dipakai.

## Bug/masalah yang pernah dilaporkan

1. **PowerShell menolak `sass.ps1`.** Error yang dilaporkan: `running scripts is disabled on this system` / `PSSecurityException`. Pengguna sebelumnya mengonfirmasi bahwa compile bekerja lewat CMD Windows. Gunakan CMD atau `cmd /c` dari PowerShell; tidak perlu mengubah Execution Policy hanya untuk menyelesaikan tugas.
2. **Bootstrap navbar/footer tetap biru.** Percobaan override Sass sebelumnya belum memberi hasil. Penyebab persisnya belum diverifikasi pada source project aktual. Periksa apakah CSS Bootstrap siap pakai masih dimuat, urutan import variabel Bootstrap, output CSS yang benar-benar ditautkan, serta cache browser.
3. **Deprecation warning Sass untuk `@import`.** Warning pernah muncul pada import Bootstrap 5.3.0. Warning ini tidak sama dengan error fatal. Jangan menganggap project gagal hanya karena warning, tetapi pastikan compile selesai dan output bekerja.
4. **`Undefined variable: $secondary`.** Pernah terjadi di `_components.scss` ketika file memakai `@use "variables"` tetapi merujuk `$secondary` tanpa namespace. Jika memakai `@use "variables" as v;`, referensikan `v.$secondary`; atau pertahankan pola variabel global yang memang dibutuhkan oleh setup Bootstrap dan konsisten dengan build.
5. **Font `jurusan.html` berbeda.** Pengguna kemudian menyadari bahwa SCSS belum dikompilasi ulang. Setelah compile, periksa tetap apakah semua halaman menautkan stylesheet yang sama dan Google Fonts tersedia.
6. **Instagram embed tidak muncul/tidak seragam.** Embed membutuhkan script Instagram, koneksi, dan konten publik. Ukuran embed dapat berbeda antar postingan. Gunakan fallback berupa tautan biasa dan uji pada breakpoint yang berbeda.
7. **Teks sambutan kepala sekolah menutupi foto di tablet.** Pernah dilaporkan sebagai masalah responsive. Belum ada konfirmasi bahwa perbaikan final sudah diuji.
8. **Potensi path aset tidak cocok.** Berbagai nama gambar dengan spasi, kapitalisasi, dan ekstensi berbeda pernah dipakai. Periksa file nyata sebelum mengubah path.

## Percobaan yang gagal atau belum terbukti

- Menggunakan variabel melalui `@use` lalu berharap Bootstrap otomatis menggunakan variabel tersebut tidak berhasil pada percobaan sebelumnya; navbar/footer tetap biru.
- Mengandalkan Bootstrap `dist/css/bootstrap.min.css` sekaligus mengustomisasi warna melalui SCSS tidak mengubah warna CSS bawaan itu dengan sendirinya.
- Menjalankan `sass ...` di PowerShell gagal karena PowerShell memblokir wrapper `sass.ps1`; command yang sama sebelumnya bisa dilakukan lewat CMD.
- Perbaikan CSS responsif Instagram dan layout kepala sekolah pernah disarankan, tetapi hasil akhir belum dikonfirmasi dalam percakapan.
- Pemanggilan font/stylesheet di halaman Jurusan pernah tidak sama efektifnya karena compile ulang belum dilakukan. Jangan mengasumsikan bug itu tetap ada setelah build baru.

## Jangan dilakukan tanpa verifikasi

- Jangan menghapus folder proyek lama atau menimpa aset sebelum memastikan backup tersedia.
- Jangan mengklaim data sekolah, kontak, sejarah, prestasi, statistik, atau sertifikasi yang belum diverifikasi.
- Jangan menganggap semua halaman dan fitur sudah selesai hanya karena template kodenya pernah ditulis dalam chat.
- Jangan mencampur Kuis JavaScript/jQuery #6–#8 ke dalam website profil sekolah. Latihan tersebut merupakan tugas yang terpisah.

## Urutan kerja berikutnya

1. Inspeksi folder baru dan file yang benar-benar tersimpan.
2. Stabilkan pipeline Bootstrap + Sass, compile, dan pastikan warna/font benar.
3. Jalankan serta rapikan `index.html` sampai lulus tes dasar.
4. Samakan shared navbar, stylesheet, dan footer di `about.html`, `jurusan.html`, dan `contact.html`.
5. Verifikasi konten dan aset.
6. Uji responsive dan fungsi semua halaman, periksa Console/Network, lalu siapkan folder final untuk dikumpulkan dan dipresentasikan.
