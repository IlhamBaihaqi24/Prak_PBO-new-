**Nama:** Ilham Baihaqi
**NPM:** 4525210029
**Kelas:** PBO A 2025/2026
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom

---

## 1. Peta Isi Repositori

```
Prak PBO/
├── codingansebelum/        kode awal (kondisi SEBELUM dikerjakan)
│   ├── pertemuan02 … pertemuan06
│   ├── pertemuan7         
│   ├── pertemuan9
│   ├── pertemuan10
│   └── pertemuan11
├── PrakPBO/                hasil pengerjaan saya (kondisi SESUDAH)
│   ├── Prak 01/            laporan Git dan GitHub (.docx)
│   ├── pert 02/            java/  php/
│   ├── prak 03/            java/  php/
│   ├── Prak 04/            src/java  src/php  bin
│   ├── Prak 05/            java/  php/
│   ├── Prak 06/            java/  php/
│   ├── Prak 07/            src/java  src/php  src/uml
│   ├── Prak 09/            java/ (Maven)  php/ (Composer)
│   ├── Prak 10/            java/ (Maven)  php/ (Composer)
│   ├── Prak 11/            src/starter/java  src/starter/php
│   └── Prak 12/            java/ (Maven)  php/ (Composer)  REFACTORING.md
├── SSAN - sebelum/         images-java/  images-php/  (Pertemuan2 … Pertemuan11)
└── SSAN - sesudah/         images-java/  images-php/  (Pertemuan2 … Pertemuan12)
```

Catatan:
- Folder `Prak 04` dan `Prak 07` memakai `src/java` dan `src/php`, sedangkan
  `Prak 09` dan `Prak 10` memakai `java/` dan `php/` dengan struktur Maven dan
  Composer. `Prak 11` berisi berkas kerangka di `src/starter/java` dan
  `src/starter/php`. `Prak 12` ada di
  `Prak 12/12-refactoring-dengan-solid-dan-repository-pattern/starter/` dengan
  `java/` (Maven) dan `php/` (Composer). Sisanya langsung `java/` dan `php/`.
- Nama folder mengandung spasi, jadi apit path dengan tanda kutip di terminal.
- Pertemuan 8 adalah ujian tengah semester (live coding), jadi tidak ada
  folder kode untuk pertemuan itu.
- Screenshot yang punya dua gambar dinamai `(1)` untuk kode dan `(2)` untuk
  hasil eksekusi. Pertemuan 11 memakai `(1)` untuk kelas utama dan `(2)` untuk
  kelas pengujiannya. Pertemuan 12 memakai `(1)` sampai `(7)` karena
  refactoring menyentuh banyak berkas (lihat bagian 4). Pertemuan 9 dan 10 versi Java hanya berisi gambar kode
  (lihat bagian 4).

---

## 2. Yang Dibutuhkan

- JDK 21 (Prak 09 dan 10 memakai Maven, dengan `maven.compiler.source` 17)
- Apache Maven 3.9+ (untuk Prak 09 dan 10)
- PHP 8.3
- Composer (untuk Prak 09 dan 10, jalankan `composer install` di folder `php/`)
- JUnit 5 untuk Java dan PHPUnit untuk PHP (Prak 11 dan 12, lihat bagian
  Pertemuan 11 dan 12)
- Windows CMD: jalankan `chcp 65001` lebih dulu agar karakter khusus tampil benar.

---

## 3. Topik dan Hasil per Pertemuan

Setiap pertemuan dibagi dua: apa yang terlihat sebelum dikerjakan, lalu apa
yang terlihat setelah selesai.

### Pertemuan 02: Kelas, Objek, dan Enkapsulasi (Mahasiswa)

Sebelum (`codingansebelum/pertemuan02`):
```bash
javac *.java && java Main
php main.php
```
Semua nilai akhir `0.00` dengan mutu `?`. Dua pengujian validasi mencetak
`MASALAH: ... seharusnya ditolak!`.

Sesudah (`PrakPBO/pert 02`):
```bash
cd java && javac *.java && java Main
cd ../php && php main.php
```
Hasil: Ani `84.90` (A), Budi `59.30` (D), Citra `92.00` (A). Nilai 150 dan NIM
kosong sekarang tercetak sebagai `Ditolak: ...`.

### Pertemuan 03: Rekening Bank

Sebelum (`codingansebelum/pertemuan03`):
- Java: jumlah rekening `-1`, setoran tidak menambah saldo, dan muncul
  `MASALAH: penarikan melebihi batas seharusnya ditolak!`.
- PHP: berhenti dengan Fatal error `TODO 5 belum dikerjakan`.

Sesudah (`PrakPBO/prak 03`):
```bash
cd java && javac *.java && java Main
cd ../php && php main.php
```
Hasil Java: saldo Ani naik menjadi `Rp1,500,000.00` setelah setoran, penarikan
berlebih ditolak (`Saldo tidak mencukupi`), saldo Budi tidak jadi negatif, dan
bunga setahun `Rp37,500.00`. Penghitung rekening menunjukkan `2`.

