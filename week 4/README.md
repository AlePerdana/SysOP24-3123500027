<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 4<br>SISTEM OPERASI</h1>
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
1. [Dasar Teori](#Dasar-teori)
2. [Soal](#soal)
3. [Referensi](#Referensi)

## Tugas Pendahuluan:</br>
1. Apa yang dimaksud redirection?</br>
   pembelokan sebuah output ke daerah yang dituju</br>
2. Apa yang dimaksud pipeline?</br>
   mengambil output sebelumnya untuk dijadikan input untuk proses selanjutnya</br>
3. Apa yang dimaksud perintah di bawah ini : echo, cat, more, sort, grep, wc, cut, uniq</br>
   echo menampilkan pesan yang diketik secara langsung, cat menampilkan isi sebuah file, more untuk menampilkan sebuah output tetapi akan dipisah secara per layar, sort untuk mensortir sebuah kalimat/kata mengikuti nomor ascii, grep berfungsi untuk mengambil kata yang telah dideklarasi, wc adalah word count untuk menampilkan jumlah kata, jumlah karakter, dan jumlah baris, Digunakan untuk mengambil kolom tertentu dari baris-baris masukannya, yang ditentukan pada option –c, dan uniq Digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, biasanya digabungkan dalam pipeline dengan sort.</br>
## Dasar teori
#### 1. PROSES I/O:</br>
Sebuah proses memerlukan Input dan Output. Instruksi (command) yang diberikan pada Linux melalui Shell disebut sebagai eksekusi program yang selanjutnya disebut proses. Setiap kali instruksi diberikan, maka Linux kernel akan menciptakan sebuah proses dengan memberikan nomor PID (Process Identity). Proses dalam Linux selalu membutuhkan Input dan menghasilkan suatu Output.
Dalam konteks Linux input/output adalah :
- Keyboard (input)
- Layar (output)
- Files
- Struktur data kernel
- Peralatan I/O lainnya (misalnya Network)

#### 2. FILE DESCRIPTOR
Linux berkomunikasi dengan file melalui file descriptor yang direpresentasikan melalui angka yang dimulai dari 0, 1, 2 dan seterusnya. Tiga buah file descriptor standar yang lalu diciptakan oleh proses adalah :
- 0 = keyboard (standar input)
- 1 = layar (standar output)
- 2 = layar (standar error)
Linux tidak membedakan antara peralatan hardware dan file. Linux memanipulasi peralatan hardware dengan memperlakukannya sama dengan ketika memperlakukan sebuah file.

#### 3.PEMBELOKAN (REDIRECTION)
Pembelokan dilakukan untuk standard input, output dan error, yaitu untuk mengalihkan file descriptor dari 0, 1 dan 2.

#### 4. PIPA (PIPELINE)
Mekanisme pipa digunakan sebagai alat komunikasi antar proses.

#### 5. FILTER
Filter adalah utilitas Linux yang dapat memproses standard input (dari keyboard) dan menampilkan hasilnya pada standard output (layar). Contoh filter adalah cat, sort, grep, pr, head, tail, paste dan lainnya. 
- Perintah ```grep``` Digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan. Pola ini disebut regular expression.
- Perintah ```wc``` Digunakan untuk menghitung jumlah baris, kata dan karakter dari baris-baris masukan yang diberikan kepadanya. Untuk mengetahui berapa baris gunakan option –l, untuk mengetahui berapa kata, gunakan option –w dan untuk mengetahui berapa karakter, gunakan option –c. Jika salah satu option tidak digunakan, maka tampilannya adalah jumlah baris, jumlah kata dan jumlah karakter.
- Perintah ```sort``` Digunakan untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter.
- Perintah ```cut``` Digunakan untuk mengambil kolom tertentu dari baris-baris masukannya, yang ditentukan pada option –c.
- Perintah ```uniq``` Digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, biasanya digabungkan dalam pipeline dengan ```sort```.

## Soal
1. Analisa hasil percobaan 1 sampai dengan 4, untuk setiap perintah jelaskan tampilannya.
Percobaan 1 : File descriptor</br>
- Output ke layar (standar output), input dari system (kernel)
```bash
$ ps
```

- Output ke layar (standar output), input dari keyboard (standard input)
```bash
 $ cat
 hallo, apa khabar
 hallo, apa khabar
 exit dengan ^d
 exit dengan ^d
 [Ctrl-d]
 ```
 
- Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
```bash
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
```

Jawab:


Percobaan 2 : Pembelokan (redirection)</br>
1. Pembelokan standar output
   ```
    $ cat 1> myfile.txt
    Ini adalah teks yang saya simpan ke file myfile.txt
   ```

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
   ```
    $ cat 0< myfile.txt
    $ cat myfile.txt
   ```

3. Pembelokan standar error untuk disimpan di file
   ```
    $ mkdir mydir (Terdapat pesan error)
    $ mkdir mydir 2> myerror.txt
    $ cat myerror.txt
   ```

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
   ```
    $ ls filebaru (Terdapat pesan error)
    $ ls filebaru 2> out.txt
    $ cat out.txt
    $ ls filebaru 2> out.txt 2>&
    $ cat out.txt
   ```

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
   ```
   $ echo “mencoba menulis file” 1> baru
   $ cat filebaru 2> baru 1>&
   $ cat baru
   ```

6. Notasi >> (append)
   ```
   $ echo “kata pertama” > surat
   $ echo “kata kedua” >> surat
   $ echo “kata ketiga” >> surat
   $ cat surat
   $ echo “kata keempat” > surat
   $ cat surat
   ```

7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
   ```
   $ cat <<++
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   ++
   $ cat <<%%%
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   %%%
   ```

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
  ```
  $ cat myfile.txt – surat
  ```

  Jawab:


Percobaan 3 : Pipa (pipeline)</br>
1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
   ```
   $ who
   $ who | sort
   $ who | sort –r
   $ who > tmp
   $ sort tmp
   $ rm tmp
   $ ls –l /etc | more
   $ ls –l /etc | sort | more
   ```

2. Untuk membelokkan standart output ke file, digunakan operator ">"
   ```
   $ echo hello
   $ echo hello > output
   $ cat output
   ```

3. Untuk menambahkan output ke file digunakan operator ">>"
   ```
   $ echo bye >> output
   $ cat output
   ```

4. Untuk membelokkan standart input digunakan operator "<"
   ```
   $ cat < output
   ```

5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
   ```
   $ cat < output > out
   $ cat out
   $ cat < output >> out
   $ cat out
   $ cat < output > output
   $ cat output
   $ cat < out >> out (Proses tidak berhenti)
   [Ctrl-c]
   $ cat out
   ```

Jawab:


Percobaan 4 : Filter
1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
   ```
    $ w –h | grep <user>
    $ grep <user> /etc/passwd
    $ ls /etc | wc
    $ ls /etc | wc –l
    $ cat > kelas1.txt
    Badu
    Zulkifli
    Yulizir
    Yudi
    Ade
    [Ctrl-d]
    $ cat > kelas2.txt
    Budi
    Gama
    Asep
    Muchlis
    [Ctrl-d]
    $ cat kelas1.txt kelas2.txt | sort
    $ cat kelas1.txt kelas2.txt > kelas.txt
    $ cat kelas.txt | sort | uniq
   ```
   
   Jawab:
   

1. Kerjakan latihan diatas dan analisa hasilnya
- Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.</br>
![ss](assets/latihan/soal1/1.png)</br>
![ss](assets/latihan/soal1/2.png)</br></br>

- Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.</br>
![ss](assets/latihan/soal2/1.png)</br>
![ss](assets/latihan/soal2/2.png)</br>
![ss](assets/latihan/soal2/3.png)</br></br>

- Urutkan file baru dengan cara membelokkan standard input.
![ss](assets/latihan/soal3/1.png)</br>
![ss](assets/latihan/soal3/1.png)</br>
![ss](assets/latihan/soal3/1.png)</br></br>

- Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
![ss](assets/latihan/soal4/1.png)</br>
![ss](assets/latihan/soal4/2.png)</br></br>

- Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
![ss](assets/latihan/soal5/1.png)</br></br>

- Urutkan kalimat berikut :
```
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
```
![ss](assets/latihan/soal6/1.png)</br></br>

- Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
![ss](assets/latihan/soal7/1.png)</br>
![ss](assets/latihan/soal7/2.png)</br></br>

- Gunakan perintah di bawah ini dan perhatikan hasilnya.
```
 $ cat > hello.txt
 dog cat
 cat duck
 dog chicken
 chicken duck
 chicken cat
 dog duck
 [Ctrl-d]
 $ cat hello.txt | sort | uniq
 $ cat hello.txt | grep “dog” | grep –v “cat”
```
![ss](assets/latihan/soal8/1.png)</br></br>

3. Berikan kesimpulan dari praktikum ini.</br>
Kesimpulan dari serangkaian percobaan yang telah dilakukan menunjukkan pemahaman yang kuat dalam penggunaan perintah dasar sistem operasi Linux/Unix. Dari penggunaan perintah seperti ls, nano, cat, sort, hingga mkdir dan cd, telah ditunjukkan kemampuan untuk melakukan berbagai tugas seperti melihat daftar direktori, mengedit dan menampilkan isi file, serta mengelola file dan direktori. Penggunaan redirection dengan simbol seperti >, >>, dan 2> juga ditunjukkan dengan baik, memungkinkan pengalihan output dari satu perintah ke perintah lainnya atau ke dalam file. Selain itu, penggunaan pipeline (|) membantu dalam mengalirkan data antar perintah, memungkinkan eksekusi serangkaian perintah secara berurutan untuk memproses data dengan cara yang lebih kompleks.

## Referensi
Sumber 1: https://www.geeksforgeeks.org/introduction-linux-shell-shell-scripting/?ref=shm_ </br>
Sumber 2: https://www.geeksforgeeks.org/how-to-use-here-document-in-bash-programming/
