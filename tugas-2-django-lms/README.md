# Simple LMS - Django Dockerized

Proyek ini adalah sistem manajemen pembelajaran (LMS) sederhana yang dibangun menggunakan **Django** dan dikelola di dalam kontainer **Docker**. Konfigurasi ini menggunakan **PostgreSQL** sebagai database utama untuk memastikan lingkungan pengembangan yang mendekati standar produksi.

## 🎯 Learning Objectives
- Implementasi containerization menggunakan Docker.
- Konfigurasi multi-container setup dengan `docker-compose`.
- Integrasi Django dengan database PostgreSQL di dalam container.
- Penerapan *best practices* pengelolaan environment variables.

## 📦 Project Structure
```text
simple-lms/
├── config/              # Django core configuration (settings, urls, wsgi)
├── docker-compose.yml   # Orchestration multi-container
├── Dockerfile           # Blueprint image untuk Django web app
├── .env.example         # Template environment variables
├── requirements.txt     # Python dependencies
├── manage.py            # Django management script
└── README.md            # Dokumentasi proyek

🚀 Cara Menjalankan Project
1. Clone Repositori
Bash
git clone [https://github.com/username/simple-lms.git](https://github.com/username/simple-lms.git)
cd simple-lms

2. Setup Environment Variables
Salin file .env.example menjadi .env dan sesuaikan nilainya:

Bash
cp .env.example .env

3. Build dan Jalankan Container
Gunakan Docker Compose untuk membangun image dan menjalankan service:

Bash
docker-compose up --build -d

4. Jalankan Migrasi Database
Buka terminal baru dan eksekusi perintah berikut agar tabel database terbentuk:

Bash
docker-compose exec web python manage.py migrate

5. Akses Aplikasi
Buka browser dan akses http://localhost:8000. Jika berhasil, Anda akan melihat halaman "Django Welcome Page".

6. Stop Service
Bash
docker-compose down

.
🔑 Environment Variables
Aplikasi ini menggunakan file .env untuk keamanan data sensitif. Berikut adalah variabel yang perlu dikonfigurasi:
Variable,Deskripsi,Contoh
DEBUG,"Mode aplikasi (1 untuk True, 0 untuk False)",1
SECRET_KEY,Key unik untuk keamanan Django,django-insecure-xxx
DB_NAME,Nama database PostgreSQL,lms_db
DB_USER,Username database,postgres
DB_PASSWORD,Password database,password123
DB_HOST,Host database (sesuai nama service di compose),db
DB_PORT,Port database,5432

📸 Screenshots
Docker Compose berhasil running
screenshot/compose_success.png

Django accessible di localhost:8000
screenshot/django_success.png

Django login
screenshot/django_admin.png

PostgreSQL connection working
screenshot/database.png

---
### 👤 Author Information
- **Nama:** Ivan Hermansyah
- **NIM:** A11.2023.14952
- **Mata Kuliah:** Pemrograman Sisi Server
---