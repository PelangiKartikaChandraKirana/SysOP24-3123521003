**Arsitektur CPU** mendefinisikan set instruksi yang dapat dijalankan oleh CPU. Set instruksi ini terdiri dari operasi dasar yang dapat dimanipulasi CPU, seperti penjumlahan, pengurangan, perpindahan data, dan operasi logika.
**Arsitektur OS** harus sesuai dengan set instruksi CPU agar dapat dijalankan dengan benar. OS menggunakan instruksi CPU untuk melakukan berbagai fungsinya, seperti manajemen memori, manajemen proses, dan interaksi dengan perangkat keras.


**CISC (Complex Instruction Set Computer)**
Memiliki set instruksi yang kompleks dan multifungsi yang bisa melakukan banian proses dalam sekali jalan, CISC juga memberikan kemudahan programmer dalam menulis program dengan lebihsedikit baris code, secara eksekusi CISC memberikan dampak performa yang lamgat karena komplesitasnya sendiri membuat CPU membutuhkan banyak clock cycle

**RISC (Reduced Instruction Set Computer)**
Memiliki set instruksi sederhana, namun instruksi ini biasanya Tanya melakukan satu fungsi spesifik dalam sustu waktu, arsitektur RISC berfokus pada performa dan efisiensinya, sehingga clock cycle lebih sedikit dan CPU dapat mengeksekusi lebih cepat

**clock cycle adalah  konsep fundamental  dalam memahami  cara kerja CPU. Biasanya 1 clock cycle melakukan fetch-decode-execute dan store.**

## Menjalankan Forking (Fork01 dan Fork02)

***Output Fork1***

![Screen Shot 2024-04-29 at 7 29 55 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/78406ad7-4f8b-487a-8ed6-7b638e97c0a1)

Setelah berhasil mengkloning repositori Git, pengguna mengakses direktori operatingsystem menggunakan perintah cd operatingsystem.

Selanjutnya, pengguna menggunakan editor teks nano untuk mengedit file fork01.cpp.

File fork01.cpp berisi program C++ sederhana yang membuat proses baru.

Pengguna kemudian mengkompilasi program C++ fork01.cpp menggunakan perintah g++ fork01.cpp -o fork01.exe.

Perintah g++ menghasilkan file yang dapat dieksekusi bernama fork01.exe.

Pesan fork01.cpp:1:17: warning: using directive refers to implicitly-defined namespace 'std' menunjukkan bahwa program C++ menggunakan namespace std secara implisit. Hal ini berarti bahwa program harus menggunakan std:: di depan setiap nama fungsi dan variabel dari namespace std.

Pengguna kemudian mengeksekusi program fork01.exe menggunakan perintah ./fork01.exe.

Output dari program menunjukkan informasi tentang proses yang sedang berjalan, termasuk ID proses, ID proses induk, dan ID pengguna.

***Output Fork02***

![Screen Shot 2024-04-29 at 7 32 45 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/c1d6444a-7b2d-4b1a-b7f0-4e42a2a017bb)

Perintah git clone digunakan untuk mengkloning repositori Git dari URL https://github.com/ferryastika ke direktori lokal bernama operatingsystem. Repositori Git berisi kode sumber program dan file-file lain yang terkait dengan program.
Perintah g++ digunakan untuk mengkompilasi program C++ fork02.cpp dan menghasilkan file yang dapat dieksekusi bernama fork02.exe. File yang dapat dieksekusi adalah file yang dapat dijalankan oleh komputer untuk menjalankan program.
Perintah ./fork02.exe digunakan untuk mengeksekusi program yang dapat dieksekusi fork02.exe. Program ini membuat dua proses baru dan menampilkan informasi tentang proses-proses tersebut.
Perintah p digunakan untuk menampilkan informasi tentang proses yang sedang berjalan. Informasi yang ditampilkan meliputi ID proses, ID proses induk, pengguna yang menjalankan proses, dan perintah yang dijalankan oleh proses.

## Menjalankan orphan dan zombie

***Output orphan***

![Screen Shot 2024-04-29 at 8 49 47 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/14490fe5-cbfb-4ad4-87eb-527e5b9e280f)


Program orphan telah dijalankan dengan sukses.
Child process dengan PID 185 telah menjadi orphan process karena parent process 184 langsung exit tanpa menunggunya.
Child process 185 akan terus berjalan sampai selesai atau dihentikan secara manual.

***Output zombie***

![Screen Shot 2024-04-29 at 8 54 02 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/225c4a1f-33e6-4553-8054-21c1dd2bfd02)


Zombie process adalah child process yang telah selesai, tetapi parent process tidak memanggil fungsi wait untuk menunggunya. Sehingga pada output diatas proses berhenti setelah 60 detik.

**Producer-Consumer problem**

Bound buffer merupakan cara/solusi mengatasi producer-consumer problem, dimana memiliki mekanisme sinkronisasi dan mekanisme kontrol akses untuk memastikan data diproduksi dan dikonsumsi secara aman, bound buffer juga meningkatkan efisiensi dan keandalan sebuah sistem.

Producer-consumer problem sendiri merupakan masalah yang terjadi pada sistem operasi berupa sistem yang berbeda atau saat multithreading, solusi yang ada pada bound buffer yang dapat diimplementasikan yaitu semafor atau memastikan producer tidak menambah data ke buffer saat sudah penuh dan mutex yaitu memastikan producer dan consumer tidak mengakses buffer secara bersamaan.
