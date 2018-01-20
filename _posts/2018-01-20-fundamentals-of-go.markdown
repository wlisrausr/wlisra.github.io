---
layout: post
title: "TIL: Dasar-Dasar Pemrograman Go"
date: 2018-01-20
comments: true
categories: [Go, Tutorial]
published: true
---

Pada artikel sebelumnya, saya telah membahas tentang bagaimana cara [meng-*install* Go dan mengatur GOPATH pada MacOS](https://wlisrausr.github.io/blog/2018/01/13/go-installation-and-setup-on-macos/){:target="_blank"}. Kali ini, saya akan coba untuk membahas beberapa poin penting dari dasar-dasar pemrograman Go yang saya pelajari dari [Go *tour online*](https://tour.golang.org/list){:target="_blank"} dan [*The Little Go Book by Carl Seguin*](http://openmymind.net/The-Little-Go-Book/){:target="_blank"}. Dua referensi yang saya rasa cukup untuk memulai perjalanan sebagai seorang [*Gopher*](https://blog.golang.org/gopher){:target="_blank"}. Sip, mari kita mulai.

#### 1. Kompilasi & *Static Typing*

Go adalah salah satu dari sekian bahasa pemrograman yang diharuskan untuk melalui proses kompilasi. Proses ini dilakukan oleh [*compiler*](https://en.wikipedia.org/wiki/Compiler){:target="_blank"} guna menerjemahkan kode yang ditulis ke bahasa tingkat rendah (dalam kasus Go yaitu *assembly*) agar nantinya dapat dijalankan sebagai dokumen *executable binary*. Salah satu cara yang dapat dilakukan untuk mengkompilasi kode yang ditulis adalah dengan menggunakan Go *command tool* berikut.

{% highlight go %}
go build [filename].go
{% endhighlight %}

Selain harus dikompilasi, Go juga merupakan salah satu bahasa yang dikategorikan kepada *statically typed*. Artinya, setiap variabel yang digunakan di dalam kode haruslah memiliki tipe data yang spesifik seperti **int**, **bool**, **string**, dan sebagainya.

#### 2. Menjalankan Kode Go

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 3. Paket-Paket (*Packages*)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 4. Tipe Data

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 5. Variabel-Variabel (*Variables*)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 6. Fungsi-Fungsi (*Functions*)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 7. Pernyataan Kondisional

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 8. Perulangan

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 9. Struktur Data

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