### Pertemuan 04: Pewarisan (Pegawai)

Sebelum (`codingansebelum/pertemuan04/Pewarisan`):
```bash
cd java && javac *.java && java Main
cd ../php && php main.php
```
Semua gaji `Rp0`, total beban gaji `Rp0`.

Sesudah (`PrakPBO/Prak 04`):
```bash
cd src/java && javac *.java && java Main
cd ../php && php main.php
```
Hasil Java: Ani (tetap) `Rp7,800,000.00`, Budi (kontrak) `Rp5,000,000.00`,
total `Rp12,800,000.00`. Angka Ani cocok dengan hitungan manual di Main
(6.000.000 + 30% = 7.800.000).

### Pertemuan 05: Polimorfisme (Bangun Datar)

Sebelum (`codingansebelum/pertemuan05`): semua luas dan keliling `0.00`.

Sesudah (`PrakPBO/Prak 05`):
```bash
cd java && javac *.java
java Main
java AntiPattern
java AntiPatternRefaktor
cd ../php && php main.php && php notifikasi.php
```
Hasil `java Main`: Lingkaran luas `153.94` keliling `43.98`, Persegi luas
`25.00` keliling `20.00`, Segitiga luas `9.0`, Trapesium luas `40.0`, dengan
total luas `227.94`.

### Pertemuan 06: Abstract Class, Interface, Enum, dan Trait (Kendaraan)

Sebelum (`codingansebelum/pertemuan06/.../starter`): bagian "Semua Movable"
hanya mencetak `(TODO 1 belum dikerjakan)`, biaya pengisian dan biaya enum
semuanya `Rp0`.

Sesudah (`PrakPBO/Prak 06`):
```bash
cd java && javac *.java && java Main
cd ../php && php main.php
```
Hasil: Mobil dan Sepeda sama-sama bisa `bergerak()`, hanya Mobil yang bisa
diisi bahan bakar (45 liter Bensin = `Rp540.000`). Enum `TipeBahanBakar` punya
harga sendiri: Bensin `Rp120.000`, Solar `Rp105.000`, Listrik `Rp25.000` untuk
10 satuan, dan hanya Listrik yang ramah lingkungan. Versi PHP menambah trait
`Loggable` yang dipakai kelas yang tidak sekerabat.

### Pertemuan 07: Pemodelan Relasi Objek dan UML (Perpustakaan)

Sebelum (`codingansebelum/perrtemuan7`): `Buku` tidak punya bab (`0 bab`),
`Jurusan` tidak punya mahasiswa (`0 mahasiswa`). Versi Java mencetak
`MASALAH: koleksi internal berhasil dikosongkan dari luar!`.

Sesudah (`PrakPBO/Prak 07`):
```bash
cd src/java && javac -d out $(find . -name "*.java") && java -cp out Main
cd ../php && php main.php
```
Hasil PHP: komposisi `Buku` memiliki 3 bab, agregasi `Jurusan` menaungi 2
mahasiswa. Setelah Budi dikeluarkan dari jurusan, jumlahnya menjadi 1, tetapi
objek Budi tetap ada. Kerangka class diagram ada di `src/uml/`.

### Pertemuan 09: Package, Namespace, dan Build Tool

Sebelum (`codingansebelum/pertemuan9`): kode awal Sistem Perpustakaan
sebelum struktur Maven dan Composer dirapikan.

Sesudah (`PrakPBO/Prak 09`):
```bash
cd java && mvn compile && mvn exec:java
cd ../php && composer install && php main.php
```
Java memakai konvensi domain terbalik `id.ac.univpancasila.perpustakaan`
dengan pustaka `asciitable` yang dikelola lewat `pom.xml`. PHP memakai
autoload PSR-4 lewat `composer.json`. Hasil PHP: tabel 3 buku dan 2 transaksi
peminjaman, lalu simulasi denda terlambat 5 hari sebesar `Rp5.000,00`.
Catatan pengujian error package/namespace ada di `percobaan.md`.

### Pertemuan 10: Exception Handling dan Pemrograman Defensif

Sebelum (`codingansebelum/pertemuan10`): `LibraryServiceKotor` dengan
`pinjam()` yang bersarang empat tingkat, pemanggil tidak tahu alasan gagal.

Sesudah (`PrakPBO/Prak 10`): `pinjam()` direfaktor memakai guard clause dan
melempar exception domain. Rincian ada di `PrakPBO/Prak 10/README.md`.

### Pertemuan 11: Collections, Generics, dan Unit Test Pertama

