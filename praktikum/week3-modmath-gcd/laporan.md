# Laporan Praktikum Kriptografi
Minggu ke-: 3 

Topik: Modular Math 

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA 

a.) Aritmatika Modular
Operasi modular dasar yaitu operasi matematika yang dilakukan modulo n (mengambil sisa bagi setelah operasi)
menghitung (a+b) mod n
contoh : 7+5 mod 12 = 12 mod 12 = 0

b.) GCD & Algoritma Euclidean
GCD adalah bilangan bulat terbesar yang dapat membagi habis dua bilangan tanpa sisa
Contoh : 
faktor dari 54 = 1, 2, 3, 6, 9, 18, 27, 54
faktor dari 24 = 1, 2, 3, 4, 6, 8, 12, 24
faktor yang sama =1, 2, 3, 6
faktor terbesar yang sama adalah 6

c.) Extended Euclidean Algorithm
Bisa digunakan untuk mencari invers modular, yang sangat penting dalam kriptografi asimetris misalnya RSA

d.) Logaritma Diskrit
disebut logaritma diskrit karena mirip logaritma biasa, bedanya ini dipakai untuk bilangan yang dihitung dengan sisa bagi
masalah ini sangat sulit diselesaikan kalau angkanya besar, jadi sering digunakan sebagai dasar keamanan dalam kriptografi modern, seperti pada sistem enkripsi dan pertukaran kunci rahasia.

PERTANYAAN DISKUSI
1. Apa peran aritmetika modular dalam kriptografi modern?
   digunakan untuk menjaga hasil enkripsi tetap dalam batas tertentu dan membuat proses enkripsi-deskripsi aman.
2. Mengapa invers modular penting dalam algoritma kunci publik (misalnya RSA)?
   diperlukan untuk membalik proses enkripsi menjadi deskripsi, seperti pada algoritma RSA
3. Apa tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar?
   sulit dihitung jika modulusnya besar, sehingga butuh waktu lama dan membuat sistem kriptografi tetap aman.
