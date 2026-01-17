# Laporan Praktikum Kriptografi
Minggu ke-: 6

Topik: Cipher Modern

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA


---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu :
1. Mengimplementasikan algoritma **DES** untuk blok data sederhana
2. Menerapkan algoritma **AES** dengan panjang kunci 128 bit
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma **RSA**
   

---

## 2. Dasar Teori
Cipher Modern adalah metode kriptografi yang digunakan algoritma matematis dan kunci yang kompleks untuk mengamankan data digital agar tidak dapat dibaca oleh pihak yang tidak berwenang

**DES** adalah cipher simetris yang memakai satu kunci yang sama untuk enkripsi dan deskripsi, namun tingkat keamanan sudah dianggap lemah karena ukuran kuncinya pendek

-**jenis:** Symmetric-key block cipher

-**panjang blok:** 64 bit

-**panjang kunci:** 56 bit efektif (8 byte)

-**mode operasi umum:** ECB, CBC

-**kelemahan:** rentan terhadap serangan brute force karena panjang kunci pendek


**AES** adalah pengembangan dari DES dengan sistem keamanan yang lebih kuat. Algoritma ini juga bersifat simetris, tetapi menggunakan kunci yang lebih panjang sehingga jauh lebih sulit ditembus

-**jenis:** Symmetric-key block cipher

-**panjang blok:** 128 bit

-**panjang kunci:** 128,192, atau 256 bit

-**mode operasi umum:** ECB, CBC, CFB, OFB, CTR, GCM,EAX

-**kelemahan:** lebih aman dari DES, efisien digunakan secara luas di era modern


**RSA** adalah cipher asimetris yang menggunakan dua kunci berbeda, yaitu kunci publik dan kunci privat. Keamanan RSA bergantung pada sulitnya memecahkan bilangan besar menjadi faktor-faktor prima

-**jenis:** Asymmetric-key (publik-key) cryptography

-**panjang kunci umum:** 1024-4096 bit

-**progres utama:** generate key pair (publik & private), enkripsi dengan publik key, deskripsi dengan privat key

-**kelemahan:** digunakan untuk pertukaran kunci aman, digital signature, dan enkripsi data sensitif


---

## Implementasi Praktikum
### DES
```python
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # kunci 64 bit (8 byte)
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)

---

## DES  
! [Hasil DES](screensghootDES.png) 
