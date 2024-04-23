<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 8<br>SISTEM OPERASI</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Marieta Nona Alfani (312350026) </strong><br>
    <strong>Ale Perdana Putra Darmawan (3123500027) </strong><br>
    <strong>Kanisius Keru Okok Dinggon(3123500028)</strong>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

## Daftar Isi
1. [Dasar Teori](#Dasar-teori)
2. [Bash - Variabel](#Bash-Variabel)
3. [Kesimpulan](#Kesimpulan)
4. [Referensi](#Referensi)

## Dasar Teori
- Shell
adalah penerjemah baris perintah, Ini adalah aplikasi untuk memberikan perintah ke berbagai sistem operasi seperti Linux, Unix, dan Mac.

- Bash
adalah versi shell yang disempurnakan, lapisan antara panggilan fungsi pengguna dan sistem operasi. 

Pengguna mengetikkan perintah melalui baris perintah atau kumpulan perintah yang juga disebut skrip. 

<h3>Persyaratan</h3>

Untuk mengikuti kursus ini, Anda harus memiliki pemahaman dasar tentang bahasa komputer, dan hal-hal berikut diperlukan:
- Sistem operasi rasa Linux
- Pengetahuan dasar tentang bahasa pemrograman apa pun 

<h3>Apa itu Bash?</h3>

Bash, kependekan dari Bourne Again Shell, adalah penerjemah shell baris perintah dan bahasa skrip sumber terbuka. Ini menafsirkan perintah yang dimasukkan pengguna, baik secara interaktif atau dari file skrip. 

Ini berfungsi sebagai antarmuka untuk memanggil perintah, memungkinkan panggilan fungsi sistem.

Ada dua jenis mode bash:
- Mode interaktif: Juga disebut penerjemah perintah, memungkinkan eksekusi perintah di terminal. Ini mengeksekusi perintah secara berurutan jika ada beberapa perintah.
- Mode non-interaktif: Ini merujuk pada skrip, memungkinkan Anda menulis sintaksis Bash yang berisi rangkaian beberapa perintah untuk eksekusi skrip.

<h3>Apa perbedaan antara Bash dan shell</h3>
Shell, alias Bourne Shell, adalah penerjemah baris perintah untuk OS Unix dan Linux. Bash, alias Bourne Again Shell, adalah versi yang disempurnakan.

<h3>Untuk apa skrip bash digunakan?</h3>

Skrip Bash memiliki banyak kasus penggunaan, termasuk:
- Menulis skrip untuk mengotomatiskan tugas pemrograman.
- Menyinkronkan tugas untuk menyalin file.
- Menjalankan tugas cron untuk penjadwalan.

<h3>Bagaimana cara menulis kode di bash?</h3>

Untuk menulis kode dalam skrip Bash, ikuti langkah-langkah berikut:
- Di terminal, buat file menggunakan ```vi test.sh```.
- Menambahkan ```#!/bin/bash``` di bagian atas file.
- Tambahkan beberapa cuplikan kode shell.
- Simpan file shell dengan ```.sh``` ekstensi.
- Jalankan skrip shell menggunakan ```./test.sh``` perintah di terminal.

<h3>Apakah Bash merupakan bahasa koding?</h3>
Bash menjalankan perintah dari terminal atau file. Ini adalah bahasa pemrograman yang beroperasi pada sistem operasi kernel Unix/Linux, berisi semua fitur untuk menulis kode lengkap.

Bash adalah tipe shell khusus yang menerima masukan dari perintah, menjalankan kode, dan memproses masukan, serta mengembalikan hasilnya. 

<h3>Jenis Shell</h3>
Ada berbagai jenis shell di OS Unix.

| Tipe Shell | Alias | Baris pertama |
|---|---|---|
| SH | Bourne Shell |	#!/bin/sh |
| Bash | Bourne Again Shell | #!/bin/bash |
| cshell | C shell | #!/bin/csh | 
| tcsh | TENEX C shell | #!/bin/tcsh |
| ksh | Korn shell | #!/bin/ksh |

<h3>Perbedaan antara Command Line dan Script di bash</h3>

Mari kita lihat perbedaan antara baris perintah dan skrip
Opsi baris perintah
- Baris perintah memiliki prompt yang menerima masukan dari pengguna.
- Perintah tidak disimpan ke file.
- Ini hanya mendukung satu perintah pada satu waktu. 

File skrip
- Mendukung banyak perintah dalam satu file.
- Prompt masih dapat ditulis dalam file skrip.
- Hanya satu baris dalam sebuah file yang dijalankan secara berurutan.

## Bash - Variabel

## Kesimpulan


## Referensi
