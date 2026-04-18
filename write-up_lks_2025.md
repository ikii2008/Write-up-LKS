# Write-Up: Investigasi File Rahasia
### LKS Cyber Security Kabupaten Cilacap — 2025

---

| Info | Detail |
|------|--------|
| **Type** | Forensic |
| **Points** | 300 |
| **Deskripsi** | — |
| **Hint** | Cari flags |

---

## Penyelesaian

Pada soal kami diberikan sebuah link yang membawa kami untuk mendownload sebuah file. Setelah didownload, file tersebut merupakan file `disk.img`.

### Langkah 1 — Cek partisi dengan `mmls`

Karena ini merupakan file `disk.img`, kami mencoba menggunakan command `mmls` untuk melihat di mana sistem Linux start.

```bash
mmls disk.img
```

Melalui command ini kami mendapati bahwa **start point ada pada `360448`**.

### Langkah 2 — List isi disk dengan `fls`

Kemudian kami menggunakan command `fls` untuk melihat file di dalamnya.

```bash
fls -o 360448 disk.img
```

Di sini terlihat direktori root ada pada inode **`1995`**.

### Langkah 3 — Masuk ke direktori root

Kami mencoba masuk ke direktori tersebut menggunakan `fls` kembali.

```bash
fls -o 360448 disk.img 1995
```

Kami menemukan sebuah direktori yang mencurigakan: **`my_folder`**.

### Langkah 4 — Cek isi `my_folder`

```bash
fls -o 360448 disk.img <inode_my_folder>
```

Ada **2 buah file** yang keduanya menyertakan teks `"flag"`. Kami mencoba membaca kedua file tersebut satu per satu menggunakan command `icat`.

```bash
icat -o 360448 disk.img <inode_file>
```

Dan **boom**, kami dapat flagnya! 🎉

---

## Flag

```
picoCTF{by73_5urf3r_152f373f}
```

---

*Write-up oleh: Wiki · LKS Cyber Security Kab. Cilacap 2025*
