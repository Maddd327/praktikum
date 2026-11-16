# Pesan Sederhana

Ini proyek praktikum CPK saya buat bikin aplikasi pengirim pesan sederhana. Untuk Kriteria 1, saya mulai dari nyiapin folder proyek, bikin halaman awal, nyoba respons PHP, terus nyatet pengerjaannya di Git.

Halaman depannya baru nampilin nama aplikasi, jadi HTML dan CSS aja udah cukup. Bagian backend pakai PHP murni. Login, daftar akun, kirim pesan, dan database nanti dikerjain saat masuk ke kriteria berikutnya.

## Isi folder

- `Frontend/` isinya `index.html` sama `css/style.css` buat tampilan.
- `Backend/` isinya `index.php` buat nyoba respons dari server PHP.
- `Docs/` isinya [catatan pengerjaan harian](Docs/log-pengerjaan.md).
- `.gitignore` dipakai supaya `.env`, varian `.env.*` selain `.env.example`, dan `Backend/config.local.php` nggak ikut ke Git. Kalau bikin `.env.example`, isinya pakai nilai contoh aja.

## Yang dipakai

- PHP 8.4
- MariaDB 10 atau lebih baru buat tahap database
- Browser dan Git

Waktu dicek pada 16 November 2026, PHP CLI yang terpasang versinya `8.4.27` dan klien MariaDB versinya `13.0.2`. Versi server dan koneksi MariaDB belum saya cek karena tahap ini belum pakai database. Waktu folder proyek pertama kali dicek, file dump SQL juga belum ada di dalamnya.

## Cara jalaninnya

Buka PowerShell di folder `cpk`. Kalau mau cek dulu PHP yang terbaca di terminal, jalankan `php --version`.

### 1. Jalankan frontend

```powershell
php -S 127.0.0.1:8080 -t Frontend
```

Buka [http://127.0.0.1:8080/](http://127.0.0.1:8080/). Nanti judul **Pesan Sederhana** muncul di tengah halaman dengan latar abu-abu muda. Kalau cuma mau lihat tampilannya, bisa juga buka `Frontend/index.html` langsung di browser.

### 2. Jalankan backend

Buka terminal kedua, masih di folder `cpk`. Perintah pertama buat cek sintaks PHP, lalu perintah kedua buat nyalain server backend.

```powershell
php -l Backend/index.php
php -S 127.0.0.1:8081 -t Backend
```

Buka [http://127.0.0.1:8081/](http://127.0.0.1:8081/). Kalau backend udah jalan, bakal muncul tulisan `Backend Pesan Sederhana berjalan.`

### 3. Cek dari PowerShell

Kalau dua server tadi masih jalan, buka terminal ketiga dan coba perintah ini.

```powershell
(Invoke-WebRequest -UseBasicParsing 'http://127.0.0.1:8080/').StatusCode
(Invoke-WebRequest -UseBasicParsing 'http://127.0.0.1:8080/css/style.css').StatusCode
(Invoke-WebRequest -UseBasicParsing 'http://127.0.0.1:8081/').Content
```

Dua perintah pertama harus keluar `200`. Yang terakhir bakal nampilin tulisan dari backend. Kalau udah selesai, tekan `Ctrl+C` di masing-masing terminal server.

Sejauh ini, sintaks PHP, respons HTTP buat halaman dan CSS, judul di HTML, serta isi dan tipe respons backend udah dicek. Saya masih perlu lihat langsung tampilannya di browser desktop dan HP.

## Catatan pengerjaan

Setiap kali ngerjain proyek ini, saya catat tanggal, apa yang dikerjain, sama kira-kira berapa lama waktunya di [Docs/log-pengerjaan.md](Docs/log-pengerjaan.md).

## Penggunaan AI

Pada 16 November 2026, saya pakai Codex buat bantu ngerapihin HTML dan CSS, 
**Perkiraan penggunaan AI** 40 % 

<details>
<summary>Cuplikan prompt yang saya pakai</summary>

"bantu saya rapihkan code ini dan cek seuai dengan kriteria 1"

</details>

## cara push ke github

- `git status` buat cek file apa aja yang diubah, ditambah, atau belum masuk commit.
- `git branch --show-current` buat cek sekarang lagi di branch mana.
- `git remote -v` buat cek alamat repo GitHub yang terhubung.
- `git log --oneline` buat lihat daftar commit secara singkat.
- `git diff` buat lihat perubahan isi file yang belum di-stage.
- `git add README.md` buat masukin perubahan README ke staging sebelum di-commit. Kalau file lain, ganti nama filenya.
- `git diff --cached` buat cek isi perubahan yang udah di-stage dan bakal masuk commit.
- `git commit -m "docs: rapikan README"` buat nyimpen perubahan yang udah di-stage ke riwayat Git lokal. Pesannya disesuaiin sama perubahan yang dibuat.
- `git remote add origin https://github.com/Maddd327/praktikum.git` buat hubungin repo lokal ke GitHub kalau belum ada remote origin.
- `git remote get-url origin` buat cek URL origin udah menuju repo yang benar atau belum.
- `git remote set-url origin https://github.com/Maddd327/praktikum.git` buat benerin URL origin kalau sebelumnya salah.
- `git push -u origin master` buat push pertama dari branch master sekaligus nyambungin branch lokal ke branch di GitHub.
- `git push` buat ngirim commit berikutnya setelah push pertama berhasil.




