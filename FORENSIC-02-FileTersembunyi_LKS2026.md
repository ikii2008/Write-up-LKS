# Write_UP: FORENSIC-02 - File Tersembunyi
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Forensic** |
| **Challange Name** | **FORERNSIC-02 - File Tersembunyi** |

---

## Deskripsi Soal

Sebuah file gambar ditemukan pada sebuah sistem.

Namun file tersebut tidak sesederhana yang terlihat.


Tugas:

·	Lakukan analisis terhadap file

·	Temukan file tersembunyi

·	Dapatkan flag

## Analisis Masalah

Menggunakan tools `binwalk` untuk mengekstrak file tersembunyi di file image.

## Langkah Penyelesaian

Pada soal ini, kami diberi sebuah file, kami mendownloadnya menggunakan `wget`. File tersebut dikompres dengan `zip`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/forensic-02.1-download_file.png" alt="forensic-02.1-download_file">
</p>

Kami mengekstraknya menggunakan command `unzip`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/forensic-02.2-extract_file.png" alt="forensic-02.2-extract_file">
</p>

Terdapat file image, pada soal,diketahui terdapat sebuah file tersembunyi, jadi kami mencoba menggunakan command:

```bash
binwalk –e 
```
Untuk mengekstrak file tersebut.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/forensic-02.3-binwalk.png" alt="forensic-02.3-binwalk">
</p>

Setelah di ekstrak, muncul direktori baru, kami masuk ke direktori itu, dan mengecek isinya.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/forensic-02.4-flag_found.png" alt="forensic-02.4-flag_found">
</p>

Pada direktori `_image.png.extracted`, terdapat file `secret.txt` yang cukup mencurigakan, jadi kami membaca file tersebut dengan command `cat`, dan kami mendapatkan flagnya.

## Analisis Teknis

Menggunakan celah yang yang terdapat pada file image, mengekstrak file tersembunyi menggunakan binwalk.

## Flag

```
LKSJATENG{hidden_file_found}
```

## Kesimpulan

Image dapat menyimpan file tersembunyi.

---

*Write-up oleh: Wiki · LKS Cyber Security Kab. Cilacap 2026*
