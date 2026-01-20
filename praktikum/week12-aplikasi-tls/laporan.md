# Laporan Praktikum Kriptografi
Minggu ke-: 12

Topik: Aplikasi TLS & E-commerce

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu :
1. Menganalisis penggunaan kripografi pada **email** dan **SSL/TLS**
2. Menjelaskan enkripsi dalam transaksi **e-commerce**
3. Mengevaluasi isu **etika & privasi** dalam penggunaan kriptografi dikehidupan sehari-hari

---

## 2. Dasar Teori
TLS melindungi data e-commerce dengan enkripsi dan autentikasi, menjaga keamanan informasi sensitif dari penyadapan atau manipulasi.

Selain itu, TLS meningkatkan kepercayaan pelanggan dengan memastikan integritas data dan mencegah serangan seperti man-in-the-middle serta phishing.

---
## 3. Analisis SSL/TLS pada website e-commerce
observasi dilakukan menggunakan browser dengan memeriksa sertifikat digital pada dua website e-commerce populer di Indonesia

### a. Tokopedia ([https://www.tokopedia.com] (https://www.tokopedia.com))
- Issuer (CA) : DigiCert Inc
- Masa berlaku : ± 1 tahun
- Algoritma kriptografi :
  a. Public Key : RSA/ECDSA
  b. Enkripsi Simetris : AES-128 / AES-256
  c. Hash : SHA-256
  
- Status keamanan : HTTPS aktif, koneksi terenkripsi dan tervalidasi
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
