# Laporan Praktikum 05: Polimorfisme

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NPM** | 4525210029 |
| **Kelas** | PBO A 2025/2026 |
| **Dosen Pengampu** | Adi Wahyu Pribadi, S.Si., M.Kom |

---

## 1. Ringkasan Soal

Bangun datar dimodelkan dengan kelas induk abstrak `BangunDatar` yang punya `luas()` dan `keliling()`. Turunannya: `Lingkaran`, `Persegi`, `Segitiga`, dan `Trapesium`. Selain itu:

1. Satu perulangan harus bisa menghitung semua bentuk tanpa `if` atau `instanceof`.
2. Program `AntiPattern` (if-else berantai) harus direfaktor menjadi polimorfik.
3. Latihan mandiri PHP: kelas `Notifikasi` dengan `Email`, `SMS`, dan `WhatsApp`.

---

## 2. Implementasi Java

**Kode awal:** [pertemuan05 (sebelum)](../../codingansebelum/pertemuan05)
**Kode akhir:** [java/ (sesudah)](java)

Kondisi awal: luas dan keliling semua bentuk `0.00`.

Yang saya kerjakan:

- Mengisi `luas()` dan `keliling()` di `Lingkaran` dan `Persegi`.
- Menambah `Segitiga` (alas, tinggi, sisi miring) dan `Trapesium` (lima ukuran) sebagai kelas turunan baru.
- Menjalankan semua bentuk lewat satu array bertipe `BangunDatar`.
- Merefaktor `AntiPattern` menjadi `AntiPatternRefaktor`: interface `Bangun` dengan tiga `record`, sehingga bentuk baru cukup menambah satu kelas.

---

## 3. Implementasi PHP

**Kode awal:** [BangunDatar.php (sebelum)](../../codingansebelum/pertemuan05/BangunDatar.php)
**Kode akhir:** [BangunDatar.php (sesudah)](php/BangunDatar.php)

Hierarkinya sama dengan Java, ditambah `notifikasi.php` untuk latihan mandiri. Satu hal perlu dibereskan: ada teks `Ini bangun datar` di baris pertama `BangunDatar.php` dan `Ini notifikasi` di `notifikasi.php`, sebelum `<?php`, sehingga PHP 8.3 berhenti dengan Fatal error karena `declare(strict_types=1)` tidak lagi menjadi pernyataan pertama. Selain itu, `BangunDatar.php` masih memuat kode demo di bagian bawah yang ikut mencetak satu blok tambahan.

---

## 4. Bukti Eksekusi

### Java

Sebelum perbaikan:

![Java sebelum](<../../SSAN - sebelum/images-java/Pertemuan5.png>)

![Java sebelum 2](<../../SSAN - sebelum/images-java/Pertemuan5 (1).png>)

![Java sebelum 3](<../../SSAN - sebelum/images-java/Pertemuan5 (2).png>)

Sesudah perbaikan:

![Java sesudah](<../../SSAN - sesudah/images-java/Pertemuan5.png>)

Keluaran `java Main`:

```
=== Bangun Datar ===
  Lingkaran    luas=    153.94  keliling=     43.98
  Persegi      luas=     25.00  keliling=     20.00
  Segitiga(alas=3.0, tinggi=6.0, sisi=5.0) luas=9.0
  Trapesium(sisiAtas=10.0, sisiBawah=6.0, tinggi=5.0, sisiKiri=5.0, sisiKanan=4.0) luas=40.0

  Total luas: 227.94
```

`java AntiPattern` dan `java AntiPatternRefaktor` sama-sama menghasilkan total luas `184.94`; bedanya hanya cara menghitungnya.

### PHP

Sebelum perbaikan:

![PHP sebelum](<../../SSAN - sebelum/images-php/Pertemuan5.png>)

Sesudah perbaikan:

![PHP sesudah](<../../SSAN - sesudah/images-php/Pertemuan5.png>)

---

## 5. Kesimpulan

Dengan polimorfisme, `Main` cukup memanggil `luas()` pada tipe induk, dan menambah bentuk baru tidak perlu mengubah kode lama. Hasil refaktor `AntiPattern` sama dengan versi aslinya (`184.94`) tetapi lebih mudah dikembangkan.
