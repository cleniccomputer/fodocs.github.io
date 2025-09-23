---
title: Menggunakan Percabangan untuk mencegah Konflik
published: 2023-09-09
description: Pelajari dasar-dasar version control dengan Git untuk pemula.
image: '/images/git/git-petanikode.png'
tags: [Git, Tutorial]
category: Development
draft: false
lang: id 
---

Bayangkan anda sedang bekerja dengan tim pada suatu repositori Git. Repositori ini dikerjakan secara bersama-sama.

Kadang… akan terjadi konflik, karena kode yang kita tulis berbeda dengan yang lain.

Misalnya, Si A menulis kode untuk fitur X dengan algoritma yang ia ketahui. Sedangkan si B menulis dengan algoritma yang berbeda.

Lalu mereka melakukan commit, dan kode sumber jadi berantakan. Anggota tim yang lain menjadi pusing.

![images](/images/git/konflik-branch-repositori-git.png)

Agar tidak terjadi hal yang seperti ini, kita harus membuat cabang (branch) tersendiri.

Misalnya, si A akan mengerjakan fitur X, maka dia harus membuat cabang sendiri. Si A akan bebas melakukan apapun di cabangnya tanpa mengganggu cabang utama *(master)*.


### Cara Membuat Cabang Baru

Perintah untuk membuat cabang adalah **git branch**, kemudian diikuti dengan nama cabangnya.

Contoh:

```bash
git branch fitur_register
```

Maka Git akanmembuat cabang bernama **fitur_register**.

![images](/images/git/percabganan-di-repositori-git.png)

Sekarang setiap orang memiliki cabangnya masing-masing. Mereka bebas bereksperimen.

Untuk melihat cabang apa saja yang ada di repositori, gunakan perintah git branch.

Contoh:

```bash
$ git branch
  halaman_login
* master
```

Tanda bintang **(*)** artinya cabang yang sedang aktif atau Kita sedang berada di sana.

### Latihan

Untuk memantapkan pemahaman tentang percabangan Git, mari kita coba praktik.

Pada repositori, buatlah sebuah cabang baru.

```bash
git branch halama_login
```

Setelah itu, pindah ke cabang yang baru saja kita buat dengan perintah:

```bash
git checkout halaman_login
```

Lalu tambahkan file **login.html**, isinya terserah anda.

![images](/images/git/pembuatan-branch-dan-eksperimen-di-branch.png)

:::note
*"Jangan lupa untuk menggunakan perintah **git status** untuk melihat status repositori."*
:::

Kita sudah menambahkan file **login.html**. Selanjutnya kita lakukan commit.

```bash
git add login.html
git commit -m "membuat file login.html"
```

Bagus! revisi kita pada cabang **halaman_login** sudah disimpan. Sekarang coba kembali ke cabang **master**.

```bash
git checkout master
```

Apakah anda menemukan file **login.html**?

Pasti tidak!

Sekarang kembali lagi ke cabang **halaman_login**.

```bash
git checkout halaman_login
```

Cek lagi, apakah sekarang file **login.html** sudah ada?

```bash
project-01/
├── index.html
└── login.html
```

Ternyata ada. Yep! kita bisa mengambil kesimpulan, kalau perubahan pada cabang **halaman_login** tidak akan berpengaruh di cabang **master**.

### Menggunakan Cabang

Anggaplah kita sudah selesai membuat fitur login di cabang **halaman_login**. Sekarang kita ingin Menggabungkannya dengan cabang **master** (utama).

Pertama, kita harus pindah dulu ke cabang **master**.

```bash
git checkout master
```

Setelah itu, barulah kita bisa menggabungkan dengan perintah **git merge**.

```bash
git merge halaman_login
```

Sekarang lihat, file **login.html** sudah ada di cabang **master**.

![images](/images/git/penggabungan-cabang-git.png)

### Mengenai Bentrok

Bentrok biasanya terjadi jika ada dua orang yang mengedit file yang sama.

Kenapa bisa begitu, ‘kan mereka sudah punya cabang masing-masing?

Bisa jadi, di cabang yang mereka kerjakan ada file yang sama dengan cabang lain. Kemudian, saat digabungkan terjadi bentrok.

Mengatasi bentrok adalah tugas dari pemilik atau pengelola repositori. Dia harus bertindak adil, kode mana yang harus diambil.

Biasanya akan ada proses diskusi dulu dalam mengambil keputusan.

Baiklah, sekarang kita akan coba membuat bentrokan 😄.

Pindah dulu ke branch **halaman_login**…

```bash
git checkout halaman_login
```

Setela itu, edit file **login.html** atau **index.html**, karena kedua file tersebut ada di kedua cabang yang akan kita gabungkan.

```diff
$ git diff
diff --git a/login.html b/login.html
index 23a3f5c..eea5658 100644
--- a/login.html
+++ b/login.html
@@ -1 +1 @@
-di sini berisi kode untuk halaman login
+<p>di sini berisi kode untuk halaman login<p>
```

Setelah itu, lakukan commit lagi:

```bash
git add login.html
git commit -m "ubah isi login.html"
```

Selanjutnya pindah ke cabang **master** dan lakukan perubahan juga di cabang ini. Ubah file yang sama seperti di cabang **halaman_login**.

Setelah itu, lakukan commit di cabang **master**

```bash
git add login.html
git commit -m "ubah isi login.html di cabang master"
```

Terakhir, coba gabungkan cabang **halaman_login** dengan cabang **master**, maka akan terjadi bentrok.

```bash
$ git merge halaman_login
Auto-merging login.html
CONFLICT (content): Merge conflict in login.html
Automatic merge failed; fix conflicts and then commit the result.
```
Nah, kita disuruh perbaiki kode yang bentrok. Sekarang buka login.html dengan teks editor.

![images](/images/git/kode-yang-bentrok.png)

Kedua kode cabang dipisahkan dengan tanda ======. Sekarang.. tugas kita adalah memperbaikinya.

Silakan eliminasi salah satu dari kode tersebut.

![images](/images/git/Eliminasi-kode-yang-bentrok.png)

Setelah itu lakukan commit untuk menyimpan perubahan ini.

```bash
git add login.html
git commit -m "perbaiki konflik"
```

Bagus! bentrokan antar ormas programmer sudah beres 😄.

### Menghapus Cabang

Cabang yang sudah mati atau tidak ada pengembangan lagi, sebaiknya dihapus.

Agar repositori kita bersih dan rapi.

Cara menghapus cabang, gunakan perintah **git branch** dengan argumen **-d** dan diikuti dengan nama cabangnya.

Contoh:

```bash
git branch -d halaman_login
```

### Akhir Kata…
Sekian tutorial ini. Semoga ada manfaatnya.

[**Referensi : petanikode**](https://www.petanikode.com/git-branch)