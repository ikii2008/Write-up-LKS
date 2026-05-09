# Write_UP: WEB-05 - File Konfigurasi Bocor (LFI)
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Web Exploitation** |
| **Challange Name** | **WEB-05 - File Konfigurasi Bocor (LFI)** |

---

## Deskripsi Soal

Portal sekolah menampilkan halaman berdasarkan parameter tertentu.

Aplikasi tidak melakukan validasi terhadap file yang dimuat.


Tugas:

·	    Analisis cara aplikasi memuat halaman

·	    Akses file yang seharusnya tidak ditampilkan

·	    Temukan flag

## Analisis Masalah

Kerentanan pada path web.

## Langkah Penyelesaian

Disini kami di arahkan ke web, lalu kami mencoba untuk mengedit url dan mengganti pagenya ke `flag.txt`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/web05.1-flag.png" alt="web05.1-flag">
</p>

## Analisis Teknis

User atau client dapat mengakses path tertentu.

## Flag

```
LKSJATENG{local_file_inclusion}
```

## Kesimpulan

Url path edit.
