# Laporan Praktikum Kriptografi
Minggu ke-: 4

Topik: Entrophy & Unicity distrance (Evaluasi kekuatan kunci dan brute force)

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA

---

## 1. Tujuan pembelajaran
1. Menyelesaikan perhitungan sederhana terkait entropi kunci.
2. Menggunakan teorema Euler pada contoh perhitungan modular & invers.
3. Menghitung unicity distance untuk ciphertext tertentu.
4. Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance.
5. Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.

---

## 2. Dasar Teori

a. Entropi yaitu ukuran ketidakpastian atau kerandoman suatu sistem, khususnya dalam konteks kunci atau pesan terenkripsi

Gunakan rumus:
[ H(K) = \log_2 |K| ]
dengan (|K|) adalah ukuran ruang kunci.

contoh :
entrophy ruang kunci 26 = 4.700439718141093 bit
entrophy ruang kunci 2^128 = 128.0 bit

b. Unicity Distance yaitu berapa banyak teks terenkripsi yang dibutuhkan agar cipher bisa dipecahkan secara unik

Gunakan rumus:
[ U = \frac{H(K)}{R \cdot \log_2 |A|} ]
dengan:

(H(K)): entropi kunci,
(R): redundansi bahasa (misal bahasa Inggris (R \approx 0.75)),
(|A|): ukuran alfabet (26 untuk A–Z).

c. Brute Force yaitu cara memecahkan password atau kode dengan mencoba semua kemungkinan sampai ketemu yang benar

---

## Implementasi Program

import math

def entropy(keyspace_size):
    return math.log2(keyspace_size)

print("Entropy ruang kunci 26 =", entropy(26), "bit")
print("Entropy ruang kunci 2^128 =", entropy(2**128), "bit")

def unicity_distance(HK, R=0.75, A=26):
    return HK / (R * math.log2(A))

HK = entropy(26)
print("Unicity Distance untuk Caesar Cipher =", unicity_distance(HK))

def brute_force_time(keyspace_size, attempts_per_second=1e6):
    seconds = keyspace_size / attempts_per_second
    days = seconds / (3600*24)
    return days

print("Waktu brute force Caesar Cipher (26 kunci) =", brute_force_time(26), "hari")
print("Waktu brute force AES-128 =", brute_force_time(2**128), "hari")

---

## Hasil eksekusi
hasil program disimpan pada :
![hasil eksekusi] (screenshoot/hasil eksekusi.png)

---
## Analisis hasil
## 1. Entropy
  - Caesar Cipher hanya memiliki entropy 4.7 bit, sehingga ruang kunci kecil dan mudah ditebak
  - AES-128 memiliki 128 bit, yang berarti ruang kuncinya sangat besar (≈ 3.4×10³⁸ kemungkinan)

 ## 2. Unicity Distance 
 - Caesar Cipher memiliki unicity distance rendah (kurang dari 1), artinya dengan ciphertext sangat pendek pun dapat dipecahkan.
- AES-128 memiliki nilai yang jauh lebih tinggi, menandakan cipher sangat sulit dipecahkan secara statistik.

## 3. Brute Force 
- Caesar Cipher dapat dipecahkan dalam waktu kurang dari satu detik.
- AES-128 membutuhkan waktu lebih dari usia alam semesta, sehingga brute force tidak praktis dilakukan.

## PERTANYAAN DISKUSI
## 1. Apa arti dari nilai entropy dalam konteks kekuatan kunci?
Nilai entropi menunjukkan seberapa besar ketidakpastian atau ruang kemungkinan dari sebuah kunci. Semakin tinggi entropinya, semakin kuat keamanan cipher karena sulit ditebak oleh penyerang.

## 2. Mengapa unicity distance penting dalam menentukan keamanan suatu cipher?
Unicity distance menentukan seberapa banyak ciphertext yang diperlukan untuk menyingkap kunci secara unik. Nilai yang tinggi menandakan cipher lebih aman terhadap analisis statistik.

## 3. Mengapa brute force masih menjadi ancaman meskipun algoritma sudah kuat?
Karena perkembangan teknologi dan komputasi kuantum dapat mempercepat pencarian kunci secara eksponensial, sehingga algoritma dengan kunci kecil atau implementasi yang lemah tetap berisiko diserang.
