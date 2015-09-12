---
layout: post
title: "Perintah Dasar"
date: 2015-09-11
categories:
---

#### Basic Listing
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

![ls-a](/resources/img/ls-a.png)