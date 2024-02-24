<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 1<br>SISTEM OPERASI</h1>
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
2. [Soal](#soal)

## Dasar teori
Pengertian Sistem Operasi:</br>
<strong>Sistem Operasi</strong> adalah perangkat lunak pada lapisan pertama yang ditempatkan pada memori komputer pada saat komputer dinyalakan booting. Sedangkan software-software lainnya dijalankan setelah sistem operasi berjalan, dan sistem operasi akan melakukan layanan inti untuk software-software itu.

## Soal
#### Sebutkan dan jelaskan proses booting !
1 . <strong>Power ON</strong>
Saat tombol power atau tombol reset dihidupkan, sumber daya listrik akan mengalir ke komputer.
Kemudian, perangkat keras akan menerima daya untuk dinyalakan.

2 . <strong>POST (Power On Selft Test)</strong>
Setelah dinyalakan, komputer akan melakukan Power-On Self-Test atau POST, yang merupakan serangkaian tes perangkat keras untuk memastikan bahwa semuanya berfungsi dengan baik. 
POST akan memeriksa RAM, prosesor, kartu grafis, dan perangkat keras lainnya. 

3 . <strong>Inisialisasi perangkat keras</strong>
Setelah POST selesai, komputer akan menginisialisasi perangkat keras seperti hard drive, keyboard, mouse, dan perangkat lainnya. 
Proses ini melibatkan tahap mengenali perangkat keras, memuat driver yang diperlukan, dan menyiapkan perangkat untuk digunakan.

4 . <strong>Membaca sektor boot</strong>
Selanjutnya, komputer akan mencari sektor boot di hard drive atau perangkat penyimpanan lainnya. 
Sektor boot adalah area khusus yang berisi instruksi awal untuk memuat sistem operasi.

5 . <strong>Memuat Sistem Operasi</strong>
Setelah sektor boot ditemukan, komputer akan memuat sistem operasi ke dalam memori utama (RAM). 
Kemudian, sistem operasi akan mengambil alih kendali dan mulai menjalankan program-program yang diperlukan untuk mengoperasikan komputer.

#### Bagaimana cara install Oracle Virtual Box dan Debian dalam Virtual Box ?

## Instalasi Oracle Virtual Box
1. Masuk ke laman download [Oracle Virtual box](https://www.virtualbox.org/wiki/Downloads), lalu download sesuai sistem operasi yang anda gunakan.
![Screenshot](screenshot/1.png)

2. Masuk ke laman Download sistem operasi [Debian](https://www.debian.org/download) untuk download sistem operasi Linux Debian.
![Screenshot](screenshot/2.png)

3. Buka setup Oracle dan pilih Next.
![Screenshot](screenshot/3.png)

4. Dalam menu tidak ada yang perlu diubah, pilih Next.
![Screenshot](screenshot/4.png)

5. Pilih Yes.
![Screenshot](screenshot/5.png)

6. Pilih Install.
![Screenshot](screenshot/6.png)

7. Oracle Virtual Box telah di install, pilih finish.
![Screenshot](screenshot/7.png)

## Instalasi Linux Debian dalam Oracle Virtual Box
1. Buka Oracle Virtual Box, lalu tekan opsi "New".
![Screenshot](screenshot/8.png)

2. Isi nama, pilih letak penyimpanan Virtual Box, masukkan file ISO debian yang telah diunduh, klik "Skip unattended Installation, dan pilih Next.
![Screenshot](screenshot/9.png)

3. Isi Username dan hostname dan ubah password, untuk domain name tidak perlu diganti, lalu pilih Next. 
![Screenshot](screenshot/10.png)

4. Tentukan RAM dan jumlah CPU yang diinginkan, lalu pilih Next.
![Screenshot](screenshot/11.png)

5. Tentukan ukuran storage didalam Virtual Machine, lalu pilih Next.
![Screenshot](screenshot/12.png)

6. Dalam tampilan ini, anda dapat melihat ulang pilihan yang anda telah pilih sebelumnya, jika sudah sesuai keinginan, pilih Finish.
![Screenshot](screenshot/13.png)

## Mengkonfigurasi Debian dalam Oracle Virtual Box
1. 
![Screenshot](screenshot/14a.png)
