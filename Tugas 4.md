## Operasi input output

### Percobaan 1 : File descriptor

1. Output ke layar (standar output), input dari system (kernel)
``` sh
$ ps
```
![Screen Shot 2024-03-18 at 9 50 38 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/1f736dbb-6df4-4a50-9dfd-caba9c03992b)
Analisa : 


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
Analisa : 

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
``` sh
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
```
![Screen Shot 2024-03-18 at 9 56 24 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/38d07d0d-9080-4920-90c5-edfab95e2dc5)
Analisa : 

## Percobaan 2 : Pembelokan (redirection)

1. Pembelokan standar output
``` sh
 $ cat 1> myfile.txt
 Ini adalah teks yang saya simpan ke file myfile.txt
```
![Screen Shot 2024-03-18 at 9 59 33 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/28cdc286-31d0-446d-a80e-a8f38ff7c2b7)
Analisa :

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
``` sh
 $ cat 0< myfile.txt
 $ cat myfile.txt
```
![Screen Shot 2024-03-18 at 10 00 36 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/f48310a2-5f73-4704-9e7a-4a38f36b41cc)
Analisa :

3. Pembelokan standar error untuk disimpan di file
``` sh
 $ mkdir mydir (Terdapat pesan error)
 $ mkdir mydir 2> myerror.txt
 $ cat myerror.txt
```
![Screen Shot 2024-03-18 at 10 02 46 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/34cb033e-0436-447d-a04e-237c0f3672ae)
Analisa :

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1
``` sh
 $ ls filebaru (Terdapat pesan error)
 $ ls filebaru 2> out.txt
 $ cat out.txt
 $ ls filebaru 2> out.txt 2>&
 $ cat out.txt
```
![Screen Shot 2024-03-18 at 10 24 14 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/6d6cad7f-b2fc-4b48-8064-cc2536a8954a)
Analisa : 

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
``` sh
$ echo “mencoba menulis file” 1> baru
$ cat filebaru 2> baru 1>&
$ cat baru
```
![Screen Shot 2024-03-18 at 10 26 04 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/b46dd310-52d5-413c-abe0-1b73ea641ae8)
Analisa :

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
Analisa :

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
Analisa :

8. Notasi – (input keyboard) adalah representan input dari keyboard.
   Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2.
   Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
``` sh
$ cat myfile.txt – surat
```
![Screen Shot 2024-03-18 at 10 33 49 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/e497aa9c-cd03-4e79-8065-98a77a2a63ce)
Analisa :


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
Analisa : 

2. Untuk membelokkan standart output ke file, digunakan operator ">"
``` sh
$ echo hello
$ echo hello > output
$ cat output
```
![Screen Shot 2024-03-18 at 10 40 42 AM](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/f7070e1d-4e6d-43f6-8d38-4a10742488ca)
Analisa : 



