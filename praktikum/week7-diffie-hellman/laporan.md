# Laporan Praktikum Kriptografi
Minggu ke-: 7

Topik: Diffie-hellman

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA


---

## Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu :
1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan **Man-in-the-Middle/MITM**).
   
---

## Dasar Teori
Diffie–Hellman Key Exchange adalah teknik kriptografi kunci publik yang memungkinkan dua pihak membentuk sebuah kunci rahasia bersama melalui jaringan yang tidak aman. Metode ini diperkenalkan oleh Whitfield Diffie dan Martin Hellman pada tahun 1976, dengan tujuan utama menghindari pengiriman kunci rahasia secara langsung agar tidak mudah disadap oleh pihak yang tidak berwenang.

Mekanisme Diffie–Hellman memanfaatkan perhitungan matematika berupa eksponensial modulo bilangan prima besar. Pada prosesnya, kedua pihak terlebih dahulu menyepakati nilai publik berupa bilangan prima dan generator. Masing-masing pihak kemudian memilih bilangan privat sebagai rahasia, lalu menghasilkan nilai publik yang ditukarkan melalui saluran komunikasi. Walaupun nilai publik tersebut dapat diakses oleh pihak lain, kunci rahasia tetap terlindungi karena tingkat kesulitan dalam menyelesaikan persoalan logaritma diskret.

Keandalan keamanan algoritma Diffie–Hellman sangat bergantung pada ukuran parameter yang digunakan. Dengan pemilihan bilangan prima yang besar, metode ini masih efektif dan aman digunakan hingga saat ini. Oleh karena itu, Diffie–Hellman banyak diterapkan pada berbagai sistem keamanan modern, seperti protokol TLS/SSL, jaringan privat virtual (VPN), dan berbagai aplikasi komunikasi yang membutuhkan pertukaran kunci secara aman.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: …  
- Pertanyaan 2: …  
)
---

## 8. Kesimpulan
(Tuliskan kesimpulan singkat (2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
