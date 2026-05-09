# Write_UP: BIN-02 - Format String
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Binary Exploitation** |
| **Challange Name** | **BINARY-03 Integer Overflow** |

---

## Deskripsi Soal

Sebuah program mengelola saldo akun.
Program menerima input dari pengguna untuk menambah saldo.


Tugas:

·	Analisis bagaimana program menghitung saldo

·	Temukan input yang menyebabkan perilaku tidak normal

·	Dapatkan flag

## Analisis Masalah

Menggunakan ghidra untuk decompile file executable.

## Langkah Penyelesaian

Kami diberi sebuah file executable dengan format `exe`. 

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/bin-03.1-execute_file.png" alt="bin-03.1-execute_file">
</p>

Karena file tersebut merupakan file executable windows karena formatnya `exe`, kami menggunakan commnad `wine` untuk menjalankan program, setelah di jalankan, terdapat input untuk memasukan jumlah deposit. Namun sebelum itu, kami mengecek sorce codenya menggunakan `ghidra`, dan mencari fungsi `main`, tapi ternyata, pada fungsi main sudah tercantum flag, jadi kami menggunakan flag tersebut untuk menyelesaikan soal.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/bin-03.2-decompile.png" alt="bin-03.2-decompile">
</p>

## Analisis Teknis

–	Informasi terdapat langsung pada source code.

–	Menggunakan ghidra untuk membaca source code.

## Flag

```
LKSJATENG{int_overflow_bug}
```

## Kesimpulan

Penggunaan `ghidra` untuk decompile atau membaca source code sebuah file executeable dan penggunaan `wine` untuk run program windows atau format `.exe`.
