---
layout: default
title: Beranda
---

# Selamat Datang di Blog Saya!

Halo pembaca, ini adalah situs web statis saya yang dibuat secara langsung dari file **Markdown** dan di-host di **GitHub Pages** menggunakan engine **Jekyll**.

### Daftar Postingan Terbaru
Berikut adalah daftar catatan harian saya:

{% for post in site.posts %}
* [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d %B %Y" }}
{% endfor %}
