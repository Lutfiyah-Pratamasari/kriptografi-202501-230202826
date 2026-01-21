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

## 3. Implementasi Praktikum
### DES
```python
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # 64-bit key
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)
```
---

### AES
```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128-bit key
cipher = AES.new(key, AES.MODE_EAX)

plaintext = b"Modern Cipher AES Example"
ciphertext, tag = cipher.encrypt_and_digest(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi
cipher_dec = AES.new(key, AES.MODE_EAX, nonce=cipher.nonce)
decrypted = cipher_dec.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
```

### RSA
```python
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Enkripsi
cipher_rsa = PKCS1_OAEP.new(public_key)
plaintext = b"RSA Example"
ciphertext = cipher_rsa.encrypt(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi
decipher_rsa = PKCS1_OAEP.new(private_key)
decrypted = decipher_rsa.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
```
---

### 4. Pertanyaan Diskusi
1. Apa perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan?

DES, AES, dan RSA
DES dan AES adalah algoritma simetris, sedangkan RSA asimetris. DES tidak aman, AES sangat aman, dan RSA cocok untuk pertukaran kunci.

2. Mengapa AES lebih banyak digunakan dibanding DES di era modern?

AES lebih banyak digunakan karena lebih aman dan lebih cepat dibanding DES.

3. Mengapa RSA dikategorikan sebagai algoritma asimetris, dan bagaimana proses pembangkitan kuncinya?

RSA sebagai algoritma asimetris
RSA menggunakan kunci publik dan privat yang dibuat dari bilangan prima besar.

---
### 5. Kesimpulan 
Cipher modern adalah metode enkripsi yang menggunakan algoritma dan perhitungan matematika yang kuat untuk menjaga keamanan data. Algoritma ini lebih aman dan efisien dibandingkan cipher lama, sehingga banyak digunakan dalam sistem keamanan digital seperti internet, perbankan, dan komunikasi online.

---
### 6. Referensi
- Stallings, W. (2017).
Cryptography and Network Security: Principles and Practice (7th ed.).
Pearson Education.

---
### 7. Commit Log
commit week6-cipher-modern
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-19

    week6-cipher-modern: implementasi cipher modern & laporan praktikum
