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

Kami mengekstraknya menggunakan command `unzip`.

Terdapat file image, pada soal,diketahui terdapat sebuah file tersembunyi, jadi kami mencoba menggunakan command:

```bash
binwalk –e 
```
Untuk mengekstrak file tersebut.

Setelah di ekstrak, muncul direktori baru, kami masuk ke direktori itu, dan mengecek isinya.

Pada direktori `_image.png.extracted`, terdapat file `secret.txt` yang cukup mencurigakan, jadi kami membaca file tersebut dengan command `cat`, dan kami mendapatkan flagnya.

## Analisis Teknis

Menggunakan celah yang yang terdapat pada file image, mengekstrak file tersembunyi menggunakan binwalk.

## Flag

```
LKSJATENG{hidden_file_found}
```

## Kesimpulan

Image dapat menyimpan file tersembunyi.
