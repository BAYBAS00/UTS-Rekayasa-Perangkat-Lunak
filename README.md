# Rancang Bangun Sistem Koperasi Simpan Pinjam

## 1. Latar Belakang
Sebuah koperasi simpan pinjam ingin mengembangkan sistem manajemen koperasi digital yang dapat mengelola kegiatan simpanan, pinjaman, dan angsuran anggota secara terintegrasi. Sistem ini bertujuan untuk meningkatkan efisiensi pengelolaan data, mempercepat proses transaksi, serta meminimalisir kesalahan pencatatan yang sering terjadi pada sistem manual.
Sistem harus mampu mengelola data anggota, mencatat transaksi simpanan dan pinjaman, serta memantau status pembayaran angsuran secara otomatis. Selain itu, sistem perlu mendukung berbagai peran pengguna seperti pengurus dan anggota, dengan hak akses yang disesuaikan berdasarkan tanggung jawab masing-masing.
Dengan adanya sistem koperasi simpan pinjam ini, diharapkan proses administrasi koperasi menjadi lebih transparan, akurat, dan efisien, sekaligus memudahkan anggota dalam memperoleh informasi terkait simpanan, pinjaman, serta transaksi mereka.

## 2. Aktor & Use Case Diagram
### Aktor Utama
- Anggota
- Pengurus

### Use Case
<img src="Use-Case.png" alt="Use Case Diagram" width="600"/>


## 3. Kelas-Kelas & Class Diagram
### Kelas Utama
- User
- Anggota
- Pengurus
- Pinjaman
- Angsuran
- Simpanan Master
- Simpanan Detail

### Class Diagram
<img src="Class-Diagram.png" alt="Use Case Diagram" width="600"/>

## 4. Prinsip SOLID & Design Patterns
### Prinsip SOLID yang Dipilih
- Single Responsibility Principle (SRP)
  Setiap class hanya punya satu tanggung jawab. Contoh: DatabaseManager hanya mengelola koneksi, UserFactory hanya membuat user, PinjamanBuilder hanya membangun objek pinjaman.
- Open/Closed Principle (OCP)
  Sistem dapat diperluas tanpa mengubah kode yang sudah ada. Misal: menambah role baru (UserAdmin) cukup tambahkan class dan Factory baru, tanpa mengubah UserFactory.
- Dependency Inversion Principle (DIP)
  AnggotaService tidak membuat dependency sendiri, tetapi menerima DatabaseManager dari luar, sehingga dependency bergantung pada abstraksi.

### Contoh Creational Design Patterns
- Singleton:
  ```php
  
class DatabaseManager {
    private static $instance = null; // Penyimpan instance tunggal

    private function __construct() {
        // Konstruktor harus private
        // Inisialisasi koneksi database hanya sekali
    }

    public static function getInstance() {
        if (self::$instance === null) {
            self::$instance = new DatabaseManager(); // Buat instance jika belum ada
        }
        return self::$instance; // Selalu mengembalikan instance yang sama
    }
}

// Penggunaan:
$db1 = DatabaseManager::getInstance();
$db2 = DatabaseManager::getInstance();

// $db1 akan selalu sama dengan $db2

  ```

- Factory Method: …
- Builder: …

## 5. Proses Penting & Diagram
### Alur Proses
- …

### Diagram
- (Activity / Sequence) …

## 6. Siklus Hidup Data & Evaluasi Desain
### Siklus Hidup Data Utama
- …

### Evaluasi Desain
- Maintainable: …
- Reusable: …
- Extendable: …

### Usulan Fitur Masa Depan
- …

## Penutup
…
