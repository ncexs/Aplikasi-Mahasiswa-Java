# Aplikasi Data Mahasiswa (JAVA & MySQL)

Projek ini adalah aplikasi CRUD (Create, Read, Update, Delete) Data Mahasiswa yang dibangun menggunakan Java Swing (NetBeans) dan terhubung ke database MySQL.

---

## ⚙️ Persyaratan Sistem

1.  **JDK (Java Development Kit)** versi 8 atau lebih tinggi.
    * [🔗 Unduh JDK 21 (LTS) Resmi dari Oracle](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html)
2.  **NetBeans IDE** (disarankan versi 11+).
    * [🔗 Unduh Apache NetBeans Terbaru](https://www.codelerity.com/netbeans/)
3.  **XAMPP / Laragon** (atau server lokal lain) dengan layanan **Apache** dan **MySQL** berjalan.
    * [🔗 Unduh XAMPP](https://www.apachefriends.org/download.html)
    * [🔗 Unduh Laragon](https://laragon.org/download)
4.  Library Java Tambahan:
    * **`mysql-connector-java.jar`** (Untuk koneksi ke MySQL)
        * [🔗 Unduh MySQL Connector/J (Pilih Platform Independent)](https://dev.mysql.com/downloads/connector/j/)
    * **`iText.jar`** (Untuk fitur Cetak PDF)
        * [🔗 Unduh iTextPDF Versi 5.5.0](https://jarcasting.com/artifacts/com.itextpdf/itextpdf/5.5.0/)
    
    *Catatan: Semua file JAR ini harus ditambahkan ke bagian **Libraries** Projek di NetBeans.*

---

## 🚀 Langkah-Langkah Penggunaan

Ikuti langkah-langkah ini agar aplikasi dapat berjalan di komputer Anda:

### 1. Download dan Ekstrak Projek

1.  Klik tombol **Code** di GitHub, lalu pilih **Download ZIP**.
2.  **Ekstrak** *file* ZIP tersebut ke lokasi yang Anda inginkan.
3.  Nama folder Projek adalah **`AplikasiDataMahasiswa`**.

### 2. Konfigurasi Database (Wajib!)

Aplikasi ini menggunakan *database* dengan nama **`mahasiswa_db`**.

1.  **Nyalakan** layanan **Apache** dan **MySQL** di XAMPP/Laragon.
2.  Buka **phpMyAdmin** (`http://localhost/phpmyadmin/`).
3.  Buat *database* baru dengan nama persis: **`mahasiswa_db`**.
4.  Jalankan perintah SQL berikut di *database* `mahasiswa_db` untuk membuat tabel `mahasiswa` dan `users`:

```sql
-- 1. Tabel untuk Data Mahasiswa (CRUD)
CREATE TABLE mahasiswa (
    nim VARCHAR(15) PRIMARY KEY,
    nama VARCHAR(100) NOT NULL,
    alamat VARCHAR(255),
    kota VARCHAR(50)
);

-- 2. Tabel untuk Login
CREATE TABLE users (
    id INT(11) NOT NULL AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(50) NOT NULL
);

-- 3. Isi Data Login Default (Gunakan 'admin' agar konsisten dengan aplikasi)
INSERT INTO users (username, password) VALUES
('admin', 'admin');
```

### 3. Import Proyek ke NetBeans

1. NetBeans → **File → Open Project**
2. Pilih folder **AplikasiDataMahasiswa**
3. Tambahkan library:
   - Klik kanan **Libraries**
   - Pilih **Add JAR/Folder**
   - Tambahkan:
     - `mysql-connector-java.jar`
     - `itextpdf-5.5.0.jar`
4. Jalankan aplikasi (**F6**)

**Login Default**
- Username: `admin`
- Password: `admin`

### 4. Mengatur Login sebagai Main Class di NetBeans

1. **Buka Properties Projek**
   - Di jendela **Projects**, klik kanan proyek **AplikasiDataMahasiswa**
   - Pilih **Properties**

2. **Pilih Menu Run**
   - Pada jendela **Project Properties**, pilih kategori **Run**

3. **Set Main Class**
   - Pada bagian **Main Class**, masukkan:
     
     `datamahasiswa.FormLogin`

   - Atau klik **Browse…** lalu pilih **FormLogin**

4. **Simpan**
   - Klik **OK**

---

### Hasil Akhir

Setelah langkah ini, setiap Anda menekan **Run Project (F6)**, aplikasi akan **selalu dimulai dari FormLogin**, sebelum masuk ke form utama (`FormMahasiswa.java`).
