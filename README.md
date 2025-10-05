# Menginstall dan Menggunakan Vim Text Editor di Linux

Sebelumnya kita sudah pernah membahas `nano`, sebuah Text editor yang cocok untuk digunakan oleh pemula. Tapi jika kamu ingin naik ke tingkat lebih lanjut, maka `vim` adalah jawabannya. `vim`merupakan salah satu File editor paling powerful yang dapat diakses menggunakan command line. Vim editor dibuat diatas dasar "vi", sebuah editor yang pertama kali diperkenalkan pada tahun 1976, `vim` menambahkan fungsionalitas dan power tambahan, sembaru mempertahankan gaya editor pendahulunya

# Instalasi
Karena penggunaan `vim` yang luas pada Linux Command Line, `vim` tersedia di repositori default hampir semua distribusi Linux

Pada Ubuntu dan Debian, gunakan `apt-get` untuk menginstall:
```
sudo apt-get install vim
```
Pada Fedora dan CentOS, install menggunakan `yum`:
```
sudo yum install vim
```
Pada Arch Linux, `vim` daoat diinstal melalui `packman`:
```
sudo pacman -S vim
```
Vim telah terinstall dengan benar.

# Membuka Vim
Biasanya, saat `vim` dijalankan tanpa argumen apapun, `vim` akan terbuka dengan dokumen kosong. Tergantung distribusi, mungkin akan ada pesan pengenalan dan liseni. Pesan ini akan hlang saat editor mulai digunakan.

Namun, kita tidak akan membuka `vim` dengan dokumen kosong. Kita akan membuat dokumen contoh bernama "baru" untuk menampilkan fitur dari `vim`
```
echo "Ini merupakan file baru. Ini line kedua dan ini line ketiga. Beberapa teks disini. Kita akan mengeditnya menggunakan vim. Ini akan sangat menyenangkan." >> baru
```
Sekarang kita akan buka file yang sudah dibuat menggunakan vim.
```
vim baru
```
vim akan terbuka dan akan keluar tampilan sperti ini:
```
Ini merupakan file baru. Ini line kedua dan ini line ketiga. Beberapa teks disini. Kita akan mengeditnya menggunakan vim. Ini akan sangat menyenangkan.
~
~
~
~
~
~
~
~
~
~
"baru" 1L, 150B written                                                                                                                         1,1             All
```
<h3>Normal Mode</h3>

**Digunakan untuk mengedit operasi. Menyalin, menempel, menghapus dan mengubah teks dilakukan pada mode ini.**

Di `vim` fungsi mengedit dilakukan dengan membuat vim memasuki Normal mode. Normal mode adalah mode yang digunakan `vim` saat program dibuka. Mode ini digunakan untuk menavigasi dokumen teks dengan cepat dan mengedit. Mode ini tidak digunakan untuk memasukkan text.

•  `esc` - Memasuki Normal mode dengan menekan key "Escape"

<h3>Insert Mode</h3>

**Digunakan untuk memasukkan teks baru ke dalam dokumen. Ada beberapa cara untuk masuk ke Insert mode.**

Untuk memasukkan teks, vim harus beralih ke Insert mode. Insert mode mirip dengan tampilan mengetik dari kebanyakan program pengetikkan text lainnya. Apa yang kamu ketik akan muncul pada layar dalam dokumen. Semua key normal akan menghasilkan karakter yang sesuai pada posisi kursor saat ini

•  `i` - Memasuki Insert mode pada posisi kursor saat ini\
•  `a` - Memasuki Insert mode setelah posisi saat ini\
•  `I` - Memasuki Insert mode pada awal dari line saat ini\
•  `A` - Memasuki Insert mode pada akhir dari line saat ini

Perubahan mode ke Insert mode ditandai dengan `-- INSERT --` pada bagian ujung kiri paling bawah.

```
Ini merupakan file baru. Ini line kedua dan ini line ketiga. Beberapa teks disini. Kita akan mengeditnya menggunakan vim. Ini akan sangat menyenangkan.
~
~
~
~
~
~
~
~
~
~
-- INSERT --                                                                                                                                   1,1             All
```

