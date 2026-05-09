# Write_UP: FORENSIC-01 - Metadata Foto
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Forensic** |
| **Challange Name** | **FORERNSIC-01 - Metadata Foto** |

---

## Deskripsi Soal

Sebuah file gambar ditemukan di dalam sebuah sistem.


Tugas:

·	Lakukan analisis terhadap file tersebut

·	Temukan informasi tersembunyi

·	Submit flag yang ditemukan

## Analisis Masalah

Penggunaan tools `exiftool` untuk metadata file image.

## Langkah Penyelesaian

Kami diberi sebuah file image, kemudian pada soal, tercantum tentang `metadata`, jadi kami menggunakan tools `exiftool` untuk metadata file image tersebut.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/forensic-01.1-exiftool_image.png" alt="forensic-01.1-exiftool_image">
</p>

Dan kami mendapatkan flagnya.

## Analisis Teknis

Flag atau informasi tersimpan pada informasi file.

## Flag

```
LKSJATENG{hidden_metadata}
```

## Kesimpulan

Penggunaan exiftool untuk metadata.
