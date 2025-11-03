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

3. Skema Dasar Kriptosystem
   Proses enkripsi dan deskripsi dapat dijelaskan melalui diagram berikut :
   ![Diagram Kriptosistem](screenshots/diagram_kriptosistem.png)

  Enkripsi : Plaintext diubah menjadi Ciphertext menggunakan algoritma dan kunci.
  Deskripsi : Ciphertext diubah kembali menjadi Plaintext menggunakan algoritma dan kunci yang sama (atau berbeda tergantung jenis sistemnya)

3. Implementasi Program Enkripsi dan Deskripsi
   Program berikut merupakan simulasi Caesar Cipher, yaitu algoritma substitusi sederhana dengan pergeseran huruf sebanyak nilai kunci tertentu
   
# file: praktikum/week2-cryptosystem/src/simple_crypto.py

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
