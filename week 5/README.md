<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 5<br>SISTEM OPERASI</h1>
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
2. [Tugas Pendahuluan](#Tugas-Pendahuluan)
3. [Percobaan](#Percobaan)
4. [Kesimpulan](#Kesimpulan)
5. [Referensi](#Referensi)

## Dasar teori
#### 1. KONSEP PROSES PADA SISTEM OPERASI LINUX
Proses adalah program yang sedang dieksekusi. Setiap kali menggunakan utilitas sistem atau program aplikasi dari shell, satu atau lebih proses "child" akan dibuat oleh shell sesuai perintah yang diberikan. Setiap kali instruksi diberikan pada Linux shell, maka kernel akan menciptakan sebuah proses-id. Proses ini disebut juga dengan terminology Unix sebagai sebuah Job. Proses Id (PID) dimulai dari 0, yaitu proses INIT, kemudian diikuti oleh proses berikutnya (terdaftar pada ```/etc/inittab```).
Beberapa tipe proses :
- Foreground
Proses yang diciptakan oleh pemakai langsung pada terminal (interaktif, dialog)
- Batch
Proses yang dikumpulkan dan dijalankan secara sekuensial (satu persatu). Prose Batch tidak diasosiasikan (berinteraksi) dengan terminal.
- Daemon
Proses yang menunggu permintaan (request) dari proses lainnya dan menjalankan tugas sesuai dengan permintaan tersebut. Bila tidak ada request, maka program ini akan berada dalam kondisi “idle” dan tidak menggunakan waktu hitung CPU. Umumnya nama proses daemon di UNIX berakhiran d, misalnya inetd, named, popd dll

#### 2. SINYAL
Proses dapat mengirim dan menerima sinyal dari dan ke proses lainnya. Proses mengirim sinyal melalui instruksi “kill” dengan format
kill [-nomor sinyal] PID
Nomor sinyal: 1 s/d maksimum nomor sinyal yang didefinisikan system

#### 3. MENGIRIM SINYAL
Mengirim sinyal adalah satu alat komunikasi antar proses, yaitu memberitahukan proses yang sedang berjalan bahwa ada sesuatu yang harus dikendalikan. Berdasarkan sinyal yang dikirim ini maka proses dapat bereaksi dan administrator/programmer dapat menentukan reaksi tersebut. Mengirim sinyal menggunakan instruksi</br>
```kill [-nomor sinyal] PID``` </br>
Sebelum mengirim sinyal PID proses yang akan dikirim harus diketahui terlebih dahulu.

#### 4. MENGONTROL PROSES PADA SHELL
Shell menyediakan fasilitas job control yang memungkinkan mengontrol beberapa job atau proses yang sedang berjalan pada waktu yang sama. Misalnya bila melakukan pengeditan file teks dan ingin melakukan interrupt pengeditan untuk mengerjakan hal lainnya. Bila selesai, dapat kembali (switch) ke editor dan melakukan pengeditan file teks kembali.</br>
Job bekerja pada foreground atau background. Pada foreground hanya diperuntukkan untuk satu job pada satu waktu. Job pada foreground akan mengontrol shell - menerima input dari keyboard dan mengirim output ke layar. Job pada background tidak menerima input dari terminal, biasanya berjalan tanpa memerlukan interaksi.</br>
Job pada foreground kemungkinan dihentikan sementara (suspend), dengan menekan [Ctrl-Z]. Job yang dihentikan sementara dapat dijalankan kembali pada foreground atau background sesuai keperluan dengan menekan "fg" atau "bg". Sebagai catatan, menghentikan job sementara sangat berbeda dengan melakuakan interrupt job (biasanya menggunakan [Ctrl-C]), dimana job yang diinterrup akan dimatikan secara permanen dan tidak dapat dijalankan lagi.

#### 5. MENGONTROL PROSES LAIN
Perintah ps dapat digunakan untuk menunjukkan semua proses yang sedang berjalan pada mesin (bukan hanya proses pada shell saat ini) dengan format:</br>
```ps -fae``` atau ```ps -aux```</br>
Beberapa versi UNIX mempunyai utilitas sistem yang disebut ```top``` yang menyediakan cara interaktif untuk memonitor aktifitas sistem. Statistik secara detail dengan proses yang berjalan ditampilkan dan secara terus-menerus di-refresh. Proses ditampilkan secara terurut dari utilitas CPU. Kunci yang berguna pada ```top``` adalah</br>
s - set update frequency</br>
u – display proses dari satu user</br>
k - kill proses (dengan PID)</br>
q- quit</br>
Utilitas untuk melakukan pengontrolan proses dapat ditemukan pada sistem UNIX adalah perintah ```killall```. Perintah ini akan menghentikan proses sesuai PID atau job number proses.

## Tugas Pendahuluan
1. Apa yang dimaksud dengan proses?</br>
Proses adalah program yang sedang dieksekusi.

2. Apa yang dimaksud perintah untuk menampilkan status proses : ```ps```, ```pstree```.</br>
- ```ps```: Menampilkan mengenai seleksi dalam proses/program yang aktif.
- ```pstree```: Menampilkan proses/program yang berjalan dalam bentuk pohon/bercabang.

3. Sebutkan opsi yang dapat diberikan pada perintah ps</br>
- Opsi ```ps -a```: Menampilkan proses dari semua pengguna. Proses yang terkait dengan terminal dan proses grup tidak ditampilkan.
- Opsi ```ps -u```: Menghasilkan format yang berorientasi pada pengguna dan memberikan informasi terperinci tentang proses yang berjalan.
- Opsi ```ps -x```: Membuat daftar proses tanpa terminal. Opsi ini menampilkan proses yang berjalan saat boot dan berjalan di latar belakang.

4. Apa yang dimaksud dengan sinyal ? Apa perintah untuk mengirim sinyal ?
Pengertian sinyal: Sinyal adalah sebuah data atau informasi yang sudah mengalami beberapa proses sedemikian rupa hingga akhirnya menjadi sebuah informasi matang untuk dikirim ke pihak penerima melalui suatu saluran transmisi.</br>
Perintah untuk mengirim sinyal:</br>
- ```kill```: Perintah ini digunakan untuk mengirim sinyal ke proses dengan menggunakan nomor sinyal.
- ```pkill```:  Ini berguna jika kita ingin menghentikan semua proses yang sesuai dengan nama proses yang sedang berjalan, termasuk proses yang dijalankan oleh skrip bash atau shell script.
- ```killall```: Perintah ini berguna jika kita ingin menghentikan semua proses yang terkait dengan sebuah program secara bersamaan, tanpa harus mengetahui PID masing-masing proses.

6. Apa yang dimaksud dengan proses foreground dan background pada job control ?
- Proses Foreground: Proses foreground adalah proses yang berjalan melalui inisiasi dan dapat dikontrol melalui terminal session, contoh proses foreground ini seperti menerima input dari keyboard dan mengirim output ke layar.
- Proses Background: Proses background adalah proses yang tidak menerima input dari terminal dan biasanya berjalan tanpa memerlukan interaksi langsung dari pengguna.

7. Apa yang dimaksud perintah-perintah penjadwalan prioritas : ```top```, ```nice```, ```renice```.
- top adalah utilitas yang memantau proses yang sedang berjalan di sistem secara real-time serta menampilkan informasi tentang penggunaan CPU, memori, dan prioritas proses.
- nice adalah perintah yang memungkinkan Anda mengatur nilai nice (prioritas) saat menjalankan suatu program.
- Renice adalah perintah yang dapat mengubah prioritas penjadwalan satu atau lebih proses yang berjalan.

## Percobaan
Shortcut:</br>
[Percobaan 1](#Percobaan-1-Status-Proses)</br>
[Percobaan 2](#Percobaan-2-Menampilkan-Hubungan-Proses-Parent-dan-Child)</br>
[Percobaan 3](#Percobaan-3-Menampilkan-Status-Proses-dengan-Berbagai-Format)</br>
[Percobaan 4](#Percobaan-4-Mengontrol-proses-pada-shell)</br>

#### Percobaan 1-Status Proses
1. Pindah ke command line terminal (tty2) dengan menekan Ctrl+Alt+F2 
dan login ke terminal sebagai user.

2. Instruksi ps (process status) digunakan untuk melihat kondisi proses yang 
ada. PID adalah Nomor Identitas Proses, TTY adalah nama terminal dimana 
proses tersebut aktif, STAT berisi S (Sleepin g) dan R (Running), COMMAND 
merupakan instruksi yang digunakan. </br>
```$ ps```

3. Untuk melihat faktor/elemen lainnya, gunakan option –u (user). %CPU 
adalah presentasi CPU time yang digunakan oleh proses tersebut, %MEM 
adalah presentasi system memori yang digunakan proses, SIZE adalah jumlah 
memori yang digunakan, RSS (Real System Storage) adalah jumlah memori 
yang digunakan, START adalah kapan proses tersebut diaktifkan.</br>
```$ ps -u```

4. Mencari proses yang spesifik pemakai. Proses diatas hanya terbatas pada 
proses milik pemakai, dimana pemakai teresbut melakukan login.</br>
```$ ps –u <user>```

5. Mencari proses lainnya gunakan opsi a (all) dan au (all user).</br>
```$ ps –a```</br>
```$ ps –au```

6. Logout dan tekan Alt+F7 untuk kembali ke mode grafis.

</br>Hasil Percobaan:</br>
[Percobaan Alfani](#Marieta-Nona-Alfani-1)</br>
[Percobaan Ale](#Ale-Perdana-Putra-Darmawan-1)</br>
[Percobaan Kanisius](#Kanisius-Keru-Okok-Dinggon-1)</br>
[Kembali ke Percobaan](#Percobaan)</br>

# Marieta Nona Alfani-1</br>
[Kembali ke percobaan 1](#Percobaan-1-Status-Proses)</br>
![ss](assets/percobaan/alfani/p1/1.jpg)</br>
![ss](assets/percobaan/alfani/p1/2.jpg)</br>
![ss](assets/percobaan/alfani/p1/3.jpg)</br>
![ss](assets/percobaan/alfani/p1/4.jpg)</br>

# Ale Perdana Putra Darmawan-1</br>
[Kembali ke percobaan 1](#Percobaan-1-Status-Proses)</br>
![ss](assets/percobaan/ale/p1/1.png)</br>
![ss](assets/percobaan/ale/p1/2.png)</br>
![ss](assets/percobaan/ale/p1/3.png)</br>
![ss](assets/percobaan/ale/p1/4.png)</br>
![ss](assets/percobaan/ale/p1/5.png)</br>
![ss](assets/percobaan/ale/p1/6.png)</br>

# Kanisius Keru Okok Dinggon-1</br>
[Kembali ke percobaan 1](#Percobaan-1-Status-Proses)</br>


#### Percobaan 2-Menampilkan Hubungan Proses Parent dan Child
1. Pindah ke command line terminal (tty2) dengan menekan Ctrl+Alt+F2 dan login ke terminal sebagai user.

2. Ketik ```ps –eH``` dan tekan Enter. Opsi e memilih semua proses dan opsi H 
menghasilkan tampilan proses secara hierarki. Proses child muncul dibawah 
proses parent. Proses child ditandai dengan awalan beberapa spasi.</br>
```$ ps -eH```

3. Ketik ```ps –e f``` dan tekan Enter. Tampilan serupa dengan langkah 2. Opsi –f akan menampilkan status proses dengan karakter grafis (\ dan _)</br>
```$ ps –e f```

4. Ketik ```pstree``` dan tekan Enter. Akan ditampilkan semua proses pada sistem dalam bentuk hirarki parent/child. Proses parent di sebelah kiri proses child. Sebagai contoh proses init sebagai parent (ancestor) dari semua proses pada sistem. Beberapa child dari init mempunyai child. Proses login mempunyai proses bash sebagai child. Proses bash mempunyai proses child startx. Proses startx mempunyai child xinit dan seterusnya.</br>
```$ pstree```

5. Ketik ```pstree | grep mingetty``` dan tekan Enter. Akan menampilkan semua proses mingetty yang berjalan pada system yang berupa console virtual. Selain menampikan semua proses, proses dikelompokkan dalam satu baris dengan suatu angka sebagai jumlah proses yang berjalan.</br>
```$ pstree | grep mingetty```

6. Untuk melihat semua PID untuk proses gunakan opsi –p.</br>
```$ pstree –p```

7. Untuk menampilk an proses dan ancestor yang tercetak tebal gunakan opsi –h.
```$ pstree –h```

</br>Hasil Percobaan:</br>
[Percobaan Alfani](#Marieta-Nona-Alfani-2)</br>
[Percobaan Ale](#Ale-Perdana-Putra-Darmawan-2)</br>
[Percobaan Kanisius](#Kanisius-Keru-Okok-Dinggon-2)</br>
[Kembali ke Percobaan](#Percobaan)</br>

# Marieta Nona Alfani-2</br>
[Kembali ke percobaan 2](#Percobaan-2-Menampilkan-Hubungan-Proses-Parent-dan-Child)</br>
![ss](assets/percobaan/alfani/p2/1.jpg)</br>
![ss](assets/percobaan/alfani/p2/2.jpg)</br>
![ss](assets/percobaan/alfani/p2/3.jpg)</br>
![ss](assets/percobaan/alfani/p2/4.jpg)</br>
![ss](assets/percobaan/alfani/p2/5.jpg)</br>
![ss](assets/percobaan/alfani/p2/6.jpg)</br>
![ss](assets/percobaan/alfani/p2/7.jpg)</br>
![ss](assets/percobaan/alfani/p2/8.jpg)</br>
![ss](assets/percobaan/alfani/p2/9.jpg)</br>
![ss](assets/percobaan/alfani/p2/10.jpg)</br>
![ss](assets/percobaan/alfani/p2/11.jpg)</br>

# Ale Perdana Putra Darmawan-2</br>
[Kembali ke percobaan 2](#Percobaan-2-Menampilkan-Hubungan-Proses-Parent-dan-Child)</br>
![ss](assets/percobaan/ale/p2/1.png)</br>
![ss](assets/percobaan/ale/p2/2.png)</br>
![ss](assets/percobaan/ale/p2/3.png)</br>
![ss](assets/percobaan/ale/p2/4.png)</br>
![ss](assets/percobaan/ale/p2/5.png)</br>
![ss](assets/percobaan/ale/p2/6.png)</br>
![ss](assets/percobaan/ale/p2/7.png)</br>
![ss](assets/percobaan/ale/p2/8.png)</br>

# Kanisius Keru Okok Dinggon-2</br>
[Kembali ke percobaan 2](#Percobaan-2-Menampilkan-Hubungan-Proses-Parent-dan-Child)</br>


#### Percobaan 3-Menampilkan Status Proses dengan Berbagai Format
1. Pindah ke command line terminal (tty2) dengan menekan Ctrl+Alt+F2 dan login ke terminal sebagai user.

2. Ketik ```ps –e | more``` dan tekan Enter. Opsi -e menampilkan semua proses dalam bentuk 4 kolom : PID, TTY, TIME dan CMD.</br>
```$ ps –e | more```</br>
Jika halaman penuh terlihat prompt --More-- di bagian bawah screen, 
tekan q untuk kembali ke prompt perintah.

3. Ketik ```ps ax | more``` dan tekan Enter. Opsi a akan menampilkan semua proses yang dihasilkan terminal (TTY). Opsi x menampilkan semua proses yang tidak dihasilkan terminal. Secara logika opsi ini sama dengan opsi –e. </br>
Terdapa 5 kolom : PID, TTY, STAT, TIME dan COMMAND.</br>
```$ ps ax | more```</br>
Jika halaman penuh terlihat prompt --More-- di bagian bawah screen, 
tekan q untuk kembali ke prompt perintah.

4. Ketik ```ps –e f | more``` dan tekan Enter. Opsi –e f akan menampilkan semua proses dalam format daftar penuh.</br>
```$ ps -e f | more```</br>
Jika halaman penuh terlihat prompt --More-- di bagian bawah screen, 
tekan q untuk kembali ke prompt perintah.

5. Ketik ```ps –eo pid,cmd | more``` dan tekan Enter. Opsi –eo akan menampilkan semua proses dalam format sesuai definisi user yaitu terdiri dari kolom PID dan CMD.</br>
```$ ps –eo pid,cmd | more```</br>
Jika halaman penuh terlihat prompt --More-- di bagian bawah screen, 
tekan q untuk kembali ke prompt perintah.

6. Ketik ```ps –eo pid,ppid,%mem,cmd | more``` dan tekan Enter. Akan menampilkan kolom PID, PPID dan %MEM. PPID adalah proses ID dari proses parent. %MEM menampilkan persentasi memory system yang digunakan proses. Jika proses hanya menggunakan sedikit memory system akan ditampilkan 0.</br>
```$ ps –eo pid,ppid,%mem,cmd | more</br>```</br>

7. Logout dan tekan Alt+F7 untuk kembali ke mode grafis.

</br>Hasil Percobaan:</br>
[Percobaan Alfani](#Marieta-Nona-Alfani-3)</br>
[Percobaan Ale](#Ale-Perdana-Putra-Darmawan-3)</br>
[Percobaan Kanisius](#Kanisius-Keru-Okok-Dinggon-3)</br>
[Kembali ke Percobaan](#Percobaan)</br>

# Marieta Nona Alfani-3</br>
[Kembali ke percobaan 3](#Percobaan-3-Menampilkan-Status-Proses-dengan-Berbagai-Format)</br>
![ss](assets/percobaan/alfani/p3/1.jpg)</br>
![ss](assets/percobaan/alfani/p3/2.jpg)</br>
![ss](assets/percobaan/alfani/p3/3.jpg)</br>
![ss](assets/percobaan/alfani/p3/4.jpg)</br>
![ss](assets/percobaan/alfani/p3/5.jpg)</br>

# Ale Perdana Putra Darmawan-3</br>
[Kembali ke percobaan 3](#Percobaan-3-Menampilkan-Status-Proses-dengan-Berbagai-Format)</br>
![ss](assets/percobaan/ale/p3/1.png)</br>
![ss](assets/percobaan/ale/p3/2.png)</br>
![ss](assets/percobaan/ale/p3/3.png)</br>
![ss](assets/percobaan/ale/p3/4.png)</br>
![ss](assets/percobaan/ale/p3/5.png)</br>
![ss](assets/percobaan/ale/p3/6.png)</br>
![ss](assets/percobaan/ale/p3/7.png)</br>
![ss](assets/percobaan/ale/p3/8.png)</br>
![ss](assets/percobaan/ale/p3/9.png)</br>
![ss](assets/percobaan/ale/p3/10.png)</br>
![ss](assets/percobaan/ale/p3/11.png)</br>
![ss](assets/percobaan/ale/p3/12.png)</br>
![ss](assets/percobaan/ale/p3/13.png)</br>
![ss](assets/percobaan/ale/p3/14.png)</br>
![ss](assets/percobaan/ale/p3/15.png)</br>
![ss](assets/percobaan/ale/p3/16.png)</br>

# Kanisius Keru Okok Dinggon-3</br>
[Kembali ke percobaan 3](#Percobaan-3-Menampilkan-Status-Proses-dengan-Berbagai-Format)</br>


#### Percobaan 4-Mengontrol proses pada shell
1. Pindah ke command line terminal (tty2) dengan menekan Ctrl+Alt+F2 dan login ke terminal sebagai user.

2. Gunakan perintah ```yes``` yang mengirim output y yang tidak pernah berhenti.</br>
```$ yes```</br>
Untuk menghentikannya gunakan Ctrl-C. 

3. Belokkan standart output ke ```/dev/null```</br>
```$ yes > /dev/null```</br>
Untuk menghentikannya gunakan Ctrl-C. 

4. Salah satu cara agar perintah yes tetap dijalankan tetapi shell tetap digunakan  untuk hal yang lain dengan meletakkan proses pada background dengan menambahkan karakter & pada akhir perintah.</br>
```$ yes > /dev/null &```</br>
Angka dalam ”[ ]” merupakan job number diikuti PID.

5. Untuk melihat status proses gunakan perintah ```jobs```.</br>
```$ jobs```

6. Untuk menghentikan job, gunakan perintah kill diikuti job number atau PID proses. Untuk identifikasi job number, diikuti prefix dengan karakter ”%”.</br>
```$ kill %<nomor job>``` contoh : ```kill %1```

7. Lihat status job setelah diterminasi</br>
```$ jobs```

</br>Hasil Percobaan:</br>
[Percobaan Alfani](#Marieta-Nona-Alfani-4)</br>
[Percobaan Ale](#Ale-Perdana-Putra-Darmawan-4)</br>
[Percobaan Kanisius](#Kanisius-Keru-Okok-Dinggon-4)</br>
[Kembali ke Percobaan](#Percobaan)</br>

# Marieta Nona Alfani-4</br>
[Kembali ke percobaan 4](#Percobaan-4-Mengontrol-proses-pada-shell)</br>
![ss](assets/percobaan/alfani/p4/1.jpg)</br>
![ss](assets/percobaan/alfani/p4/2.jpg)</br>

# Ale Perdana Putra Darmawan-4</br>
[Kembali ke percobaan 4](#Percobaan-4-Mengontrol-proses-pada-shell)</br>
![ss](assets/percobaan/ale/p4/1.png)</br>
![ss](assets/percobaan/ale/p4/2.png)</br>
![ss](assets/percobaan/ale/p4/3.png)</br>
![ss](assets/percobaan/ale/p4/4.png)</br>
![ss](assets/percobaan/ale/p4/5.png)</br>
![ss](assets/percobaan/ale/p4/6.png)</br>
![ss](assets/percobaan/ale/p4/7.png)</br>
![ss](assets/percobaan/ale/p4/8.png)</br>

# Kanisius Keru Okok Dinggon-4</br>
[Kembali ke percobaan 4](#Percobaan-4-Mengontrol-proses-pada-shell)</br>

## Kesimpulan
Keseluruhan, pemahaman tentang konsep proses, pengiriman sinyal, penggunaan perintah untuk mengontrol proses pada shell, serta pemahaman tentang perbedaan antara proses latar depan dan latar belakang adalah kunci dalam manajemen efektif dari eksekusi program dan penggunaan sumber daya sistem pada sistem operasi Linux.

## Referensi
Sumber 1: https://www.linuxid.net/31474/tutorial-penggunaan-perintah-ps-di-linux-terminal/ </br>
Sumber 2: https://masdzikry.com/pengertian-sinyal/ </br>
Sumber 3: https://www.linuxsec.org/2016/10/manajemen-proses-di-linux-dengan-ps-kill.html </br>
Sumber 4: https://blog.unnes.ac.id/eltux/use-bashs-job-control-to-manage-foreground-and-background-processes/ </br>
Sumber 5: https://id.linux-console.net/?p=10999#gsc.tab=0 </br>
Sumber 6: https://frameboxxindore.com/id/linux/how-do-i-use-nice-and-renice-command-in-linux.html </br>
