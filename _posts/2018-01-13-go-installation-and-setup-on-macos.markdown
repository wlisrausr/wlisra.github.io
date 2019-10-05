---
layout: post
title: "TIL: Instalasi dan Pengaturan Bahasa Pemrograman Go di MacOS"
date: 2018-01-13
comments: true
categories: [Programming]
published: true
---

Saat mengikuti [*interview* rekrutmen Tokopedia](https://wlisrausr.github.io/blog/2017/12/25/register-experience-as-software-engineer-at-tokopedia/){:target="_blank"} bulan lalu, saya sempat mengajukan beberapa pertanyaan kepada *interviewer*. Salah satunya adalah tentang teknologi/*tools* yang saat ini digunakan oleh [Tokopedia](https://www.tokopedia.com/){:target="_blank"}. Ternyata, salah satunya adalah [Go *programming language*](https://golang.org/){:target="_blank"}. Bahasa yang dikembangkan oleh [Google LLC](https://en.wikipedia.org/wiki/Google){:target="_blank"} dan sedang *hype* di kalangan *developer* saat ini. Oleh karenanya, saya manjadi tertantang untuk mempelajari & menjadikan Go sebagai salah satu *expertise* saya selama bekerja di Tokopedia nantinya.

Dikarenakan niat saya untuk mempelajari bahasa ini secara mendalam, maka saya harus melakukan instalasi dan pengaturan secara langsung di komputer pribadi saya. Jika hanya ingin mencicipi atau melihat Go *in action* secara umum, silahkan kunjungi [Go *tour online*](https://tour.golang.org/welcome/1){:target="_blank"}.

### Sebelum Instalasi

Sebelum melakukan instalasi, ada baiknya cek terlebih dahulu apakah Go sudah ter-*install* di komputer dengan menjalankan perintah berikut pada *shell/terminal*.

{% highlight go %}
$ go version
{% endhighlight %}

Jika sudah, *shell/terminal* akan memberikan keluaran seperti berikut dengan versi yang mungkin akan berbeda.

{% highlight go %}
$ go version
go version go1.9.2 darwin/amd64
{% endhighlight %}

Instalasi tidak perlu dilakukan jika Go sudah ter-*install* di komputer, kecuali hendak melakukan pembaharuan ke versi yang lebih tinggi.

### Instalasi

Cara termudah yang dapat dilakukan untuk meng-*install* Go di MacOS adalah dengan menggunakan [Brew package manager](https://brew.sh/){:target="_blank"}. Pastikan Brew sudah ter-*install* dan jalankan perintah berikut pada *shell/terminal*.

{% highlight go %}
$ brew install go
{% endhighlight %}

Jika proses ini berjalan dengan lancar hingga selesai, maka versi dari Go yang ter-*install* dapat dicek menggunakan perintah "**`go version`**" sebelumnya.

### Pengaturan GOPATH

Setelah instalasi berhasil dilakukan, Go belum dapat digunakan sepenuhnya. Kita diharuskan untuk mengatur **`GOPATH`** *environment variable* untuk menentukan lokasi/*path* dari Go *workspace*. Dengan kata lain, kita harus menentukan lokasi/*path* dari semua kode Go yang akan ditulis nantinya.

Secara *default* (jika `GOPATH` tidak di-*set*), Go akan berasumsi bahwa *workspace* berada di **`$HOME/go`**. Saya pribadi menetapkan lokasi dari Go *workspace* ini di **`$HOME/code/go`**. Lokasi/*path* dari Go *workspace* dapat ditetapkan di manapun selama tidak sama dengan lokasi/*path* dari instalasi Go.

Untuk mengatur **`GOPATH`**, silahkan tambahkan 3 baris berikut pada *file* "**`~/.zshrc`**" (jika menggunakan [zsh](https://en.wikipedia.org/wiki/Z_shell){:target="_blank"}) atau "**`~/.bash_profile`**" (jika menggunakan [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)){:target="_blank"}) dan *save*. Jangan lupa sesuaikan lokasi/*path*-nya masing-masing.

{% highlight go %}
export PATH=$PATH:/usr/local/bin/go
export GOPATH=$HOME/code/go
export PATH=$PATH:$(go env GOPATH)/bin
{% endhighlight %}

Jalankan perintah berikut di *shell/terminal* agar **`PATH`** tersebut ditambahkan pada *environment variable*.

{% highlight go %}
# Jika menggunakan zsh
$ source ~/.zshrc

# Jika menggunakan bash
$ source ~/.bash_profile
{% endhighlight %}

Untuk memastikan bahwa **`PATH`** berhasil ditambahkan, jalankan perintah berikut pada *shell/terminal*.

{% highlight go %}
$ echo $GOPATH && echo $PATH
{% endhighlight %}

Jika berhasil, *shell/terminal* akan memberikan keluaran dari **`PATH`** lengkap keduanya.

{% highlight go %}
$ echo $GOPATH && echo $PATH
/Users/wlisrausr/code/go
/Users/wlisrausr/.rbenv/shims:/Users/wlisrausr/.rbenv/bin:/Users/wlisrausr/.composer/vendor/bin:/usr/local/sbin:/usr/local/opt/php71/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Users/wlisrausr/Library/Android/sdk/tools:/Users/wlisrausr/Library/Android/sdk/platform-tools:/Users/wlisrausr/.composer/vendor/bin:/Users/wlisrausr/.fzf/bin:/usr/local/bin/go:/Users/wlisrausr/code/go/bin
{% endhighlight %}

Tambahkan pula 3 direktori baru (**bin**, **pkg**, **src**) pada *workspace* agar kode dan lokal *packages* Go lebih rapi dan terstruktur.

{% highlight go %}
$ mkdir -p $GOPATH/bin
$ mkdir -p $GOPATH/pkg
$ mkdir -p $GOPATH/src
{% endhighlight %}

### Pengujian

Kita dapat memastikan apakah instalasi dan pengaturan tersebut sudah berfungsi dengan baik dengan cara meng-*install* **gotour** secara lokal. Jalankan perintah berikut pada *shell/terminal*.

{% highlight go %}
$ go get golang.org/x/tour/gotour
{% endhighlight %}

Jika proses ini berhasil, maka kita dapat menjalankan perintah "**`gotour`**" pada *shell/terminal* dan mempelajari Go pada *browser* secara *offline*.

*That's it*. Semoga bermanfaat dan jangan sungkan untuk meninggalkan komentar.

***Note***: Jika ingin melakukan instalasi dan pengaturan pada OS berbeda, silahkan kunjungi [dokumentasi resmi Go](https://golang.org/doc/install){:target="_blank"}.
