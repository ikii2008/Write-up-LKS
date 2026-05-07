# Write_UP: BIN-02 - Format String
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Binary Exploitation** |
| **Challange Name** | **BIN-02 - Format String** |

---

## Deskripsi Soal

Sebuah program menerima input dari pengguna dan menampilkannya kembali.
Namun terdapat kesalahan dalam cara program menampilkan input tersebut.


Tugas:

·	Analisis bug pada program

·	Manfaatkan bug tersebut untuk mendapatkan flag

## Analisis Masalah

Pemanfaatan bug format string yang biasanya pada fungsi printf. Menggunakan %p untuk memicu bug format string dan memunculkan alamat.

## Langkah Penyelesaian

Pada soal ini, kami mendapatkan sebuah file executeable `exe`, kami menjalankan file tersebut dengan `wine`. Di program ini, kami diminta untuk memasukan pesan, namun pada soal tercantum tentang format string, yang dimana format string biasanya memiliki bug pada fungsi `printf` yaitu tidak ada filter seperti `%s` pada fungsi printf. Jadi kami memasukan input `%p` untuk memicu bug dan agar program menampilkan alamat program.

Kami mendapatkan alamatnya, kemudian kami menuju `cybercheff` untuk mencoba mendecode teks yang diberikan.

Disini terdapat teks aneh, kami mencoba memfilter teks tersebut dengan menghapus teks yang tidak digunakan dan memasukkan resep `reverse` untuk membalik teks.

Kami mendapatkan teks yang sepertinya merupakan flag, jadi kami menyusun flagnya dan menginputkan flag tersebut pada soal.

## Analisis Teknis

Tidak ada filter atau pengamanan pada fungsi printf yang memicu bug format string.

## Flag

```
LKSJATENG{format_string_bug}
```

## Kesimpulan

Pemanfaatan bug format string pada fungsi printf.
