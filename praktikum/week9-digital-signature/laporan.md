# Laporan Praktikum Kriptografi
Minggu ke-: 9

Topik: Digital Signature (RSA/DSA)

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.
2. Memverifikasi keaslian tanda tangan digital.
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.

---

## 2. Dasar Teori
Digital signature merupakan metode keamanan berbasis kriptografi yang digunakan untuk menjamin keaslian dan keutuhan dokumen atau data elektronik. Tanda tangan digital berfungsi sebagai identitas pengirim, sehingga penerima dapat memastikan bahwa informasi berasal dari pihak yang sah dan tidak mengalami perubahan selama proses pengiriman.
Konsep digital signature menggunakan sepasang kunci, yaitu kunci privat untuk membuat tanda tangan dan kunci publik untuk memverifikasi keabsahannya. Dengan mekanisme ini, digital signature mampu memberikan jaminan autentikasi, integritas data, dan non-repudiation, sehingga banyak diterapkan pada transaksi elektronik dan sistem berbasis web.

---
## 3. Implementasi Program 
```python
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generate RSA keys
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Original message
message = b"Hello, ini pesan penting."
h = SHA256.new(message)

# Signing
signature = pkcs1_15.new(private_key).sign(h)
print("Signature:", signature.hex())

# Verification
try:
    pkcs1_15.new(public_key).verify(h, signature)
    print("Verifikasi berhasil: tanda tangan valid.")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak valid.")

# Modified message
fake_message = b"Hello, ini pesan palsu."
h_fake = SHA256.new(fake_message)

try:
    pkcs1_15.new(public_key).verify(h_fake, signature)
    print("Verifikasi berhasil (seharusnya gagal).")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak cocok dengan pesan.")
```
---
## 4. Hasil
berada di dalam folder screenshoot

---
## 5. Pertanyaan Diskusi
1. Apa perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA?
   RSA enkripsi menjaga kerahasiaan pesan, sedangkan RSA tanda tangan digital memastikan keaslian dan keutuhan pesan.

2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?
   Tanda tangan digital menjamin integritas dan otentikasi karena dibuat dari hash pesan dan kunci privat pengirim.
   
3. Bagaimana peran Certificate Authority (CA) dalam sistem tanda tangan digital modern?
   Certificate Authority (CA) memverifikasi identitas pemilik kunci publik dan menjamin keabsahan tanda tangan digital.

   ---
## 6. Kesimpulan
Pada praktikum ini berhasil diimplementasikan tanda tangan digital menggunakan RSA.  
Hasil percobaan menunjukkan bahwa tanda tangan digital efektif untuk menjamin keaslian dan integritas pesan, serta dapat mendeteksi adanya perubahan pada data.  

---
## 7. Commit Log
```
commit week9-digital-signature
Author: Lutfiyah Pratama Sari<lutfipratamasari@gmail.com>
Date:   2026-01-19

    week9-digital-signature: implementasi dan laporan
```
