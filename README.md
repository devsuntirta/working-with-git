# Bekerja dengan Git dan GitHub di Universitas Sultan Ageng Tirtayasa

Panduan ini ditujukan bagi pengembang di lingkungan Universitas Sultan Ageng Tirtayasa (UNTIRTA) yang ingin memulai bekerja dengan Git serta berkolaborasi melalui GitHub. Proses mencakup pengklonan repositori yang sudah ada, membuat repositori latihan, hingga praktik kolaborasi tim yang baik.

![Git Flow Workflow]([https://logos-world.net/wp-content/uploads/2020/11/GitHub-Logo.png](https://allvectorlogo.com/img/2021/12/github-logo-vector.png))

## Mengkloning Repositori dari GitHub

Untuk mulai bekerja dengan proyek yang sudah ada di GitHub:

1. Pastikan Anda memiliki akses ke repositori (public atau Anda diundang sebagai kolaborator).
2. Buka halaman repositori di GitHub.
3. Klik tombol **Code**, lalu salin URL yang tersedia (HTTPS atau SSH).
4. Buka terminal dan arahkan ke direktori tempat Anda ingin menyimpan repositori.
5. Jalankan perintah berikut:

```bash
git clone <URL>
```

> Jika Anda menggunakan SSH, pastikan kunci SSH Anda sudah ditambahkan ke akun GitHub.

Repositori akan disalin ke folder lokal dan siap untuk dikerjakan.

---

## Membuat Repositori Latihan

Untuk latihan atau eksperimen, buat repositori baru di luar repositori produksi:

1. Login ke akun GitHub Anda.
2. Klik tombol **New repository**.
3. Isi nama repositori dan pengaturan lainnya.
4. Klik **Create repository**.
5. Inisialisasi proyek lokal Anda dengan:

```bash
git init
git remote add origin <URL-repo-baru>
```

---

## Praktik Kolaborasi Tim di GitHub

Untuk mendukung kerja tim yang efisien, berikut beberapa praktik terbaik yang sebaiknya diterapkan:

### 1. Gunakan Branch untuk Setiap Fitur atau Perbaikan

Buat branch terpisah untuk setiap fitur baru atau perbaikan bug:

```bash
git checkout -b fitur/login
```

Branch ini akan memudahkan penggabungan ke `main` atau `develop` tanpa konflik.

### 2. Commit Secara Konsisten dan Terstruktur

![Git Flow Workflow](https://scalastic.io/assets/img/git-flow-workflow.svg)

Lakukan commit secara berkala dengan pesan yang deskriptif. Gunakan [Conventional Commit](https://www.conventionalcommits.org/) untuk standarisasi. Contoh konvensi:

- `feat`: Penambahan fitur baru  
- `fix`: Perbaikan bug  
- `docs`: Perubahan dokumentasi  
- `style`: Perubahan gaya kode (indentasi, spasi, dll)  
- `refactor`: Refaktor kode tanpa mengubah fungsionalitas  
- `test`: Penambahan atau perubahan pada unit test  

**Contoh:**

```bash
git commit -m "feat: Menambahkan validasi email di form registrasi"
```

### 3. Buat Pull Request untuk Review

Setelah fitur selesai dikembangkan, dorong perubahan ke GitHub:

```bash
git push origin fitur/login
```

Kemudian buka Pull Request (PR) dari branch tersebut ke branch utama (`main` atau `develop`) untuk ditinjau tim. Review ini membantu menjaga kualitas dan konsistensi kode.

### 4. Selalu Sinkronkan dengan Branch Utama

Untuk menghindari konflik, pastikan branch kerja Anda selalu diperbarui:

```bash
git pull origin main
# atau jika menggunakan rebase:
git fetch origin
git rebase origin/main
```

### 5. Atasi Konflik dengan Teliti

Jika terjadi konflik saat merge atau rebase:

- Periksa file yang konflik.
- Edit secara manual untuk menyelesaikannya.
- Lakukan commit ulang setelah konflik diselesaikan.
- Jalankan testing lokal untuk memastikan tidak ada error baru.

---

Dengan menerapkan panduan ini, kolaborasi tim dalam proyek GitHub di lingkungan UNTIRTA akan menjadi lebih lancar, terstruktur, dan mudah dikelola.
