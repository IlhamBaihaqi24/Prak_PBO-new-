# Praktikum 06 — Abstract Class, Interface, Enum, dan Trait

---

**Nama:** Ilham Baihaqi  
**NPM:** 4525210029  
**Kelas:** PBO A 2025/2026  
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom

---

Studi kasus: kendaraan (`Mobil`, `Sepeda`) dengan kemampuan bergerak dan diisi bahan bakar.

## Isi folder

| Folder | Berkas | Keterangan |
|---|---|---|
| `java/` | `Kendaraan`, `Movable`, `Fuelable`, `TipeBahanBakar`, `Mobil`, `Sepeda`, `Main` | Versi Java |
| `php/` | `abstraksi.php`, `main.php` | Versi PHP (semua kelas di satu berkas) |

## Konsep yang dipelajari

- `abstract class` `Kendaraan` untuk kode yang sama di semua kendaraan.
- Interface `Movable` dan `Fuelable` (sepeda bergerak tetapi tidak butuh bahan bakar).
- Enum `TipeBahanBakar` (Bensin, Solar, Listrik) yang punya label, harga, dan method.
- Trait `Loggable` di PHP.

## Cara menjalankan

Java:
```bash
cd java
javac *.java
java Main
```

PHP:
```bash
cd php
php main.php
```
