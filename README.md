**Nama:** Ilham Baihaqi
**NPM:** 4525210029
**Kelas:** PBO A 2025/2026
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom

---

## 1. Peta Isi Repositori

```
Prak PBO/
├── codingansebelum/       
│   ├── pertemuan02 … pertemuan06
├── PrakPBO/                hasil pengerjaan saya (kondisi SESUDAH)
│   ├── Prak 01/            laporan Git dan GitHub (.docx)
│   ├── pert 02/            java/  php/
│   ├── prak 03/            java/  php/
│   ├── Prak 04/            src/java  src/php  bin
│   ├── Prak 05/            java/  php/
│   └── Prak 06/            java/  php/
├── SSAN - sebelum/         images-java/  images-php/
└── SSAN - sesudah/         images-java/  images-php/
```

Catatan: nama folder `Prak 04` memakai `src/java` dan `src/php`, sedangkan
yang lain langsung `java/` dan `php/`. Nama folder juga mengandung spasi, jadi
apit path dengan tanda kutip di terminal.

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

Sebelum (`codingansebelum/pertemuan05`): semua luas dan keliling `0.00`.

Sesudah (`PrakPBO/Prak 05`):
```bash
cd java && javac *.java
java Main
java AntiPattern
java AntiPatternRefaktor
cd ../php && php main.php && php
