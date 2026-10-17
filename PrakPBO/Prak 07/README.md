# Laporan Praktikum 07: Relasi Objek dan UML (Sistem Perpustakaan)

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NPM** | 4525210029 |
| **Kelas** | PBO A 2025/2026 |
| **Dosen Pengampu** | Adi Wahyu Pribadi, S.Si., M.Kom |

---

## 1. Ringkasan Soal

Sistem Perpustakaan Universitas Pancasila (lihat [`src/deskripsi-kebutuhan.md`](src/deskripsi-kebutuhan.md)) dipakai untuk membedakan dua jenis relasi objek:

1. **Komposisi:** `Buku` memiliki `Bab`; bab tidak berarti di luar bukunya.
2. **Agregasi:** `Jurusan` menaungi `Mahasiswa`; mahasiswa tetap ada walau dilepas dari jurusan.
3. Koleksi internal tidak boleh bisa diubah dari luar, dan jumlah eksemplar tidak boleh negatif.
4. Kerangka class diagram ada di [`src/uml/perpustakaan-kerangka.puml`](src/uml/perpustakaan-kerangka.puml).

Modul dosen: [`PPT-Praktikum-07-pemodelan-relasi-objek-dan-uml.pptx`](PPT-Praktikum-07-pemodelan-relasi-objek-dan-uml.pptx)

---

## 2. Implementasi Java

**Kode akhir:** [src/java](src/java) (paket `model` dan `service`, serta `Main.java`)

Salinan kerangka awal tidak tersimpan di `codingansebelum`, jadi tidak ada tautan "sebelum".

Yang saya kerjakan:

- Membuat `Bab` sebagai kelas bersarang dengan constructor `private` di dalam `Buku`, sehingga hanya `Buku` yang bisa melahirkan bab (komposisi).
- Membuat `tambahBab(int, String)` menerima nomor dan judul, bukan objek `Bab`.
- Mengembalikan `List.copyOf(bab)` dari `getBab()` agar koleksi internal tidak bisa diubah dari luar.
- Membuat `Jurusan.daftarkan()` menerima objek `Mahasiswa` dari luar, menolak `null`, dan melewati NIM yang sudah terdaftar (agregasi).
- Membuat `keluarkan()` melepas mahasiswa dari daftar tanpa menghapus objeknya.
- Mengisi `PerpustakaanService` untuk tambah, cari, pinjam, dan kembalikan koleksi.

---

## 3. Implementasi PHP

**Kode akhir:** [src/php/relasi.php](src/php/relasi.php) dan [main.php](src/php/main.php)

- Memakai `enum JenisKeanggotaan` dan `enum StatusKoleksi` sebagai pengganti string bebas.
- Membuat `Bab` hanya dibentuk di dalam `Buku::tambahBab()`.
- Menolak jumlah eksemplar negatif di constructor `Buku`, serta melempar `UnderflowException` saat stok habis.
- Membuat `Jurusan` menerima `Mahasiswa` dari luar, sama seperti versi Java.

---

## 4. Bukti Eksekusi

Belum ada screenshot untuk pertemuan ini di folder `SSAN`. Perintah menjalankan:

```bash
# Java (Git Bash)
cd src/java
javac -d out $(find . -name "*.java")
java -cp out Main

# PHP
cd src/php
php main.php
```

Keluaran Java:

```
=== Komposisi: Buku memiliki Bab ===
  Pemrograman Berorientasi Objek   A. W. Pribadi    [3 eks, 3 bab]
    Bab 1: Paradigma Objek
    Bab 2: Enkapsulasi
    Bab 3: Pewarisan dan Polimorfisme

  Mencoba mengubah koleksi internal dari luar...
    Ditolak — koleksi bab tidak bisa diubah dari luar. Benar.

=== Agregasi: Jurusan menaungi Mahasiswa ===
  TI - Teknik Informatika (2 mahasiswa)
  Setelah Budi pindah: TI - Teknik Informatika (1 mahasiswa)
  Budi tetap ada sebagai objek: 2024002 Budi Santoso
```

Keluaran PHP (`php main.php`):

```
=== Komposisi: Buku memiliki Bab ===
  Pemrograman Berorientasi Objek   A. W. Pribadi    [3 eks, 3 bab, status: TERSEDIA]
    Bab 1: Paradigma Objek
    Bab 2: Enkapsulasi
    Bab 3: Pewarisan dan Polimorfisme

=== Agregasi: Jurusan menaungi Mahasiswa ===
  TI - Teknik Informatika (2 mahasiswa)
  Setelah Budi pindah: TI - Teknik Informatika (1 mahasiswa)
  Budi tetap ada sebagai objek: 2024002 Budi Santoso (MAHASISWA)
```

Yang belum ada: `analisis.md`, `bukti-relasi.md`, serta diagram `usecase.puml`, `class.puml`, dan `sequence-pinjam.puml`.

---

## 5. Kesimpulan

Komposisi terlihat dari bab yang hanya bisa dibuat oleh `Buku` dan koleksinya yang ditolak diubah dari luar, sedangkan agregasi terlihat dari `Mahasiswa` yang tetap hidup setelah keluar dari `Jurusan`.
