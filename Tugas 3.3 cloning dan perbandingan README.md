
### Melakukan clone https://github.com/ferryastika/flops-iops

![Screen Shot 2024-03-17 at 12 17 05 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/7ecf6238-b9cb-4334-8d98-c1307e1fc3e7)

## Build Binaries
```sh
$ make
```
![Screen Shot 2024-03-17 at 12 19 20 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/565ff56c-b6b5-4744-8db7-7a6ee03d6204)

Perintah ini digunakan untuk mengompilasi program dari kode sumber. Make akan mencari file bernama "Makefile" di direktori saat ini dan mengikuti aturan yang ditentukan di dalamnya untuk membangun program.



## Cleaning Old Build
```sh
$ make clean
```
![Screen Shot 2024-03-17 at 12 19 49 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/e479a535-4095-472a-8d22-03d715d8dd61)

Perintah ini digunakan untuk membersihkan file sementara dan objek yang dihasilkan oleh perintah make. Ini berguna untuk membersihkan direktori dari file-file yang tidak diperlukan setelah proses kompilasi selesai.



## Install Binaries
```sh
$ sudo make install
```
![Screen Shot 2024-03-17 at 12 20 19 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/681dba78-f5dd-4a8f-bd99-69b9a681f859)

Perintah ini digunakan untuk menginstal program yang telah dikompilasi ke dalam sistem.


## Uninstall Binaries
```sh
$ sudo make uninstall
```
![Screen Shot 2024-03-17 at 12 20 53 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/c02617ba-984c-4df3-8493-b040e19e441c)

Perintah ini digunakan untuk menghapus program yang telah diinstal menggunakan make install. Ini akan menghapus file yang telah disalin ke sistem.



## Usage
```sh
$ iops64 $(nproc)
```
![Screen Shot 2024-03-17 at 1 52 13 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/a0c81509-fb3c-47ef-82f0-152926ce5a09)
![Screen Shot 2024-03-17 at 1 52 34 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/e7c7c3b2-ce73-48eb-af9e-5cb7acca8a7f)

Perintah ini digunakan untuk mengukur jumlah operasi input/output per detik (IOPS) pada perangkat blok tertentu. $(nproc) digunakan untuk mendapatkan jumlah inti CPU yang tersedia.



```sh
$ flops64 $(nproc)
```
![Screen Shot 2024-03-17 at 2 41 36 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/e2a32770-219f-46dd-8c78-17b218affd6b)
![Screen Shot 2024-03-17 at 2 42 09 PM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/768b7a74-63b9-4afe-b3c3-3890de34915f)


Perintah ini digunakan untuk mengukur jumlah operasi floating point per detik (FLOPS) pada CPU dengan presisi 64-bit. Seperti sebelumnya, $(nproc) digunakan untuk mendapatkan jumlah inti CPU yang tersedia.


## Perbandingan Eksekusi
![WhatsApp Image 2024-03-18 at 09 04 09](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/ad27574d-72f1-4fa6-b31c-f72b72fa1833)



**Analisa hasil percobaan**
Dari plot perbandingan di atas, dapat dilihat bahwa Alyssa memiliki nilai rata-rata IOPS dan FLOPS yang lebih tinggi dibandingkan dengan Dyzka, Pelangi, dan Feby. Hal ini menunjukkan bahwa PC Alyssa cenderung memiliki performa yang lebih baik dalam menangani operasi input/output (IOPS) dan operasi floating point (FLOPS).

Kesimpulan yang bisa diambil adalah performa komputer dalam hal IOPS dan FLOPS sangat penting tergantung pada kebutuhan aplikasi atau tugas yang dijalankan. Semakin tinggi nilai IOPS dan FLOPS, semakin baik kemampuan komputer tersebut dalam menangani tugas-tugas yang memerlukan operasi input/output dan operasi floating point secara cepat dan efisien.


## Kesimpulan IOPS dan FLOPS
Singkatnya, IOPS (Input/Output Operations Per Second) mengukur jumlah operasi input/output yang dapat dilakukan oleh sistem dalam satu detik, sementara FLOPS (Floating Point Operations Per Second) mengukur jumlah operasi titik mengambang yang dapat dilakukan oleh sistem dalam satu detik.

IOPS penting untuk mengukur kinerja penyimpanan dan sistem berbasis disk, sedangkan FLOPS adalah ukuran kinerja komputasi numerik, yang terutama relevan dalam komputasi ilmiah dan pemrosesan gambar. Baik IOPS maupun FLOPS adalah indikator kinerja penting dalam evaluasi sistem komputer, dengan nilai yang lebih tinggi menunjukkan kinerja yang lebih baik dalam masing-masing domain tersebut.
