---
title: Cara Install Git dan Konfigurasi Awal yang Harus Dilakukan
published: 2023-09-09
description: Ini adalah postingan pertama blog Astro saya.
image: '/images/git/git-petanikode.png'
tags: [Git, Tutorial]
category: Development
draft: false
lang: id 
---

Kita sudah mengenal Git pada tulisan sebelumnya. Selanjutnya Kita akan melakukan instalasi dan persiapan untuk mulai belajar Git.

Tulisan ini terbagi menjadi tiga bagian:

1. Cara Instalasi Git di Linux.
2. Cara Instalasi Git di Windows.
3. Konfigurasi Awal yang Harus dilakukan Setelah Menginstal Git.

Mari kita mulai…

## 1. Cara Install Git di Linux

Instalasi Git pada Distro keluarga Debian dapat menggunakan perintah apt.
```bash
sudo apt install git
```

atau
```bash
sudo apt-get install git
```

Pada Fedora:
```bash
yum install git
```

Setelah itu, coba periksa versi yang terinstal dengan perintah:
```bash
git --version
```

Pada komputer saya, versi yang terinstal adalah: 2.43
![images](/images/git/git-version.png)

## 2. Cara Install Git di Windows

Instalasi Git di Windows memang tidak seperti di Linux yang ketik perintah langsung terinstal.

Kita harus men-download dulu, kemudian melakukan ritual `next -> next -> finish`.

Tapi dalam ritual tersebut, ada pilihan yang harus diperhatikan agar perintah git dapat dikenali di CMD.

## Download Git

Silakan buka website resminya [Git](git-scm.com). Kemudian unduh Git sesuai dengan arsitektur komputer kita. Kalau menggunakan 64bit, unduh yang 64bit. Begitu juga kalau menggunakan 32bit.
Langkah-langkah Install Git di Windows

Baiklah, mari kita mulai ritual instalnya. Silakan klik 2x file instaler Git yang sudah diunduh.

![images](/images/git/1.BukafileinstalerGit.JPG)

Maka akan muncul informasi lisensi Git, klik Next > untuk melanjutkan.

![images](/images/git/2.Informasitentanggit.JPG)

Selanjutnya menentukan lokasi instalasi. Biarkan saja apa adanya, kemudian klik `Next ->.`

![images](/images/git/3.Lokasiinstal.JPG)

Selanjutnya pemilihan komponen, biarkan saja seperti ini kemudian klik `Next ->.`

![images](/images/git/4.Pemilihankomponen.JPG)

Selanjutnya pemilihan direktori start menu, klik `Next ->.`

![images](/images/git/5.pembuatanstartmenu.JPG)

Selanjutnya pengaturan *PATH Environment*. Pilih yang tengah agar perintah `git` dapat di kenali di Command Prompt (`CMD`). Setelah itu klik `Next ->.`

![images](/images/git/6.Pathenvironment.JPG)

Selanjutnya konversi *line ending*. Biarkan saja seperti ini, kemudian klik `Next ->.`

![images](/images/git/7.konversilineending.JPG)

Selanjutnya pemilihan *emulator terminal*. Pilih saja yang bawah, kemudian klik `Next >.`

![images](/images/git/8.Pemilihanemulatorterminal.JPG)

Selanjutnya pemilihan opsi ekstra. Klik saja `Next ->.`

![images](/images/git/9.KonfigurasiOpsiEkstra.JPG)

Selanjutnya pemilihan *opsi eksperimental*, langsung saja klik Install untuk memulai instalasi.

![images](/images/git/10.Opsiekperimental.JPG)

Tunggu beberapa saat, instalasi sedang dilakukan.

![images](/images/git/11.Installing.JPG)

Setelah selesai, kita bisa langsung `klik Finish.`

![images](/images/git/12.Finish.JPG)

Selamat, Git sudah terinstal di Windows. Untuk mencobanya, silakan buka CMD atau PowerShell, kemudian ketik perintah `git --version.`

![images](/images/git/13.Percobaan.JPG)

## Cara Install Git di MacOS

Buat kamu yang menggunakan MacOS, git bisa diinstal dengan `brew`.

Buka terminal lalu, ketik perintah berikut untuk menginstal Git:
```bash
brew install git
```

Tunggulah beberapa saat sampai proses instalasinya selesai. Setelah itu, coba ketik perintah berikut untuk mengecek versi git yang terinstal:
```bash
git --version
```

Maka hasilnya:

![images](/images/git/versi-git-macos.png)

Ini artinya, git versi 2.42.0 sudah terinstal dengan benar di MacOS. Selanjutnya, kita bisa lakukan konfigurasi awal.


## 3. Konfigurasi Awal yang Harus Dilakukan

Ada beberapa konfigurasi yang harus dilakukan sebelum mulai menggunakan Git, seperti menentukan name dan email.

Silakan lakukan konfigurasi dengan perintah berikut ini.
```bash
git config --global user.name "Cleanic Computer"
git config --global user.email contoh@cleaniccomputer.com
```

Kemudian periksa konfigurasinya dengan perintah:
```bash
git config --list
```

![images](/images/git/git-config-list.png)

Konfigurasi `core.editor` bersifat opsional. Sedangkan name dan email wajib.

Jika kamu memiliki akun Github, Gitlab, Bitbucket atau yang lainnya…

maka username dan *email* harus mengikuti akun tersebut agar mudah diintegrasikan.

Selain konfigurasi awal ini, kamu juga bisa konfigurasi SSH key untuk Github, Gitlab, dan Bitbucket.

Silakan baca caranya di sini:

- [Cara Setup SSH Key untuk Github](#)
- [Cara Setup SSH Key untuk Gitlab](#)
- [Cara Setup SSH Key untuk Bitbucket](#)

## Konfigurasi Default Branch saat ini

Secara default, repository Git akan menggunakan nama branch master ketika kita baru pertama membuat repository.

Nama ini sebenarnya mulai ditinggalkan dan disarankan pakai nama `main`. Soalnya di Github.. default branch atau branch utama yang digunakan adalah `main`.

Saat kita mau upload repo ke Github, nantinya kita akan diminta untuk mengubah `master` menjadi `main`.

Biar tidak repot, kita setup aja dari awal.

Lalu gimana caranya supaya Git otomatis menggunakan `main` secara default?

Gampang, kita cukup tambahkan konfigurasi ini.

Silakan ketik di Terminal atau CMD:
```bash
git config --global init.defaultBranch main
```

Dengan demikian, Git akan otomatis menggunakan nama main sebagai branch utama.

## Apa Selanjutnya?

Bagus, kita sudah mempersiapkan semuanya. Selanjutnya kita bisa langsung belajar membuat [repositori git](#).

