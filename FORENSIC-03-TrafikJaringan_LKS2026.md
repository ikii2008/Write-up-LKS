# Write_UP: FORENSIC-03 - Trafik Jaringan
### LKS Cybersecurity Kabupaten Cilacap - 2026

---

| Info | Detail |
|------|--------|
| **Team** | **CTFdiary** |
| **Affiliation** | **SMK Tamtama 1 Sidareja** |
| **Category** | **Forensic** |
| **Challange Name** | **FORERNSIC-03 - Trafik Jaringan** |

---

## Deskripsi Soal

Sebuah file hasil capture lalu lintas jaringan ditemukan pada sebuah sistem.


Tugas:

·	Analisis traffic jaringan

·	Temukan informasi sensitif yang dikirimkan

·	Submit flag yang sesuai

## Analisis Masalah

·	Menggunakan wireshark untuk analisis jaringan

·	Memfilter trafik untuk mempermudah dalam analisis

## Langkah Penyelesaian

Pada soal ini, kami diberi sebuah file `pcap`.

Kami menggunakan `wireshark` untuk analisis trafik `pcap` tersebut. Pada soal tercantum bahwa kami harus mencari informasi sensitif yang dikirimkan, jadi kami memfilter analisis untuk mencari `stream http` dengan info `POST`, karena pada soal di cantumkan informasi sensitif yang di kirimkan.

Kami mencoba mengecek informasi pada stream tersebut dengan klik kanan, lalu menu `follow`, dan pilih `follow http stream`.

Disini terdapat informasi yang sangat sensitif, yaitu username dan password, pada soal terdapat format flag yaitu `LKSJATENG{user_pass}`, jadi kami mengedit format tersebut dan mencantumkan informasi yang kami dapat pada format flag menjadi `LKSJATENG{Iwan_123456}`.

## Analisis Teknis

Menggunakan wireshark untuk analisis histori trafik jaringan yang terjadi pada lingkungan jaringan, memfilter pencarian, dan menyesuaikan informasi yang didapat dengan format flag yang diketahui.

## Flag

```
LKSJATENG{Iwan_123456}
```

## Kesimpulan

Histori trafik jaringan dapat dibaca menggunakan wireshark, filterisasi dapat mempermudah proses analisis.
