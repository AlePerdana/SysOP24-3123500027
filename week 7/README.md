<div align="center">
  <h1 style="text-align: center;font-weight: bold">PRAKTIKUM 7<br>SISTEM OPERASI</h1>
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
2. [Fork](#Fork-Parent---Child-Process)
3. [Tugas](#Tugas)
4. [Kesimpulan](#Kesimpulan)
5. [Referensi](#Referensi)

## Dasar teori
### Process - Fork - Multithread
Setiap program atau bagian dari program yang sedang dieksekusi oleh CPU disebut dengan proses. Proses dapat berjalan secara foreground atau background. Untuk melihat seluruh proses yang sedang berjalan gunakan perintah ```$ ps -e``` . Bisa juga menggunakan perintah ```$pstree | more``` untuk melihat secara detil proses yang sefan berjalan dengan format tree.

Setiap proses akan memilik PID Process ID). Apabila dibutuhkan Sebuah proses bisa memiliki proses anakan. Dalam hubungan tersebut proses dapat diibaratkan seperti orang tua (parent) dengan anak (child) yang turun temurun.</br>
- Setiap proses memiliki parent dan child.
- Setiap proses memiliki ID (pid) dan parent ID (ppid), kecuali proses init atau systemd.
- ppid dari sebuah proses adalah ID dari parent proses tersebut.

fork digunakan untuk menduplikasi proses. Proses yang baru disebut dengan child proses, sedangkan proses pemanggil disebut dengan parent proses.

Exec adalah function yang digunakan untuk menjalankan program baru dan mengganti program yang sedang berlangsung. exec adalah program family yang memiliki berbagai fungsi variasi, yaitu execvp, execlp, execv, dan lain lain.

wait adalah function yang digunakan untuk mendapatkan informasi ketika child proses berganti state-nya. Pergantian state dapat berupa termination, resume, atau stop.

## Fork Parent - Child Process
- Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)</br>
Jawab:</br>
Konsep fork dalam sistem operasi adalah mekanisme untuk menduplikasi proses yang sedang berjalan. Proses yang dihasilkan disebut sebagai child process, yang merupakan salinan dari parent process. Proses ini memiliki PID (Process ID) yang unik dan PPID (Parent Process ID) yang merujuk pada PID dari parent process. Fork memungkinkan eksekusi program secara paralel dan independen.

Dalam implementasi fork, setiap proses memiliki hubungan hierarki seperti orang tua dan anak. Misalnya, jika sebuah main process melakukan fork, maka akan tercipta parent process dan child process. Child process ini akan memiliki PPID yang sama dengan PID dari parent process. Fungsi ini sering digunakan dalam pemrograman untuk menciptakan proses baru dan memanfaatkan multithreading.

### Contoh implementasi c</br>
#### Source Code:</br>
![ss](assets/peta/3.png)</br>
#### Output:</br>
![ss](assets/peta/1.png)</br>
#### Peta Logika:</br>
![ss](assets/peta/2.png)</br>
Analisa: Saat pembuatan fork, proses yang ditunjuk akan menunjukkan PID unik sendiri sedangkan PPID menunjukkan terminal yang menjalankan proses tersebut. Untuk child process, PID unik yang didapatkan akan hampir sama dengan parent process dan untuk PPID akan menunjuk ke parent process yang telah di fork. Contohnya seperti program diatas yang dijalankan untuk mengambil PID dan PPID, saat menjalankan testc2.2 untuk fork testc, dapat dilihat bahwa PID testc memiliki PID unik dan PPID menunjuk ke terminal bash pada main process. Saat setelah di fork, PID dan PPID testc tetap sama seperti main process dan untuk child process, proses akan memiliki PID unik sendiri yang hampir mendekati parent process sedangkan untuk PPID akan menunjuk ke parent process yaitu testc.

- Akses dan cloning repo : https://github.com/ferryastika/operatingsystem.git
![ss](assets/clone/1.png)</br>

- Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c, fork04.c, fork05.cdan fork06.c.</br>
Jawab:</br>
- fork01.cpp
Program:
```
using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>

int main(void) {
	pid_t mypid;
	uid_t myuid;
	for (int i = 0; i < 3; i++) {
		mypid = getpid();
		cout << "I am process " << mypid << endl;
		cout << "My parent process ID is " << getppid() << endl;
		cout << "The owner of this process has uid " << getuid()
	<< endl;
	sleep(3);
	}
return 0;
}
```
Output:</br>
![ss](assets/fork/f1.png)</br>

1. Deskripsi Kode Program:</br>
    - Fungsi getpid() mengambilkan ID proses saat ini.
    - Fungsi getppid() mengambilkan ID proses induk (parent process).
    - Fungsi getuid() mengambil ID pengguna (user ID) yang memiliki kepemilikan atas proses ini.
    - Fungsi sleep(3) menghentikan proses selama 3 detik.

2. Visualisasi Pohon Proses:</br>
```
Main Process (PID: A)
|
| \
|  Child Process (PID: B) //loop pertama
| \
|  Child Process (PID: B) //loop kedua
 \ 
   Child Process (PID: B) /loop ketiga
```

- fork02.cpp
Program:
```
#include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;

int main(void) {
	pid_t childpid;
	int x = 5;
	childpid = fork();

	while (1) {
		cout << "This is process ID" << getpid() << endl;
		cout << "In this process the value of x becomes " << x << endl;	
		sleep(2);
		x++;
	}
	return 0;
}
```
Output:</br>
![ss](assets/fork/f2.png)



## Tugas


## Kesimpulan


## Referensi

