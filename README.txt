====================================================
TEMPLATE BRANCH - PROFESSIONAL STRUCTURE
====================================================

Project Name  : My Website
Repository    : my-website
Environment   : Local / Development / Production
Author        : isrohadi18
Created Date  : Rabu, 21 Januari 2026

====================================================
1. PROJECT DESCRIPTION
====================================================

Project ini adalah aplikasi website yang dikembangkan
menggunakan struktur folder profesional agar:

- Mudah dikembangkan
- Mudah dipelihara
- Siap untuk kerja tim
- Aman untuk production

Semua perubahan source code dilakukan melalui branch
dan Pull Request (PR), bukan langsung ke branch main.

====================================================
2. REPOSITORY STRUCTURE
====================================================

my-website/
│
├─ src/                    -> Source utama aplikasi
│   ├─ pages/              -> Halaman website
│   │   ├─ login.html
│   │   ├─ dashboard.html
│   │   └─ register.html
│   │
│   ├─ components/         -> Komponen reusable
│   │   ├─ header.html
│   │   └─ footer.html
│   │
│   └─ assets/             -> Asset pendukung
│       ├─ images/
│       └─ icons/
│
├─ css/                    -> File CSS
│   └─ style.css
│
├─ js/                     -> File JavaScript
│   └─ main.js
│
├─ docs/                   -> Dokumentasi project
│   ├─ API.txt
│   └─ CHANGELOG.txt
│
├─ .gitignore              -> File yang diabaikan Git
├─ README.txt              -> Dokumentasi utama
└─ index.html              -> Entry point aplikasi

====================================================
3. BRANCHING STRATEGY
====================================================

Branch utama:
- main        -> branch stabil / production

Branch kerja:
- feature/<nama-fitur>     -> fitur baru
- bugfix/<nama-bug>        -> perbaikan bug
- hotfix/<nama-issue>      -> perbaikan darurat

CONTOH:
- feature/login
- feature/dashboard
- bugfix/form-validation

====================================================
4. WORKFLOW DEVELOPMENT
====================================================
A. SETUP AWAL (REPO LOKAL KE GITHUB)

1. Buat folder project lokal
   (contoh: template-branch)

2. Inisialisasi repository Git
   git init

3. Buat file awal (wajib untuk commit pertama)
   contoh:
   touch README.txt

4. Commit awal
   git add README.txt
   git commit -m "Initial commit: setup project"

5. Gunakan branch utama modern
   git branch -M main

6. Buat repository kosong di GitHub
   (tanpa README / .gitignore / license)

7. Hubungkan repo lokal ke GitHub
   git remote add origin https://github.com/username/my-website.git

+  git remote -v              (Check remote yang terhubung)
   git remote remove origin   (Jika ingin menghapus remote)

8. Push pertama ke GitHub
   git push -u origin main

----------------------------------------------------

B. WORKFLOW PENGEMBANGAN FITUR (HARIAN)

1. Pastikan branch main terbaru
   git checkout main
   git pull origin main

2. Buat branch fitur baru
   git checkout -b feature/login

3. Tambahkan / ubah file
   (edit menggunakan editor lokal)

4. Stage & commit
   git add .
   git commit -m "Feature: tambah halaman login"

5. Push branch
   git push -u origin feature/login

6. Buat Pull Request di GitHub
   Base    : main
   Compare : feature/login

7. Review & merge

8. Hapus branch lama setelah merge
   git checkout main
   git pull origin main
   git branch -d feature/login
   git push origin --delete feature/login

+  Melihat Semua Commit & branch
   git log --oneline --graph --all --decorate

====================================================
5. COMMIT MESSAGE STANDARD
====================================================

Gunakan format berikut:

- Feature: <deskripsi fitur>
- Bugfix: <deskripsi bug>
- Refactor: <perubahan struktur code>
- Hotfix: <perbaikan darurat>

CONTOH:
- Feature: tambah tampilan login
- Bugfix: validasi form login
- Refactor: rapikan struktur folder

====================================================
6. RULES (WAJIB DIPATUHI)
====================================================

[✔] Dilarang commit langsung ke main
[✔] Setiap fitur harus pakai branch
[✔] Wajib Pull Request sebelum merge
[✔] Commit message harus jelas
[✔] Struktur folder harus konsisten

====================================================
7. DEPLOYMENT NOTE
====================================================

Branch main selalu berisi code yang:
- Stabil
- Siap dijalankan
- Bebas error kritikal

Branch lain hanya untuk development.

====================================================
END OF DOCUMENT
====================================================
