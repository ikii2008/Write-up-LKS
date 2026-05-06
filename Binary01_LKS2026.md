# Write_UP: BIN-01 - Buffer Overflow
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Binary Exploitation** |
| **Challange Name** | **BIN-01 - Buffer Overflow** |

---

## Deskripsi Soal

Sebuah program menerima input dari pengguna.
Program tersebut tidak melakukan pengecekan panjang input.
·	Analisis perilaku program
·	Temukan cara untuk memicu kondisi tidak normal
·	Dapatkan flag

## Analisis Masalah

Menggunakan tools online untuk membaca atau decompile file executable

## Langkah Penyelesaian

Pada soal ini, kami diberi sebuah file executable dengan format exe, kami mencoba menggunakan tools online bernama `decompiler exploler`. Saat sudah di decompile, ternyata flag tercantum pada source code. Dilihat tools binary ninja pada web tersebut.

## Analisis Teknis

Informasi terdapat pada source code saat di decompile.

## Flag

```
LKSJATENG{bsc_buffer_overflow}
```

## Kesimpulan

Penggunaan tools online untuk decompile file executeable.
