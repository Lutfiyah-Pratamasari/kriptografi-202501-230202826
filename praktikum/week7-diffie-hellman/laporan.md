# Laporan Praktikum Kriptografi
Minggu ke-: 7

Topik: Diffie-hellman

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA


---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu :
1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan **Man-in-the-Middle/MITM**).
   
---

## 2. Dasar Teori
Diffie–Hellman Key Exchange adalah teknik kriptografi kunci publik yang memungkinkan dua pihak membentuk sebuah kunci rahasia bersama melalui jaringan yang tidak aman. Metode ini diperkenalkan oleh Whitfield Diffie dan Martin Hellman pada tahun 1976, dengan tujuan utama menghindari pengiriman kunci rahasia secara langsung agar tidak mudah disadap oleh pihak yang tidak berwenang. 

---

## 3. Prinsip Kerja Diffie-Hellman 
Diffie-Hellman memungkinkan dua pihak (Alice dan Bob) menghasilkan **kunci rahasia bersama** meskipun hanya bertukar informasi melalui jaringan publik.

Prosesnya:
1. Alice dan Bob menyepakati bilangan **prima p** dan **generator g** (publik).
2. Masing-masing memilih **private key**:
   - Alice: `a`
   - Bob: `b`
3. Masing-masing menghitung **public key**:
   - `A = g^a mod p`
   - `B = g^b mod p`
4. Mereka saling bertukar public key.
5. Keduanya menghitung **shared secret**:
   - Alice: `K = B^a mod p`
   - Bob: `K = A^b mod p`

Nilai keduanya akan sama karena sifat aritmetika modular:

(g^b)^a mod p == (g^a)^b mod p

---

## 4. Implementasi Program
```python
import random

# parameter umum (publik)
p = 23
g = 5

# private key
a = random.randint(1, p-1)
b = random.randint(1, p-1)

# public key
A = pow(g, a, p)
B = pow(g, b, p)

# shared secret
shared_secret_A = pow(B, a, p)
shared_secret_B = pow(A, b, p)

print("Kunci bersama Alice :", shared_secret_A)
print("Kunci bersama Bob   :", shared_secret_B)
```
---
## 5. Hasil eksekusi
ada didalam folder screenshot

---
## 6. Simulasi serangan MITM
Pada serangan MITM:

- Eve mencegat **public key A** dan **B**.
- Eve menggantinya masing-masing dengan **public key palsu E1** dan **E2**.

Akibatnya:
- Alice menghasilkan kunci rahasia dengan Eve → `K_AE`
- Bob menghasilkan kunci rahasia dengan Eve → `K_BE`
- Alice dan Bob tidak memiliki kunci yang sama, tetapi Eve memiliki keduanya.

**Contoh alur komunikasi:**

Alice --> A* (palsu dari Eve) --> Bob z
Bob --> B* (palsu dari Eve) --> Alice

**Perhitungan Eve:**
- `K_AE = (public_Alice)^e mod p`
- `K_BE = (public_Bob)^e mod p`

Sehingga Eve dapat membaca semua pesan terenkripsi.

**Kesimpulan:** Diffie-Hellman murni rentan MITM jika tidak memakai autentikasi.

---
## 7. Pertanyaan diskusi
1. Mengapa Diffie-Hellman memungkinkan pertukaran kunci di saluran publik?
   
   Diffie–Hellman memungkinkan pertukaran kunci di saluran publik karena kunci rahasia tidak pernah dikirim, hanya nilai publik yang sulit diturunkan kembali akibat kompleksitas logaritma diskrit.
   
2. Apa kelemahan utama protokol Diffie-Hellman murni?
   
   Kelemahan utama Diffie–Hellman murni adalah tidak adanya autentikasi, sehingga rentan terhadap serangan Man-in-the-Middle (MITM).
   
3. Bagaimana cara mencegah serangan MITM pada protokol ini?

   Pencegahan MITM dilakukan dengan menambahkan autentikasi, seperti tanda tangan digital, sertifikat, atau penggunaan protokol aman seperti TLS.

   ---
## 8. Kesimpulan 
Pada praktikum ini:
- Protokol Diffie-Hellman berhasil menghasilkan kunci yang sama antara dua pihak.  
- MITM dapat terjadi jika tidak ada autentikasi.  
- Untuk keamanan nyata, Diffie-Hellman harus digabungkan dengan mekanisme verifikasi identitas.

  ---
## 9. Bukti Pengumpulan Git
commit week7-diffie-hellman
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-18

    week7-diffie-hellman: implementasi dan laporan