Sebelum (`codingansebelum/pertemuan11`): kerangka dengan bagian `TODO` yang
masih kosong.
- Java: `Repository<T>` belum berfungsi (`simpan()` tidak menyimpan apa pun,
  `cariById()` selalu `Optional.empty()`, `cariSemua()` selalu kosong,
  `hapus()` selalu `false`). Semua uji di `RepositoryTest` masih berisi
  `fail("TODO ... belum dikerjakan")`.
- PHP: `KoleksiBuku` belum berfungsi (`cariByIsbn()` selalu `null`, `filter()`
  mengembalikan koleksi kosong, `map()` kosong, `jumlahkan()` selalu `0.0`).
  Semua uji di `KoleksiBukuTest` masih memanggil `$this->fail(...)`.

Sesudah (`PrakPBO/Prak 11/src/starter`):
- Java: `Repository<T>` menyimpan data di `LinkedHashMap` dengan kunci dari
  fungsi `pengambilKunci`. `cariById()` mengembalikan `Optional.ofNullable(...)`
  agar tidak pernah `null`, `cariSemua()` mengembalikan `List.copyOf(...)`
  sehingga koleksi internal tidak bocor, dan `hapus()` bernilai `true` bila ada
  yang terhapus. `RepositoryTest` berisi 8 uji JUnit 5 (5 uji dari soal, 3 uji
  tambahan: kunci sama menimpa, hapus id yang tidak ada, dan urutan terjaga).
- PHP: `KoleksiBuku` memakai typed collection dengan `simpan()`,
  `cariByIsbn(): ?Buku`, `filter()` (`array_filter` + `array_values`),
  `map()`, `jumlahkan()` (`array_reduce`), dan `kelompokkan()`.
  `KoleksiBukuTest` berisi 10 uji PHPUnit (5 uji dari soal, 5 uji tambahan:
  larik berindeks urut, ISBN sama menimpa, filter tanpa indeks berlubang,
  pengelompokan berdasarkan penulis, dan iterasi dengan `foreach`).

Folder ini berisi berkas kerangka, bukan proyek Maven atau Composer utuh.
Untuk menjalankan ujinya:
```bash
# Java: tambahkan dependensi JUnit 5 dari pom-tambahan.xml ke pom.xml,
# letakkan Repository.java di src/main/java dan RepositoryTest.java
# di src/test/java pada package id.ac.univpancasila.perpustakaan, lalu:
mvn test

# PHP: di proyek Composer, pasang PHPUnit dan petakan autoload-dev, lalu:
composer require --dev phpunit/phpunit
./vendor/bin/phpunit tests
```

### Pertemuan 12: Refactoring dengan SOLID dan Repository Pattern

Sebelum: `LibraryService` dari sesi 10 dan 11 membuat penyimpanannya sendiri
(`new Repository<>(Buku::getNomorInduk)` di Java dan `new KoleksiBuku()` di
PHP), sehingga aturan bisnis terikat ke satu implementasi penyimpanan dan tidak
bisa diuji dengan repository palsu. Aturan denda per jenis anggota juga belum
dipisah. Tiga temuan pelanggaran SOLID (DIP, OCP, SRP) beserta tabel
sebelum dan sesudah ada di `REFACTORING.md`.

Sesudah (`PrakPBO/Prak 12/12-refactoring-dengan-solid-dan-repository-pattern/starter`):
- Repository pattern: interface `BookRepository` (`simpan`, `cariByIsbn`,
  `cariSemua`, `kurangiStok`) dengan implementasi `InMemoryBookRepository`.
  `LibraryService` menerimanya lewat constructor, jadi tidak ada lagi `new`
  untuk urusan penyimpanan di dalam service.
- Strategy pattern: interface `AturanDenda` (`hitung`, `nama`) dengan
  implementasi `DendaMahasiswa` (Rp1.000/hari), `DendaDosen` (Rp500/hari), dan
  `DendaBebas` untuk anggota kehormatan (selalu 0). `AturanDendaFactory`
  memilih aturan berdasarkan jenis anggota. `DendaAlumni` menjadi bukti
  Open-Closed: jenis keempat ditambahkan tanpa menyunting `LibraryService`.
- Dependency injection manual: seluruh objek dirakit di titik masuk program
  (`Main.java` dan `main.php`), yaitu `InMemoryBookRepository` dan `AturanDenda`
  disuntikkan ke `LibraryService`.
- Pengujian: `LibraryServiceTest` berisi 3 uji di Java dan 3 uji di PHP, termasuk
  uji dengan repository palsu yang selalu gagal untuk membuktikan Dependency
  Inversion. Laporan surefire di `java/target/surefire-reports` mencatat
  `RepositoryTest` 9 uji dan `LibraryServiceTest` 3 uji, semuanya tanpa gagal.

```bash
cd "Prak 12/12-refactoring-dengan-solid-dan-repository-pattern/starter"
cd java && mvn test
cd ../php && composer install && ./vendor/bin/phpunit tests && php main.php
```
