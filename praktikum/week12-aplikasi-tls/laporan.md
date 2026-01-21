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

### a. Tokopedia (https://www.shopee.com)
- Issuer (CA) : DigiCert Inc
- Masa berlaku : ± 1 tahun
- Algoritma kriptografi :
  
  a. Public Key : RSA/ECDSA
  
  b. Enkripsi Simetris : AES-128 / AES-256
  
  c. Hash : SHA-256
  
  
- Status keamanan : HTTPS aktif, koneksi terenkripsi dan tervalidasi
  hasilnya berada di dalam folder screenshot

### b. Lazada (https://www.lazada.com)
- Issuer (CA) : DigiCert Inc
- Masa berlaku : ± 1 tahun
- Algoritma Kriptografi :

  a. Public Key : RSA / ECDSA

  b. Enkripsi Simetris : AES-128 / AES-256

  c. Hash : SHA-256

- Status keamanan : HTTPS aktif, koneksi aman
---

## 4. Perbandingan HTTPS vs HTTP

|  Aspek                | HTTP               | HTTPS          |
| --------------------- | ------------------ | -------------- |
| Enkripsi              | Tidak ada          | Ada (TLS)      |
| Keamanan data         | Rentan disadap     | Terlindungi    |
| Sertifikat digital    | Tidak ada          | Ada (CA)       |
| Kepercayaan pengguna  | Rendah             | Tinggi         |

website tanpa HTTPS sangat rentan terhadap penyadapan dan manipulasi data

---

## 5. Enkripsi dalam transaksi e-commerce
pada proses login dan pembayaran di e-commerce:

* Data username, password, dan OTP dienkripsi menggunakan TLS.
* Informasi pembayaran (nomor kartu, token pembayaran) diamankan dengan enkripsi simetris (AES).
* TLS mencegah serangan **Man‑in‑the‑Middle (MITM)** dengan verifikasi sertifikat.

**Ancaman jika TLS tidak digunakan**:

* Pencurian akun
* Penyadapan data kartu kredit
* Manipulasi transaksi
* Phishing dan spoofing
---

## 6. Analisis etika dan privasi
### a. Isu Privasi pada Email Terenkripsi
Teknologi seperti **PGP** dan **S/MIME** memungkinkan email dienkripsi end‑to‑end sehingga hanya pengirim dan penerima yang dapat membaca isi pesan. Hal ini melindungi privasi, tetapi juga menimbulkan tantangan bagi organisasi dan pemerintah.

### b. Dilema Etika
* **Audit Email Karyawan**
  Perusahaan memiliki kepentingan keamanan, namun membuka email terenkripsi karyawan tanpa izin melanggar privasi.

* **Pengawasan Pemerintah**
  Enkripsi melindungi warga, tetapi menyulitkan penegakan hukum dalam kasus kejahatan siber. Hal ini memunculkan dilema antara keamanan nasional dan hak privasi individu.

---

## 7. Jawaban Pertanyaan
1. Perbedaan Utama HTTP dan HTTPS

HTTP tidak menggunakan enkripsi sehingga data dikirim dalam bentuk plaintext. HTTPS menggunakan TLS untuk mengenkripsi data, menjamin kerahasiaan, integritas, dan autentikasi.

2. Pentingnya Sertifikat Digital dalam TLS

Sertifikat digital memastikan identitas server yang sah dan mencegah pemalsuan website. Sertifikat dikeluarkan oleh Certificate Authority (CA) yang dipercaya.

3. Kriptografi, Privasi, dan Tantangan Etika

Kriptografi melindungi privasi komunikasi digital, namun menimbulkan tantangan hukum dan etika terkait pengawasan, penegakan hukum, dan tanggung jawab organisasi.

---

## 8. Kesimpulan
TLS/SSL merupakan komponen vital dalam keamanan email dan e‑commerce. Penerapannya meningkatkan kepercayaan pengguna dan melindungi data sensitif. Namun, penggunaan kriptografi juga harus diimbangi dengan kebijakan etika dan hukum yang adil agar privasi tetap terjaga.

---

## 9. Referensi
* Stallings, W. (2017). *Cryptography and Network Security*, Bab 15.

---

## 10. Commit Log
```
commit week-12-aplikasi-tls
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-21

    week12-aplikasi-tls: Aplikasi TLS & E-Commerce
```
