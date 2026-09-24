# pertemuan-04-validasi-2225250113

## Identitas

**Nama:** Masya Bantani

**NIM:** 225250113

**Kelas:** 3E 

 **Jurusan:** Pendidikan Matematika

---

## Deskripsi

Pertemuan 04 membahas **seleksi multi-kondisi dan validasi input dalam Python**. Pada pertemuan ini, program dikembangkan menggunakan struktur `if-elif-else` untuk menangani beberapa kondisi yang saling berkaitan.

Selain membuat klasifikasi berdasarkan kondisi tertentu, program juga dilengkapi dengan **validasi input** agar masukan pengguna sesuai dengan tipe data dan rentang yang telah ditentukan.

Materi dan latihan pada pertemuan ini meliputi:

* Seleksi multi-kondisi menggunakan `if-elif-else`.
* Validasi tipe data menggunakan `try-except`.
* Validasi rentang nilai.
* Klasifikasi berdasarkan beberapa kondisi.
* Pengujian program menggunakan beberapa kasus uji.
* Dokumentasi hasil program menggunakan README.
* Pengelolaan kode menggunakan Git dan GitHub.

---

## Tujuan Pembelajaran

Setelah menyelesaikan tugas pada pertemuan ini, diharapkan dapat:

1. Membuat program dengan struktur `if-elif-else`.
2. Membuat kondisi yang saling eksklusif dan mencakup seluruh kemungkinan.
3. Melakukan validasi input berdasarkan tipe data.
4. Melakukan validasi input berdasarkan rentang nilai.
5. Menggunakan `try-except` untuk menangani input yang tidak sesuai.
6. Menguji program menggunakan kasus valid dan tidak valid.
7. Mendokumentasikan proses pengambilan keputusan dan hasil pengujian.
8. Mengelola file program menggunakan Git dan GitHub.

---

## Struktur Repository

```text
pertemuan-04-validasi-NIM/
│
├── README.md
├── .gitignore
│
├── latihan/
│   ├── 01_predikat_nilai.py
│   ├── 02_kategori_bilangan.py
│   ├── 03_validasi_rentang.py
│   ├── 04_validasi_tipe.py
│   └── 05_klasifikasi_segitiga_sudut.py
│
└── praktik/
    └── validasi_klasifikasi_nilai.py
```

---

# Latihan

## 1. Predikat Nilai

Program menerima nilai akhir dan menentukan predikat berdasarkan rentang nilai.

### Tabel Keputusan

| Predikat | Syarat          | Contoh Masukan |
| -------- | --------------- | -------------: |
| A        | Nilai ≥ 85      |             92 |
| B        | 70 ≤ Nilai < 85 |             75 |
| C        | 60 ≤ Nilai < 70 |             60 |
| D        | 50 ≤ Nilai < 60 |             50 |
| E        | Nilai < 50      |           49.9 |

### Kasus Uji

| Input | Hasil yang Diharapkan |
| ----: | --------------------- |
|    92 | A                     |
|    85 | A                     |
|  84.9 | B                     |
|    70 | B                     |
|    60 | C                     |
|    50 | D                     |
|  49.9 | E                     |

---

## 2. Kategori Bilangan

Program menerima sebuah bilangan bulat dan mengklasifikasikannya menjadi bilangan negatif, nol, positif genap, atau positif ganjil.

### Tabel Keputusan

| Kategori                | Syarat                   | Contoh |
| ----------------------- | ------------------------ | -----: |
| Bilangan negatif        | `x < 0`                  |     -7 |
| Nol                     | `x == 0`                 |      0 |
| Bilangan positif genap  | `x > 0` dan `x % 2 == 0` |      8 |
| Bilangan positif ganjil | `x > 0` dan `x % 2 != 0` |     13 |

### Kasus Uji

| Input | Hasil yang Diharapkan   |
| ----: | ----------------------- |
|    -7 | Bilangan negatif        |
|     0 | Nol                     |
|     8 | Bilangan positif genap  |
|    13 | Bilangan positif ganjil |

---

## 3. Validasi Rentang Sudut

Program menerima besar sudut dalam derajat. Input harus lebih dari 0° dan kurang dari 180°.

### Tabel Keputusan

| Kondisi              | Hasil           |
| -------------------- | --------------- |
| Sudut ≤ 0 atau ≥ 180 | Masukan ditolak |
| 0 < Sudut < 90       | Sudut lancip    |
| Sudut = 90           | Sudut siku-siku |
| 90 < Sudut < 180     | Sudut tumpul    |

### Kasus Uji

| Input | Hasil yang Diharapkan |
| ----: | --------------------- |
|    45 | Sudut lancip          |
|    90 | Sudut siku-siku       |
|   135 | Sudut tumpul          |
|     0 | Masukan ditolak       |
|   180 | Masukan ditolak       |
|   -30 | Masukan ditolak       |

