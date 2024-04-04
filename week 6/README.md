<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 6<br>SISTEM OPERASI</h1>
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
2. [Percobaan](#Percobaan)
3. [Latihan](#Latihan)
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

## Percobaan
Shortcut:</br>
[Percobaan 5](#Percobaan-5-Menghentikan-dan-memulai-kembali-job)</br>
[Percobaan 6](#Percobaan-6-Percobaan-dengan-Penjadwalan-Prioritas)</br>

### Percobaan 5-Menghentikan dan memulai kembali job
1. Cara lain meletakkan job pada background dengan memulai job secara normal (pada foreground), stop job dan memulai lagi pada background</br>
```$ yes > /dev/null``` </br>
Hentikan sementara job (suspend), bukan menghentikannya (terminate), tetapi menghentikan sementara job sampai di restart. Untuk menghentikan sementara job gunakan Ctrl-Z.</br>

2. Untuk restart job pada foreground , gunakan perintah ```fg```.</br>
```$ fg``` </br>

3. Shell akan menampilkan nama perintah yang diletakkan di foreground. Stop job lagi dengan Ctrl-Z. Kemudian gunakan perintah bg untuk meletakkan job pada background.</br>
```$ bg``` </br>
Job tidak bisa dihentikan dengan Ctrl-Z karena job berada pada background. Untuk menghentikannya, letakkan job pada foreground dengan ```fg``` dan kemudian hentikan sementara dengan Ctrl-Z.</br>
```$ fg``` </br>

4. Job pada background dapat digunakan untuk menampilkan teks pada terminal, dimana dapat diabaikan jika mencoba mengerjakan job lain.</br>
```$ yes &``` </br>
Untuk menghentikannya tidak dapat menggunakan Ctrl-C. Job harus dipindah ke foreground, baru dihentikan dengan cara tekan ```fg``` dan tekan Enter, kemudian dilanjutkan dengan Ctrl-Z untuk menghentikan sementara.</br>

5. Apabila ingin menjalankan banyak job dalam satu waktu, letakkan job pada foreground atau background dengan memberikan job ID
```$ fg %2``` atau ```$ %2```
```$ bg %2```

6. tekan fg dan tekan Enter, kemudian dilanjutkan dengan Ctrl-Z untuk menghentikan sementara.

7. Lihat job dengan perintah ps -fae dan tekan Enter. Kemudian hentikan proses dengan perintah kill.
```$ ps -fae```
```$ kill -9 <NomorPID>```

8. Logout dan tekan Alt+F7 untuk kembali ke mode grafis

</br>Hasil Percobaan:</br>
[Percobaan Alfani](#Marieta-Nona-Alfani-5)</br>
[Percobaan Ale](#Ale-Perdana-Putra-Darmawan-5)</br>
[Percobaan Kanisius](#Kanisius-Keru-Okok-Dinggon-5)</br>
[Kembali ke Percobaan](#Percobaan)</br>

#### Marieta Nona Alfani-5
[Kembali ke percobaan 5](#Percobaan-5-Menghentikan-dan-memulai-kembali-job)</br>
![ss](assets/percobaan/alfani/p5/1.jpg)</br>
![ss](assets/percobaan/alfani/p5/2.jpg)</br>
![ss](assets/percobaan/alfani/p5/3.jpg)</br>
![ss](assets/percobaan/alfani/p5/4.jpg)</br>
![ss](assets/percobaan/alfani/p5/5.jpg)</br>
![ss](assets/percobaan/alfani/p5/6.jpg)</br>
![ss](assets/percobaan/alfani/p5/7.jpg)</br>

#### Ale Perdana Putra Darmawan-5
[Kembali ke percobaan 5](#Percobaan-5-Menghentikan-dan-memulai-kembali-job)</br>
![ss](assets/percobaan/ale/p5/1.png)</br>
![ss](assets/percobaan/ale/p5/2.png)</br>
![ss](assets/percobaan/ale/p5/3.png)</br>
![ss](assets/percobaan/ale/p5/4.png)</br>
![ss](assets/percobaan/ale/p5/5.png)</br>
![ss](assets/percobaan/ale/p5/6.png)</br>
![ss](assets/percobaan/ale/p5/7.png)</br>
![ss](assets/percobaan/ale/p5/8.png)</br>
![ss](assets/percobaan/ale/p5/9.png)</br>
![ss](assets/percobaan/ale/p5/10.png)</br>
![ss](assets/percobaan/ale/p5/11.png)</br>
![ss](assets/percobaan/ale/p5/12.png)</br>
![ss](assets/percobaan/ale/p5/13.png)</br>
![ss](assets/percobaan/ale/p5/14.png)</br>

#### Kanisius Keru Okok Dinggon-5
[Kembali ke percobaan 5](#Percobaan-5-Menghentikan-dan-memulai-kembali-job)</br>

### Percobaan 6-Percobaan dengan Penjadwalan Prioritas
1. Login sebagai root.

2. Buka 3 terminal, tampilkan pada screen yang sama. 

3. Pada setiap terminal, ketik ```PS1 = ” \w:”``` diikuti Enter. ```\w``` menampilkan path pada direktori home.

4. Karena login sebagai root, maka akan ditampilkan ~: pada setiap terminal. Untuk setiap terminal ketik ```pwd``` dan tekan Enter untuk melihat bahwa Anda sedang berada pada direktori /root.

5. Buka terminal lagi (keempat), atur posisi sehingga keempat terminal terlihat pada screen.

6. Pada terminal keempat, ketik ```top``` dan tekan Enter. Maka program top
akan muncul. Ketik ```i```. Top akan menampilkan proses yang aktif. Ketik ```lmt```. Top tidak lagi menampilkan informasi pada bagian atas dari screen. Pada percobaan ini, terminal ke empat sebagai jendela Top.

7. Pada terminal 1, bukalah program executable C++ dengan mengetik program ```yes``` dan tekan Enter. 

8. Ulangi langkah 7 untuk terminal 2.

9. Jendela Top akan menampilkan dua program yes sebagai proses yang berjalan. Nilai %CPU sama pada keduanya. Hal ini berarti kedua proses mengkonsumsi waktu proses yang sama dan berjalan sama cepat. PID dari kedua proses akan berbeda, misalnya 3148 dan 3149. Kemudian gunakan terminal 3 (yang tidak menjalankan primes maupun Jendela Top) dan ketik ```renice 19 <PID terimnal 1>``` (contoh : ```renice 19 3148```) dan diikuti Enter. Hal ini berarti mengganti penjadwalan prioritas dari proses ke 19.

10. Tunggu beberapa saat sampai program top berubah dan terlihat pada jendela Top. Pada kolom STAT memperlihatkan N untuk proses 3148. Hal ini berarti bahwa penjadwalan prioritas untuk proses 3148 lebih besar (lebih lambat) dari 0. Proses 3149 berjalan lebih cepat.

11. Program top juga mempunyai fungsi yang sama dengan program renice. Pilih Jendela Top dan tekan r. Program top terdapat prompt PID to renice: tekan 3148 (ingat bahwa Anda harus mengganti 3148 dengan PID Anda sendiri) dan tekan Enter. Program top memberikan prompt Renice PID 3148 to value: tekan -19 dan tekan Enter.

12. Tunggu beberapa saat sampai top berubah dan lihat nilai %CPU pada kedua proses. Sekarang proses 3148 lebih cepat dari proses 3149. Kolom status menunjukkan < pada proses 3148 yang menunjukkan penjadwalan prioritas lebih rendah (lebih cepat) dari nilai 0.

13. Pilih terminal 3 (yang sedang tidak menjalankan yes atau program top) dan ketik nice –n -10 yes dan tekan Enter. Tunggu beberapa saat agar program top berubah dan akan terlihat proses primes ketiga. Misalnya PID nya 4107. Opsi -10 berada pada kolom NI (penjadwalan prioritas). 

14. Jangan menggunakan mouse dan keyboard selama 10 detik. Program topmenampilkan proses yang aktif selain program yes. Maka akan terlihat proses top terdaftar tetapi %CPU kecil (dibawah 1.0) dan konsisten. Juga terlihat proses berhubungan dengan dekstop grafis seperti X, panel dll.

15. Pindahkan mouse sehingga kursor berubah pada screen dan lihat apa yang terjadi dengan tampilan top. Proses tambahan akan muncul dan nilai %CPU berubah sebagai bagian grafis yang bekerja. Satu alasan adalah bahwa proses 4107 berjalan pada penjadwalan prioritas tinggi. Pilih jendela Top, ketik r. PID to renice : muncul prompt. Ketik 4107 (ubahlah 4107 dengan PID Anda) dan tekan Enter. Renice PID 4107 to value: muncul prompt. Ketik 0 dan tekan Enter. Sekarang pindahkan mouse ke sekeliling screen. Lihat perubahannya.

16. Tutup semua terminal window.

17. Logout dan login kembali sebagai user.

</br>Hasil Percobaan:</br>
[Percobaan Alfani](#Marieta-Nona-Alfani-6)</br>
[Percobaan Ale](#Ale-Perdana-Putra-Darmawan-6)</br>
[Percobaan Kanisius](#Kanisius-Keru-Okok-Dinggon-6)</br>
[Kembali ke Percobaan](#Percobaan)</br>

#### Marieta Nona Alfani-6
[Kembali ke percobaan 6](#Percobaan-6-Percobaan-dengan-Penjadwalan-Prioritas)</br>
![ss](assets/percobaan/alfani/p6/1.jpg)</br>
![ss](assets/percobaan/alfani/p6/2.jpg)</br>
![ss](assets/percobaan/alfani/p6/3.jpg)</br>
![ss](assets/percobaan/alfani/p6/4.jpg)</br>
![ss](assets/percobaan/alfani/p6/5.jpg)</br>
![ss](assets/percobaan/alfani/p6/6.jpg)</br>
![ss](assets/percobaan/alfani/p6/7.jpg)</br>
![ss](assets/percobaan/alfani/p6/8.jpg)</br>
![ss](assets/percobaan/alfani/p6/9.jpg)</br>
![ss](assets/percobaan/alfani/p6/10.jpg)</br>
![ss](assets/percobaan/alfani/p6/11.jpg)</br>
![ss](assets/percobaan/alfani/p6/12.jpg)</br>
![ss](assets/percobaan/alfani/p6/13.jpg)</br>
![ss](assets/percobaan/alfani/p6/14.jpg)</br>

#### Ale Perdana Putra Darmawan-6
[Kembali ke percobaan 6](#Percobaan-6-Percobaan-dengan-Penjadwalan-Prioritas)</br>
![ss](assets/percobaan/ale/p6/1.png)</br>
![ss](assets/percobaan/ale/p6/2.png)</br>
![ss](assets/percobaan/ale/p6/3.png)</br>
![ss](assets/percobaan/ale/p6/4.png)</br>
![ss](assets/percobaan/ale/p6/5.png)</br>
![ss](assets/percobaan/ale/p6/6.png)</br>
![ss](assets/percobaan/ale/p6/7.png)</br>
![ss](assets/percobaan/ale/p6/8.png)</br>
![ss](assets/percobaan/ale/p6/9.png)</br>
![ss](assets/percobaan/ale/p6/10.png)</br>
![ss](assets/percobaan/ale/p6/11.png)</br>
![ss](assets/percobaan/ale/p6/12.png)</br>
![ss](assets/percobaan/ale/p6/13.png)</br>
![ss](assets/percobaan/ale/p6/14.png)</br>
![ss](assets/percobaan/ale/p6/15.png)</br>
![ss](assets/percobaan/ale/p6/16.png)</br>
![ss](assets/percobaan/ale/p6/17.png)</br>
![ss](assets/percobaan/ale/p6/18.png)</br>
![ss](assets/percobaan/ale/p6/19.png)</br>
![ss](assets/percobaan/ale/p6/20.png)</br>
![ss](assets/percobaan/ale/p6/21.png)</br>
![ss](assets/percobaan/ale/p6/22.png)</br>
![ss](assets/percobaan/ale/p6/23.png)</br>
![ss](assets/percobaan/ale/p6/24.png)</br>
![ss](assets/percobaan/ale/p6/25.png)</br>
![ss](assets/percobaan/ale/p6/26.png)</br>

#### Kanisius Keru Okok Dinggon-6
[Kembali ke percobaan 6](#Percobaan-6-Percobaan-dengan-Penjadwalan-Prioritas)</br>


## Latihan
1. Masuk ke tty2 dengan Ctrl+Alt+F2. Ketik ps –au dan tekan Enter. Kemudian perhatikan keluaran sebagai berikut :
Hasil ```ps -au```:</br>
![ss](assets/latihan/l1/au.png)</br>
![ss](assets/latihan/l1/aux1.png)</br>
![ss](assets/latihan/l1/aux2.png)</br>
![ss](assets/latihan/l1/aux3.png)</br>
![ss](assets/latihan/l1/aux4.png)</br>
![ss](assets/latihan/l1/aux5.png)</br>
![ss](assets/latihan/l1/aux6.png)</br>
![ss](assets/latihan/l1/aux7.png)</br>
![ss](assets/latihan/l1/aux8.png)</br>
![ss](assets/latihan/l1/aux9.png)</br>
![ss](assets/latihan/l1/aux10.png)</br>
![ss](assets/latihan/l1/aux11.png)</br>

a. Sebutkan nama-nama proses yang bukan root
- USER=ale; PID=1122; COMMAND=/usr/libexec/gdm-wayland-session /usr/bin/gnome-session
- USER=ale; PID=1126; COMMAND=/usr/libexec/gnome-session-binary
- USER=ale; PID=1901; COMMAND=bash
- USER=ale; PID=2188; COMMAND=ps -au

b. Tulis PID dan COMMAND dari proses yang paling banyak menggunakan CPU time
- PID=1231; COMMAND=/usr/bin/gnome-shell; CPU time=4.3

c. Sebutkan buyut proses dan PID dari proses tersebut
- Dengan menggunakan ```pstree```, buyut proses gnome-shell adalah systemd

d. Sebutkan beberapa proses daemon
- USER=root; PID=475; COMMAND=/usr/libexec/accounts-daemon
- USER=avahi; PID=479; COMMAND=avahi-daemon: running [SysOp-3123500027.local]
- USER=root; PID=493; COMMAND=/usr/libexec/power-profiles-daemon
- USER=ale; PID=1301; COMMAND=usr/libexec/goa-daemon

e. Pada prompt login lakukan hal-hal sebagai berikut :
```$ csh```
```$ who```
```$ bash```
```$ ls```
```$ sh```
```$ ps```
hasil:
![ss](assets/latihan/l1/prompt.png)</br>
Analisa:
- ```$ csh``` : CSH adalah juru bahasa baris perintah yang memungkinkan pengguna untuk menjalankan perintah dan program di komputer. CSH juga menyediakan bahasa pemrograman yang dapat digunakan untuk membuat skrip shell.
- ```$ who``` : Berfungsi untuk melihat user aktif yang login.
- ```$ bash``` : shell default untuk sebagian besar distribusi Unix dan Linux dan banyak digunakan oleh pemrogram dan administrator sistem.
- ```$ ls``` : Berfungsi untuk melihat nama file/direktori secara lengkap.
- ```$ sh``` : Bourne Shell atau shell (command interpreter) default dari unix.
- ```$ ps``` : Berufungsi untuk menampilkan kondisi proses yang ada.

f. Sebutkan PID yang paling besar dan kemudian buat urut-urutan proses sampai ke PPID = 1. 
- Untuk PID yang paling besar adalah 2382.
- Berikut urutan proses terbesar ke terkecil (PPID = 1)
![ss](assets/latihan/l1/ppid1.png)</br>
![ss](assets/latihan/l1/ppid2.png)</br>
![ss](assets/latihan/l1/ppid3.png)</br>
![ss](assets/latihan/l1/ppid4.png)</br>
![ss](assets/latihan/l1/ppid5.png)</br>
![ss](assets/latihan/l1/ppid6.png)</br>
![ss](assets/latihan/l1/ppid7.png)</br>

2. Cobalah format tampilan ps dengan opsi berikut dan perhatikan hasil tampilannya :</br>
· ```-f``` daftar penuh</br>
Analisa: Menampilkan UID, PID, PPID, C, STIME, TTY, TIME, dan CMD</br>
· ```-j``` format job</br>
Analisa: Menampilkan PID, PGID, SID, TTY, TPGID, STAT, UID, TIME, dan COMMAND</br>
· ```j```format job control</br>
Analisa: Menampilkan PPID, PID, PGID, SID, TTY, TPGID, STAT, UID, TIME, dan COMMAND</br>
· ```l``` daftar memanjang</br>
Analisa: Menampilkan F, UID, PPID, PRI, NI, VSZ, RSS, WCHAN, STAT, TTY, TIME, dan COMMAND</br>
· ```s``` format sinyal</br>
Analisa: Menampilkan UID, PID, PENDING, BLOCKED, IGNORED, CAUGHT, STAT, TTY, TIME, dan COMMAND</br>
· ```v``` format virtual memory</br>
Analisa: Menampilkan PID, TTY, STAT, TIME, MAJFL, TRS, DRS, RSS, %MEM, dan COMMAND</br>
· ```X``` format register i386</br>
Analisa: Menampilkan PID, STACKP, ESP, EIP, TMOUT, ALARM, STAT, TTY, TIME, dan COMMAND</br>
Hasil:</br>
![ss](assets/latihan/l2/1.png)</br>
![ss](assets/latihan/l2/2.png)</br>

3. Lakukan urutan pekerjaan berikut :</br>
a. Gunakan perintah find ke seluruh direktory pada sistem, belokkan output sehingga daftar direktori dialihkan ke file directories.txt dan daftar pesan error dialihkan ke file errors.txt</br>
![ss](assets/latihan/l3/1a.png)</br>
![ss](assets/latihan/l3/1b.png)</br>
![ss](assets/latihan/l3/1c.png)</br>

b. Gunakan perintah sleep 5. Apa yang terjadi dengan perintah ini ?</br>
![ss](assets/latihan/l3/2a.png)</br>
![ss](assets/latihan/l3/2b.png)</br>
![ss](assets/latihan/l3/2c.png)</br>
Analisa: Saat menjalankan perintah sleep 5, terminal akan berada dalam keadaan berhenti selama 5 detik. saat menjalankan perintah lain, maka perintah yang dijalankan akan dijalankan saat perintah sleep selesai berjalan sesuai detik yang telah diberikan.

c. Jalankan perintah pada background menggunakan &</br>
![ss](assets/latihan/l3/3.png)</br>
Analisa: Saat menjalankan sleep dibackground dan dilihat dalam perintah jobs saat 5 detik pertama, maka perintah akan ditampilkan dengan kondisi running/bernjalan. saat setelah 5 detik telah berjalan, maka perintah sleep akan dalam kondisi done/selesai.

d. Jalankan sleep 15 pada foreground, hentikan sementara dengan Ctrl-Z dan kemudian letakkan pada background dengan bg. Ketikkan jobs. Ketikkan ps. Kembalikan job ke foreground dengan perintah fg. </br>
![ss](assets/latihan/l3/4.png)</br>
Analisa: Saat pertama menjalankan sleep 15 pada foreground dan menghentikannya menggunakan ctrl-z, perintah sleep 15 akan berhenti sementara. saat perintah sleep 15 diletakkan ke background, perintah sleep akan kembali jalan dan dapat dilihat pada perintah jobs yang menunjukkan status running dan muncul dalam perintah ps. dan terakhir perintah sleep diletakkan pada foreground dan akan menghentikan terminal dengan sisa waktu yang ada.

e. Jalankan sleep 15 pada background menggunakan & dan kemudian gunakan perintah kill untuk menghentikan proses diikuti job number.</br>
![ss](assets/latihan/l3/5.png)</br>
Analisa: Setelah menjalankan sleep 15 dalam background menggunakan &, maka akan ditampilkan proses sleep dengan job number disebelah kiri proses. setelah mengetahui job number, saya gunakan perintah kill untuk mematikan perintah sleep 15 yang akan langsung berhenti berjalan.

f. Jalankan sleep 15 pada background menggunakan & dan kemudian gunakan kill untuk menghentikan sementara proses. Gunakan bg untuk melanjutkan menjalankan proses. </br>
![ss](assets/latihan/l3/6.png)</br>
Analisa: Setelah menjalankan perintah sleep 15 dalam background menggunakan &, saya menggunakan perintah kill -STOP %1 untuk menghentikan proses sleep sementara. setelah dicek menggunakan jobs yang menampilkan kondisi proses stopped, saya menjalankannya kembali dibackground menggunakan bg. saat dicek menggunakan jobs, proses yang ditampilkan sudah dalam kondisi done dikarenakan proses sleep telah selesai berjalan selama 15 detik.

g. Jalankan sleep 60 pada background 5 kali dan terminasi semua pada dengan menggunakan perintah killall.</br>
![ss](assets/latihan/l3/7.png)</br>
Analisa: Pertama, menjalankan sleep 60 dalam background menggunakan & lalu ditampilkan semua proses dengan menggunakan perintah jobs yang menunjukkan semua proses sleep sedang berjalan. setelah itu, menjalankan perintah killall sleep untuk menghentikan semua proses sleep yang akan ditampilkan dengan pesan terminated yang menunjukkan bahwa proses sleep sudah dihentikan.

h. Gunakan perintah ps, w dan top untuk menunjukkan semua proses yang
sedang dieksekusi.</br>
- Perintah ps:
![ss](assets/latihan/l3/8a.png)</br>
Analisa: Perintah ps akan menampilkan semua proses yang sedang dijalankan.

- perintah w:
![ss](assets/latihan/l3/8b.png)</br>
Analisa: Perintah w akan menampilkan semua proses yang sedang dijalankan dengan tampilan yang lebih detail dibandingkan perintah ps.

- Perintah top:
![ss](assets/latihan/l3/8c.png)</br>
Analisa: Perintah top akan menampilkan semua proses foreground dan background yang akan ditampilkan secara real-time atau secara lamgsung dengan memperlihatkan semua informasi seperti PID, USER, %CPU, %MEM, TIME, dan COMMAND.

i. Gunakan perintah ps –aeH untuk menampilkan hierarki proses. Carilah init proses. Apakah Anda bisa identifikasi sistem daemon yang penting ? Dapatkan Anda identifikasi shell dan subprose s ?</br>
![ss](assets/latihan/l3/9a.png)</br>
![ss](assets/latihan/l3/9b.png)</br>
![ss](assets/latihan/l3/9c.png)</br>
![ss](assets/latihan/l3/9d.png)</br>
![ss](assets/latihan/l3/9e.png)</br>
![ss](assets/latihan/l3/9f.png)</br>
![ss](assets/latihan/l3/9g.png)</br>
Analisa: Saat menggunakan perintah ps -aeH akan ditampilkan herarki proses. Dalam tampilan ini saya mendapatkan proses init/induk dari semua proses yang diindikasikan dengan pid=1 yang bernama systemd. untuk sistem daemon yang penting yaitu seperti accounts, avahi, dbus, rtkit, goa, dan ibus. untuk mengetahui perbedaan shell dengan subproses yaitu dengan melihat proses yang memiliki awalan proses awalan yang sama tapi diikuti dengan - yang menunjukkan subproses, contohnya seperti shell systemd dengan subproses systemd-journal, systemd-udevd, dan systemd-timesyn.

j. Kombinasikan ps –fae dan grep, apa yang Anda lihat ?</br>
![ss](assets/latihan/l3/10.png)</br>
Analisa: Saat menjalankan ps -fae akan ditampilkan macam macam proses, tapi dengan menggunakan grep yang saya input dengan grep systemd, maka saya akan hanya ditampilkan dengan proses yang memiliki nama systemd dalam tampilan proses ps -fae.

k. Jalankan proses sleep 300 pada background. Log off komputer dan log in kembali. Lihat daftar semua proses yang berjalan. Apa yang terjadi pada proses sleep ?</br>
- Saat menjalankan sleep dan sebelum logout:</br>
![ss](assets/latihan/l3/11a.png)</br>
- Setelah logout dan login kembali:</br>
![ss](assets/latihan/l3/11a.png)</br>
Analisa: setelah menjalankan sleep dan logout dan login kembali, proses sleep telah berhenti yang dapat dibuktikan dengan perintah jobs setelah login kembali.

## Kesimpulan
Proses merupakan program yang sedang dieksekusi di sistem, dan ada tiga tipe utama proses: foreground, batch, dan daemon. Selain itu, proses dapat berkomunikasi dengan proses lainnya melalui pengiriman dan penerimaan sinyal. Shell Linux menyediakan berbagai fasilitas kontrol proses, seperti menghentikan sementara (suspend) dan melanjutkan (resume) proses.

Dengan menggunakan perintah-perintah seperti fg, bg, kill, dan ps, pengguna dapat menghentikan, memulai kembali, dan mengontrol proses dengan lebih efisien. Perintah fg digunakan untuk memindahkan proses dari background ke foreground, sementara bg digunakan untuk memindahkan proses dari foreground ke background. Perintah kill berguna untuk menghentikan proses secara paksa dengan menggunakan nomor PID, sedangkan perintah ps digunakan untuk melihat daftar proses yang sedang berjalan di sistem.

Melalui penggunaan perintah renice, pengguna dapat mengubah prioritas proses yang sedang berjalan, sehingga mengatur seberapa banyak sumber daya sistem yang dialokasikan untuk proses tertentu. Dengan demikian, proses-proses yang lebih penting atau kritis dapat diberikan prioritas yang lebih tinggi untuk memastikan kinerja sistem yang optimal.Selain itu, penggunaan perintah top memberikan pengawasan real-time terhadap aktivitas sistem, termasuk informasi tentang penggunaan CPU, memori, dan proses-proses yang sedang berjalan. Dengan perintah ini, pengguna dapat mengidentifikasi proses-proses yang menggunakan sumber daya sistem secara berlebihan atau memiliki prioritas yang salah.

penggunaan perintah shell seperti find, sleep, kill, dan ps memberikan kemampuan untuk mengelola dan memantau proses dengan efisien di sistem operasi Linux. Dengan memahami penggunaan perintah-perintah ini, pengguna dapat mencari, menghentikan, dan memantau proses-proses dengan cepat dan mudah, meningkatkan efektivitas dalam administrasi sistem.

## Referensi
Sumber 1: https://perbedaan.budisma.net/perbedaan-antara-csh-dan-bash.html#:~:text=Shell%20CSH%20Unix%20dan%20Linux%20dibuat%20pada%20awal,pemrograman%20yang%20dapat%20digunakan%20untuk%20membuat%20skrip%20shell. </br>
Sumber 2: https://unix.stackexchange.com/questions/68611/whats-the-difference-between-ctrl-z-and-kill-stop </br>
Sumber 3: https://id.eyewated.com/cara-menggunakan-perintah-init-di-linux/ </br>
