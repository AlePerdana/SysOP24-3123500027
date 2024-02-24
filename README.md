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
1. Masuk ke laman [Oracle Virtual box](https://www.virtualbox.org/wiki/Downloads), lalu unduh sesuai sistem operasi yang anda gunakan.
![Screenshot](screenshot/1.png)

2. Masuk ke laman Download sistem operasi [Debian](https://www.debian.org/download) untuk mengunduh sistem operasi Linux Debian.
![Screenshot](screenshot/2.png)

3. Buka setup Oracle dan klik Next.
![Screenshot](screenshot/3.png)

4. Dalam menu tidak ada yang perlu diubah, klik Next.
![Screenshot](screenshot/4.png)

5. Klik Yes.
![Screenshot](screenshot/5.png)

6. Klik Install.
![Screenshot](screenshot/6.png)

7. Oracle Virtual Box telah di install, klik finish.
![Screenshot](screenshot/7.png)

## Instalasi Linux Debian dalam Oracle Virtual Box
1. Buka Oracle Virtual Box, lalu klik opsi "New".
![Screenshot](screenshot/8.png)

2. Isi nama, pilih letak penyimpanan Virtual Box, masukkan file ISO debian yang telah diunduh, klik "Skip unattended Installation, dan klik Next.
![Screenshot](screenshot/9.png)

3. Isi Username dan hostname dan ubah password, untuk domain name tidak perlu diganti, lalu klik Next. 
![Screenshot](screenshot/10.png)

4. Tentukan RAM dan jumlah CPU yang diinginkan, lalu klik Next.
![Screenshot](screenshot/11.png)

5. Tentukan ukuran storage didalam Virtual Machine, lalu klik Next.
![Screenshot](screenshot/12.png)

6. Dalam tampilan ini, anda dapat melihat ulang pilihan yang anda telah pilih sebelumnya, jika sudah sesuai keinginan, pilih Finish.
![Screenshot](screenshot/13.png)

## Mengkonfigurasi Debian dalam Oracle Virtual Box
1. Klik "Start" untuk membuka Virtual Machine.
![Screenshot](screenshot/14a.png)

2. Pilih Graphical Install untuk memulai konfigurasi Debian.
![Screenshot](screenshot/15.png)

3. Pilih Bahasa, lalu klik continue.
![Screenshot](screenshot/16.png)

4. Pilih lokasi, lalu klik continue.
![Screenshot](screenshot/17.png)

5. Pilih konfigurasi bahasa Keyboard, lalu klik continue.
![Screenshot](screenshot/18.png)

6. Isi Hostname, lalu klik continue.
![Screenshot](screenshot/19.png)

7. Untuk nama domain tidak perlu diisi, klik continue.
![Screenshot](screenshot/20.png)

8. Isi root password, lalu klik continue.
![Screenshot](screenshot/21.png)

9. Isi nama, lalu klik continue.
![Screenshot](screenshot/22.png)

10. Isi username, lalu klik continue.
![Screenshot](screenshot/23.png)

11. Pilih lokasi jam, lalu klik continue.
![Screenshot](screenshot/24.png)

12. Untuk partition disk, pilih manual, lalu klik continue.
![Screenshot](screenshot/25.png)

13. Pilih opsi seperti pada gambar dibawah, lalu klik continue.
![Screenshot](screenshot/26.png)

14. Pilih "Yes" untuk membuat partition disk baru, lalu klik continue.
![Screenshot](screenshot/27.png)

15. Pilih pri/log untuk membuat bagian partition disk, lalu klik continue.
![Screenshot](screenshot/28.png)

16. Pilih "create new partition disk" untuk membuat partition disk, lalu klik continue.
![Screenshot](screenshot/29.png)

17. Tentukan jumlah penyimpanan partition disk pertama, lalu klik continue.
![Screenshot](screenshot/30.png)

18. Pilih "primary" agar menjadikan penyimpanan utama, lalu klik continue.
![Screenshot](screenshot/31.png)

19. Pilih "beginning", lalu klik continue.
![Screenshot](screenshot/32.png)

20. pilih opsi "done setting up the partition" klik continue.
![Screenshot](screenshot/33.png)

21. Setelah membuat partition disk pertama, silahkan membuat partition disk ke dua, tentukan isi penyimpanan yang ukurannya lebih kecil dibandingkan partition disk pertama, lalu klik continue.
![Screenshot](screenshot/34.png)

22. Untuk partition disk kedua, pilih opsi logical dan pada mount point pilih Enter manually dan ketik "/storage", lalu klik continue.
![Screenshot](screenshot/35.png)

23. Setelah membuat partition disk kedua, silahkan membuat partition disk ke tiga, tentukan isi penyimpanan yang ukurannya lebih kecil dibandingkan partition disk kedua, lalu klik continue.
![Screenshot](screenshot/36.png)

24. Untuk partition disk kedua, pilih opsi logical, lalu jadikan "swap area" pada bagian "use as:", lalu klik continue.
![Screenshot](screenshot/37.png)

25. Cek ulang seperti gambar dibawah, jika sudah sesuai, klik continue.
![Screenshot](screenshot/38.png)

26. Pilih opsi "Yes", lalu klik continue.
![Screenshot](screenshot/39.png)

27. Pilih opsi "no", lalu klik continue.
![Screenshot](screenshot/40.png)

28. Pilih lokasi terdekat untuk mengunduh package manager, lalu klik continue.
![Screenshot](screenshot/41.png)

29. Pilih archive mirror, lalu klik continue.
![Screenshot](screenshot/42.png)

30. Pada bagian ini tidak perlu diisi, klik continue
![Screenshot](screenshot/43.png)

31. Pilih opsi "Yes", lalu klik continue.
![Screenshot](screenshot/44.png)

32. Pilih opsi "/dev/sda", lalu klik continue.
![Screenshot](screenshot/45.png)

33. Instalasi dan konfigurasi Debian telah selesai, klik continue dan Virtual machine akan me-reboot. 
![Screenshot](screenshot/46.png)

34. Tampilan Linux Debian setelah reboot.
![Screenshot](screenshot/47.png)
