# Laporan Praktikum Kriptografi
Minggu ke-: 13

Topik: Tinychain

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Menjelaskan peran hash function dalam blockchain.
2. Melakukan simulasi sederhana Proof of Work (PoW).
3. Menganalisis keamanan cryptocurrency berbasis kriptografi.

---

## 2. Dasar Teori
TinyChain adalah blockchain sederhana yang digunakan untuk mempelajari mekanisme Proof of Work (PoW). Setiap blok harus melalui proses pencarian hash dengan tingkat kesulitan tertentu sebelum dapat ditambahkan ke rantai, sehingga menjamin keabsahan data.

Mekanisme PoW pada TinyChain membuat perubahan data menjadi sulit dilakukan karena memerlukan perhitungan ulang pada blok-blok berikutnya. Hal ini menjaga keamanan dan integritas data dalam sistem blockchain.

---

## 3. Hash Function dalam Blockchain
Fungsi hash kriptografis memiliki karakteristik utama:
- Deterministik
- Sulit dibalik (one-way)
- Perubahan kecil pada input menghasilkan output yang sangat berbeda
- Output berukuran tetap
  
Dalam blockchain, hash digunakan untuk:
- Menghubungkan blok satu dengan yang lain
- Menjamin integritas data
- Mendeteksi perubahan atau pemalsuan data
---

## 4. Proof of Work (PoW)
Proof of Work adalah mekanisme konsensus yang mengharuskan penambang (miner) menyelesaikan teka-teki kriptografi dengan mencari nilai nonce yang menghasilkan hash sesuai tingkat kesulitan (difficulty).

Semakin tinggi difficulty, semakin lama waktu yang dibutuhkan untuk menemukan hash yang valid.

---

## 5. Hasil Simulasi Mining
Program TinyChain berhasil melakukan mining beberapa blok dengan:

- Hash SHA-256
- Difficulty = 4
- Proses mining menghasilkan hash dengan prefix "0000"
  selanjutnya hasil berada dalam folder screenshot
---

## 6. Pertanyaan Diskusi
1. Mengapa fungsi hash sangat penting dalam blockchain?
   Fungsi hash penting dalam blockchain karena berperan menjaga integritas data, menghubungkan setiap blok secara aman, dan memudahkan pendeteksian perubahan data sekecil apa pun.
   
2. Bagaimana Proof of Work mencegah double spending?
   Proof of Work mencegah double spending dengan mewajibkan validasi blok melalui proses komputasi, sehingga satu transaksi hanya dapat dicatat pada satu blok yang sah di dalam blockchain.
   
3. Apa kelemahan dari PoW dalam hal efisiensi energi?
Kelemahan PoW dalam efisiensi energi adalah kebutuhan daya komputasi yang sangat besar, karena proses penambangan melibatkan perhitungan berulang yang menghabiskan banyak listrik.

---
## 7. Kesimpulan
Blockchain menggunakan fungsi hash untuk menjaga data tetap aman dan utuh antar blok, sementara Proof of Work memastikan setiap transaksi valid dan menghindari pengeluaran ganda. Namun, meskipun PoW menjaga keamanan, mekanisme ini kurang efisien karena memerlukan banyak energi dan daya komputasi.

---

## 8. Referensi
-Yli-Huumo, J., Ko, D., Choi, S., Park, S., & Smolander, K. (2016). Where Is Current Research on Blockchain Technology?—A Systematic Review. PLOS ONE.
-Stallings, W. (2017). Cryptography and Network Security: Principles and Practice (7th ed.). Pearson.

---

## 9. Commit Log
```
commit week-13-tinychain
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-21

    week13-tinychain: TinyChain Proof of Work
```
