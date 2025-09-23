---
title: Cara Membuat Repositori Baru dalam Proyek
published: 2023-09-09
description: Pelajari dasar-dasar version control dengan Git untuk pemula.
image: '/images/git/git-petanikode.png'
tags: [Git, Tutorial]
category: Development
draft: false
lang: id 
---

Repositori (repository) dalam bahasa indonesia artinya gudang. Repositori merupakan istilah yang digunakan untuk direktori proyek yang menggunakan Git.

Jika kita memiliki sebuah direktori dengan nama proyek-01 dan di dalamnya sudah menggunakan git, maka kita sudah punya repositori bernama proyek-01.

### Membuat Repository

Pembuatan repositori dapat dilakukan dengan perintah **git init nama-dir**. Contoh:

```bash
git init proyek-01
```

Perintah tersebut akan membuat direktori bernama **proyek-01**. Kalau direktorinya sudah ada, maka Git akan melakukan inisialisasi di dalam direktori tersebut.

Perintah **git init** akan membuat sebuah direktori bernama **.git** di dalam proyek kita. Direktori ini digunakan Git sebagai database untuk menyimpan perubahan yang kita lakukan.

Hati-hati!

Kalau kita menghapus direktori ini, maka semua rekaman atau catatan yang dilakukan oleh Git akan hilang.

### Contoh-contoh lain

Perintah berikut ini akan membuat repositori pada direktori saat ini *(working directory)*.

```bash
git init .
```

Tanda titik **(.)** artinya kita akan membuat repository pada direktori tempat kita berada saat ini.

![images](/images/git/membuat-repositori-git.png)

Perintah berikut ini akan membuat repositori pada direktori **/var/www/html/proyekweb/**.
```bash
git init /var/www/html/proyekweb
```

### .gitignore

**.gitignore** merupakan sebuah file yang berisi daftar nama-nama file dan direktori yang akan diabaikan oleh Git.

Perubahan apapun yang kita lakukan terhadap file dan direktori yang sudah masuk ke dalam daftar** .gitignore** tidak akan dicatat oleh Git.

Cara menggunakan **.gitignore**, buat saja sebuah file bernama .gitignore dalam root direktori proyek/repositori.

```diff
/vendor/
/upload/
/cache
test.php
```

Pada contoh file **.gitignore** di atas, saya memasukkan direktori **vendor, upload, cache** dan file **test.php**. File dan direktori tersebut akan diabaikan oleh Git.

Pembuatan file .gitignore sebaiknya dilakukan di awal pembuatan repositori.

Contoh .gitignore pada proyek-proyek tertentu, bisa dilihat di [repositori ini](https://github.com/github/gitignore).

### Penutup

Sekian dulu untuk tutorial kedua ini, Kita baru saja mengetahui cara pembuatan repositori dan tentang **.gitignore**.

Penggunaan **.gitignore** memang belum dapat kita rasakan saat ini, karena kita belum membuat revisi apa pun. Karena itu, silakan lanjutkan ke tutorial ketiga [‘Membuat Revisi’](../git-commit/).