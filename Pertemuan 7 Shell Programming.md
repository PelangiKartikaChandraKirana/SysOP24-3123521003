## Operasi input output

### Percobaan 1 : File descriptor

1. Output ke layar (standar output), input dari system (kernel)
``` sh
$ ps
```
![Screen Shot 2024-03-18 at 9 50 38 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/1f736dbb-6df4-4a50-9dfd-caba9c03992b)
Analisa : Perintah ps digunakan untuk menampilkan informasi mengenai proses yang sedang aktif di dalam system operasi linux


2. Output ke layar (standar output), input dari keyboard (standard input)
``` sh
 $ cat
 hallo, apa khabar
 hallo, apa khabar
 exit dengan ^d
 exit dengan ^d
 [Ctrl-d]
```
![Screen Shot 2024-03-18 at 9 55 23 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/6c163ef7-b365-4c89-a961-4ece472fca89)
Analisa : Perintah cat digunakan untuk standar input keyboard ke standar output dalam terminal 

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
``` sh
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
```
![Screen Shot 2024-03-18 at 9 56 24 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/38d07d0d-9080-4920-90c5-edfab95e2dc5)
Analisa : Perintah mkdir merupakan perintah untuk membuat direktori, apabila membuat direktori lagi dengan format nama yang sama maka akan muncul pesan bahwa file direktori tidak dapat dibuat atau standar input error


## Percobaan 2 : Pembelokan (redirection)

1. Pembelokan standar output
``` sh
 $ cat 1> myfile.txt
 Ini adalah teks yang saya simpan ke file myfile.txt
```
![Screen Shot 2024-03-18 at 9 59 33 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/28cdc286-31d0-446d-a80e-a8f38ff7c2b7)
Analisa : Perintah cat 1> myfile.txt berfungsi sebagai pembelokan standart output atau yang berfungsi untuk membelokkan standar input kedalam 1 file bernama myfile.txt


2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
``` sh
 $ cat 0< myfile.txt
 $ cat myfile.txt
```
![Screen Shot 2024-03-18 at 10 00 36 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/f48310a2-5f73-4704-9e7a-4a38f36b41cc)
Analisa : Cat 0< myfile.txt berfungsi sebagai pembelokkan standar output yang sebelumnya telah diinputkan pada praktek sebelumnya


3. Pembelokan standar error untuk disimpan di file
``` sh
 $ mkdir mydir (Terdapat pesan error)
 $ mkdir mydir 2> myerror.txt
 $ cat myerror.txt
```
![Screen Shot 2024-03-18 at 10 02 46 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/34cb033e-0436-447d-a04e-237c0f3672ae)
Analisa : Perintah mkdir mydir 2> myerror berjalan ketika dimasukkan perintah tersebut kemudian di enter maka perintah pertama kali dijalankan adalah mkdir mydir yang dilanjut dengan proses penyalinan

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1
``` sh
 $ ls filebaru (Terdapat pesan error)
 $ ls filebaru 2> out.txt
 $ cat out.txt
 $ ls filebaru 2> out.txt 2>&
 $ cat out.txt
```
![Screen Shot 2024-03-18 at 10 24 14 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/6d6cad7f-b2fc-4b48-8064-cc2536a8954a)
Analisa : Perintah ls filebaru 2> out.txt 2>&1 berfungsi untuk menghapus isi file yang tadinya di copykan kedalam file out.txt &1 digunakan untuk langsung mengeluarkan isi dari file out.txt 

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
``` sh
$ echo “mencoba menulis file” 1> baru
$ cat filebaru 2> baru 1>&
$ cat baru
```
![Screen Shot 2024-03-18 at 10 26 04 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/b46dd310-52d5-413c-abe0-1b73ea641ae8)
Analisa : Perintah echo mencoba menulis file 1> baru merupakan proses penyalinan pesan error, penyalinan dari ls filebaru yang tidak da pada direktori tersebut sehingga muncul pesan bahwa file yang dimaksud tidak tersedia


6. Notasi >> (append)
``` sh
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat
$ echo “kata keempat” > surat
$ cat surat
```
![Screen Shot 2024-03-18 at 10 29 12 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/fc21b227-42ac-474a-8f1e-43f52c3f5fe9)
Analisa : Perintah ini berfungsi untuk menambahkan isi dari file tanpa menghapus yang ada di dalamnya.


