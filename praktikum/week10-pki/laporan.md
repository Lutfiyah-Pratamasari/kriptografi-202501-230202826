# Laporan Praktikum Kriptografi
Minggu ke-: 10

Topik: Public Key Infrastruktur

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu :

1. Membuat sertifikat digital sederhana
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh:HTTPS, TLS)

---

## 2. Dasar Teori
Public Key Infrastruktur (PKI) merupakan sistem yang mengelola kunci publik dan kunci privat untuk menjamin keamanan komunikasi digital, mencangkup autentifikasi, kerahasiaan, dan integritas data melalui penggunaan sertifikat digital.

PKI didukung oleh pihak terpercaya seperti Certificate Authority (CA) dan Registration Authority (RA) yang memverifikasi identitas serta mengelola sertifikat, sehingga memungkinkan pertukaran data yang aman dan terpercaya pada jaringan publik

---

## 3. Langkah Percobaan
Langkah- langkah :
1. Membuat pasangan kunci RSA (private key & public key)
2. Menentukan identitas sertifikat (Country, Organization, Common Name).
3. Menentukan masa berlaku sertifikat
4. Menandatangani sertifikat menggunakan private key
5. Menyimpan sertifikat dalam format `.pem `.
---

## 4. Source Code
```python
from cryptography import x509
from cryptography.x509.oid import NameOID
from cryptography.hazmat.primitives import hashes, serialization
from cryptography.hazmat.primitives.asymmetric import rsa
from datetime import datetime, timedelta

# Generate key pair
key = rsa.generate_private_key(public_exponent=65537, key_size=2048)

# Buat subject & issuer (CA sederhana = self-signed)
subject = issuer = x509.Name([
    x509.NameAttribute(NameOID.COUNTRY_NAME, u"ID"),
    x509.NameAttribute(NameOID.ORGANIZATION_NAME, u"UPB Kriptografi"),
    x509.NameAttribute(NameOID.COMMON_NAME, u"example.com"),
])

# Buat sertifikat
cert = (
    x509.CertificateBuilder()
    .subject_name(subject)
    .issuer_name(issuer)
    .public_key(key.public_key())
    .serial_number(x509.random_serial_number())
    .not_valid_before(datetime.utcnow())
    .not_valid_after(datetime.utcnow() + timedelta(days=365))
    .sign(key, hashes.SHA256())
)

# Simpan sertifikat
with open("cert.pem", "wb") as f:
    f.write(cert.public_bytes(serialization.Encoding.PEM))

print("Sertifikat digital berhasil dibuat: cert.pem")
```
---

## 5. Hasil 
berada didalam folder screenshoot

---

## 6. Verifikasi Sertifikat dan Peran CA
Sertifikat digital diverifikasi menggunakan publik key milik issuer (CA). Dalam sitem nyata :
a. Browser memiliki daftar root CA terpercaya
b. Browser memverifikasi tanda tangan sertifikat menggunakan publik key CA
c. Jika valid dan masa berlaku sesuai, koneksi dianggap aman

---

## 7. Analisis PKI dalam kasus nyata
### a. Verifikasi Sertifikat HTTPS oleh Browser
Browser melakukan :
1. Pengecekan tanda tangan sertifikat
2. Pengecekan rantai sertifikat hingga root CA
3. Validasi masa berlaku dan domain
4. Pengecekan revocation (CRL/OCSP)

Jika semua valid, koneksi HTTPS diterima.

### b. Dampak CA Palsu
jika CA palsu menerbitkan sertifikat :
1. Penyerang dapat melakukan Man-in-the-Middle (MITM)
2. Data sensitif seperti password dan nomor kartu kredit dapt dicuri
3. Kepercayaan terhadap sistem keamanan internet terganggu

### c. Pentingnya PKI
PKI menjamin :
1. Kerahasiaan data (enkripsi)
2. Keaslian identitas (authentication)
3. Integritas data
4. Kepercayaan dalam transaksi online

Tanpa PKI, komunikasi aman di internet hampir tidak mungkin dilakukan 

---

## 8. Pertanyaan Diskusi
1. Apa fungsi utama Certificate Authority (CA)?
   memverifikasi identitas pihak yang mengajukan sertifikat dan menerbitkan sertifikat digital agar kunci public yang digunakan dapat dipercaya dalam komunikasi digital

2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?
   karena, tidak divalidasi oleh CA terpercaya, self-signed certificate kurang aman dan tidak dipercaya pada sistem produksi

3. Bagaimana PKI mencegah serangan MITM dalam TLS/HTTPS?
   memverifikasi identitas server melalui sertifikat digital dari CA terpercaya, sehingga clien yakin berkomunikasi dengan pihak yang benar.

---
## 9. Kesimpulan 
PKI memastikan keamanan dan kepercayaan komunikasi digital dengan sertifikat dan otoritas terpercaya, sehingga data aman dari penyadapan dan pemalsuan

---
## 10. Referensi

- Stallings, W. (2017). Cryptography and Network Security: Principles and Practice. Pearson Education.

-Kahn Academy. (2020). Public Key Infrastructure (PKI) Overview

---
## 11. Commit Log
```
commit week10-pki
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-20

    week10-pki: implementasi PKI & laporan praktikum
```