<h3>Visual Mode</h3>

**Digunakan unntuk seleksi visual. Banyak command yang tersedia dalam Normal mode dapat diterapkan pada bagian teks yang di sorot secara spesifik.**

Mode ketiga yang digunakan `vim` adalah Visual mode. Mode ini digunakan untuk seleksi visual dan manipulasi teks. Bagian teks ditandai sebagai target command pengeditan atau pemformatan selanjutnya

•  `v` - Memasuki Visual mode reguler. Seleksi dilakukan dengan menggerakkan kursor ke atas, bawah, kiri, dan kanan. Ditandai dengan `-- VISUAL --` di bagian kiri bawah.\
•  `V` - Memasuki Visual line mode. Seluruh line dipilih, dari awal hiingga akhir karakter, dengan bergerak ke atas dan ke bawah.\
•  `Ctrl _ V` - Memasuki Visual block mode. Sebuah kotak digunakan untuk seleksi yang dapat diperluas dan diperkecil. Bagian dari beberapa line dapat dipilih dengan metode ini

<h3>Command Mode</h3>

**Digunakan untuk menjalankan command vim. Masuk ke mode ini dengan menggunakan key titik dua**

Mode tambahan yang digunakan untuk pengeditan kompleks, mengubah pengaturan, dan mengontrol `vim itu sendiri adalah Command mode. Mode ini digunakan untuk menyimpan dokume`n, keluar dari program, melakukan pencarian kompleks, dan banyak hal lainnya.

•  `:` - Memasuki Command mode.

# Navigasi

<h3>Basic Navigation</h3>

Selalu mungkin untuk menavigasi tks menggunakan arrow key, tetapi `vim` menyediakan cara yang lebih cepat untuk berpindah di dalam dokumen. Dalam Normal mode, kamu dapat menggunakan key h, j, k dan l untuk berpindah ke kiri, bawah, atas, kanan.

•  `h` - Geser ke kiri.\
•  `j` - Geser ke bawah.\
•  `k` - Geser ke atas.\
•  `l` - Geser ke kanan.

key ini mungkin terlihat membingungkan pada awalnya, tetapi key ini dipilih dengan alasan tertentu. Key ini terletak di baris tengah keyboard standar. Hal ini berarti tangan pengguna bergerak dari posisi istirahat jauh lebih sedikit dibandingkan dengan arrow key.

**Navigasi Lanjutan**

Terdapat shortcut navigasi lainnya. Berikut adalah beberapa yang paling berguna:

•  `gg` - Geser ke bagian paling atas dari dokumen.\
•  `G` - Geser ke bagian paling bawah dari dokumen. Tambahkan angka di depan untuk pergi ke nomor line tersebut.\
•  `w` - Geser ke kata selanjutnya. Tambahkan angka di depan untuk berpindah sebanyak kata tersebut.\
•  `b` - Mundur satu kata. Tambahkan angka di depan untuk mundur sebanyak kata tersebut.\
•  `e` - Geser ke akhir dari kata. Tambahkan angka di depan untuk berpindah sebanyak kata tersebut.\
•  `0` - Geser ke awal dari line.\
•  `$` - Geser ke akhir dari line.

# Editing

Mengedit teks di `vim` dilakukan dengan menjalankan command pada Normal mode.

Perlu diketahui bahwa command pengeditan di `vim` sangat powerful ketika digabungkan dengan command gerakan. Semua command navigasi dapat digunakan sebagai arah. Misalnya kamu dapat menjalankan command pengeditan pada sebuah kata diikuti dengan `w`

Berikut adalah beberapa tindakan yang dapat anda pilih:

<h3>Menghapus Teks</h3>

•  `x` - Menghapus karakter di bawah posisi kursor.\
•  `d` - Menghapus ke arah yang ditentukan setelah memberi command. Misalnya, `dl` menghapus karakter ke kanan.\
•  `dd` - Menghapus line.\
•  `D` - Menghapus dari posisi saat ini hingga akhir dari line.

