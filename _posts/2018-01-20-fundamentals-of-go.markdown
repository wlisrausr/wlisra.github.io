---
layout: post
title: "TIL: Dasar-Dasar Pemrograman Go"
date: 2018-01-20
comments: true
categories: [Go, Tutorial]
published: false
---

Pada artikel sebelumnya, saya telah membahas tentang bagaimana cara untuk [meng-*install* Go dan mengatur GOPATH pada MacOS](https://wlisrausr.github.io/blog/2018/01/13/go-installation-and-setup-on-macos/){:target="_blank"}. Kali ini, saya akan coba untuk membahas beberapa poin penting terkait dasar-dasar pemrograman Go yang saya rangkum dari [Go *tour online*](https://tour.golang.org/list){:target="_blank"} dan [*The Little Go Book by Carl Seguin*](http://openmymind.net/The-Little-Go-Book/){:target="_blank"}. Dua referensi yang saya rasa cukup untuk memulai perjalanan sebagai seorang [*Gopher*](https://blog.golang.org/gopher){:target="_blank"}. Sip, mari kita mulai.

#### 1. Kompilasi & *Static Typing*

Go adalah salah satu dari sekian bahasa pemrograman yang diharuskan untuk melalui proses kompilasi (*compile*). Proses ini dilakukan oleh [*compiler*](https://en.wikipedia.org/wiki/Compiler){:target="_blank"} guna menerjemahkan kode yang ditulis ke bahasa tingkat rendah (dalam kasus Go yaitu *assembly*) agar nantinya dapat dijalankan sebagai dokumen *executable binary*. Salah satu cara yang dapat dilakukan untuk mengkompilasi kode Go adalah dengan menggunakan Go *command tool* berikut.

{% highlight go %}
$ go build [filename].go
{% endhighlight %}

Selain harus dikompilasi, Go juga merupakan salah satu bahasa yang dikategorikan ke dalam *statically typed*. Artinya, setiap variabel yang digunakan di dalam kode haruslah memiliki tipe data spesifik seperti ***integer***, ***boolean***, ***string***, dan sebagainya.

#### 2. Menjalankan Kode Go

Seperti layaknya tradisi umum saat belajar bahasa pemrograman, mari mulai dengan menjalankan kode Go sederhana berupa "***hello world***". Dikarenakan saya sudah [mengatur Go *workspace*](https://wlisrausr.github.io/blog/2018/01/13/go-installation-and-setup-on-macos/){:target="_blank"} sebelumnya, maka saya akan menggunakannya sekarang. Silahkan masuk ke direktori "**src**" pada Go *workspace*, tambahkan direktori baru dengan nama "**hello**", buka teks *editor* favorit dan ketik kode berikut.

{% highlight go linenos %}
package main

import "fmt"

func main() {
        fmt.Printf("Hello world\n")
}
{% endhighlight %}

Simpan *file* dengan nama "**hello.go**" di dalam direktori "**hello**". Kemudian, jalankan Go *command tool* berikut untuk mengkompilasi dan meng-*install* kode tersebut ke dalam direktori "**bin**".

{% highlight go %}
$ go install
{% endhighlight %}

Jika berhasil, perintah tersebut akan menghasilkan sebuah dokumen *executable binary* bernama "**hello**" di dalam direktori "**bin**". Jalankan perintah berikut untuk melihat keluarannya.

{% highlight go %}
$ $GOPATH/bin/hello
Hello world
{% endhighlight %}

#### 3. Paket (*Package*)

Setiap *program*/aplikasi Go pastilah dibangun dengan menggunakan beberapa paket. Paket utama yang akan dijalankan sebagai *entry point* adalah "**main**". Penamaan paket ini sendiri dapat dilakukan dengan menggunakan kata kunci "**package**" dengan format dan contoh seperti berikut.

{% highlight go %}
// Format
package nama_paket

// Contoh
package blog
{% endhighlight %}

Pada Go, konvensi penamaan paket akan mengikuti lokasi terakhir dari direktori paket (direktori paling dalam) atau elemen terakhir dari ***import path***. Contohnya, jika ingin membangun sebuah sistem *blogging*, kita dapat menamai paketnya dengan nama "**blog**" dan menempatkan seluruh kode di dalam direktori "**$GOPATH/src/blog**".

Selain itu, kita juga dapat memanfaatkan fitur *import* (menggunakan kata kunci "**import**") jika ingin mengakses paket lain di dalam suatu paket dengan format dan contoh seperti berikut.

{% highlight go %}
// Format
// Single import statement
import "paket_path"

// Multiple import statement
import "paket_path_1"
import "paket_path_2"

// Factored import statement
import (
        "paket_path_1"
        "paket_path_2"
)

// Contoh
// Single import statement
import "math/rand"

// Multiple import statement
import "fmt"
import "math/rand"

// Factored import statement
import (
        "fmt"
        "math/rand"
)

{% endhighlight %}

Perlu diingat, *import* ini berbeda halnya dengan penamaan paket. Jika nama paket hanya perlu ditulis dalam bentuk satu nilai saja, maka *import* paket haruslah ditulis dalam bentuk lokasi *path* dari paket yang akan diakses.

#### 4. Tipe Data

Ada 7 tipe data dasar dari Go yaitu:
- Boolean (bool)
- String (string)
- Integer (int, int8, int16, int32, int64, uint, uint8, uint16, uint32, uint64, uintptr)
- Byte (uint8 alias)
- Rune (int32 alias)
- Float (float32, float64)
- Complex (complex64, complex128)

Dari ketujuh tipe data tersebut, ada 1 tipe yang mungkin terlihat kurang familiar yaitu *complex*.

#### 5. Variabel (*Variable*)

Deklarasi variabel pada Go dapat dilakukan dengan menggunakan kata kunci "**var**" dengan format dan contoh seperti berikut.

{% highlight go %}
// Format
var nama_variabel tipe_data

// Contoh
var menikah bool
var no_rumah int
var nama string
{% endhighlight %}

Jika variabel dideklarasi tanpa nilai inisial eksplisit, maka Go akan memberikan nilai kosong pada variabel. Nilai kosong dari variabel bertipe numerik (**int** dan **float**) adalah 0, boolean = false, dan string = "" (string kosong).

Jika tidak ingin menggunakan nilai kosong sebagai nilai awal, kita dapat melakukan inisialisasi pada variabel dengan format dan contoh seperti berikut.

{% highlight go %}
// Format
var nama_variabel tipe_data = nilai

// Contoh
var menikah bool = true
var no_rumah int = 66
var nama string = "Wanda Ichsanul Isra"
{% endhighlight %}

Proses deklarasi dan inisialisasi variabel juga dapat dilakukan sejalan dengan menggunakan operator "**:=**" (*short variable declaration operator*). Perlu diingat, operator ini hanya dapat digunakan di dalam fungsi saja.

{% highlight go %}
// Format
nama_variabel := nilai

// Contoh
func main() {
        hidayah := getHidayah()
}

func getHidayah() {
        return true
}
{% endhighlight %}

#### 6. Konstanta (*Constant*)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 7. Fungsi (*Function*)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 8. Pernyataan Kondisional

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 9. Perulangan

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### 10. Struktur Data

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
