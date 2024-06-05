<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 1<br>SISTEM OPERASI</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Ale Perdana Putra Darmawan (3123500027) </strong><br>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

## Daftar Isi
- [Daftar Isi](#daftar-isi)
- [Dasar teori](#dasar-teori)
- [Soal](#soal)
    - [ \> Sebutkan dan jelaskan proses booting !](#--sebutkan-dan-jelaskan-proses-booting-)
    - [ \> Bagaimana cara install Oracle Virtual Box dan Debian dalam Virtual Box ?](#--bagaimana-cara-install-oracle-virtual-box-dan-debian-dalam-virtual-box-)
- [Instalasi Oracle Virtual Box](#instalasi-oracle-virtual-box)
- [Mengkonfigurasi Debian dalam Oracle Virtual Box](#mengkonfigurasi-debian-dalam-oracle-virtual-box)
- [Instalasi Linux Debian dalam Oracle Virtual Box](#instalasi-linux-debian-dalam-oracle-virtual-box)

## Dasar teori
Pengertian Sistem Operasi:</br>
<strong>Sistem Operasi</strong> adalah perangkat lunak pada lapisan pertama yang ditempatkan pada memori komputer pada saat komputer dinyalakan booting. Sedangkan software-software lainnya dijalankan setelah sistem operasi berjalan, dan sistem operasi akan melakukan layanan inti untuk software-software itu.

## Soal
#### <h3> > Sebutkan dan jelaskan proses booting !</h3>
1. Pertama, kita menekan tombol Power komputer. Setelah komputer dihidupkan, keadaan memori masih kosong. Pada saat ini masih belum ada instruksi yang bisa dieksekusi oleh prosesor. Namun pengguna tidak perlu ikut memberi intruksi karena prosesor telah dirancang untuk mencari alamat tertentu di BIOS. Saat inilah prosesor menjalankan BIOS.

2. Kedua, BIOS mulai mengambil alih sebagai sistem operasi sementara komputer, lalu proses akan berlanjut dengan melakukan inspeksi terhadap semua kesalahan (penyebab variasi data) dalam memori, maupun Device-Device yang memang terhubung kepada komputer. Proses inilah yang sering dikenal dengan POST atau Power-On Self Test. Jika terdapat device yang bermasalah, proses tidak akan berlanjut. Tetapi memberi peringatan tentang masalah device tersebut.

3. ketiga, Proses dilanjutkan dengan BIOS mencari kartu grafis yang tertanam pada komputer dan berikutnya sistem BIOS menjalankan kartu grafis BIOS, serta pengecekan BIOS terhadap ROM.

4. Keempat, Setelah BIOS selesai melakukan pengecekan awal, BIOS akan mencari sistem operasi yang sudah diinstall lalu memuatnya pada memori serta segera menjalankannya. Kemudian, BIOS akan menjalankan sistem operasi tersebut. Jika sistem operasi mengalami error atau tidak ditemukan, BIOS akan menampilkan pesan kesalahan atau menu pilihan untuk masuk ke dalam visual BIOS.

5. Saat komputer telah diambil alih oleh sistem operasi, pengguna dapat mulai menjalankan berbagai program-program yang diinginkan.

#### <h3> > Bagaimana cara install Oracle Virtual Box dan Debian dalam Virtual Box ?</h3>

## Instalasi Oracle Virtual Box
1. Masuk ke laman [Oracle Virtual box](https://www.virtualbox.org/wiki/Downloads), lalu unduh sesuai sistem operasi yang anda gunakan.
![Screenshot](Assets/1.png)

2. Masuk ke laman Download sistem operasi [Debian](https://www.debian.org/download) untuk mengunduh sistem operasi Linux Debian.
![Screenshot](Assets//2.png)

3. Buka setup Oracle dan klik Next.</br>
![Screenshot](Assets/3.png)

4. Dalam menu tidak ada yang perlu diubah, klik Next.
![Screenshot](Assets/4.png)

5. Klik Yes.</br>
![Screenshot](Assets/5.png)

6. Klik Install.
![Screenshot](Assets/6.png)

7. Oracle Virtual Box telah di install, klik finish.
![Screenshot](Assets/7.png)

## Mengkonfigurasi Debian dalam Oracle Virtual Box
1. Buka Oracle Virtual Box, lalu klik opsi "New".
![Screenshot](Assets/8.png)

2. Isi nama, pilih letak penyimpanan Virtual Box, masukkan file ISO debian yang telah diunduh, klik "Skip unattended Installation, dan klik Next.
![Screenshot](Assets/9.png)

3. Isi Username dan hostname dan ubah password, untuk domain name tidak perlu diganti, lalu klik Next. 
![Screenshot](Assets/10.png)

4. Tentukan RAM dan jumlah CPU yang diinginkan, lalu klik Next.
![Screenshot](Assets/11.png)

5. Tentukan ukuran storage didalam Virtual Machine, lalu klik Next.
![Screenshot](Assets/12.png)

6. Dalam tampilan ini, anda dapat melihat ulang pilihan yang anda telah pilih sebelumnya, jika sudah sesuai keinginan, pilih Finish.
![Screenshot](Assets/13.png)

## Instalasi Linux Debian dalam Oracle Virtual Box
1. Klik "Start" untuk membuka Virtual Machine.
![Screenshot](Assets/14a.png)

2. Pilih Graphical Install untuk memulai konfigurasi Debian.
![Screenshot](Assets/15.png)

3. Pilih Bahasa, lalu klik continue.
![Screenshot](Assets/16.png)

4. Pilih lokasi, lalu klik continue.
![Screenshot](Assets/17.png)

5. Pilih konfigurasi bahasa Keyboard, lalu klik continue.
![Screenshot](Assets/18.png)

6. Isi Hostname, lalu klik continue.
![Screenshot](Assets/19.png)

7. Untuk nama domain tidak perlu diisi, klik continue.
![Screenshot](Assets/20.png)

8. Isi root password, lalu klik continue.
![Screenshot](Assets/21.png)

9. Isi nama, lalu klik continue.
![Screenshot](Assets/22.png)

10. Isi username, lalu klik continue.
![Screenshot](Assets/23.png)

11. Pilih lokasi jam, lalu klik continue.
![Screenshot](Assets/24.png)

12. Untuk partition disk, pilih manual, lalu klik continue.
![Screenshot](Assets/25.png)

13. Pilih opsi seperti pada gambar dibawah, lalu klik continue.
![Screenshot](Assets/26.png)

14. Pilih "Yes" untuk membuat partition disk baru, lalu klik continue.
![Screenshot](Assets/27.png)

15. Pilih pri/log untuk membuat bagian partition disk, lalu klik continue.
![Screenshot](Assets/28.png)

16. Pilih "create new partition disk" untuk membuat partition disk, lalu klik continue.
![Screenshot](Assets/29.png)

17. Tentukan jumlah penyimpanan partition disk pertama, lalu klik continue.
![Screenshot](Assets/30.png)

18. Pilih "primary" agar menjadikan penyimpanan utama, lalu klik continue.
![Screenshot](Assets/31.png)

19. Pilih "beginning", lalu klik continue.
![Screenshot](Assets/32.png)

20. pilih opsi "done setting up the partition" klik continue.
![Screenshot](Assets/33.png)

21. Setelah membuat partition disk pertama, silahkan membuat partition disk ke dua, tentukan isi penyimpanan yang ukurannya lebih kecil dibandingkan partition disk pertama, lalu klik continue.
![Screenshot](Assets/34.png)

22. Untuk partition disk kedua, pilih opsi logical dan pada mount point pilih Enter manually dan ketik "/storage", lalu klik continue.
![Screenshot](Assets/35.png)

23. Setelah membuat partition disk kedua, silahkan membuat partition disk ke tiga, tentukan isi penyimpanan yang ukurannya lebih kecil dibandingkan partition disk kedua, lalu klik continue.
![Screenshot](Assets/36.png)

24. Untuk partition disk kedua, pilih opsi logical, lalu jadikan "swap area" pada bagian "use as:", lalu klik continue.
![Screenshot](Assets/37.png)

25. Cek ulang seperti gambar dibawah, jika sudah sesuai, klik continue.
![Screenshot](Assets/38.png)

26. Pilih opsi "Yes", lalu klik continue.
![Screenshot](Assets/39.png)

27. Pilih opsi "no", lalu klik continue.
![Screenshot](Assets/40.png)

28. Pilih lokasi terdekat untuk mengunduh package manager, lalu klik continue.
![Screenshot](Assets/41.png)

29. Pilih archive mirror, lalu klik continue.
![Screenshot](Assets/42.png)

30. Pada bagian ini tidak perlu diisi, klik continue
![Screenshot](Assets/43.png)

31. Pilih opsi "Yes", lalu klik continue.
![Screenshot](Assets/44.png)

32. Pilih opsi "/dev/sda", lalu klik continue.
![Screenshot](Assets/45.png)

33. Instalasi dan konfigurasi Debian telah selesai, klik continue dan Virtual machine akan me-reboot. 
![Screenshot](Assets/46.png)

34. Tampilan Linux Debian setelah reboot.
![Screenshot](Assets/47.png)
