# Write_UP: CRYPTO-04 - Weak Password Hash
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Cryptography** |
| **Challange Name** | **CRYPTO-04 - Weak Password Hash** |

---

## Deskripsi Soal

Sebuah password administrator disimpan menggunakan metode hashing yang sudah tidak direkomendasikan.


Tugas:

·	Analisis jenis hash

·	Temukan password aslinya

·	Gunakan password tersebut untuk mendapatkan flag

## Analisis Masalah

Menggunakan tools online untuk hash dan reverse.

## Langkah Penyelesaian

Kami diberi sebuah file `zip`, namun pada saat kami mencoba untuk `unzip`, terdapat password yang harus diberikan.

Kami membuka hint, dan mendapatkan sebuah teks yang sepertinya merupakan `hash`.

Jadi kami menggunakan tools online bernama `crackstation` untuk mendecode hash ini.

Setelah di decode, kami mendapatkan teks  `admin1234`, kami menggunakan teks tersebut untuk di inputkan ke file `hash.zip` saat `unzip` tadi.

Setelah di ekstrak, kami mendapatkan file `hash.txt`, dan setelah kami baca menggunakan command `cat`, kami mendapatkan teks yang mirip dengan flag, namun masih acak. Kami menggunakan tools online lagi bernama `cyberchef`, dan memasukan teks tadi dengan resep reverse untuk membalik teks.

## Analisis Teknis

Hashing dengan tools online.

## Flag

```
LKSJATENG{weak_password_hash}
```

## Kesimpulan

Encoding hash dan reverse.
