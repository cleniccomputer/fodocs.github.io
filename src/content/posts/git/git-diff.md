---
title: Melihat Perbandingan Revisi dengan Git Diff
published: 2023-09-09
description: Pelajari dasar-dasar version control dengan Git untuk pemula.
image: '/images/git/git-petanikode.png'
tags: [Git, Tutorial]
category: Development
draft: false
lang: id 
---

Pada tutorial sebelumnya, kita sudah belajar cara melihat log revisi di repositori. Sekarang kita kan pelajari perintah **git diff**, fungsinya untuk melihat perbedaan perubahan di revisi.

### Melihat Perbandingan Perubahan yang Dilakukan pada Revisi

Gunakan perintah berikut ini untuk melihat perubahan yang dilakukan pada revisi tertentu.

```bash
git diff cf08ca0837cf26f1c595be36bb3a6b815e311be1
```
*cf08ca0837cf26f1c595be36bb3a6b815e311be1* adalah nomer revisi yang ingin dilihat.

![images](/images/git/git-diff-pada-nomer-revisi.png)

Lihatlah hasil di atas, simbol plus **(+)** artinya kode yang ditambahkan. Sedangkan kalau ada kode yang dihapus simbolnya akan menggunakan minus **(-)**.

**Contoh:**
Ditambahkan:
```bash
+ <p>ini kode yang ditambahkan</p>
```

Dihapus:
```bash
- <i>ini kode yang dihapus</i>
```

Dimodifikasi/diubah:
```bash
- <span>ini kode sebelum diubah</span>
+ <span>ini kode sesudah diubah</span>
```

Sekarang kita akan mencoba mengubah isi dari **index.html**.

Sebelum diubah:
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Belajar Git - Project 01</title>
    </head>
    <body>
        <p>Hello Semua, Saya sedang belajar Git</p>
    </body>
</html>
```

Setelah diubah:
```html
etelah diubah:

<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Belajar Git - Project 01</title>
    </head>
    <body>
        <p>Hello Dunia!, Saya sedang belajar Git</p>
    </body>
</html>
```

Setelah itu lakukan jalankan perintah git diff lagi.

![images](/images/git/perbedaan-revisi.png)

Apa yang dilakukan **git diff**? Perintah **git diff** akan membandingkan perubahan yang baru saja dilakukan dengan revisi/commit terakhir.

### Melihat Perbandingan pada File

Apa bila kita melakukan banyak perubahan, maka akan banyak sekali tampil output. Karena itu, kita mungkin hanya perlu melihat perubahan untuk file tertentu saja. Untuk melihat perbandingan perubahan pada file tertentu, gunakan perintah berikut.

```bash
git diff index.html
```

Perintah di atas akan melihat perbedaan perubahan pada file **index.html** saja.

### Melihat Perbandingan antara Revisi/Commit

Perintah untuk membandingkan perubahan pada revisi dengan revisi yang lain adalah sebagai berikut.

```bash
git diff <nomer commit> <nomer commit>
```

contoh:

```bash
git diff cf08ca0837cf26f1c595be36bb3a6b815e311be1 06f735af7724558164c87f6b1ce3ca7778eb1c1b
```

### Perbandingan Antar Cabang (Branch)

Kita memang belum masuk ke materi percabangan di Git. Tapi tidak ada salahnya mengetahui cara melihat perbandingan perubahan antar cabang.

```bash
git diff <nama cabang> <nama cabang>
```

### Penutup
Kita sudah pelajari fungsi dari perintah **git diff**. Perintah ini untuk melihat perbandingan perubahan apa saja yang telah dilakukan pada repositori. Selanjutnya, kita akan belajar membatalkan revisi.

Selanjutnya: [Tutorial Git 06 - Membatalkan Revisi](../git-revert/)