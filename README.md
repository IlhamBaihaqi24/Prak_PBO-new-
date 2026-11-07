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
│   ├── perrtemuan7         (nama folder memang tertulis dengan dua "r")
│   ├── pertemuan9
│   └── pertemuan10
├── PrakPBO/                hasil pengerjaan saya (kondisi SESUDAH)
│   ├── Prak 01/            laporan Git dan GitHub (.docx)
│   ├── pert 02/            java/  php/
│   ├── prak 03/            java/  php/
│   ├── Prak 04/            src/java  src/php  bin
│   ├── Prak 05/            java/  php/
│   ├── Prak 06/            java/  php/
│   ├── Prak 07/            src/java  src/php  src/uml
│   ├── Prak 09/            java/ (Maven)  php/ (Composer)
│   └── Prak 10/            java/ (Maven)  php/ (Composer)
├── SSAN - sebelum/         images-java/  images-php/  (Pertemuan2 … Pertemuan10)
└── SSAN - sesudah/         images-java/  images-php/  (Pertemuan2 … Pertemuan10)
```

Catatan:
- Folder `Prak 04` dan `Prak 07` memakai `src/java` dan `src/php`, sedangkan
  `Prak 09` dan `Prak 10` memakai `java/` dan `php/` dengan struktur Maven dan
  Composer. Sisanya langsung `java/` dan `php/`.
- Nama folder mengandung spasi, jadi apit path dengan tanda kutip di terminal.
- Pertemuan 8 adalah ujian tengah semester (live coding), jadi tidak ada
  folder kode untuk pertemuan itu.
- Screenshot yang punya dua gambar dinamai `(1)` untuk kode dan `(2)` untuk
  hasil eksekusi. Pertemuan 9 dan 10 versi Java hanya berisi gambar kode
  (lihat bagian 4).

---

## 2. Yang Dibutuhkan

- JDK 21 (Prak 09 dan 10 memakai Maven, dengan `maven.compiler.source` 17)
- Apache Maven 3.9+ (untuk Prak 09 dan 10)
- PHP 8.3
- Composer (untuk Prak 09 dan 10, jalankan `composer install` di folder `php/`)
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

---

## 4. Daftar Screenshot

| Pertemuan | Java | PHP |
|---|---|---|
| 02 – 05 | `Pertemuan2` … `Pertemuan5` (sebelum dan sesudah) | sama |
| 06 | kode dan hasil (sebelum), kode (sesudah) | kode dan hasil |
| 07 | kode dan hasil (sebelum), kode (sesudah) | kode dan hasil |
| 09 | kode | kode dan hasil |
| 10 | kode | kode |

Pertemuan 9 dan 10 versi Java hanya berisi kode karena butuh Maven dan
pustaka eksternal, sedangkan Pertemuan 10 berupa menu interaktif.
