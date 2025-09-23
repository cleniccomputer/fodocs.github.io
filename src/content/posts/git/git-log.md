---
title: Melihat Catatan Log Revisi
published: 2023-09-09
description: Pelajari dasar-dasar version control dengan Git untuk pemula.
image: '/images/git/git-petanikode.png'
tags: [Git, Tutorial]
category: Development
draft: false
lang: id 
---

Pada [tutorial sebelumnya](../git-commit/), kita sudah membuat dua revisi pada repositori project-01. Sekarang bagaimana caranya kita melihat catatan log dari revisi-reivisi tersebut?

Git sudah menyediakan perintah git log untuk melihat catatan log perubahan pada repositori. Contoh penggunaannya:

```bash
git log
```

Maka kita akan melihat log perubahan apa saja yang sudah dilakukan dalam repositori.

![images](/images/git/log-revisi-yang-sudah-dibuat.png)

### Log yang Lebih Pendek

Untuk menampilkan log yang lebih pendek, kita bisa menambahkan argumen **--oneline**.

```bash
git log --online
```

Maka akan menghasilkan output:

```log
06f735a ditambahkan isi
cf08ca0 commit pertama
```

### Log pada Nomer Revisi/Commit

Untuk melihat log pada revisi tertentu, kita bisa memasukan nomer revisi/commit.

```log
git log cf08ca0837cf26f1c595be36bb3a6b815e311be1
```

Maka menghasilkan output:

```log
commit cf08ca0837cf26f1c595be36bb3a6b815e311be1
Author: Ardianta Pargo <ardianta_pargo@yahoo.co.id>
Date:   Mon Feb 13 18:08:56 2017 +0800

    commit pertama
```

### Log pada File Tertentu

Untuk melihat revisi pada file tertentu, kita dapat memasukan nama filenya.

```bash
git log index.html
```

Maka akan menghasilkan output:

```log
commit 06f735af7724558164c87f6b1ce3ca7778eb1c1b
Author: Ardianta Pargo <ardianta_pargo@yahoo.co.id>
Date:   Mon Feb 13 18:26:50 2017 +0800

    ditambahkan isi

commit cf08ca0837cf26f1c595be36bb3a6b815e311be1
Author: Ardianta Pargo <ardianta_pargo@yahoo.co.id>
Date:   Mon Feb 13 18:08:56 2017 +0800

    commit pertama

```

Karena file **index.html** sudah direvisi sebanyak dua kali.

### Log Revisi yang dilakukan oleh Author Tertentu

Misalkan dalam repositori dikerkajan oleh banyak orang. Maka kita dapat melihat revisi apa saja yang di lakukan oleh orang tertentu dengan perintah berikut:

```bash
git log --author='Ocatocat'
```

### Penutup

Itulah beberapa cara melihat log revisipada repositori, Perintah yang di gunaka adlah **git log**. Selanjutnya kita pelajari perintah **git diff** untuk melihat perbandingan pada revisi.

Selanjutnya: [Tutorial Git 05 - Melihat Perbandingan Revisi](../git-diff/)