# Praktikum 05 — Polimorfisme

---

**Nama:** Ilham Baihaqi  
**NPM:** 4525210029  
**Kelas:** PBO A 2025/2026  
**Dosen Pengampu:** Adi Wahyu Pribadi, S.Si., M.Kom

---

Studi kasus: bangun datar dengan kelas induk abstrak `BangunDatar` (menghitung luas dan keliling).

## Isi folder

| Folder | Berkas | Keterangan |
|---|---|---|
| `java/` | `BangunDatar`, `Lingkaran`, `Persegi`, `Segitiga`, `Trapesium`, `Main` | Hierarki bangun datar |
| `java/` | `AntiPattern`, `AntiPatternRefaktor` | Contoh tanpa polimorfisme dan versi refaktornya |
| `php/` | `BangunDatar.php`, `main.php` | Hierarki bangun datar versi PHP |
| `php/` | `notifikasi.php` | Latihan mandiri: Email, SMS, WhatsApp |

## Konsep yang dipelajari

- Upcasting: variabel bertipe induk, objek bertipe turunan.
- Satu perulangan bisa dipakai untuk semua bentuk tanpa `if` / `instanceof`.
- Refaktor dari `if-else` berantai menjadi polimorfik.

## Cara menjalankan

Java:
```bash
cd java
javac *.java
java Main
java AntiPattern
java AntiPatternRefaktor
```

PHP:
```bash
cd php
php main.php
php notifikasi.php
```
