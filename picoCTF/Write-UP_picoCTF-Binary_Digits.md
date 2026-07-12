# Write-UP: picoCTF - Binary Digits

---

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/Binary_Digits/Challange.png" alt"challange">
</p>

| Info | Detail |
| Category | Forensics |
| Points | 100 |
| Hint | - |

---

## Description.

This file doesn't look like much... just a bunch of 1s and 0s. But maybe it's not just random noise. Can you recover anything meaningful from this?
Download the file here.

## Resolution.

Pada tantangan ini, disediakan sebuah file yang dapat di download, saya mendownloadnya menggunakan tools `wget` lalu mengecek jenis file dengan command `file`.

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/Binary_Digits/wget_and_file.png" alt"wget and file">
</p>

Didapatkan sebuah file dengan nama `digits.bin`, file tersebut berisi teks `ASCII`, jadi saya membacanya menggunakan command `cat`.

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/Binary_Digits/cat.png" alt"cat">
</p>

Isi dari file merupakan kumpulan kode biner yaitu angka 0 dan 1, kemungkinan ini adalah cryptography dengan jenis biner, jadi saya mencoba mendekripsi seluruh isi file pada tools online yaitu `CyberChef`.

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/Binary_Digits/cyberchef1.png" alt"cyberchef1">
</p>

Output yanng dihasilkan adalah `raw binary data` dari file `image` dengan ekstensi `jpeg`, jadi saya menambahkan resep `render image`.

<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/Binary_Digits/cyberchef2.png" alt"cyberchef2">
</p>

Didapatkan sebuah output berupa gambar, dan di dalam gambar tersebut ada sebuah flag untuk menyelesaikan tantangan.

Berikut ini adalah gambarnya:

link
<p align="center">
    <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/picoCTF/Binary_Digits/image.png" alt"flag image">
</p>

## Flag.

```
picoCTF{h1dd3n_1n_th3_b1n4ry_d4e39e9e}
```
---

## Kesimpulan.

Pada tantangan ini, diajarkan tentang cryptography dengan jenis biner serta contoh raw binary data dari file image. 

---

*Write-UP oleh: Wiki - 2026*
