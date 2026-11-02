# ⚙️ Pengelolaan Jobs dan Proses pada Linux

## 📌 Deskripsi

Jobs merupakan pekerjaan atau proses yang dijalankan melalui shell Linux. Pengguna dapat menjalankan pekerjaan di foreground maupun background.

Pada materi ini, digunakan Shell Script untuk menjalankan perintah secara berulang dengan interval waktu 10 detik. Setiap eksekusi akan mencatat tanggal dan waktu ke dalam sebuah file bernama `hasil`.

## 🎯 Tujuan

- Memahami konsep pekerjaan (jobs) pada Linux.
- Mengenal penggunaan Shell Script.
- Memahami perulangan menggunakan `while`.
- Menggunakan perintah `date` untuk mendapatkan tanggal dan waktu.
- Memahami penggunaan `sleep` untuk memberikan jeda.
- Menyimpan hasil perintah ke dalam file.

## 💻 1. Kode Shell Script

Berikut adalah script yang digunakan dalam praktikum:

```bash
#!/bin/bash

while true
do
    date >> hasil
    sleep 10
done
```

## 🔍 2. Penjelasan Kode

### 1. Menentukan Interpreter

```bash
#!/bin/bash
```

Menentukan bahwa script dijalankan menggunakan interpreter Bash.

### 2. Membuat Perulangan

```bash
while true
do
    ...
done
```

Digunakan untuk menjalankan perintah secara terus-menerus selama kondisi bernilai benar.

### 3. Mengambil Tanggal dan Waktu

```bash
date >> hasil
```

Perintah `date` digunakan untuk menampilkan tanggal dan waktu saat ini.

Operator `>>` berfungsi menambahkan hasil perintah ke bagian akhir file `hasil` tanpa menghapus isi sebelumnya.

### 4. Memberikan Jeda

```bash
sleep 10
```

Memberikan jeda selama 10 detik sebelum perintah berikutnya dijalankan.

## 🚀 3. Cara Menjalankan Script

Simpan script ke dalam file bernama `jobs.sh`.

Berikan izin eksekusi:

```bash
chmod +x jobs.sh
```

Jalankan script:

```bash
./jobs.sh
```

Script akan terus berjalan dan mencatat tanggal serta waktu setiap 10 detik ke file `hasil`.

## 📂 4. Melihat Hasil

Untuk melihat isi file hasil:

```bash
cat hasil
```

Untuk melihat lima catatan terakhir:

```bash
tail -n 5 hasil
```

## ⏹️ 5. Menghentikan Script

Jika script dijalankan di foreground, tekan:

```text
Ctrl + C
```

Jika script dijalankan di background menggunakan:

```bash
./jobs.sh &
```

Lihat daftar pekerjaan:

```bash
jobs
```

Untuk menghentikan pekerjaan background, gunakan:

```bash
kill %1
```

Perintah tersebut menghentikan pekerjaan nomor 1 pada shell saat ini.

## 📖 Kesimpulan

Melalui praktikum ini, dapat dipahami bahwa Shell Script dapat digunakan untuk menjalankan pekerjaan secara berulang di Linux.

Perintah `while` digunakan untuk melakukan perulangan, `date` mengambil informasi waktu, `sleep` memberikan jeda, dan operator `>>` menyimpan hasil ke dalam file.

Pengelolaan jobs juga memungkinkan pengguna menjalankan dan menghentikan pekerjaan melalui terminal Linux.

---

**Materi:** Sistem Operasi  
**Topik:** Shell Scripting dan Job Management
