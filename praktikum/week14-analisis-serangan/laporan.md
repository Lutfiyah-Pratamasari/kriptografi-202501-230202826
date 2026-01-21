# Laporan Praktikum Kriptografi
Minggu ke-: 14

Topik: Analisis Serangan Kriptografi

Nama: Lutfiyah Pratama Sari

NIM: 230202826

Kelas: 5 IKRA

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

1. Mengidentifikasi jenis serangan pada sistem informasi nyata.
2. Mengevaluasi kelemahan algoritma kriptografi yang digunakan.
3. Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.

---

## 2. Dasar Teori
Analisis serangan kriptografi adalah proses menguji keamanan sistem enkripsi untuk menemukan kelemahan, seperti melalui brute force atau dictionary attack. Tujuannya untuk memperkuat algoritma dan melindungi data dari manipulasi atau pencurian dengan menerapkan mekanisme keamanan tambahan seperti hash, salt, dan enkripsi yang kuat.

---

## 3. Identifikasi kasus serangan
Kasus yang dianalisis adalah serangan dictionary password

- Definisi: Serangan menebak password dengan mencocokkan daftar kata umum (dictionary) terhadap hash.
- Penyebab berhasil: Pengguna memakai password lemah.
- Kelemahan sistem: Tidak ada salt atau hashing berulang.

## Vektor Serangan 
- Penyerang memperoleh hash password dari database yang bocor
- Menggunakan daftar password umum (misalnya: 123456, password, admin)
- Meng-hash setiap kata dalam dictionary
- Membandingkan hasil hash dengan hash target
- Jika cocok → password berhasil ditebak
---

## 4. Evaluasi Kelemahan Sistem
## a. Kelemahan algoritma kriptografi
- Menggunakan hash cepat (mis. SHA-256)
- Tidak memakai salt sehingga hash mudah dicocokkan
- Tidak ada key stretching (iterasi hashing)
- Hash cepat memudahkan serangan skala besar

## b. Kelemahan Implementasi
- Password pengguna terlalu sederhana
- Tidak ada proteksi brute force/dictionary
- Tidak ada mekanisme delay atau penguncian akun
- Database hash mudah diakses saat terjadi kebocoran

---

## 5. Simulasi serangan
- Menunjukkan bagaimana password dapat ditebak jika:
- Hash diketahui
- Password ada dalam dictionary
---

## 6. Analisis Keamanan dan rekomendasi
## a. Mengapa sistem ini rentan?

karena menggunakan password yang mudah ditebak serta algoritma hash cepat tanpa mekanisme pengamanan tambahan seperti salt dan iterasi

## b. Rekomendasi Algoritma Pengganti

Sistem sebaiknya menggunakan hashing khusus password seperti bcrypt, scrypt, atau Argon2 yang lebih lambat serta mendukung salt dan key stretching, sehingga menyulitkan serangan dictionary dan brute force.

## c. Rekomendasi Tambahan

Selain hashing, sistem perlu: password kuat, batas percobaan login, autentikasi dua faktor, dan pengamanan database.

---

## 7. Jawaban Pertanyaan
1. Mengapa banyak sistem lama masih rentan terhadap brute force?
   Karena menggunakan algoritma kriptografi usang dan tidak diperbarui mengikuti perkembangan ancaman.

2. Apa perbedaan kelemahan algoritma dan implementasi?
   Kelemahan algoritma berasal dari desain kriptografi, sedangkan kelemahan implementasi berasal dari cara penerapannya.

3. Bagaimana menjaga keamanan kriptografi di masa depan?
   
Dengan audit keamanan berkala, pembaruan algoritma, dan penerapan standar keamanan modern. 

---

## 8. Kesimpulan
Sistem dengan password lemah dan hash tanpa perlindungan mudah diserang menggunakan dictionary attack. Menggunakan algoritma hashing aman seperti bcrypt/Argon2 beserta salt dan kebijakan keamanan tambahan dapat melindungi data pengguna.

---

## 9. Daftar Pustaka
- Bonneau, J. (2012). The Science of Guessing: Analyzing an Anonymous Corpus of 70 Million Passwords. IEEE Symposium on Security and Privacy.

- Stallings, W. (2017). Cryptography and Network Security: Principles and Practice (7th ed.). Pearson.

---

## 10. Commit Log
```
commit week14-analisis-serangan
Author: Lutfiyah Pratama Sari <lutfipratamasari@gmail.com>
Date:   2026-01-21

    week14-analisis-serangan: analisis serangan
```