7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard.
   Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus
   sama dan tanda penutup harus diberikan pada awal baris
``` sh
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
![Screen Shot 2024-03-18 at 10 32 38 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/878732f2-5b53-430f-98f6-439011eb2bcc)
Analisa : Perintah ini digunakan sebagai pembatas input dari keyboard


8. Notasi – (input keyboard) adalah representan input dari keyboard.
   Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2.
   Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
``` sh
$ cat myfile.txt – surat
```
![Screen Shot 2024-03-18 at 10 33 49 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/e497aa9c-cd03-4e79-8065-98a77a2a63ce)
Analisa : 
Perintah ini akan menampilkan isi file step by step atau satu persatu sesuai dengan urutan file yang dimasukkan setelah perintah cat


### Percobaan 3 : Pipa (pipeline)

1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
Pembelokan standar output
``` sh
$ who
$ who | sort
$ who | sort –r
$ who > tmp
$ sort tmp
$ rm tmp
$ ls –l /etc | more
$ ls –l /etc | sort | more
```
![Screen Shot 2024-03-18 at 10 37 50 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/7b282913-7ccd-4766-9cbc-86400b7b80dc)
![Screen Shot 2024-03-18 at 10 39 05 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/9a53988b-eba8-4eb8-9e1d-e417de902885)
Analisa : Perintah diatas adalah perintah yang digunakan untuk mengetahui user yang sedang aktif


2. Untuk membelokkan standart output ke file, digunakan operator ">"
``` sh
$ echo hello
$ echo hello > output
$ cat output
```
![Screen Shot 2024-03-18 at 10 40 42 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/f7070e1d-4e6d-43f6-8d38-4a10742488ca)
Analisa : Menggunakan operator > untuk membelokkan standar output ke dalam file dan menambahkan output ke dalam file tanpa menghapus isi file kita gunakan operator >> untuk membelokkan perintah kita menggunakan <<


3. Untuk menambahkan output ke file digunakan operator ">>"
``` sh
$ echo bye >> output
$ cat output
```
![Screen Shot 2024-03-18 at 10 41 15 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/ba079f36-3ac0-4e69-9f13-6f2ea6335943)
Analisa :Menggunakan operator > untuk membelokkan standar output ke dalam file dan menambahkan output ke dalam file tanpa menghapus isi file kita gunakan operator >> untuk membelokkan perintah kita menggunakan <<

4. Untuk membelokkan standart input digunakan operator "<"
``` sh
$ cat < output
```
![Screen Shot 2024-03-18 at 10 41 36 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/169ec9b9-5620-4e1c-a62e-6272dec68bad)
Analisa : Menggunakan operator > untuk membelokkan standar output ke dalam file dan menambahkan output ke dalam file tanpa menghapus isi file kita gunakan operator >> untuk membelokkan perintah kita menggunakan <<


5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
``` sh
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
![Screen Shot 2024-03-18 at 10 48 14 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/28389291-03c0-4951-b6df-a384939bec56)
Analisa : Perintah cat out membuat layer kita akan penuh dengan kata-kata hello dan out karena kedua kata itu diulang berulang kali ke dalam file out melalui cat <out>> out


### Percobaan 4

