---
layout: post
title: "Basic Bash Shell Command"
date: 2015-09-11
categories:
---

### The Shell
Shell GNU/Linux adalah utilitas interaktif khusus. ini menyediakan cara bagi pengguna untuk memulai program, mengelola file pada filesystem, dan mengelola proses yang berjalan pada sistem Linux. Inti dari shell adalah command prompt. Command prompt adalah bagian interaktif shell. Hal ini memungkinkan Anda untuk memasukkan perintah teks, dan kemudian menterjemahkan perintah dan mengeksekusi mereka dalam kernel.

Shell berisi seperangkat perintah internal yang Anda gunakan untuk mengendalikan hal-hal seperti menyalin file, memindahkan file, mengubah nama file, menampilkan program-program yang sedang berjalan pada sistem, dan menghentikan program berjalan pada sistem. Selain perintah internal, shell juga memungkinkan Anda untuk memasukkan nama dari sebuah program pada command prompt.

### Basic Listing
Perintah `ls` pada bentuk paling dasar menampilkan file dan direktori yang terletak di direktori saat ini:

```
saifulindo: ~ $ ls
Applications  Backup  Documents  README.md  Web  tmp
```
Perhatikan bahwa perintah `ls` menghasilkan daftar urutan abjad (di kolom daripada baris). 

Anda dapat menggunakan parameter -F dengan perintah `ls` membedakan antara file dan direktori. Menggunakan parameter -F menghasilkan output berikut:

```
saifulindo: ~ $ ls -F
Applications/  Backup/  Documents/  README.md  Web/  tmp/
```
Parameter `-F` tersebut adalah flags direktori dengan sebuah slash, untuk membantu mengidentifikasi mereka dalam daftar. Demikian pula, itu flags file yang dapat dieksekusi (seperti direktori `Web` di atas) dengan tanda garing, untuk membantu Anda lebih mudah menemukan berkas yang dapat dijalankan pada sistem.Di Linux, file tersembunyi adalah file dengan nama file yang dimulai dengan periode, File-file ini tidak muncul dalam default daftar `ls`(dengan demikian, mereka disebut hidden).

Untuk menampilkan file hidden beserta dengan normal file dan direktori, gunakan parameter `-a`. Gambar ini menunjukkan contoh penggunaan parameter `-a` dengan perintah `ls`.

![ls-a]({{site.baseurl}}/resources/img/ls-a.png)

Beberapa paramater lain seperti `ls -F -R`, `ls -l`, Anda dapat menggunakan lebih dari satu parameter pada satu waktu jika Anda ingin. Tanda parameter  ganda harus tercantum secara terpisah, tetapi tanda parameter tunggal dapat dikombinasikan bersama-sama ke dalam sebuah string di belakang tanda. Kombinasi yang umum digunakan adalah parameter `-a` daftar semua file, parameter `-i` ke daftar inode untuk setiap file, parameter `-l` untuk menghasilkan sepanjang daftar dan parameter `-s` untuk daftar ukuran blok dari file. Inode dari file atau direktori adalah nomor identifikasi unik kernel menetapkan setiap objek pada filesystem. Menggabungkan semua parameter ini menciptakan seseuatu yang mudah di ingat ada;ah parameter `-sail`:

```
saifulindo: ~ $ ls -sail
total 84
163198  4 drwxr-xr-x 11 saifulindo saifulindo  4096 Sep 12 03:00 .
 41545  4 drwxr-xr-x  4 root       root        4096 Aug  2 00:36 ..
163165  8 -rw-------  1 saifulindo saifulindo  4491 Sep 12 05:41 .bash_history
163199  4 -rw-r--r--  1 saifulindo saifulindo   220 Apr  9  2014 .bash_logout
163200  4 -rw-r--r--  1 saifulindo saifulindo  3694 Aug  2 00:36 .bashrc
163172  4 drwx------  2 saifulindo saifulindo  4096 Aug 15 16:28 .cache
163240  4 drwxr-xr-x  3 saifulindo saifulindo  4096 Aug  2 00:36 .config
163341  4 -rw-r--r--  1 saifulindo saifulindo    48 Sep  8 09:59 .gitconfig
163167 16 drwxr-xr-x 95 saifulindo saifulindo 16384 Sep 11 13:05 .npm
163201  4 -rw-r--r--  1 saifulindo saifulindo   675 Apr  9  2014 .profile
163170  4 drwxr-xr-x  2 saifulindo saifulindo  4096 Sep  8 09:14 .ssh
163599  0 -rw-r--r--  1 saifulindo saifulindo     0 Sep 12 03:00 Apalah
163243  4 drwxr-xr-x  2 saifulindo saifulindo  4096 Aug  2 00:36 Applications
163244  4 drwxr-xr-x  2 saifulindo saifulindo  4096 Aug  2 00:36 Backup
163245  4 drwxr-xr-x  4 saifulindo saifulindo  4096 Sep  8 02:02 Documents
163246  4 -rw-r--r--  1 saifulindo saifulindo  2104 Aug  2 00:36 README.md
163247  4 drwxr-xr-x  6 saifulindo saifulindo  4096 Sep 11 15:32 Web
163365  4 drwxr-xr-x  3 saifulindo saifulindo  4096 Sep 11 13:05 tmp
```
