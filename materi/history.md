# 📜 Pengaturan Command History pada Linux

## 📌 Deskripsi

Command History merupakan fitur pada Linux yang digunakan untuk menyimpan dan melihat riwayat perintah yang pernah dijalankan oleh pengguna melalui terminal.

Fitur ini memudahkan pengguna untuk mengakses kembali perintah sebelumnya tanpa harus mengetik ulang.

## 🎯 Tujuan

- Memahami fungsi Command History pada Linux.
- Mengetahui cara mengatur jumlah riwayat perintah.
- Memahami penggunaan variabel `HISTSIZE`.
- Menampilkan sejumlah perintah terakhir yang pernah dijalankan.

## 💻 1. Mengatur Jumlah History

Perintah berikut digunakan untuk mengatur jumlah riwayat perintah yang disimpan dalam daftar history Bash:

```bash
HISTSIZE=20
```

**Penjelasan:**

- `HISTSIZE` merupakan variabel lingkungan Bash yang mengatur jumlah maksimum perintah dalam daftar history di memori shell.
- Nilai `20` berarti Bash menyimpan maksimal 20 perintah dalam daftar tersebut.
- Nilai bawaan pada konfigurasi awal yang digunakan dalam materi ini adalah 1000.

## 💻 2. Melihat Riwayat Perintah

Untuk menampilkan riwayat perintah yang pernah dijalankan, gunakan:

```bash
history
```

Perintah tersebut akan menampilkan daftar riwayat perintah Bash.

## 💻 3. Menampilkan 5 Perintah Terakhir

Untuk melihat hanya lima perintah terakhir, gunakan kombinasi berikut:

```bash
history | tail -n 5
```

**Penjelasan:**

| Perintah  | Fungsi                                    |
| --------- | ----------------------------------------- | -------------------------------------- |
| `history` | Menampilkan riwayat perintah Bash         |
| `         | `                                         | Mengirim output ke perintah berikutnya |
| `tail`    | Menampilkan bagian akhir output           |
| `-n 5`    | Membatasi output menjadi 5 baris terakhir |

## 📝 4. Contoh Penggunaan

Misalnya pengguna menjalankan beberapa perintah:

```bash
pwd
ls
cd Documents
mkdir latihan
date
```

Kemudian menjalankan:

```bash
history | tail -n 5
```

Terminal akan menampilkan lima baris terakhir dari output riwayat perintah.

Hasil aktual dapat berbeda tergantung perintah yang sudah dijalankan sebelumnya.

## 💡 Catatan Tambahan

Pengaturan `HISTSIZE=20` berlaku pada sesi Bash yang sedang berjalan.

Jika ingin membuat pengaturan tersebut berlaku secara permanen untuk sesi Bash interaktif, tambahkan baris berikut ke file `~/.bashrc`:

```bash
HISTSIZE=20
```

Kemudian muat ulang konfigurasi:

```bash
source ~/.bashrc
```

## 📖 Kesimpulan

Command History merupakan fitur penting dalam Linux yang membantu pengguna melihat kembali perintah yang pernah dijalankan.

Dengan menggunakan variabel `HISTSIZE`, pengguna dapat mengatur jumlah riwayat perintah yang disimpan. Sementara itu, perintah `history` dan `tail` dapat digunakan untuk menampilkan riwayat perintah sesuai kebutuhan.

---

**Materi:** Sistem Operasi  
**Topik:** Linux Command History
