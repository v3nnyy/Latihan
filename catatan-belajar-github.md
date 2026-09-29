# Catatan Belajar GitHub

## 1. Git dan GitHub

- **Git** adalah alat untuk mencatat riwayat perubahan file di komputer.
- **GitHub** adalah layanan daring untuk menyimpan repository Git dan bekerja sama dengan orang lain.
- **Repository (repo)** adalah folder proyek beserta riwayat perubahannya.

## 2. Istilah penting

- **Commit**: rekaman sekumpulan perubahan, disertai pesan.
- **Branch**: jalur kerja terpisah agar perubahan bisa dibuat tanpa langsung mengubah branch utama.
- **Remote**: alamat repository di layanan daring, biasanya diberi nama `origin`.
- **Push**: mengirim commit lokal ke remote.
- **Pull**: mengambil dan menggabungkan perubahan dari remote.
- **Clone**: menyalin repository remote ke komputer.
- **Pull Request (PR)**: usulan untuk meninjau dan menggabungkan perubahan dari satu branch ke branch lain.
- **Merge**: menggabungkan perubahan dari beberapa branch.

## 3. Periksa dan atur Git

Pastikan Git sudah terpasang, lalu periksa versinya:

```bash
git --version
```

Atur nama dan email yang akan dicatat pada commit:

```bash
git config --global user.name "Nama Anda"
git config --global user.email "email@example.com"
```

Lihat pengaturan:

```bash
git config --global --list
```

## 4. Alur dasar: proyek baru

Buat repository baru di GitHub, lalu hubungkan folder proyek lokal:

```bash
cd nama-folder-proyek
git init
git add .
git commit -m "Buat versi awal"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

Ganti `USERNAME` dan `NAMA-REPO` sesuai alamat repository Anda. Jika repository dibuat di GitHub dengan README atau berkas lain, cara termudah untuk menghindari riwayat yang berbeda biasanya adalah **clone** repository tersebut terlebih dahulu.

## 5. Alur harian

```bash
git status
git add nama-file
git commit -m "Jelaskan perubahan"
git push
```

- `git status` menunjukkan perubahan yang belum dicatat.
- `git add` memilih perubahan yang akan masuk ke commit. Gunakan `git add .` untuk memilih semua perubahan di folder saat ini setelah memeriksa status.
- `git commit` menyimpan perubahan terpilih ke riwayat lokal.
- `git push` mengirim commit ke GitHub.

Sebelum mulai bekerja, ambil perubahan terbaru:

```bash
git pull
```

## 6. Mengambil proyek dari GitHub

```bash
git clone https://github.com/USERNAME/NAMA-REPO.git
cd NAMA-REPO
```

Setelah mengubah file, gunakan alur harian untuk menyimpan dan mengirim perubahan.

## 7. Bekerja dengan branch dan Pull Request

Buat branch untuk satu tugas:

```bash
git switch -c tambah-halaman-kontak
```

Setelah mengubah file:

```bash
git status
git add .
git commit -m "Tambah halaman kontak"
git push -u origin tambah-halaman-kontak
```

Kemudian buka GitHub, buat **Pull Request** dari branch tersebut ke `main`, tinjau perubahannya, dan gabungkan jika sudah siap. Nama branch sebaiknya singkat dan menggambarkan tugas.

## 8. README dan `.gitignore`

- `README.md` menjelaskan tujuan proyek, cara menjalankannya, dan informasi penting bagi pengguna atau kontributor.
- `.gitignore` mencantumkan file atau folder yang tidak perlu dimasukkan ke Git, misalnya file hasil build atau konfigurasi lokal.
- Jangan pernah memasukkan kata sandi, token akses, kunci privat, atau rahasia lain ke repository. Jika rahasia terlanjur diunggah, cabut atau rotasi rahasia tersebut; menghapus file pada commit terbaru saja tidak menghapusnya dari riwayat.

## 9. Konflik perubahan

Konflik dapat terjadi ketika perubahan pada bagian file yang sama tidak bisa digabung otomatis.

1. Jalankan `git status` untuk melihat file yang berkonflik.
2. Buka file dan cari penanda seperti `<<<<<<<`, `=======`, dan `>>>>>>>`.
3. Tentukan isi akhir yang benar, lalu hapus penanda konflik.
4. Tandai file dan buat commit:

```bash
git add nama-file
git commit -m "Selesaikan konflik"
```

## 10. Latihan singkat

1. Buat repository baru di GitHub.
2. Clone ke komputer.
3. Tambahkan `README.md` yang berisi judul dan tujuan proyek.
4. Jalankan `git status`, lalu `git add README.md`.
5. Buat commit dengan pesan yang jelas dan kirim dengan `git push`.
6. Buat branch baru, ubah README, push branch, lalu ajukan Pull Request.

## 11. Perintah ringkas

| Perintah | Kegunaan |
|---|---|
| `git status` | Melihat kondisi perubahan |
| `git add <file>` | Memilih perubahan untuk commit |
| `git commit -m "pesan"` | Mencatat perubahan |
| `git pull` | Mengambil perubahan terbaru |
| `git push` | Mengirim commit ke remote |
| `git clone <url>` | Menyalin repository remote |
| `git switch -c <nama>` | Membuat dan berpindah ke branch |
| `git log --oneline` | Melihat ringkasan riwayat commit |
