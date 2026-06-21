# Write-Up: TryHackme, Offensive Security Intro


<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/offensive-security-intro.png" alt="Offensive Security Intro">
</p>

---

## Task 1 Think Like a Hacker!

Pada tugas 1, dijelaskan bahwa room ini akan membawa user ke pelatihan peretasan situs web dengan simulasi di lingkungan yang aman dan legal. Kemudian user ditanya manakah istilah yang digunakan untuk menggambarkan tindakan peretasan untuk menemukan celah kerentanan sistem, yang dimana jawabannya ada offensive security.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task1.png" alt="task1">
</p>

## Task 2 Starting the Lab

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task2.png" alt="task2">
</p>

Pada task 2 ini dijelaskan bahwa ruangan ini menggunakan desktop virtual untuk simulasi, dan pengguna akan diarahkan ke sistem virtual yang dimaksud setelah mengklik menu view site yang tersedia. 

Sebelum lanjut ke sistem virtual, ada deskripsi yang di sediakan untuk situs tersebut, yaitu `Aplikasi perbankan palsu yang disebut FakeBank akan diluncurkan. Ketika  laboratorium dimuat, Anda akan melihat aplikasi perbankan berjalan di  browser Anda`. Dan pada room ini pengguna harus mencari `berapa nomor rekening bank yang ditampilkan dalam aplikasi FakeBank`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task2-site.png" alt="task2-site">
</p>

Setelah pengguna menuju ke situs yang tersedia, pengguna akan di arahkan menuju sistem, yang dimana akan ditampilkan situs dengan nama `FakeBank`. Pada situs ini terdapat beberapa informasi yang tersedia seperti akun, nomor rekening serta transaksi. Sesuai dengan pertanyaan yang diberikan yaitu berapa nomor rekening yang ditampilkan pada FakeBank, nomor rekening yang ditampilkan adalah `8881`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task2-complete.png" alt="task2-complete">
</p>

## Task 3 Find Hidden Pages
---

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3.png" alt="task3">
</p>

Pada tugas 3, user akan mencari kelemahan pada website FakeBank. 

Dijelaskan bahwa: 

Setelah mengklik tombol "Lihat Situs" di atas, user  akan mulai menggunakan terminal. Terminal digunakan untuk berinteraksi dengan perangkat dan alat keamanan siber.

Salah satu kesalahan umum yang dilakukan situs web adalah membiarkan halaman tersembunyi dapat diakses. Kami akan menggunakan terminal untuk menjalankan perintah yang dapat mencari ini.

Di dalam terminal, salin dan tempel perintah dirb di bawah ini dan tunggu hingga selesai. Setiap baris dari keluaran yang dimulai dengan + adalah halaman yang telah ditemukan.

```bash
dirb http://fakebank.thm
````

`Dirb` akan menemukan dua URL. Gunakan informasi ini untuk menjawab pertanyaan di bawah ini.

Pada tugas kali ini, user akan menggunakan tools `dirbuster`.

`Dirbuster` adalah tools yang digunakan untuk brute force agar user dapat menemukan direktori serta file tersembunyi  pada sebuah server website.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3-terminal.png" alt="task3-terminal">
</p>

Pada situs yang disediakan, user akan secara langsung disediakan sebuah terminal untuk menjalankan tools dirbuster. Sesuai dengan deskripsi yang tersedia, kita akan menggunakan command `dirb http://fakebank.thm`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3-dirbuster.png" alt="task3-dirbuster">
</p>

Scan telah selesai, `dirbuster` telah menemukan dua direktori yaitu `/bank-transfer` dan `/images`. Sebelumnya sudah diketahui bahwa ada direktori `images` pada server website dan kita ditanya apa direktori tersembunyi lainnya, jadi kita akan menjawab task 3 dengan `http://fakebank.thm/bank-transfer`.

<p align="center">
  <img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task3-complete.png" alt="task3-complete">
</p>

## Task 4 Attack the Admin Page
---

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4.png" alt="task4">
</p>

Pada tugas 4, user diharuskan menemukan panel admin tersembunyi yang memungkinkan user menambahkan uang ke akunnya. Pada tugas ini, dijelaskan bahwa kita harus menuju ke panel `admin`, pada task 3, kita menemukan direktori yaitu `bank-transfer`, yang dimana pada task 4 ini juga user diharuskan menggunakan direktori tersebut untuk menggali informasi yang dibutuhkan. Jadi disini kita akan menggunakan teknik `URL path exploit` berupa `directory traversal`.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-site.png" alt="task4-site">
</p>

Situs yang disediakan akan mengarahkan kita ke website `FakeBank`, sesuai  dengan instruksi, kita harus menambahkan `/bank-transfer` ke URL.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-bank-transfer.png" alt="task4-bank-transfer">
</p>

Pada page ini, kita diharuskan memasukan nomor akun `8881` dan nominal uang `$2000` atau lebih.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-flag.png" alt="task4-flag">
</p>

Setelah klik deposit, muncul sebuah flag, yang berarti kita mendapatkan jawaban untuk tugas 4 ini.

<p align="center">
	<img src="https://github.com/ikii2008/Write-up-LKS/blob/main/asset/TryHackme/Offensive_Security_Intro/task4-complete.png" alt="task4-complete">
</p>

```
FLAG: BANK-HACKED
```

## Kesimpulan
---

Pada room ini, kita diajarkan beberapa teknik dan teori peretasan website, seperti penggunaan `dirbuster` dan teknik `directory traversal` yang dimana tools dan teknik tersebut dapat saling terkait dan merupakan salah satu celah yang dapat dimanfaatkan oleh attacker untuk mengexploitasi sebuah web.
