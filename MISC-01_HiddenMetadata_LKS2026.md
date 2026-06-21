# Write_UP: MISC-01 Hidden Metadata
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Miscellaneous** |
| **Challange Name** | **Misc-01 Hidden Metadata** |

---

## Deskripsi Soal

Sebuah foto ditemukan di internet.

## Analisis Masalah

·	Analisis metadata file

·	Temukan informasi tersembunyi

·	Dapatkan flag

·	Menggunakan `exiftool`

## Langkah Penyelesaian

Pada soal ini, kami diberi file `image`, kami mencoba menggunakan `exiftool` untuk metadata sesuai pada soal yang menyebutkan metadata.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/misc-01.1-metadata.png" alt="misc-01.1-metadata">
</p>

Kami mendapatkan flagnya.

## Analisis Teknis

Celah pada informasi metadata dari file image.

## Flag

```
LKSJATENG{metadata_flags}
```

## Kesimpulan

Informasi dapat disembunyikan pada  file image.

---

*Write-up oleh: Wiki · LKS Cyber Security Kab. Cilacap 2026*
