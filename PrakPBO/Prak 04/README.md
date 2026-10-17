# Laporan Praktikum 04: Pewarisan (Inheritance)

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NPM** | 4525210029 |
| **Kelas** | PBO A 2025/2026 |
| **Dosen Pengampu** | Adi Wahyu Pribadi, S.Si., M.Kom |

---

## 1. Ringkasan Soal

Sistem penggajian memakai kelas induk abstrak `Pegawai` dengan dua turunan:

1. `PegawaiTetap`: gaji pokok ditambah tunjangan masa kerja 2% per tahun, maksimal 40%.
2. `PegawaiKontrak`: menerima gaji pokok apa adanya.
3. Gaji pokok tidak boleh negatif.
4. Setiap jenis pegawai harus menyebut jenisnya lewat method abstrak `jenis()`.

---

## 2. Implementasi Java

**Kode awal:** [Pewarisan/java (sebelum)](../../codingansebelum/pertemuan04/Pewarisan/java)
**Kode akhir:** [src/java (sesudah)](src/java)

Kondisi awal: semua gaji `Rp0` dan total beban gaji `Rp0`.

Yang saya kerjakan:

- Menolak gaji pokok negatif di constructor `Pegawai`, dan `hitungGaji()` induk mengembalikan gaji pokok.
- Membuat `PegawaiTetap` memanggil `super(...)` lalu meng-override `hitungGaji()` dengan tunjangan `Math.min(masaKerja * 2%, 40%)`.
- Membuat `PegawaiKontrak` memakai `hitungGaji()` bawaan induk dan hanya menambah `bulanKontrak`.
- Mengimplementasikan `jenis()` di kedua turunan (`TETAP` dan `KONTRAK`).

---

## 3. Implementasi PHP

**Kode awal:** [Pewarisan/php (sebelum)](../../codingansebelum/pertemuan04/Pewarisan/php)
**Kode akhir:** [src/php (sesudah)](src/php)

Bagian PHP belum selesai:

- `hitungGaji()` di `Pegawai` dan `PegawaiTetap` masih mengembalikan `0` (bertanda `// ganti`).
- `main.php` memakai kelas `Dosen` dan `PegawaiHarian` yang belum dibuat.
- `main.php` memanggil `Pegawai.php`, sedangkan berkasnya bernama `pegawai.php`; di Windows tidak masalah, tetapi di Linux berkas tidak akan ditemukan.

---

## 4. Bukti Eksekusi

### Java

Sebelum perbaikan:

![Java sebelum](<../../SSAN - sebelum/images-java/Pertemuan4.png>)

Sesudah perbaikan (`java Main`):

![Java sesudah](<../../SSAN - sesudah/images-java/Pertemuan4.png>)

```
=== Daftar Gaji ===
  19870102010    TETAP     Ani Lestari          Rp7,800,000.00
  K-2024-007     KONTRAK   Budi Santoso         Rp5,000,000.00

  Total beban gaji: Rp12,800,000.00
```

Gaji Ani cocok dengan hitungan manual: 6.000.000 + 30% = 7.800.000.

### PHP

Sebelum perbaikan:

![PHP sebelum](<../../SSAN - sebelum/images-php/Pertemuan4.png>)

Sesudah (`php main.php`):

![PHP sesudah 1](<../../SSAN - sesudah/images-php/Pertemuan4 (1).png>)

![PHP sesudah 2](<../../SSAN - sesudah/images-php/Pertemuan4 (2).png>)

---

## 5. Kesimpulan

Dengan pewarisan, rumus gaji tiap jenis pegawai cukup ditulis sekali di kelasnya dan dipanggil lewat tipe `Pegawai`. Versi Java sudah benar; versi PHP masih perlu dilengkapi.
