<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 3<br>SISTEM OPERASI</h1>
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
3. [Referensi](#Referensi)

## Dasar teori
IOPS:</br>
IOPS merupakan singkatan dari Input/Output per Second. Pengertian IOPS adalah pengukuran kinerja untuk Hard Drive (HDD atau SSD) dan jaringan area penyimpanan untuk menunjukkan seberapa cepat suatu perangkat atau media penyimpanan dapat membaca atau menulis data dalam setiap detik.
Sebenarnya ada 3 faktor yang harus diperhatikan untuk kinerja penyimpanan yaitu kecepatan bandwidth, latensi, dan IOPS. Namun, hampir seluruh vendor berfokus pada IOPS dimana memerhatikan seberapa cepat penyimpanan mereka.

FLOPS:</br>
FLOPS adalah singkatan dari istilah dalam bahasa Inggris Floating point Operations Per Second yang merujuk pada satuan untuk jumlah perhitungan yang dapat dilakukan oleh sebuah perangkat komputasi (dalam hal ini adalah komputer) terhadap bilangan pecahan (floating point) tiap satu satuan waktu. FLOPS merupakan satuan pengukuran kecepatan kinerja suatu mikroprosesor biasanya dalam suatu aplikasi ilmiah (scientific application), seperti untuk menghitung/mensimulasikan data pergerakan Bumi secara waktu nyata.

## Soal
1. Jalankan VM Debian anda, lalu lakukan clone https://github.com/ferryastika/flops-iops. Compile dan eksekusi sesuai petunjuk. Sesuiakan jumlah thread dengan jumlah CPU yang ada di VM Debianmu. Catat hasilnya dan jelaskan arti dari hasil ekskusi. Lakukan sebanyak 5 kali. Bandingkan hasilnya anatar temanmu. Buat Plot perbandinnga hasil untuk masing-masing PC di tiap kelompokmu. Analisa hasil percobaan tadi dan beri kesimpulan tentang IOPS dan FLOPS.

Marieta Nona Alfani (312350026)</br>
Monitor:</br>
![ss](assets/monitor/1fani.jpg)</br>

Hasil IOPS:</br>
![ss](assets/iops/1fani.jpg)</br>
![ss](assets/iops/2fani.jpg)</br>
![ss](assets/iops/3fani.jpg)</br>
![ss](assets/iops/4fani.jpg)</br>
![ss](assets/iops/5fani.jpg)</br>
Hasil FLOPS:</br>
![ss](assets/flops/1fani.jpg)</br>
![ss](assets/flops/2fani.jpg)</br>
![ss](assets/flops/3fani.jpg)</br>
![ss](assets/flops/4fani.jpg)</br>
![ss](assets/flops/5fani.jpg)</br>

Ale Perdana Putra Darmawan (3123500027)</br>
Monitor:</br>
![ss](assets/monitor/1ale.png)</br>

Hasil IOPS:</br>
![ss](assets/iops/1ale.png)</br>
![ss](assets/iops/2ale.png)</br>
![ss](assets/iops/3ale.png)</br>
![ss](assets/iops/4ale.png)</br>
![ss](assets/iops/5ale.png)</br>

Hasil FLOPS:</br>
![ss](assets/flops/1ale.png)</br>
![ss](assets/flops/2ale.png)</br>
![ss](assets/flops/3ale.png)</br>
![ss](assets/flops/4ale.png)</br>
![ss](assets/flops/5ale.png)</br>

Kanisius Keru Okok Dinggon(3123500028)</br>
monitor:</br>

2. Apabila Debian VM mu masih belum terdapat packeage gcc, make dan git, lakukan instalasi dan catat setiap langkahnya!

## Referensi
sumber 1: https://www.cekssd.com/pengertian-iops/
sumber 2: https://id.wikipedia.org/wiki/FLOPS
