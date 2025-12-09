# Laporan Praktikum Kriptografi
Minggu ke-: 5

Topik: Cipher Klasik

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA 

---

##  Tujuan Pembelajaran
 a. Menerapkan algoritma Caesar Cipher untuk enkripsi dan dekripsi teks.
 b. Menerapkan algoritma Vigenère Cipher dengan variasi kunci.
 c. Mengimplementasikan algoritma transposisi sederhana.
 d. Menjelaskan kelemahan algoritma kriptografi klasik.
 
---

## 1. Dasar Teori
Cipher Klasik adalah metode kriptografi sederhana yang mengubah huruf atau urutan huruf menggunakan kunci tertentu untuk menjaga kerahasiaan pesan

a. Caesar Cipher : teknik penyandian sederhana yang mengubah setiap huruf pada pesan dengan cara digeser beberapa posisi dalam alfabet berdasarkan kunci tertentu

b. Vigenere Cipher : metode penyandian yang menggunakan kata kunci untuk menentukan pergeseran huruf yang berbeda-beda pada setiap huruf pesan, sehingga lebih sulit dipecahkan dibandingkan Caesar Cipher

c. Transposisi Cipher : mengubah urutan huruf dalam pesan tanpa mengganti hurufnya, sehingga teks menjadi sulit dibaca. 

---
## 2. Hasil Uji Implementasi 

### Caesar Cipher

| Plaintext | Key | Ciphertext | Decrypted |
|-----------|-----|------------|------------|
| CLASSIC CIPHER | 3 | FODVVLF FLSKHU |CLASSIC CIPHER |

### Vigenere Cipher
| Plaintext | Key | Ciphertext | Decrypted |
|------------|-----|-------------|-----------|
| KRIPTOGRAFI | KEY | URMVXYSLC3Q | KRIPTOGRAFI |

### Transposisi Cipher
| Plaintext | Key | Ciphertext | Decrypted |
|------------|-----|------------|------------|
| TRANSPOSITIONCIPHER | 5 | TPOINSNHARTOSITCENPR | TRANSPOSITIONCIPHER |

## 3. Screenshoot Hasil Program
Berikut tampilan hasil eksekusi program di terminal :
![Hasil Uji Coba ] (screenshoot/hasil.png)

---

## 4. Jawaban Pertanyaan diskusi 

1. Kelemahan caesar & Vigenere Cipher
   - Caesar Cipher hanya memiliki 25 kemungkinan kunci yaitu  
