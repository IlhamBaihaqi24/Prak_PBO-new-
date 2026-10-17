**Nama:** Ilham Baihaqi
**NPM:** 4525210029
**Kelas:** PBO A 2025/2026
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom

---

## 1. Peta Isi Repositori

```
Prak PBO/
├── codingansebelum/        kode awal dari dosen (kondisi SEBELUM)
│   └── pertemuan02 … pertemuan06
├── PrakPBO/                hasil pengerjaan saya (kondisi SESUDAH)
│   ├── Prak 01/            laporan Git dan GitHub (.docx)
│   ├── pert 02/            java/  php/
│   ├── prak 03/            java/  php/
│   ├── Prak 04/            src/java  src/php  bin
│   ├── Prak 05/            java/  php/
│   ├── Prak 06/            java/  php/
│   └── Prak 07/            src/java  src/php  src/uml  lib
├── SSAN - sebelum/         images-java/  images-php/
└── SSAN - sesudah/         images-java/  images-php/
```

---

## 2. Yang Dibutuhkan

- JDK 21
- PHP 8.3
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

Sebelum (`codingansebelum/pertemuan05`):
```bash
javac *.java && java Main
php main.php
```
Luas dan keliling semua bentuk `0.00`, total luas `0.00`.

Sesudah (`PrakPBO/Prak 05`):
```bash
cd java && javac *.java
java Main
java AntiPattern
java AntiPatternRefaktor
cd ../php && php main.php
```
Hasil Java (`Main`): Lingkaran `153.94`, Persegi `25.00`, Segitiga (3,4,5)
`6.00`, total luas `184.94`, dan downcasting ke `Lingkaran` menampilkan
jari-jari `7.0`. `AntiPattern` dan `AntiPatternRefaktor` sama-sama menghasilkan
total `184.94`; bedanya, versi refaktor tidak memakai `if-else` berantai.
`php/notifikasi.php` adalah latihan mandiri (Email, SMS, WhatsApp).

### Pertemuan 06: Abstract Class, Interface, Enum, dan Trait (Kendaraan)

Sebelum (`codingansebelum/pertemuan06/.../starter`):
```bash
cd java && javac *.java && java Main
cd ../php && php main.php
```
- Java: muncul `(TODO 1 belum dikerjakan)`, biaya isi bahan bakar `Rp0`.
- PHP: kecepatan `0 km/jam`, nama bahan bakar tercetak `?`, biaya `Rp0`.

Sesudah (`PrakPBO/Prak 06`):
```bash
cd java && javac *.java && java Main
cd ../php && php main.php
```
Hasil Java: Toyota Avanza melaju dengan kecepatan maksimum `180 km/jam`,
Sepeda dikayuh, isi penuh Bensin `Rp540,000`. Biaya 10 satuan: Bensin
`Rp120,000`, Solar `Rp105,000`, Listrik `Rp25,000` (hanya Listrik yang ramah
lingkungan). PHP menampilkan hasil yang sama, ditambah baris log dari trait
`Loggable` yang dipakai kelas tak sekerabat.

### Pertemuan 07: Relasi Objek dan UML (Sistem Perpustakaan)

Sebelum: belum ada salinannya di `codingansebelum`. Kerangka dari dosen
berisi komentar `TODO` pada `Buku`, `Jurusan`, dan `PerpustakaanService`.

Sesudah (`PrakPBO/Prak 07`):

Java (Linux/macOS/Git Bash):
```bash
cd "src/java"
javac -d out $(find . -name "*.java")
java -cp out Main
```
Java (Windows CMD):
```bat
cd src\java
dir /s /b *.java > sumber.txt
javac -d out @sumber.txt
java -cp out Main
```
PHP:
```bash
cd src/php && php main.php
```

Hasil:
- Komposisi `Buku` dan `Bab`: tiga bab tercetak, lalu percobaan mengosongkan
  `getBab()` dari luar ditolak (`Ditolak ... koleksi bab tidak bisa diubah dari luar`).
- Agregasi `Jurusan` dan `Mahasiswa`: jurusan TI semula `2 mahasiswa`, setelah
  Budi dikeluarkan menjadi `1 mahasiswa`, dan objek Budi (`2024002 Budi Santoso`)
  tetap ada.
- Versi PHP juga menampilkan status koleksi (`TERSEDIA`) dan `enum`
  `StatusKoleksi` serta `JenisKeanggotaan`.

Isi folder lain: `src/deskripsi-kebutuhan.md` (kebutuhan sistem),
`src/uml/perpustakaan-kerangka.puml` (kerangka class diagram), dan berkas PPT
praktikum.

---

## 4. Screenshot

Screenshot hasil jalan ada di `SSAN - sebelum` dan `SSAN - sesudah`, dibagi
`images-java` dan `images-php`, dengan nama berkas `PertemuanN.png`
(N = nomor pertemuan).
