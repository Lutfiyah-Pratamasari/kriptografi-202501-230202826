# Laporan Praktikum Kriptografi
Minggu ke-: 11

Topik:  Secret Sharing

Nama: Lutfiyah Pratama Sari

NIM:230202826

Kelas: 5 IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu :
1. Menjelaskan konsep Shamir Secret Sharing (SSS)
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS
3. Menganalisis keamanan skema distribusi rahasia 

---

## 2. Dasar Teori
Secret Sharing adalah metode kriptografi untuk membagi rahasia menjadi beberapa bagian agar tidak diketahui oleh satu pihak saja

Rahasia hanya dapat dipulihkan jika jumlah bagian tertentu digabungkan dan teknik ini meningkatkan keamanan dan kendalan dalam pengelolaan data atau kunci rahasia. 

---

## 3. Implementasi Shamir Secret Sharing
pada praktikum ini digunakan library `secretsharing` untuk melakukan pembagian dan rekonstruksi rahasia secara sederhana

## Langkah-langkah :
a. Menentukan rahasia yang akan dibagi
b. Menentukan jumlah total share (`n`)
c. Menentukan threshold (`k`), yaitu jumlah minimum share yang dibutuhkan untuk merekonstruksi rahasia
d. Membagi rahasia menjadi beberapa share
e. Merekonstruksi rahasia menggunakan minimal `k` share

## Hasil
- Rahasia berhasil dibagi menjadi beberapa share
- Rahasia berhasil direkonstruksi kembali menggunakan minimal threshold share
- Rekonstruksi gagal jika jumlah share kurang dari threshold

## Source Code Implementasi
``` python
from secretsharing import SecretSharer

secret_text = "KriptografiUPB2025"

secret_hex = secret_text.encode("utf-8").hex()

# Membagi rahasia menjadi 5 share dengan threshold 3
shares = SecretSharer.split_secret(secret_hex, 3, 5)
print("Shares:", shares)

recovered_hex = SecretSharer.recover_secret(shares[:3])

recovered_text = bytes.fromhex(recovered_hex).decode("utf-8")
print("Recovered secret:", recovered_text)
```
---

## 4. Simulasi Manual (Tanpa library)
Simulasi Shamir Secret Sharing dilakukan manual untuk memahami konsep polinomial dan interpolasi lagrange dalam pembagian dan pemulihan rahasia

## a. Pemilihan Bilangan Prima
dipilih sebuah bilangan prima (p) yang cukup besar untuk digunakan sebagai modulo dalam se-luruh operasi aritmatika. Pengguna modulo bilangan prima bertujuan untuk menjaga sifat keamanan dan menghindari collision pada perhitungan.

## b. Pembentukan Polinomial
dibentuk  sebuah polinomal berderajat (k-1) sebagai berikut :

[ f(x) =a_1x + a_2x^2 + \dots + a_{k-1}x^{k-1}\mod p]

dengan :
a. (a_0) sebagian `rahasia` (secret)

b. (a_1, a_2, \dots) sebagai koefisien acak

## c. Pembagian Share
nilai share diperoleh dengan menghitung pasangan titik :

[ (x, f(x)) ]

Setiap pasangan titik tersebut dibagikan kepada pihak yang berbeda sebagai share rahasia.

## d. Rekonstruksi rahasia 
Rekontruksi rahasia dilakukan menggunakan Interpolasi Lagrange dengan minimal (k) buah share. Nilai rahasia diperoleh dengan menghitung niali polinomial pada (x = 0 ), yaitu :

[ secret = f(0) ]

Jika jumlah sharre yang tersedia kurang dari threshold (k), maka rahasia tidak dapat direkonstruksi.

## e. Hasil simulasi manual
berada didalam folder screenshot

---

## 5. Analisis Keamanan Shamir Secret Sharing 
## a. Keamanan Skema (k, n) 

Skema (k, n) tetap aman meskipun sebagian share bocor karena informasi dari kurang dari `k` share tidak memberikan informasi apa pun tentang rahasia asli

## b. Resiko pemilihan threshold
- Threshold terlalu kecil : meningkatkan resiko rekonstruksi rahasia oleh pihak tidak berwenang
- Threshold terlalu besar : meningkatkan resiko rahasia tidak dapat direkonstruksi jika beberapa share hilang

## c. Penerapan di dunia nyata 
Shamir Secret S hraing banyak digunakan dalam :
- Manajemen kunci cryptocurrency (multi-signature wallet)
- Sistem recovery password
- Penyimpanan kunci enkripsi tingkat enterprise
- Sistem keamanan organisasi dengan pembagian otoritas

---

## 6. Pertanyaan Diskusi
1. Apa keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci secara langsung?
   Keuntungan utama SSS adalah rahasia tidak tersimpan utuh pada satu pihak, sehingga kebocoran satu bagian tidak mengungkapkan kunci
   
2. Apa peran threshold (k) dalam keamanan secret sharing?
   Threshold (k) menentukan jumlah minimum bagian yang harus digabungkan kontrol dan keamanan
   
3. Contoh skenario nyata penggunaan SSS
   Contoh penggunaan SSS adalah pengamanan kunci kriptografi pada sistem perbankan, server terdistribusi, atau dompet kripto bersama
---

## 7. Kesimpulan
Shamir Secret Sharing meningkatkan keamanan dengan memecah rahasia ke beberapa bagian, sehingga hanya sejumlah tertentu yang dapat mengungkapkannya dan resiko kebocoran dapat diminimalkan

---

## 8. Referensi
- Jihun Hwang, Hemanta K. Maji, Hai H. Nguyen, Xiuyu Ye. (2025). Leakage‑Resilience of Shamir’s Secret Sharing: Identifying Secure Evaluation Places. LIPIcs ITC 2025, Lecture Notes in Information‑Theoretic Cryptography.

- Baghery, K., Ebrahimi, E., Mirzamohammadi, O., & Sedaghat, M. (2025). Traceable Verifiable Secret Sharing and Applications. Cryptology ePrint Archive.
---

## 9. Commit Log
```
commit week11-secret-sharing
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-20

    week11-secret-sharing: implementasi dan laporan
```
