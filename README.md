# Tugas_SatriaAnugraPutra
UTS Teknik Kompilasi
Satria Anugra Putra - 231011401474


1. Mengapa power() harus dipanggil di dalam term(), bukan sebaliknya?

Karena operator pangkat (^) memiliki prioritas lebih tinggi dibandingkan operator kali (*) dan bagi (/).

Urutan prioritas operator:
1. ^
2. * dan /
3. + dan -

Contoh:
a ^ 2 * b

Harus dihitung menjadi:
(a ^ 2) * b

Bukan:
a ^ (2 * b)

Karena itu fungsi power() harus dipanggil di dalam term(), agar operasi pangkat diproses lebih dulu.


2. Apa yang terjadi pada fase Analisis Semantik jika variabel z digunakan tetapi tidak ada di symbol_table?

Compiler akan memeriksa apakah variabel sudah terdaftar di symbol_table.

Jika variabel z tidak ditemukan, maka compiler menghasilkan error:

Semantic Error: Undefined variable 'z'

Artinya variabel tersebut belum didefinisikan sehingga tidak bisa digunakan dalam ekspresi.


3. Mengapa instruksi TAC untuk a ^ 2 harus muncul sebelum + ?

Karena operasi penjumlahan (+) membutuhkan hasil dari operasi a ^ 2 terlebih dahulu.

Contoh:
a ^ 2 + b * c

Maka TAC:

t1 = a ^ 2
t2 = b * c
t3 = t1 + t2

Instruksi t3 baru bisa dijalankan setelah t1 dan t2 selesai dihitung.

Jadi operasi dengan prioritas lebih tinggi akan muncul lebih dahulu dalam TAC.
