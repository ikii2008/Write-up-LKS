# Write-UP: picoCTF -

---

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/DISKO_1/Challenge.png" alt"challenge">
</p>

---

| Info | Detail |
|------|--------|
| **Challenge Name** | DISKO_1 |
| **Category** | Forensics |
| **Dificulty** | Easy |
| **Points** | 1 |
| **Hint** | Maybe Strings could help? If only there was a way to do that? |

---

## Description.

Can you find the flag in this disk image?
Download the disk image here.

## Resolution.

Pada tantangan ini, disediakan sebuah file `disk image`. Saya mendownloadnya menggunakan `wget`.

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/DISKO_1/wget.png" alt"wget">
</p>

File yang disediakan merupakan file `disk image` dengan ekstensi `.dd`. File dengan ekstensi `.dd` adalah jenis file `disk image mentah (raw image)` yang berisi salinan bit-per-bit yang sangat akurat dari sebuah media penyimpanan.

File ini masih dikompresi menggunakan `gz`, jadi saya mengekstraknya dengan tools `gunzip`. Kemudian sesuai dengan hint yang tersedia, saya menggunakan tools `strings` untuk memebaca atau menampilkan teks `ASCII` yang ada di dalam file serta menggunakan `grep` untuk memfilter kata dan mencari kata `pico`.

```bash
strings disko-1.dd | grep pico
```

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/DISKO_1/strings_and_grep.png" alt"strings and grep">
</p>


## Flag.

```
picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}
```
---

## Kesimpulan.

Pada tantangan ini, user diajarkan tentang disk image dan penggunaan tools strings untuk membaca atau menampilkan teks ASCII pada sebuah file.

---

*Write-UP oleh: Wiki - 2026*
