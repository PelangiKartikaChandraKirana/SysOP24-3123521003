1. **Perbedaan pararel concurrent dan pararel-concurrent**
![WhatsApp Image 2024-05-14 at 09 03 30](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/8212e08a-d7dd-4532-86ce-9c168b44ba28)


**Tugas paralel**

>Tugas paralel adalah tugas yang dapat dijalankan secara bersamaan pada inti CPU yang berbeda. Hal ini berarti bahwa setiap tugas memiliki inti CPU sendiri untuk dijalankan, sehingga mereka dapat berjalan secara independen satu sama lain.

**Tugas konkuren**

>Tugas konkuren adalah tugas yang dapat dijalankan secara bergantian pada inti CPU yang sama. Hal ini berarti bahwa tugas-tugas tersebut harus berbagi waktu pada satu inti CPU, sehingga mereka tidak dapat berjalan secara simultan.

**Tugas paralel-konkuren**

>Tugas paralel-konkuren adalah tugas yang dapat dijalankan secara paralel atau konkuren, tergantung pada ketersediaan inti CPU. Jika ada inti CPU yang tersedia, tugas tersebut akan dijalankan secara paralel. Jika tidak ada inti CPU yang tersedia, tugas tersebut akan dijalankan secara konkuren.


**Contoh**

Tugas paralel: Menjalankan dua program yang berbeda pada dua inti CPU yang berbeda.
Tugas konkuren: Menjalankan dua program yang berbeda pada satu inti CPU.
Tugas paralel-konkuren: Menjalankan dua program yang berbeda, di mana satu program dijalankan pada satu inti CPU dan program lainnya dijalankan pada inti CPU lainnya jika tersedia, atau secara konkuren pada inti CPU yang sama jika tidak ada inti CPU yang tersedia.


2. **Dining Philosophers Problem dan Reader Writer Problem: Persamaan dan Perbedaan**
>Dining Philosophers Problem (Diner Problem) dan Reader Writer Problem (RWP) adalah dua masalah klasik dalam ilmu komputer yang membahas tentang sinkronisasi akses ke sumber daya bersama. Meskipun kedua masalah ini memiliki beberapa kesamaan, terdapat perbedaan fundamental dalam cara mereka dimodelkan dan diselesaikan.

**Persamaan:**

>Sumber daya bersama: Baik DPP dan RWP melibatkan sumber daya bersama yang diakses oleh beberapa proses (atau entitas).
>Kebutuhan sinkronisasi: Akses ke sumber daya bersama harus disinkronkan untuk mencegah konflik dan memastikan integritas data.
>Potensi deadlock: Kedua masalah ini dapat menyebabkan deadlock jika tidak diselesaikan dengan tepat.

**Perbedaan:**

>Jenis akses: DPP berfokus pada akses eksklusif ke sumber daya (filosofer hanya boleh makan dengan dua garpu). RWP, di sisi lain, memperbolehkan akses berbagi untuk membaca (beberapa pembaca dapat membaca data secara bersamaan) dan akses eksklusif untuk menulis (hanya satu penulis yang boleh menulis data pada satu waktu).
>Kondisi awal: DPP dimulai dengan semua filsuf dalam keadaan berpikir dan ingin makan. RWP tidak memiliki kondisi awal yang ditentukan, dan pembaca dan penulis dapat memulai akses kapan saja.
>Solusi: Solusi DPP umumnya berfokus pada mencegah deadlock dengan memastikan bahwa tidak ada dua filsuf yang memegang kedua garpu yang sama pada saat yang sama. Solusi RWP berfokus pada pemberian prioritas akses yang tepat antara pembaca dan penulis untuk menghindari konflik dan memastikan integritas data.

**Contoh:**

>DPP: Bayangkan lima filsuf yang duduk di sekitar meja bundar dengan lima mangkuk spageti dan lima pasang garpu. Setiap filsuf hanya dapat memegang dua garpu pada satu waktu, dan mereka harus memiliki dua garpu untuk makan. Solusi DPP perlu memastikan bahwa tidak ada dua filsuf yang duduk bersebelahan dapat memegang kedua garpu mereka secara bersamaan, sehingga mencegah deadlock.
>RWP: Bayangkan database yang diakses oleh pembaca dan penulis. Pembaca hanya dapat membaca data dari database, sedangkan penulis dapat mengubah data. Solusi RWP perlu memastikan bahwa penulis tidak dapat mengakses database saat pembaca sedang membaca, dan bahwa pembaca tidak dapat mengakses database saat penulis sedang menulis data baru.
