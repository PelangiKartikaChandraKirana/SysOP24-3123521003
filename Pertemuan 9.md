**Arsitektur CPU** mendefinisikan set instruksi yang dapat dijalankan oleh CPU. Set instruksi ini terdiri dari operasi dasar yang dapat dimanipulasi CPU, seperti penjumlahan, pengurangan, perpindahan data, dan operasi logika.
**Arsitektur OS** harus sesuai dengan set instruksi CPU agar dapat dijalankan dengan benar. OS menggunakan instruksi CPU untuk melakukan berbagai fungsinya, seperti manajemen memori, manajemen proses, dan interaksi dengan perangkat keras.


**CISC (Complex Instruction Set Computer)**
Memiliki set instruksi yang kompleks dan multifungsi yang bisa melakukan banian proses dalam sekali jalan, CISC juga memberikan kemudahan programmer dalam menulis program dengan lebihsedikit baris code, secara eksekusi CISC memberikan dampak performa yang lamgat karena komplesitasnya sendiri membuat CPU membutuhkan banyak clock cycle

**RISC (Reduced Instruction Set Computer)**
Memiliki set instruksi sederhana, namun instruksi ini biasanya Tanya melakukan satu fungsi spesifik dalam sustu waktu, arsitektur RISC berfokus pada performa dan efisiensinya, sehingga clock cycle lebih sedikit dan CPU dapat mengeksekusi lebih cepat

**clock cycle adalah  konsep fundamental  dalam memahami  cara kerja CPU. Biasanya 1 clock cycle melakukan fetch-decode-execute dan store.**

``` Menjalankan orphan dan zombie ```

***Output orphan***

![Screen Shot 2024-04-25 at 10 04 50 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/a3db16a2-3d36-47b4-911f-efa63ce1438c)

Program orphan telah dijalankan dengan sukses.
Child process dengan PID 185 telah menjadi orphan process karena parent process 184 langsung exit tanpa menunggunya.
Child process 185 akan terus berjalan sampai selesai atau dihentikan secara manual.

***Output zombie***

![Screen Shot 2024-04-25 at 10 14 31 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/0af46891-8fa0-44c6-bdad-f506ab833968)

Zombie process adalah child process yang telah selesai, tetapi parent process tidak memanggil fungsi wait untuk menunggunya. Sehingga pada output diatas proses berhenti setelah 60 detik.

**Producer-Consumer problem**

Bound buffer merupakan cara/solusi mengatasi producer-consumer problem, dimana memiliki mekanisme sinkronisasi dan mekanisme kontrol akses untuk memastikan data diproduksi dan dikonsumsi secara aman, bound buffer juga meningkatkan efisiensi dan keandalan sebuah sistem.

Producer-consumer problem sendiri merupakan masalah yang terjadi pada sistem operasi berupa sistem yang berbeda atau saat multithreading, solusi yang ada pada bound buffer yang dapat diimplementasikan yaitu semafor atau memastikan producer tidak menambah data ke buffer saat sudah penuh dan mutex yaitu memastikan producer dan consumer tidak mengakses buffer secara bersamaan.
