# Laporan Praktikum 02: Kelas, Objek, dan Enkapsulasi

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NPM** | 4525210029 |
| **Kelas** | PBO A 2025/2026 |
| **Dosen Pengampu** | Adi Wahyu Pribadi, S.Si., M.Kom |

---

## 1. Ringkasan Soal

Kelas `Mahasiswa` menyimpan NIM, nama, dan tiga nilai (tugas, UTS, UAS). Aturan yang harus dijaga:

1. NIM tidak boleh kosong dan tidak berubah setelah objek jadi.
2. Setiap nilai harus berada di antara 0 dan 100.
3. Nilai akhir = 30% tugas + 30% UTS + 40% UAS.
4. Huruf mutu: ≥ 80 A, ≥ 70 B, ≥ 60 C, ≥ 50 D, selain itu E.

---

## 2. Implementasi Java

**Kode awal:** [Mahasiswa.java (sebelum)](../../codingansebelum/pertemuan02/Mahasiswa.java)
**Kode akhir:** [Mahasiswa.java (sesudah)](java/Mahasiswa.java)

Kondisi awal: nilai akhir selalu `0.00`, mutu `?`, dan data salah tetap diterima.

Yang saya kerjakan:

- Menjadikan `nim` dan `nama` sebagai `private final` tanpa `setNim()`, sehingga identitas tidak bisa diganti.
- Menaruh bobot di konstanta `BOBOT_TUGAS`, `BOBOT_UTS`, `BOBOT_UAS`, bukan angka langsung di method.
- Menolak NIM `null` atau kosong di constructor dengan `IllegalArgumentException`.
- Memusatkan cek rentang nilai di method privat `pastikanNilaiSah()` yang dipanggil untuk ketiga nilai.
- Menghitung `nilaiAkhir()` dari nilai dikali bobot, lalu `hurufMutu()` memetakannya ke A sampai E dengan `if`.

---

## 3. Implementasi PHP

**Kode awal:** [Mahasiswa.php (sebelum)](../../codingansebelum/pertemuan02/Mahasiswa.php)
**Kode akhir:** [Mahasiswa.php (sesudah)](php/Mahasiswa.php)

Logikanya sama dengan Java, hanya sintaksnya yang berbeda:

- Memakai constructor property promotion, dengan `readonly` pada `$nim` dan `$nama` sebagai padanan `final`.
- Memeriksa NIM setelah `trim()` dan melempar `InvalidArgumentException` bila kosong.
- Memakai `pastikanNilaiSah()` untuk batas 0 sampai 100.
- Memakai `match (true)` pada `hurufMutu()`.

---

## 4. Bukti Eksekusi

### Java

Sebelum perbaikan:

![Java sebelum](<../../SSAN - sebelum/images-java/Pertemuan2.png>)

Sesudah perbaikan (`java Main`):

![Java sesudah](<../../SSAN - sesudah/images-java/Pertemuan2.png>)

### PHP

Sebelum perbaikan:

![PHP sebelum](<../../SSAN - sebelum/images-php/Pertemuan2.png>)

Sesudah perbaikan (`php main.php`):

![PHP sesudah](<../../SSAN - sesudah/images-php/Pertemuan2.png>)

Teks keluaran sesudah perbaikan (Java):

```
=== Rekap Nilai ===
  2024001    Ani Lestari        akhir= 84.90  mutu=A
  2024002    Budi Santoso       akhir= 59.30  mutu=D
  2024003    Citra Wijaya       akhir= 92.00  mutu=A

=== Objek menolak data yang melanggar aturan ===
  Ditolak: Nilai tugas harus di rentang 0.0-100.0, diberikan: 150.0
  Ditolak: NIM tidak boleh kosong atau null
```

---

## 5. Kesimpulan

Aturan data kini dijaga oleh kelas `Mahasiswa` sendiri, sehingga objek dengan nilai 150 atau NIM kosong tidak pernah terbentuk. Java dan PHP sama-sama menghasilkan nilai akhir dan mutu yang benar.