<h3>Mengubah Teks</h3>

•  `r` - Mengubah karakter di bawah posisi kursor dengan karakter lain. Masukkan karakter yang kamu ganti setelah menjalankan command ini.\
•  `c` - Mengubah teks ke arah yang mengikuti. Misalnya, `cw` mengubah kata saat ini. Setelah menjalankan command ini, `vim` akan masuk ke Insert mode sehingga kamu dapat memasukkan kteks pengganti.\
•  `C` - Mengubah teks hingga akhir dari line. Ini akan membuat `vim` masuk ke Insert mode.

# Menyalin dan Menempel

•  `y` - Copy (atau "yank") ke arah mengikuti.\
•  `yy` - Copy seluruh line.\
•  `Y` - Copy hingga akhir line.\
•  `p` - Paste line terakhir yang di copy (atau dihapus) di bawah line saat ini.\
•  `P` - Paste line terakhir yang di copy (atau dihapus) di atas line saat ini.


# Lainnya

•  `u` - Undo tindakan terakhir.\
•  `Ctrl+R` - Redo tindakan terakhir.\
•  `J` - Menggabungkan line di bawah ke line saat ini.

# Mengelola Dokumen

`vim` mengelola dokumen terutama melalu Command mode. Commande dijalankan dengan mengetik `:` sebelum setiap command

•  `:q` -Keluar dari `vim`. Jika perubahan belum disimpan command ini akan gagal.\
•  `:q!` - Keluar dari `vim` dan membatalkan semua perubahan yang belum disimpan.\
•  `:w` - Simpan perubahan. Tambahkan spasi dan nama file jika ingin menyimpan ke lokasi yang berbeda atau jika ini adalah pertamakalinya kamu menentukan lokasi penyimpanan.\
•  `:e` - Edit file.\
•  `:bn` - Edit file berikutnya yang terbuka di  `vim`.\
•  `:bp` - Edit file sebelumnya yang terbuka di  `vim`.\

# Menggabungkan Semuanya

Seperti yang telah disebutkan sebelumnya, kekuatan `vim` berasal fsri kemampuannya untuk menggabungkan beberapa command yang berbeda. Cara termudah untuk memahami konsep ini adalah menganggap command dari `vim` sebagai bahasa. Key pada Normal modedapat mewakili kata sifat, kata kerja, dan objek.

Misalnya, untuk menyalin (yank) 4 kata , cukup terjemahkan kata tersebut menjadi command yang dkenali oleh `vim`. Dalam hal ini, commandnya adalah:
```
y4w
```
Untuk menhapus dari line saat ini hingg akhir dari line, ketik:
```
dG
```
Sangat membantu juga untuk memahami beberapa konvensi yang digunakan `vim` dalam command pengeditannya. Misalnya, huruf yang diulang biasanya diterapkan pada seluruh line. Kita dapat menyalin seluruh line dengan:
```
yy
```
Di sisi lain, versi kapital dari command pengeditan sering kali menargetkan dari posisi kursor saat ini hingga akhir line. Misalnya, untuk mengubah teks dari sini hingga akhir line, kamu dapat menggunakan:
```
C
```
Untuk melakukan tindakan yang sama pada lebih dari satu line, cukup tambahkan awalan bernomor ke command. Ini akan mengubah teks dari posisi saat ini hingga akhir line berikutnya:
```
2C
```
Ada banyak teknik lain yang powerful yang dapat digunakan dengan `vim`, namun teknik-teknik tersebut diluar cakupan panduan ini. Jika ingin mempelajari lebih lanjut, langkah awal yangbaik adalah menggunakan tutorial bawaan dari `vim`. tutorial ini tidak akan membahas topik-topik lanjutan, tetapi akan memberi gambaran yang baik tentang cara menggunakan `vim` untuk melakukan pnegeditan dasar. mulai dengan mengetik command berikut:
```
vimtutor
```

Sekian yang dapat saya sampaikan, mohon maaf apabila ada salah kata atau kekurangan dalam penyampaian. Akhir kata, Wassalam
