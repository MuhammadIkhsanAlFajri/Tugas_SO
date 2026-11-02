# 🐧 Konfigurasi `/etc/profile` pada Linux

## 📌 Deskripsi

`/etc/profile` merupakan file konfigurasi sistem Linux yang dijalankan ketika pengguna melakukan login menggunakan shell yang mendukung konfigurasi profile.

File ini berfungsi untuk mengatur lingkungan kerja pengguna, seperti konfigurasi prompt terminal, pemuatan konfigurasi Bash, serta pengaturan environment melalui direktori `/etc/profile.d/`.

## 🎯 Tujuan

- Memahami fungsi file `/etc/profile`.
- Mengetahui cara konfigurasi prompt terminal.
- Memahami proses pemuatan konfigurasi Bash.
- Mengenal direktori `/etc/profile.d/`.
- Memahami penggunaan kondisi dan perulangan dalam Shell Script.

## 💻 Kode Konfigurasi

Berikut merupakan potongan konfigurasi yang terdapat pada materi `/etc/profile`:

```bash
if [ "${BASH-}" ] && [ "${BASH}" != "/bin/sh" ]; then
    # The file bash.bashrc already sets the default PS1.
    # PS1='\h:\w\$ '
    if [ -f /etc/bash.bashrc ]; then
        . /etc/bash.bashrc
    fi
else
    if [ "$(id -u)" -eq 0 ]; then
        PS1='# '
    else
        PS1='$ '
    fi
fi

if [ -d /etc/profile.d ]; then
    for i in /etc/profile.d/*.sh; do
        if [ -r $i ]; then
            . $i
        fi
    done
    unset i
fi

echo "profile dari .bash_profile"
```

## 🔍 Penjelasan Kode

### 1. Pemeriksaan Bash

```bash
if [ "${BASH-}" ] && [ "${BASH}" != "/bin/sh" ]; then
```

Memeriksa apakah shell yang digunakan adalah Bash dan bukan `/bin/sh`.

### 2. Memuat Konfigurasi Bash

```bash
if [ -f /etc/bash.bashrc ]; then
    . /etc/bash.bashrc
fi
```

Memeriksa keberadaan file `/etc/bash.bashrc`, kemudian memuat konfigurasinya jika tersedia.

### 3. Mengatur Prompt Terminal

```bash
if [ "$(id -u)" -eq 0 ]; then
    PS1='# '
else
    PS1='$ '
fi
```

Mengatur tampilan prompt terminal berdasarkan identitas pengguna:

| Simbol | Keterangan                |
| ------ | ------------------------- |
| `#`    | Menandakan pengguna root  |
| `$`    | Menandakan pengguna biasa |

### 4. Memuat Konfigurasi `/etc/profile.d/`

```bash
if [ -d /etc/profile.d ]; then
    for i in /etc/profile.d/*.sh; do
        if [ -r $i ]; then
            . $i
        fi
    done
fi
```

Bagian ini memeriksa direktori `/etc/profile.d/`, kemudian memuat file konfigurasi berekstensi `.sh` yang dapat dibaca.

### 5. Menghapus Variabel Sementara

```bash
unset i
```

Menghapus variabel `i` setelah proses perulangan selesai.

### 6. Menampilkan Pesan

```bash
echo "profile dari .bash_profile"
```

Menampilkan pesan ke terminal sebagai output perintah.

## 📖 Kesimpulan

File `/etc/profile` memiliki peran penting dalam proses inisialisasi lingkungan pengguna Linux.

Melalui konfigurasi ini, sistem dapat memuat pengaturan Bash, menentukan prompt terminal, serta menjalankan konfigurasi tambahan dari direktori `/etc/profile.d/`.

---

**Materi:** Sistem Operasi  
**Topik:** Linux Environment dan Profile
