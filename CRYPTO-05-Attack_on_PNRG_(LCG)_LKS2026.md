# Write_UP: CRYPTO-05 - Attack on PNRG (LCG)
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Cryptography** |
| **Challange Name** | **CRYPTO-05 - Attack on PNRG (LCG)** |

---

## Deskripsi Soal

Sebuah sistem menggunakan generator bilangan acak yang tidak aman untuk keperluan keamanan.


Tugas:

·	Analisis pola bilangan acak

·	Prediksi output berikutnya

·	Submit flag

## Analisis Masalah

Menggunakan python untuk scripting untuk memprediksi angka yang muncul selanjutnya dalam attack on pnrg lcg attack.

## Langkah Penyelesaian

Pada tantangan ini, kami diberi file `txt`. Kami membacanya dan isinya sebagai berikut:

Kami diberi beberapa angka, dan ada rumus lcg yaitu: 

```
x(n+1) = (a*Xn +c) mod m
``` 
dengan nilai `m = 1000`. Tugasnya adalah untuk menentukan bilangan acak selanjutnya, , namun kami belum mengetahui nilai `a` dan `c`, jadi pada soal ini pertama kami mencari terlebih dahulu nilai a dan c nya. jadi kami membuat script python untuk menentukan outputnya, scriptnya sebagai berikut:

```python
from math import gcd
m = 1000

x1 = 134
x2 = 321
x3 = 500
x4 = 543

d1 = (x2 - x1) % m
d2 = (x3 - x2) % m
d3 = (x4 - x3) % m

g = gcd(d1, m)

d12 = d1 // g
d22 = d2 // g
d32 = d3 // g
m2 = m // g

inv = pow(d1, -1, m)
a = (d2 * inv) % m

c = (x2 - a*x1) % m

x5 = (a * x4 + c) % m
print(x5)
```

Lalu kami menjalankan script tersebut dengan `python 3`.

Muncul output `274`, sesuai format flag, kami menginputkan output ini ke flag, lalu menginputkan flagnya ke soal.

## Analisis Teknis

Scripting python untuk lcg menentukan output acak selanjutnya.

## Flag

```
LKSJATENG{274}
```

## Kesimpulan

Menebak atau menentukan output acak selanjutnya yang merupakan bagian materi lcg dari attack on pnrg, dengan script python.
