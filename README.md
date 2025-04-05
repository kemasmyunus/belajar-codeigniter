# Belajar CodeIgnite

Framework CodeIgniter sangat cocok untuk kamu yang baru belajar pengembangan web dengan PHP. Dengan arsitektur MVC (Model-View-Controller), CodeIgniter membantu kamu menulis kode lebih terstruktur dan mudah dipelihara.

---

## 1. Apa Itu CodeIgniter?

CodeIgniter adalah framework PHP yang ringan, cepat, dan mudah digunakan. Cocok untuk membuat aplikasi web dari kecil sampai besar. Versi terbaru (CI 4) sudah mendukung fitur-fitur modern PHP seperti Namespaces, Autoloading, dan RESTful API.

Kelebihan CodeIgniter:
- Ringan dan cepat
- Dokumentasi lengkap
- Mudah dipelajari (cocok untuk pemula)
- Arsitektur MVC yang terstruktur

---

## 2. Instalasi CodeIgniter

### Langkah-langkah:
1. Unduh CodeIgniter dari situs resmi: https://codeigniter.com
2. Ekstrak ke folder web server kamu (misal: `htdocs/codeigniter4/` untuk XAMPP)
3. Akses melalui browser:
   
   http://localhost/codeigniter4/public

Catatan: CI 4 membutuhkan minimal PHP versi 7.4

---

## 3. Struktur Folder CodeIgniter 4

| Folder         | Fungsi                                                      |
|----------------|-------------------------------------------------------------|
| `app/`         | Tempat kamu menulis kode (Controller, Model, View)          |
| `public/`      | Folder yang diakses browser (index.php)                     |
| `system/`      | Inti dari CodeIgniter (jangan diubah)                       |
| `writable/`    | Tempat log, cache, upload, dan lainnya                      |

Memahami struktur folder ini sangat penting agar kamu tidak menaruh file di tempat yang salah.

---

## 4. Routing Dasar

Routing adalah proses mengatur URL agar sesuai dengan controller dan method tertentu.
Semua route diatur di file:

```
app/Config/Routes.php
```

Contoh:

```php
$routes->get('/halo', 'Halo::index');
```

Artinya, ketika pengguna membuka `localhost/halo`, maka controller `Halo` akan memanggil method `index()`.

---

## 5. Controller

Controller bertanggung jawab mengatur alur logika aplikasi.
File controller disimpan di:

```
app/Controllers/
```

Contoh Controller:

```php
namespace App\Controllers;

class Halo extends BaseController {
    public function index() {
        return view('halo_view');
    }
}
```

Controller di atas akan memuat view bernama `halo_view.php`.

---

## 6. View

View adalah bagian dari aplikasi yang menampilkan antarmuka ke pengguna.
Disimpan di:

```
app/Views/
```

Contoh View `halo_view.php`:

```php
<html>
<head><title>Halo</title></head>
<body>
  <h1>Halo Dunia!</h1>
</body>
</html>
```

View ini akan ditampilkan ketika method `index()` pada controller `Halo` dipanggil.

---

## 7. Koneksi Database

Sebelum membuat model, kita harus mengatur koneksi database di file:

```
app/Config/Database.php
```

Contoh konfigurasi:

```php
public $default = [
    'hostname' => 'localhost',
    'username' => 'root',
    'password' => '',
    'database' => 'nama_database',
    'DBDriver' => 'MySQLi'
];
```

Pastikan nama database sudah dibuat di phpMyAdmin.

---
