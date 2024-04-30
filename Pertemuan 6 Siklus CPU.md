**Siklus CPU (Fetch, Decode, Execute) untuk Mengeksekusi Program:**
1. **Fetch (Ambil):** CPU mengambil instruksi dari memori yang ditunjukkan oleh program counter (PC).
2. **Decode (Dekode):** CPU mendekode instruksi tersebut untuk memahami apa yang harus dilakukan dan data mana yang terlibat.
3. **Execute (Eksekusi):** Instruksi dieksekusi oleh CPU, mungkin melibatkan manipulasi data, perhitungan, atau transfer data.


![1 drawio](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/f7cb8f02-cb29-4a6b-84b7-2b7277cb91e3)
Didalam CPU itu terdapat Control Unit, Accumulator, dan ALU atau Arithmetic Logic Unit. Selain 3 itu terdapat register lain seperti Program Counter (PC), Current Intruction Register (CIR), Memory Address Register (MAR), dan Memory Data Register (MDR).

![2 drawio](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/84a44bbb-fbc3-4a98-aaee-faa8a6028d69)
Pertama Program Counter akan menyimpan insturksi selanjutnya yang akan dieksekusi


![3 drawio](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/7594ed67-a168-44b8-b700-fd3564241052)
Selanjutnya alamat memori tadi harus disimpan didalam Memory Address Register, setelah itu isi dari alamat memori tersebut akan dimuat di Memory Data Register, Selanjutnya instruksi tadi harus disimpan di Current Instruction Register.


![4 drawio](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/5ce44987-9baf-45fc-abbb-3096de5885ae)
Setelah diambil ke dalam Current Instruction Register, Program Counter nya akan bertambah 1.

![collage-from-picmyna (6)](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/d4340d96-75f7-42de-9640-d30d48bb3a9c)
(1) Sekarang dapat melakukan decode kode instruksi, Masukan instruksi tersebut ke Control Unit, (2) Setelah insturksi LOAD 10 dieksekusi maka selanjutnya CPU akan melakukan fetch memori 10, Jadi Memory Address Register nya berubah menjadi 10. (3) Lalu ambil isi dari memori 10 dan simpan di Memory Data Register , (4) lalu dari MDR akan disimpan juga di Akumulator.

![collage-from-picmyna (1)](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/219efba3-c493-45a3-b5a2-6b12c23964bc)
Setelah instruksi pertama dilakukan maka selanjutnya adalah fetch instruksi ke dua. (1) Program Counter nya sudah menunjukan alamat memori yang baru maka tinggal copy saja alamt memori tersebut ke Memory Address Register. (2) lalu ambil isi dari alamat memori 101 dan simpan di Memory Data Register. (3) lalu insturksi dari alamat memori 101 akan disimpan juga di Current Instruction Register. (4) setelah itu Program Counter akan bertambah 1 menunjukan instruksi selanjutnya.

![collage-from-picmyna (2)](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/1f5f1424-7c77-4141-91a0-657b03bafcf2)
(1) lakukan decode instruksi kedua sama seperti instruksi pertama dengan diteruskan ke Control Unit. (2) Setelah Control Unit mengerti bahwa instruksi ini add, maka instuksi add akan diteruskan ke ALU. (3) isi dari Akumulator dipindahkan ke ALU. (4) Karena akan mengambil isi dari alamat memori 11, maka alamt memori tersebut harus dipindahkan ke Memory Address Register.


![collage-from-picmyna (3)](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/19d2afcf-75f5-47c0-b7b3-3a50a0e71e47)
(5) Setelah itu pindahkan isi dari alamat memori 11 ke dalam Memory Data Register dan (6) teruskan ke Akumulator. (7) Kemudian ALU akan menambahkan angka 3 dengan 2 (8) dan menampilan kembali hasilnya ke Akumulator sehingga bisa menjaga total running itu.

![collage-from-picmyna (7)](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/ccc39cea-04a1-4a23-be53-8a8e42accaf0)
Kemudian lakukan kembali fetch instruksi ke tiga, (1) lokasi memori 102 di copy ke Memory Address Register. (2)Isi dari alamat memori 102 dicopy ke Memory Data Register. (3) Instruksi tersebut dipindahkan ke Current Instruction Register. (4) Lalu selanjutnya Program Counter akan ditambah 1 menjadi 103, disini biasanya akan ada instruksi halt atau stop diakhir program.




![collage-from-picmyna (5)](https://github.com/PelangiKartikaChandraKirana/SysOP24-3123521003/assets/160555525/ccd2cd3a-822b-4e0a-b8b3-6a4ca57cdfce)
(1) Lalu decode instruksi ketiga, dengan simpan instruksi tersebut kedalam Control Unit. (2) Karena disini instruksinya adalah untuk STORE atau menyimpan hasil ke alamat memori 12 maka simpan lokasi 12 ke Memory Address Register. (3) Lalu hasil dari Akumulator dipindahkan ke Memory Data Register (4) dan dari Memory Data Register akan dilanjutkan ke lokasi memori 12. Begitu lah program ini terselesaikan.


**Peran Bahasa Pemrograman:**
> Bahasa pemrograman memungkinkan programmer menulis kode dalam bentuk yang bisa dimengerti oleh manusia.
> Memberikan abstraksi tingkat tinggi untuk mengekspresikan logika program.

**Peran Compiler:**
> Compiler menerjemahkan kode dari bahasa pemrograman ke bahasa mesin yang dapat dimengerti oleh CPU.
> Proses ini melibatkan kompilasi, optimisasi, dan pembuatan file eksekusi.

**Peran Sistem Operasi:**
> Sistem operasi mengelola sumber daya komputer dan menyediakan lingkungan eksekusi untuk program.
> Bertanggung jawab atas manajemen CPU, memori, dan perangkat keras lainnya.
> Memfasilitasi interaksi antara program dan perangkat keras.