---

## 4. Validasi Tipe dan Rentang

Program menerima jumlah soal yang benar dari total 20 soal.

Input harus berupa bilangan bulat dan berada pada rentang **0 sampai 20**. Setelah input valid, program menghitung persentase dan menentukan apakah siswa tuntas.

### Tabel Keputusan

| Kondisi                    | Hasil           |
| -------------------------- | --------------- |
| Input bukan bilangan bulat | Masukan ditolak |
| Input < 0 atau > 20        | Masukan ditolak |
| Persentase ≥ 75%           | Tuntas          |
| Persentase < 75%           | Belum tuntas    |

### Kasus Uji

|       Input | Hasil yang Diharapkan |
| ----------: | --------------------- |
|          15 | 75.00% — Tuntas       |
|          14 | 70.00% — Belum tuntas |
|          20 | 100.00% — Tuntas      |
|           0 | 0.00% — Belum tuntas  |
|          21 | Masukan ditolak       |
| `dua belas` | Masukan ditolak       |

---

## 5. Klasifikasi Segitiga Berdasarkan Sudut

Program menerima tiga sudut segitiga. Setiap sudut harus lebih dari 0° dan jumlah ketiga sudut harus sama dengan 180°.

### Validasi

```text
a > 0
b > 0
c > 0
a + b + c = 180°
```

Program menggunakan toleransi:

```python
abs(a + b + c - 180) > 1e-9
```

untuk memeriksa ketepatan jumlah sudut.

### Tabel Keputusan

| Kondisi Sudut Terbesar | Hasil              |
| ---------------------- | ------------------ |
| Sudut terbesar > 90°   | Segitiga tumpul    |
| Sudut terbesar = 90°   | Segitiga siku-siku |
| Sudut terbesar < 90°   | Segitiga lancip    |

### Kasus Uji

| Sudut A | Sudut B | Sudut C | Hasil              |
| ------: | ------: | ------: | ------------------ |
|      60 |      60 |      60 | Segitiga lancip    |
|      90 |      45 |      45 | Segitiga siku-siku |
|     120 |      30 |      30 | Segitiga tumpul    |
|     100 |      50 |      40 | Masukan ditolak    |
|       0 |      90 |      90 | Masukan ditolak    |

---

# Praktik 1 — Validasi dan Klasifikasi Nilai Akhir

File:

```text
praktik/validasi_klasifikasi_nilai.py
```

Praktik 1 menggabungkan validasi input, perhitungan nilai akhir, pengecekan kehadiran, dan klasifikasi predikat.

Nilai akhir dihitung menggunakan bobot:

```text
Nilai akhir = 0.6 × nilai ujian + 0.4 × nilai tugas
```

## Validasi Input

Ketiga input harus berupa angka dan berada pada rentang 0 sampai 100.

Input yang divalidasi:

1. Nilai ujian.
2. Nilai tugas.
3. Persentase kehadiran.

Program menggunakan `try-except ValueError` untuk menangani input yang bukan angka.

---

## Tabel Keputusan Praktik 1

### Validasi Input

| Kondisi                    | Hasil                 |
| -------------------------- | --------------------- |
| Input bukan angka          | Masukan ditolak       |
| Nilai ujian < 0 atau > 100 | Masukan ditolak       |
| Nilai tugas < 0 atau > 100 | Masukan ditolak       |
| Kehadiran < 0 atau > 100   | Masukan ditolak       |
| Semua input valid          | Lanjut ke perhitungan |

### Predikat Nilai

| Predikat | Syarat                |
| -------- | --------------------- |
| A        | Nilai akhir ≥ 85      |
| B        | 70 ≤ Nilai akhir < 85 |
| C        | 60 ≤ Nilai akhir < 70 |
| D        | 50 ≤ Nilai akhir < 60 |
| E        | Nilai akhir < 50      |

### Status Kelulusan

| Kondisi                            | Status                          |
| ---------------------------------- | ------------------------------- |
| Kehadiran < 80%                    | Tidak memenuhi syarat kehadiran |
| Kehadiran ≥ 80% dan predikat A/B/C | Lulus                           |
| Kehadiran ≥ 80% dan predikat D/E   | Belum lulus                     |

Pengecekan kehadiran dilakukan terlebih dahulu sebelum klasifikasi predikat.

---

# Hasil Pengujian Praktik 1

