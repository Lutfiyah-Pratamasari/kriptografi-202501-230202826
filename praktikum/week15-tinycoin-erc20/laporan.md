# Laporan Praktikum Kriptografi
Minggu ke-: 15

Topik: Tinycoin ERC20

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Mengembangkan proyek sederhana berbasis algoritma kriptografi.
2. Mendokumentasikan proses implementasi proyek ke dalam repository Git.
3. Menyusun laporan teknis hasil proyek akhir.
---

## 2. Dasar Teori
TinyCoin adalah token digital yang dikembangkan menggunakan standar ERC20 pada blockchain Ethereum. Standar ini memungkinkan token beroperasi secara konsisten dan kompatibel dengan berbagai dompet digital, smart contract, serta aplikasi terdesentralisasi.

Melalui penerapan smart contract ERC20, seluruh transaksi TinyCoin dijalankan secara otomatis dan transparan. Setiap aktivitas token tercatat permanen di blockchain, sehingga menjamin keamanan, keandalan, dan kepercayaan pengguna.

---

## 3. Teknologi yang digunakan
- Solidity ^0.8.x
- OpenZeppelin ERC20
- Remix IDE
- Ethereum Virtual Machine 

---

## 4. Gambaran Smart Contact TinyCoin
TinyCoin merupakan token standar ERC20 dengan karakteristik:

- Token Name: TinyCoin
- Symbol: TNC
- Desimal: 18
- Initial supply dicetak ke alamat deployer saat kontrak dibuat
- Menggunakan OpenZeppelin untuk keamanan dan standarisasi

---

## 5. Source Code
Smart contract dikompilasi dan dideploy menggunakan Remix IDE pada lingkungan JavaScript VM / testnet Ethereum. Setelah proses deployment berhasil, kontrak siap diuji menggunakan fungsi-fungsi ERC20 yang tersedia.

---

## 6. Hasil pengujian 
di dalam folder screenshoot

---

## 7. Analisis keamanan dasar 
Beberapa aspek keamanan yang dianalisis:

- Overflow dan Underflow
  Tidak terjadi karena Solidity versi ≥ 0.8 memiliki proteksi otomatis.
- Reentrancy Attack
  Kontrak tidak memiliki fungsi kompleks yang memicu reentrancy.
- Unauthorized Minting
  Token hanya dicetak satu kali pada constructor.
  
Secara keseluruhan, smart contract tergolong aman untuk skala pembelajaran.

---

## 8. Dokumentasi Teknis
Dokumentasi teknis lengkap meliputi:

- Penjelasan kontrak ERC20 TinyCoin
- Hasil pengujian fungsi utama
- Jawaban pertanyaan diskusi
- Analisis keamanan dasar
---

## 9. Referensi
- Stallings, W. (2017). Cryptography and Network Security
- Stinson, D. (2019). Cryptography: Theory and Practice
- OpenZeppelin Documentation

---

## 10. Kesimpulan
Implementasi TinyCoin ERC20 berhasil dilakukan dengan baik. Smart contract dapat dideploy, diuji, dan berfungsi sesuai standar ERC20. Dokumentasi dan bukti pengujian telah dilampirkan secara lengkap.

----
## 11. Commit Log

commit week15-tinycoin-erc20
Author: Lutfiyah Pratama Sari <lutfipratama@gmail.com >
Date:   2026-01-27

    week15-tinycoint-erc20: Proyek kelompok Tinycoin ERC20

---
