# Praktikum 04 — Pewarisan (Inheritance)

---

**Nama:** Ilham Baihaqi  
**NPM:** 4525210029  
**Kelas:** PBO A 2025/2026  
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom

---

Studi kasus: hierarki pegawai dengan kelas induk abstrak `Pegawai`.

## Isi folder

| Folder | Keterangan |
|---|---|
| `src/java/` | Kode Java: `Pegawai`, `PegawaiTetap`, `PegawaiKontrak`, `Main` |
| `src/php/` | Kode PHP: `pegawai.php` (semua kelas) dan `main.php` |
| `bin/` | Hasil kompilasi Java (`.class`) |
| `.vscode/` | Pengaturan VS Code |

## Konsep yang dipelajari

- `abstract class` dan method abstract (`jenis()`).
- `extends` dan pemanggilan konstruktor induk (`super` / `parent::`).
- Override method `hitungGaji()`.
- `PegawaiTetap`: gaji pokok + tunjangan masa kerja 2% per tahun (maksimal 40%).

## Cara menjalankan

Java:
```bash
cd src/java
javac *.java
java Main
```

PHP:
```bash
cd src/php
php main.php
```