| No. | Ujian | Tugas | Kehadiran | Nilai Akhir | Predikat | Status                          |
| --: | ----: | ----: | --------: | ----------: | :------: | ------------------------------- |
|   1 |    90 |    80 |        95 |       86.00 |     A    | Lulus                           |
|   2 |    75 |    70 |        85 |       73.00 |     B    | Lulus                           |
|   3 |    60 |    60 |        80 |       60.00 |     C    | Lulus                           |
|   4 |    55 |    50 |        90 |       53.00 |     D    | Belum lulus                     |
|   5 |    40 |    30 |       100 |       36.00 |     E    | Belum lulus                     |
|   6 |    90 |    90 |        75 |       90.00 |     -    | Tidak memenuhi syarat kehadiran |

### Pengujian Input Tidak Valid

| No. | Ujian | Tugas | Kehadiran | Hasil                            |
| --: | ----: | ----: | --------: | -------------------------------- |
|   7 |   105 |    80 |        90 | Nilai ujian ditolak              |
|   8 |    80 |    -5 |        90 | Nilai tugas ditolak              |
|   9 |    80 |    80 |     `abc` | Input ditolak karena bukan angka |

---

# Cara Menjalankan Program

Pastikan terminal berada di folder utama repository.

### Menjalankan Latihan

Contoh:

```bash
python3 latihan/01_predikat_nilai.py
```

Latihan lainnya:

```bash
python3 latihan/02_kategori_bilangan.py
python3 latihan/03_validasi_rentang.py
python3 latihan/04_validasi_tipe.py
python3 latihan/05_klasifikasi_segitiga_sudut.py
```

### Menjalankan Praktik 1

```bash
python3 praktik/validasi_klasifikasi_nilai.py
```

Pada Windows, jika `python3` tidak dikenali, dapat menggunakan:

```bash
python praktik/validasi_klasifikasi_nilai.py
```

---

# Refleksi

Pada awal pengerjaan, salah satu hal yang perlu diperhatikan adalah **input yang tidak sesuai dengan tipe data yang diharapkan**. Misalnya, pada program validasi jumlah soal, pengguna dapat memasukkan teks seperti `dua belas`, padahal program membutuhkan bilangan bulat.

Masukan tersebut dapat menyebabkan error jika langsung dikonversi menggunakan `int()`. Oleh karena itu, program menggunakan `try-except ValueError` untuk menangani kesalahan konversi. Dengan cara tersebut, program tidak berhenti karena error, tetapi memberikan pesan bahwa masukan harus berupa bilangan bulat.

Selain itu, pada Praktik 1, validasi kehadiran harus dilakukan sebelum menentukan status berdasarkan predikat. Dengan demikian, mahasiswa yang memiliki kehadiran di bawah 80% tetap dinyatakan **tidak memenuhi syarat kehadiran**, meskipun nilai akhirnya tinggi.

---

# Checklist Pengerjaan

* [x] Latihan 1 — Predikat Nilai
* [x] Latihan 2 — Kategori Bilangan
* [x] Latihan 3 — Validasi Rentang
* [x] Latihan 4 — Validasi Tipe
* [x] Latihan 5 — Klasifikasi Segitiga Sudut
* [x] Praktik 1 — Validasi dan Klasifikasi Nilai Akhir
* [x] Validasi tipe menggunakan `try-except`
* [x] Validasi rentang input
* [x] Perhitungan nilai akhir dengan bobot 60% dan 40%
* [x] Pengecekan kehadiran minimal 80%
* [x] Klasifikasi predikat A–E
* [x] Pengujian kasus valid dan tidak valid
* [x] Dokumentasi tabel keputusan
* [x] Dokumentasi hasil pengujian
* [x] Refleksi pengerjaan

---

# Git dan GitHub

Repository digunakan untuk menyimpan kode program, README, dan hasil pengerjaan Praktik 1.

Contoh tahapan commit:

```bash
git add .
git commit -m "Tambah latihan seleksi multi-kondisi"
```

```bash
git add .
git commit -m "Tambah validasi dan praktik 1"
```

```bash
git add .
git commit -m "Lengkapi README dan pengujian"
```

Kemudian lakukan push ke repository GitHub:

```bash
git push origin main
```

Sebelum melakukan push, dapat memeriksa status repository dengan:

```bash
git status
```

dan melihat riwayat commit dengan:

```bash
git log --oneline
```

---

# Kesimpulan

Pada Pertemuan 04, program Python dikembangkan menggunakan seleksi multi-kondisi `if-elif-else` serta validasi input untuk memastikan data yang diberikan sesuai dengan aturan program. Melalui lima latihan dan Praktik 1, penerapan kondisi, validasi tipe, validasi rentang, perhitungan, dan pengujian program dapat dilakukan secara terstruktur.

Dokumentasi melalui README digunakan untuk menjelaskan keputusan program, hasil pengujian, serta proses pengerjaan sehingga program dapat lebih mudah dipahami dan diperiksa kembali.
