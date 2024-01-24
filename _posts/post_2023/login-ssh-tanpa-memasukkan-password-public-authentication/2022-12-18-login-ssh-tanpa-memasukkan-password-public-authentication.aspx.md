---
title: Login SSH tanpa memasukkan password (Public-Authentication)
date: 2022-12-26 09:45:47 +07:00
tags: [linux, centos, blog, ssh]
description: Login SSH tanpa memasukkan password.
image: "/login-ssh-tanpa-memasukkan-password-public-authentication.aspx/terminal.png"
---

Halo semua, sudah lama sekali tidak menulis artikel, terlebih lagi pada tahun ini, sepertinya sudah cukup lama dari vakum dan harus memulai hal baru kembali.  
Nah pada kali ini, saya akan menjelaskan cara melakukan akses ke server menggunakan SSH tanpa memasukkan password. 

Sebenarnya banyak cara untuk mengakses server tanpa password, namun metode paling aman dan banyak digunakan adalah dengan metode authentikasi dengan ssh-key. Untuk metode ini membuat sebuah public key dengan private key yang bersinambungan. 
Untuk private key nya di letakkan di local sedangkan public key nya di masukkan kedalam server.

Untuk membuat authentikasi dengan ssh key kurang lebih seperti berikut ini :

  * Generate SSH key dari perangkat di local menggunakan&nbsp;`ssh-keygen`. Command ini nantinya akan mengenerate 2 file yaitu private key dan juga public key pada folder&nbsp;`.ssh`
  * Copy-kan public key kedalam server, untuk mudahnya bisa masuk ke server dan masukkan public key nya kedalam&nbsp;`.ssh/authorized_keys`. Untuk metode lainnya bisa menggunakan command&nbsp;`ssh-copy-id`.
  * Untuk selanjutnya uji coba dengan menggunakan command&nbsp;`ssh`&nbsp;pada perangkat local dan akses ke server yang sudah di pasang&nbsp;`public key`nya tersebut. Jika sudah sesuai maka harusnya sudah bisa masuk tanpa password.

Untuk sekedar informasi tambahakan bahwa authentikasi dengan ini lebih aman dari pada password, namun juga dari sisi anda perlu melakukan pengamanan pada private key tersebut.  
Karena pada dasarnya setiap orang yang memiliki private key tersebut dapat masuk kedalam server anda.