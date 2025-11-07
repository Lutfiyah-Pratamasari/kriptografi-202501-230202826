# Laporan Praktikum Kriptografi
Minggu ke-: 2  
Topik: Cryptosystem (Komponen, Enkripsi & Dekripsi, Simetris & Asimetris)  
Nama: Lutfiyah Pratama Sari
NIM: 230202826
Kelas: 5 IKRA

Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:
A. Mengidentifikasi komponen dasar kriptosistem (plaintext, ciphertext, kunci, algoritma).
B. Menggambarkan proses enkripsi dan dekripsi sederhana.
C. Mengklasifikasikan jenis kriptosistem (simetris dan asimetris).

1. Komponen Dasar Kriptosistem
   Sebuah kriptosistem terdiri dari beberapa komponen utama sebagai berikut:
   Plaintext : Pesan asli yang ingin dikirim atau disimpan sebelum dienkripsi.
   Ciphertext : Pesan hasil enkripsi yang tidak dapat dibaca tanpa kunci.
   Kunci (Key) : Nilai rahasia yang digunakan dalam proses enkripsi dan dekripsi.
   Algoritma : Metode matematis untuk mengubah plaintext menjadi ciphertext dan sebaliknya.

2. Skema Dasar Kriptosystem
   Proses enkripsi dan deskripsi dapat dijelaskan melalui diagram berikut :
   ![Diagram Kriptosistem](screenshots/diagram_kriptosistem.png)

  Enkripsi : Plaintext diubah menjadi Ciphertext menggunakan algoritma dan kunci.
  Deskripsi : Ciphertext diubah kembali menjadi Plaintext menggunakan algoritma dan kunci yang sama (atau berbeda tergantung jenis sistemnya)

3. Implementasi Program Enkripsi dan Deskripsi
   Program berikut merupakan simulasi Caesar Cipher, yaitu algoritma substitusi sederhana dengan pergeseran huruf sebanyak nilai kunci tertentu

file : src/simple crypto.py 
def encrypt(plaintext, key):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char
    return result

def decrypt(ciphertext, key):
    result = ""
    for char in ciphertext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift - key) % 26 + shift)
        else:
            result += char
    return result

if __name__ == "__main__":
    message = "Cryptosystem Test"
    key = 5

    enc = encrypt(message, key)
    dec = decrypt(enc, key)

    print("Plaintext :", message)
    print("Ciphertext:", enc)
    print("Decrypted :", dec)

4. Hasil eksekusi ![Deskripsi gambar](hasil eksekusi.png)

5. Klasifikasi Simetris dan Asimetris
   - Kriptografi Simetris : sistem enkripsi yang menggunakan satu kunci yang sama untuk proses ekripsi dan deskripsi (AES, DES)
     Sistem ini leboh cepat dan efisien, namun memiliki kelemahan pada keamanan distribusi kunci karena kunci harus dibagi kepada pihak lain. 
   - Kriptografi Asimetris : menggunakan dua kunci berbeda (RSA, ECC)
     lebih aman, karena kunci privat tidak perlu dibagikan tetapi proses enkripsi dan deskripsinya lebih lambat karena perhitungannya lebih kompleks.

  PERTANYAAN DISKUSI
1. Sebutkan komponen utama dalam sebuah kriptosistem?
   plaintext, ciphertext, algoritma enkripsi, algoritma deskripsi, kunci (key)
2. Apa kelebihan dan kelemahan sistem simetris dibandingkan asimetris?
   simetris
   kelebihan : yaitu proses ekripsi dan deskripsi lebih cepat dan efisien
   kekurangan : lebih aman karena tidak memerlukan pertukaran kunci rahasia

   asimetris
   kelebihan : distribusi kunci tidak aman, karena kuncu harus dibagikan ke penerima
   kekurangan : proses enkripsi-deskripsi lebih lambat karena kompleksitas tinggi
3. Mengapa distribusi kunci menjadi masalah utama dalam kriptografi simetris?
   karena pengirim dan penerima harus memiliki kunci yang sama, dan kunci tersebut harus dikirim melalui saluran komunikasi. 
