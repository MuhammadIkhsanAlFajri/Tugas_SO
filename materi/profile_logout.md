# 🚪 Konfigurasi `.bash_logout` pada Linux

## 📌 Deskripsi

`.bash_logout` merupakan file konfigurasi Bash yang dijalankan ketika pengguna keluar (logout) dari sesi login shell.

File ini dapat digunakan untuk menjalankan perintah tertentu secara otomatis ketika sesi terminal berakhir, seperti membersihkan layar terminal, menampilkan pesan, dan mengatur proses saat pengguna logout.

Pada praktikum ini, file `.bash_logout` digunakan untuk membersihkan layar terminal serta menampilkan pesan terima kasih sebelum sesi berakhir.

## 🎯 Tujuan

- Memahami fungsi file `.bash_logout` pada Linux.
- Mengetahui proses yang dijalankan ketika pengguna logout.
- Memahami penggunaan kondisi `if` dalam Shell Script.
- Mengenal perintah `echo`, `sleep`, dan `clear`.
- Memahami penggunaan variabel lingkungan `SHLVL`.

## 💻 1. Kode Konfigurasi

Berikut merupakan kode konfigurasi yang digunakan dalam praktikum:

```bash
# ~/.bash_logout: executed by bash(1) when login shell exits.

# when leaving the console clear the screen to increase privacy

if [ "$SHLVL" = 1 ]; then
    [ -x /usr/bin/clear_console ] && /usr/bin/clear_console -q
fi

echo "Terima kasih atas sesi yang diberikan"
sleep 5
clear
```

## 🔍 2. Penjelasan Kode

### 1. Komentar Konfigurasi

```bash
# ~/.bash_logout: executed by bash(1) when login shell exits.
```

Menjelaskan bahwa file `.bash_logout` dijalankan ketika sesi login shell Bash berakhir.

Baris yang diawali tanda `#` merupakan komentar dan tidak dieksekusi oleh shell.

### 2. Memeriksa Tingkat Shell

```bash
if [ "$SHLVL" = 1 ]; then
    ...
fi
```

Digunakan untuk memeriksa nilai variabel lingkungan `SHLVL`.

Jika nilainya `1`, perintah di dalam kondisi akan dijalankan. Variabel ini menunjukkan tingkat atau kedalaman shell yang sedang berjalan.

### 3. Membersihkan Konsol

```bash
[ -x /usr/bin/clear_console ] && /usr/bin/clear_console -q
```

Penjelasan:

- `-x` memeriksa apakah file dapat dieksekusi.
- `/usr/bin/clear_console` merupakan program untuk membersihkan konsol.
- `&&` menjalankan perintah berikutnya jika perintah sebelumnya berhasil.
- `-q` menjalankan perintah dalam mode quiet.

### 4. Menampilkan Pesan

```bash
echo "Terima kasih atas sesi yang diberikan"
```

Perintah `echo` digunakan untuk menampilkan pesan ke terminal ketika pengguna logout.

### 5. Memberikan Jeda Waktu

```bash
sleep 5
```

Digunakan untuk memberikan jeda selama 5 detik sebelum perintah selanjutnya dijalankan.

### 6. Membersihkan Layar Terminal

```bash
clear
```

Digunakan untuk membersihkan tampilan terminal setelah pesan ditampilkan.

## 🛠️ 3. Cara Menggunakan

File `.bash_logout` biasanya terletak di direktori home pengguna.

Untuk membukanya, gunakan:

```bash
nano ~/.bash_logout
```

Masukkan konfigurasi yang telah dibuat, kemudian simpan file.

Untuk mengakhiri sesi login shell, gunakan:

```bash
exit
```

Setelah logout, perintah yang terdapat dalam `.bash_logout` akan dijalankan sesuai kondisi shell.

## 📝 4. Contoh Hasil Penggunaan

Ketika pengguna keluar dari sesi login shell, proses yang dilakukan adalah:

1. Memeriksa tingkat shell melalui `SHLVL`.
2. Membersihkan konsol jika kondisi terpenuhi dan program tersedia.
3. Menampilkan pesan terima kasih.
4. Menunggu selama 5 detik.
5. Membersihkan layar terminal.

## 📖 Kesimpulan

File `.bash_logout` merupakan salah satu file konfigurasi Bash yang berguna untuk menjalankan perintah secara otomatis ketika pengguna keluar dari sesi login shell.

Melalui praktikum ini, dapat dipahami penggunaan kondisi `if`, variabel lingkungan `SHLVL`, serta perintah `echo`, `sleep`, dan `clear` dalam Shell Script.

Dengan konfigurasi tersebut, pengguna dapat mengatur tindakan yang dilakukan terminal sebelum sesi login berakhir.

---

**Materi:** Sistem Operasi  
**Topik:** Konfigurasi Bash Logout
