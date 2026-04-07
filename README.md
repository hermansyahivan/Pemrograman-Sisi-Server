📦 Dockerized WordPress Project


👤 Identitas


Nama : Ivan Hermansyah


NIM : A11.2023.14952


📌 1. Deskripsi Project

Project ini merupakan implementasi WordPress menggunakan Docker Compose dengan beberapa layanan utama:

🌐 WordPress (Web Server)
🗄️ MySQL (Database)
⚡ Redis (Caching)

Tujuan dari project ini adalah untuk memahami bagaimana menjalankan aplikasi web berbasis container serta menghubungkan beberapa service dalam satu environment.

🚀 2. Cara Menjalankan Project

Ikuti langkah-langkah berikut:

1️⃣ Install & Jalankan Docker

Pastikan sudah menginstall Docker, lalu jalankan Docker Desktop

2️⃣ Masuk ke Folder Project
cd wordpress-docker
3️⃣ Jalankan Container
docker-compose up -d
4️⃣ Cek Container Berjalan
docker ps
5️⃣ Akses WordPress

Buka browser dan akses:

http://localhost:8000

📸 3. Screenshot Hasil

Berikut dokumentasi hasil implementasi:

No	Keterangan	File
1	Menjalankan service Docker	screenshot/service.png
2	Halaman instalasi WordPress	screenshot/page_instalasi.png
3	Dashboard WordPress	screenshot/dashboard.png
4	3 Container berjalan	screenshot/info_container.png
5	Test Redis Ping	screenshot/redis_ping.png
6	Membuat postingan baru	screenshot/new_post.png
7	Konfigurasi Redis Cache	screenshot/redis_cache.png
❓ 4. Jawaban Pertanyaan
1. Kenapa perlu volume untuk MySQL?

Volume digunakan agar data database tidak hilang saat container dihentikan atau dihapus.
Tanpa volume, data akan ikut terhapus karena container bersifat ephemeral (sementara).

2. Apa fungsi depends_on?

depends_on digunakan untuk mengatur urutan startup container, sehingga service tertentu (seperti MySQL) berjalan lebih dulu sebelum service lain (seperti WordPress).

3. Bagaimana WordPress terhubung ke MySQL?

WordPress terhubung ke MySQL melalui:

Environment variables
Hostname: mysql (nama service di Docker)
Port: 3306

Docker otomatis membuat network internal, sehingga antar container bisa saling berkomunikasi.

4. Apa keuntungan menggunakan Redis di WordPress?

Redis berfungsi sebagai caching system.

Keuntungannya:
⚡ Mempercepat loading website
🗄️ Mengurangi beban database MySQL
🚀 Meningkatkan performa WordPress
📈 Cocok untuk website dengan traffic tinggi

✅ Kesimpulan

Dengan menggunakan Docker Compose, kita dapat:

Menjalankan WordPress dengan mudah
Mengelola multi-container dalam satu project
Meningkatkan performa menggunakan Redis
Menjaga data tetap aman dengan volume
