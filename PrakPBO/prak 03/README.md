# Laporan Praktikum 03: Constructor, Static, dan Konstanta

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NPM** | 4525210029 |
| **Kelas** | PBO A 2025/2026 |
| **Dosen Pengampu** | Adi Wahyu Pribadi, S.Si., M.Kom |

---

## 1. Ringkasan Soal

Kelas `RekeningBank` mencatat nomor, pemilik, dan saldo. Ketentuannya:

1. Ada dua cara membuat rekening: tanpa saldo awal dan dengan saldo awal.
2. Jumlah rekening yang dibuat dihitung lewat anggota `static`.
3. Bunga tahunan 2,5%, biaya admin Rp5.000, dan batas tarik sekali Rp5.000.000 disimpan sebagai konstanta.
4. Setoran dan penarikan harus positif, penarikan tidak boleh melebihi saldo, dan saldo tidak boleh negatif.

---

## 2. Implementasi Java

**Kode awal:** [RekeningBank.java (sebelum)](../../codingansebelum/pertemuan03/RekeningBank.java)
**Kode akhir:** [RekeningBank.java (sesudah)](java/RekeningBank.java)

Kondisi awal: jumlah rekening `-1`, setoran tidak menambah saldo, dan penarikan berlebih lolos.

Yang saya kerjakan:

- Membuat dua constructor, satu dengan `saldoAwal` dan satu tanpa saldo awal.
- Menyimpan bunga, biaya admin, dan batas tarik sebagai `static final`.
- Menolak `setor()` dan `tarik()` bila jumlahnya tidak positif, dan `tarik()` juga menolak saldo tidak cukup serta jumlah di atas batas.
- Membuat `potongBiayaAdmin()` memakai `Math.max(0, ...)` agar saldo tidak turun di bawah nol.
- Mengisi `bungaSetahun()` dan `getJumlahRekening()` sebagai method `static`.

Yang masih kurang: constructor tanpa saldo awal belum menaikkan `jumlahRekening`, jadi program uji menampilkan `2` padahal seharusnya `3`.

---

## 3. Implementasi PHP

**Kode awal:** [RekeningBank.php (sebelum)](../../codingansebelum/pertemuan03/RekeningBank.php)
**Kode akhir:** [RekeningBank.php (sesudah)](php/RekeningBank.php)

Bagian PHP belum saya kerjakan: `setor()`, `tarik()`, `potongBiayaAdmin()`, `getJumlahRekening()`, dan `bungaSetahun()` masih kerangka, sedangkan `rekeningPelajar()` masih melempar `TODO 5 belum dikerjakan`. Karena itu `php main.php` berhenti dengan Fatal error.

---

## 4. Bukti Eksekusi

### Java

Sebelum perbaikan:

![Java sebelum](<../../SSAN - sebelum/images-java/Pertemuan3.png>)

Sesudah perbaikan (`java Main`):

![Java sesudah](<../../SSAN - sesudah/images-java/Pertemuan3.png>)

```
Jumlah rekening di awal: 0
Rekening[111] Ani            Rp1,000,000.00
Rekening[222] Budi           Rp0.00
Rekening[333] Citra          Rp250,000.00
Jumlah rekening sekarang: 2   (seharusnya 3, bukan 4)

=== Operasi ===
Setelah setor 500.000  -> Rekening[111] Ani            Rp1,500,000.00
  Ditolak: Saldo tidak mencukupi
Budi setelah potong admin: Rekening[222] Budi           Rp0.00   (saldo tidak boleh negatif)
Bunga setahun dari saldo Ani: Rp37,500.00
```

### PHP

Sebelum perbaikan:

![PHP sebelum](<../../SSAN - sebelum/images-php/Pertemuan3.png>)

Tangkapan kode `main.php` yang dipakai:

![PHP sesudah](<../../SSAN - sesudah/images-php/Pertemuan3.png>)

---

## 5. Kesimpulan

Versi Java sudah menolak setoran dan penarikan yang tidak sah, menjaga saldo tidak negatif, dan menghitung bunga lewat method `static`. Yang tersisa: menaikkan penghitung di constructor kedua dan menyelesaikan versi PHP.
