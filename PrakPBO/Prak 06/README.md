# Laporan Praktikum 06: Abstract Class, Interface, Enum, dan Trait

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NPM** | 4525210029 |
| **Kelas** | PBO A 2025/2026 |
| **Dosen Pengampu** | Adi Wahyu Pribadi, S.Si., M.Kom |

---

## 1. Ringkasan Soal

Kendaraan dimodelkan dengan campuran abstraksi:

1. `Kendaraan` adalah kelas abstrak yang menyimpan merek dan tahun.
2. Interface `Movable` untuk yang bisa bergerak dan `Fuelable` untuk yang bisa diisi bahan bakar.
3. `Mobil` memakai keduanya, sedangkan `Sepeda` hanya `Movable`.
4. Enum `TipeBahanBakar` (Bensin, Solar, Listrik) menyimpan label, harga, dan perilakunya.
5. PHP: trait `Loggable` dipakai kelas yang tidak sekerabat.

---

## 2. Implementasi Java

**Kode awal:** [starter/java (sebelum)](../../codingansebelum/pertemuan06/06-abstract-class-interface-enum-dan-trait/starter/java)
**Kode akhir:** [java/ (sesudah)](java)

Kondisi awal: bagian `Movable` belum jalan (`TODO 1 belum dikerjakan`) dan semua biaya `Rp0`.

Yang saya kerjakan:

- Melengkapi `Mobil` (4 roda, kecepatan 180, isi bahan bakar dengan cek kapasitas) dan `Sepeda` (2 roda, kecepatan 30).
- Membuat `Sepeda` meng-override `ringkasanGerak()` dari method `default` di `Movable`.
- Mengisi `biayaPengisian()` sebagai harga dikali jumlah, dan `ramahLingkungan()` yang bernilai `true` hanya untuk `LISTRIK`.

---

## 3. Implementasi PHP

**Kode awal:** [starter/php (sebelum)](../../codingansebelum/pertemuan06/06-abstract-class-interface-enum-dan-trait/starter/php)
**Kode akhir:** [php/abstraksi.php (sesudah)](php/abstraksi.php)

- Menyatukan interface, enum, trait, dan kelas dalam satu berkas `abstraksi.php`.
- Memakai `enum TipeBahanBakar: string` dengan method biaya dan ramah lingkungan.
- Menyisipkan trait `Loggable` ke `Mobil` lewat `use`, sehingga muncul baris log berstempel waktu.

---

## 4. Bukti Eksekusi

### Java

Sesudah perbaikan (`java Main`):

![Java sesudah](<../../SSAN - sesudah/images-java/Pertemuan6.png>)

```
=== Semua Movable ===
Toyota Avanza melaju di jalan raya
    kecepatan maksimum 180 km/jam
Sepeda sedang dikayuh.
    Sepeda bergerak dengan cara dikayuh.

=== Hanya yang Fuelable ===
Bahan bakar berhasil diisi 45.0 liter.
  Diisi penuh Bensin ? biaya Rp540,000

=== Enum punya perilaku ===
  Bensin   ramah lingkungan? false  biaya 10 satuan: Rp120,000
  Solar    ramah lingkungan? false  biaya 10 satuan: Rp105,000
  Listrik  ramah lingkungan? true   biaya 10 satuan: Rp25,000
```

### PHP

Sebelum perbaikan:

![PHP sebelum 1](<../../SSAN - sebelum/images-php/Pertemuan6 (1).png>)

![PHP sebelum 2](<../../SSAN - sebelum/images-php/Pertemuan6 (2).png>)

Sesudah perbaikan (`php main.php`):

![PHP sesudah 1](<../../SSAN - sesudah/images-php/Pertemuan6 (1).png>)

![PHP sesudah 2](<../../SSAN - sesudah/images-php/Pertemuan6 (2).png>)

---

## 5. Kesimpulan

Kelas abstrak menampung kode yang sama, interface membagi kemampuan, enum menyimpan data tetap beserta perilakunya, dan trait membagi kode ke kelas yang tidak sekerabat. Hasil Java dan PHP konsisten: biaya isi Bensin `Rp540.000` dan hanya Listrik yang ramah lingkungan.
