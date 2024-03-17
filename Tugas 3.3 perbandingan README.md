## Berikut adalah penjelasan singkat dan fungsionalitas dari perintah Debian yang disebutkan:

1. `$ make`: Perintah ini digunakan untuk mengompilasi program dari kode sumber. Make akan mencari file bernama "Makefile" di direktori saat ini dan mengikuti aturan yang ditentukan di dalamnya untuk membangun program.

2. `$ make clean`: Perintah ini digunakan untuk membersihkan file sementara dan objek yang dihasilkan oleh perintah make. Ini berguna untuk membersihkan direktori dari file-file yang tidak diperlukan setelah proses kompilasi selesai.

3. `$ sudo make install`: Perintah ini digunakan untuk menginstal program yang telah dikompilasi ke dalam sistem. Biasanya, ini akan menyalin file biner dan file lain yang diperlukan ke lokasi yang ditentukan, seperti `/usr/local/bin`.

4. `$ sudo make uninstall`: Perintah ini digunakan untuk menghapus program yang telah diinstal menggunakan `make install`. Ini akan menghapus file yang telah disalin ke sistem.

5. `$ iops64 $(nproc)`: Perintah ini digunakan untuk mengukur jumlah operasi input/output per detik (IOPS) pada perangkat blok tertentu. `$(nproc)` digunakan untuk mendapatkan jumlah inti CPU yang tersedia.

6. `$ flops64 $(nproc)`: Perintah ini digunakan untuk mengukur jumlah operasi floating point per detik (FLOPS) pada CPU dengan presisi 64-bit. Seperti sebelumnya, `$(nproc)` digunakan untuk mendapatkan jumlah inti CPU yang tersedia.



## Perbandingan Eksekusi

https://docs.google.com/spreadsheets/d/1CVZH3rk8T0rY-0BirmPdzeeieXzrKRjIVq6fb6Yu5GQ/edit#gid=0

**Analisa hasil percobaan**



## Kesimpulan IOPS dan FLOPS
Singkatnya, IOPS (Input/Output Operations Per Second) mengukur jumlah operasi input/output yang dapat dilakukan oleh sistem dalam satu detik, sementara FLOPS (Floating Point Operations Per Second) mengukur jumlah operasi titik mengambang yang dapat dilakukan oleh sistem dalam satu detik.

IOPS penting untuk mengukur kinerja penyimpanan dan sistem berbasis disk, sedangkan FLOPS adalah ukuran kinerja komputasi numerik, yang terutama relevan dalam komputasi ilmiah dan pemrosesan gambar. Baik IOPS maupun FLOPS adalah indikator kinerja penting dalam evaluasi sistem komputer, dengan nilai yang lebih tinggi menunjukkan kinerja yang lebih baik dalam masing-masing domain tersebut.
