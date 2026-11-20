# PRAKTIKUM PERTEMUAN 12
## Refactoring dengan SOLID dan Repository Pattern

**Nama:** Ilham Baihaqi  
**NPM:** 4525210029  
**Kelas:** PBO A 2025/2026  
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom
---

## 1. Deskripsi Praktikum

Praktikum pertemuan 12 membahas refactoring kode Sistem Perpustakaan pada bahasa pemrograman Java dan PHP agar sesuai dengan prinsip SOLID.

Tujuan praktikum ini adalah memisahkan penyimpanan data dari aturan bisnis menggunakan Repository Pattern, memisahkan aturan denda menggunakan Strategy Pattern, merakit objek dengan dependency injection manual, serta membuktikan manfaatnya lewat unit test.

## 2. Tujuan Praktikum

1. Menemukan pelanggaran SOLID pada kode sendiri.
2. Memisahkan tanggung jawab penyimpanan dari aturan bisnis dengan Repository Pattern.
3. Menyuntikkan dependensi lewat constructor secara manual tanpa framework.
4. Mengganti rantai if jenis anggota dengan Strategy Pattern dan Factory.
5. Membuktikan bahwa aturan bisnis dapat diuji tanpa penyimpanan sesungguhnya.

## 3. Materi Praktikum

### A. Java

Beberapa materi yang dipelajari:
- Interface `BookRepository` dan implementasi `InMemoryBookRepository`.
- Dependency Injection lewat constructor pada `LibraryService`.
- Interface `AturanDenda` sebagai Strategy.
- `AturanDendaFactory` untuk memilih aturan denda.
- Open-Closed Principle dengan menambah `DendaAlumni` tanpa menyunting `LibraryService`.
- Unit Testing menggunakan JUnit 5 dengan repository palsu yang selalu gagal.

### B. PHP

Materi yang dipelajari:
- Interface `BookRepository` dan `InMemoryBookRepository`.
- Dependency Injection pada `LibraryService`.
- Interface `AturanDenda` dan `AturanDendaFactory`.
- Perakitan objek di `main.php`.
- Unit Testing menggunakan PHPUnit.

## 4. Struktur Folder

```text
Prak 12/
│
├── screenshots/
│   ├── 01-libraryservice-java.png
│   ├── 02-bookrepository-java.png
│   ├── 03-inmemorybookrepository-java.png
│   ├── 04-aturandenda-java.png
│   ├── 05-aturandendafactory-java.png
│   ├── 06-main-java.png
│   ├── 07-libraryservicetest-java.png
│   ├── 08-libraryservice-php.png
│   ├── 09-bookrepository-php.png
│   ├── 10-inmemorybookrepository-php.png
│   ├── 11-aturandenda-php.png
│   ├── 12-aturandendafactory-php.png
│   ├── 13-main-php.png
│   └── 14-libraryservicetest-php.png
│
├── 12-refactoring-dengan-solid-dan-repository-pattern/
│   ├── Modul-Praktikum-12-refactoring-dengan-solid-dan-repository-pattern.docx
│   ├── README.md
│   └── starter/
│       ├── java/          (Maven)
│       ├── php/           (Composer)
│       ├── CATATAN.md
│       ├── REFACTORING-template.md
│       └── REFACTORING.md
│
└── README.md
```

## 5. Penjelasan Program

**Java**

`LibraryService` tidak lagi membuat penyimpanannya sendiri. Ia menerima `BookRepository` dan `AturanDenda` lewat constructor, sehingga service hanya bergantung pada abstraksi.

`BookRepository` berisi kontrak `simpan()`, `cariByIsbn()`, `cariSemua()`, dan `kurangiStok()`. Implementasinya ada di `InMemoryBookRepository`.

`AturanDenda` berisi `hitung()` dan `nama()`. Implementasinya adalah `DendaMahasiswa`, `DendaDosen`, `DendaBebas` untuk anggota kehormatan, dan `DendaAlumni` sebagai bukti Open-Closed. `AturanDendaFactory` memilih aturan sesuai jenis anggota.

Seluruh objek dirakit di `Main.java`. `LibraryServiceTest` menguji service dengan `InMemoryBookRepository` dan dengan repository palsu yang selalu melempar exception.

**PHP**

Struktur PHP dibuat sejajar dengan Java:
- `BookRepository` dan `InMemoryBookRepository` untuk penyimpanan.
- `AturanDenda` dan `AturanDendaFactory` untuk aturan denda.
- `LibraryService` menerima repository dan aturan denda lewat constructor.
- `main.php` merakit seluruh objek.
- `LibraryServiceTest` menguji `LibraryService` menggunakan PHPUnit.

**REFACTORING.md**

Berisi tiga temuan pelanggaran SOLID, yaitu DIP, OCP, dan SRP, beserta tabel sebelum dan sesudah refactoring.

## 6. Dokumentasi Praktikum

Berikut dokumentasi kode program yang dikerjakan:

### Java

**LibraryService.java**

![LibraryService Java](screenshots/01-libraryservice-java.png)

**BookRepository.java**

![BookRepository Java](screenshots/02-bookrepository-java.png)

**InMemoryBookRepository.java**

![InMemoryBookRepository Java](screenshots/03-inmemorybookrepository-java.png)

**AturanDenda.java**

![AturanDenda Java](screenshots/04-aturandenda-java.png)

**AturanDendaFactory.java**

![AturanDendaFactory Java](screenshots/05-aturandendafactory-java.png)

**Main.java**

![Main Java](screenshots/06-main-java.png)

**LibraryServiceTest.java**

![LibraryServiceTest Java](screenshots/07-libraryservicetest-java.png)

### PHP

**LibraryService.php**

![LibraryService PHP](screenshots/08-libraryservice-php.png)

**BookRepository.php**

![BookRepository PHP](screenshots/09-bookrepository-php.png)

**InMemoryBookRepository.php**

![InMemoryBookRepository PHP](screenshots/10-inmemorybookrepository-php.png)

**AturanDenda.php**

![AturanDenda PHP](screenshots/11-aturandenda-php.png)

**AturanDendaFactory.php**

![AturanDendaFactory PHP](screenshots/12-aturandendafactory-php.png)

**main.php**

![main PHP](screenshots/13-main-php.png)

**LibraryServiceTest.php**

![LibraryServiceTest PHP](screenshots/14-libraryservicetest-php.png)

## 7. Kesimpulan

Melalui praktikum pertemuan 12, saya mempelajari cara merefaktor kode agar sesuai dengan prinsip SOLID. Dengan Repository Pattern, penyimpanan data terpisah dari aturan bisnis sehingga penyimpanan dapat diganti tanpa mengubah `LibraryService`.

Saya juga memahami penggunaan Strategy Pattern dan Factory untuk aturan denda, serta dependency injection manual yang merakit seluruh objek di satu tempat. Unit test dengan repository palsu membuktikan bahwa aturan bisnis dapat diuji terpisah dari penyimpanannya.

---