1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
``` sh
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
![Screen Shot 2024-03-18 at 10 51 06 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/602f77c6-b8bb-4e2e-a19f-b7e586dd2042)
![Screen Shot 2024-03-18 at 10 52 54 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/64a23b02-30fa-4856-a0e1-a54bf5c03f77)
![Screen Shot 2024-03-18 at 10 54 31 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/16ac4596-9515-466c-9df0-b04e6ba5e579)

Analisa : Perintah diatas menampilkan data nama siswa kelas 1 dan kelas 2 dalam kelas.txt

## Latihan

1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.
![Screen Shot 2024-03-18 at 10 57 17 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/8fcb6734-35e8-4429-a083-8fc2787631f7)
> Analisa : Perintah $ ls -l > file.txt akan menyimpan output dari perintah ls -l ke dalam file bernama file.txt. Perintah kedua (cat file.txt) akan menampilkan isi dari file tersebut ke dalam terminal.

2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
![Screen Shot 2024-03-18 at 10 58 56 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/d54d06f5-4be5-4794-8116-6269c9e3302e)
> Analisa : Perintah pertama (cat /etc/passwd >> file.txt) akan menambahkan isi dari file /etc/passwd ke dalam file file.txt, tanpa menghapus konten yang sudah ada sebelumnya. Perintah kedua (cat file.txt) akan menampilkan isi keseluruhan file file.txt, termasuk tambahan dari file /etc/passwd.

   
3. Urutkan file baru dengan cara membelokkan standard input.
![Screen Shot 2024-03-18 at 10 59 48 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/2a3c3140-dbc6-462e-b4ac-fcc5716c6b20)
> Analisa : Perintah $ sort < file.txt akan mengurutkan baris-baris dalam file file.txt dan menampilkannya di terminal.


4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
![Screen Shot 2024-03-18 at 11 00 24 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/0ba5f868-2d2e-4b28-92f0-6e54140b5b1c)
> Analisa : Akan mengurutkan isi file file.txt dan menyimpan hasilnya dalam file baru bernama baru.urut

5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
![Screen Shot 2024-03-18 at 11 02 15 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/f9c1e7a2-8210-448c-aba2-79316666cce8)
> Analisa : Perintah $ mkdir latihan2 akan membuat direktori bernama "latihan2" di direktori aktif.
Perintah $ mkdir latihan2 2> myerror.txt akan membuat direktori "latihan2", namun jika terjadi kesalahan, pesan kesalahan akan ditangkap dan ditulis ke dalam file "myerror.txt".
Perintah $ cat myerror.txt, dan tidak ada pesan kesalahan yang ditampilkan, maka hal itu berarti tidak ada kesalahan yang terjadi saat membuat direktori "latihan2" kedua kalinya.

6.  Urutkan kalimat berikut :
``` sh
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
```
Dengan menggunakan notasi here document (<@@@ ...@@@)
![Screen Shot 2024-03-18 at 11 03 12 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/7d365994-6455-47f7-a1a9-d5856778de64)
> Analisa : Perintah sort <<@@@ akan membuka sebuah here document, yang memungkinkan untuk menuliskan beberapa baris teks dan menyampaikannya ke perintah sort untuk diurutkan. Kemudian menutup here document dengan menggunakan delimiter yang sama (@@@).


7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
![Screen Shot 2024-03-18 at 11 05 33 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/aee230eb-70de-4e7c-beef-45a507310014)
> Analisa : Perintah pertama (cat baru.urut) akan menampilkan isi dari file baru.urut (jika ada).
Perintah kedua (cat baru.urut | wc) akan menghitung jumlah baris, kata, dan karakter dari file baru.urut.
Perintah ketiga (cat baru.urut | wc -l) akan menghitung jumlah baris dari file baru.urut.
Perintah keempat (cat baru.urut | wc -c) akan menghitung jumlah karakter dari file baru.urut.
Perintah kelima (cat baru.urut | wc -w) akan menghitung jumlah kata dari file baru.urut.
   
8. Gunakan perintah di bawah ini dan perhatikan hasilnya
``` sh
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
![Screen Shot 2024-03-18 at 11 08 56 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/6753b799-7427-46a1-b602-055c08b7c27f)
> Analisa : $ cat > hello.txt: Perintah ini membuka file hello.txt untuk penulisan dan menunggu input dari pengguna melalui keyboard.
$ cat > hello.txt | sort | uniq: Ada masalah pada perintah ini. Saat Anda menggunakan operator >, output dari perintah cat akan dialirkan ke dalam file hello.txt. Namun, karena menggunakan pipeline (|), output tersebut tidak akan lagi tersedia untuk perintah sort dan uniq. Oleh karena itu, tidak akan ada hasil yang diteruskan ke sort dan uniq.
$ cat > hello.txt | grep "dog" | grep -v "cat": Seperti pada perintah sebelumnya, ada masalah pada penggunaan operator >. Saat Anda menggunakan >, output dari perintah cat akan disimpan dalam file hello.txt. Namun, karena menggunakan pipeline (|), output tersebut tidak akan tersedia untuk perintah grep. Oleh karena itu, tidak akan ada input yang diberikan kepada perintah grep.


## Kesimpulan
> Saya bisa mengenal fungsi-fungsi dari perintah dasar linux, saya juga bisa mempraktekkan serta membuktikan secara langsung fungsi dari perintah dasar linux. Saya dapat mengetahui penggunaan operasi I/O proses dapat dipahami dengan mudah sesuai kebutuhan.
