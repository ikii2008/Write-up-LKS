# Write-Up: Investigasi File Rahasia
### LKS Cyber Security Kabupaten Cilacap — 2025

---

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/lks2025.1-challange.png" alt="lks2025.1-challange">
</p>

| Info | Detail |
|------|--------|
| **Type** | Forensic |
| **Points** | 300 |
| **Deskripsi** | — |
| **Hint** | Cari flags |

---

## Penyelesaian

Pada soal kami diberikan sebuah link yang membawa kami untuk mendownload sebuah file. Setelah didownload, file tersebut merupakan file `disk.img`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/lks2025.2-disk_image.png" alt="lks2025.2-disk_image">
</p>

Karena ini merupakan file disk.img maka kami mencoba menggunakan command mmls untuk melihat dimana sistem linux start.

```bash
mmls disk.flag.img
```

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/lks2025.3-mmls.png" alt="lks2025.3-mmls">
</p>

Melalui command ini kami mendapati bahwa start poin ada pada 360448. Kemudian kami menggunakan command fls untuk melihat file di dalamnya.

```bash
fls -o 360448 disk.flag.img
```

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/lks2025.4-fls.png" alt="lks2025.4-fls">
</p>

Disini terlihat direktori root ada pada 1995, maka kami mencoba masuk ke direktori tersebut menggunakan command fls kembali. 

```bash
fls -o 360448 disk.flag.img 1995
```

Kemudian kami menemukan sebuah direktori yang mencurigakan, yaitu my_folder, kemudian kami melihat ke direktori tersebut menggunakan command fls. 

```bash
fls -o 360448 disk.flag.img 3981
```

Ada 2 buah file yangn keduanya menyertakan text “flag” dan kami mencoba membaca kedua file itu satu-persatu menggunakan command icat.

```bash
icat -o 360448 disk.flag.img 2371
```

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/lks2025.5-flag.png" alt="lks2025.5-flag">
</p>

Dan boomm, kami dapat flagnya.

---

## Flag

```
picoCTF{by73_5urf3r_152f373f}
```

---

*Write-up oleh: Wiki · LKS Cyber Security Kab. Cilacap 2025*
