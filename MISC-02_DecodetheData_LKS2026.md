# Write_UP: MISC-02 Decode the Data
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Miscellaneous** |
| **Challange Name** | **Misc-02 Decode the Data** |

---

## Deskripsi Soal

Data berikut tampak terenkripsi.


Tugas:

·	Analisis data

·	Tulis script untuk decode

·	Temukan flag

## Analisis Masalah

Menggunakan `python` untuk decoding `hex`.

## Langkah Penyelesaian

Pada file yang diberikan, terdapat teks encoding yang dari cirinya seperti di encode menggunakan `hex`:

```
4c 4b 53 4a 41 54 45 4e 47 7b 73 63 72 69 70 74 69 6e 67 5f 70 6f 77 65 72 7d
```

Jadi kami menggunakan `python` untuk decoding dan menggunakan script sebagai berikut:

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/misc-02.1-scripting_python.png" alt="misc-02.1-scripting_python">
</p>

## Analisis Teknis

Menambahkan `“0x”` pada tiap kata, yang merupakan format hex, kemudian scripting menggunakan python.

## Flag

```
LKSJATENG{scripting_power}
```

## Kesimpulan

Decoding hex dengan python.

---

*Write-up oleh: Wiki · LKS Cyber Security Kab. Cilacap 2026*
