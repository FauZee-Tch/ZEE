<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal Pengumuman Sekolah</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #2ecc71;
            --warning: #f39c12;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1.5rem 0;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
        }
        
        .logo-text h1 {
            font-size: 1.8rem;
            margin-bottom: 5px;
        }
        
        .logo-text p {
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 20px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 8px 15px;
            border-radius: 4px;
            transition: background 0.3s;
        }
        
        nav a:hover, nav a.active {
            background: rgba(255, 255, 255, 0.2);
        }
        
        .main-content {
            display: flex;
            gap: 30px;
            margin: 30px 0;
        }
        
        .announcements {
            flex: 3;
        }
        
        .sidebar {
            flex: 1;
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
        }
        
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--secondary);
            color: var(--primary);
        }
        
        .announcement-card {
            background: white;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s, box-shadow 0.3s;
            border-left: 4px solid var(--secondary);
        }
        
        .announcement-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .announcement-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
        }
        
        .announcement-title {
            font-size: 1.3rem;
            color: var(--primary);
        }
        
        .announcement-date {
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        .announcement-content {
            color: #555;
            margin-bottom: 15px;
        }
        
        .announcement-category {
            display: inline-block;
            background: var(--secondary);
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        
        .category-important {
            background: var(--accent);
        }
        
        .category-academic {
            background: var(--success);
        }
        
        .category-general {
            background: #9b59b6;
        }
        
        .admin-panel {
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            margin-top: 30px;
        }
        
        .admin-form {
            display: grid;
            gap: 15px;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
        }
        
        .form-group label {
            margin-bottom: 5px;
            font-weight: 500;
            color: var(--primary);
        }
        
        .form-control {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }
        
        .btn {
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: background 0.3s;
        }
        
        .btn-primary {
            background: var(--secondary);
            color: white;
        }
        
        .btn-primary:hover {
            background: #2980b9;
        }
        
        .btn-danger {
            background: var(--accent);
            color: white;
        }
        
        .btn-danger:hover {
            background: #c0392b;
        }
        
        .btn-warning {
            background: var(--warning);
            color: white;
        }
        
        .btn-warning:hover {
            background: #e67e22;
        }
        
        .admin-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        footer {
            background: var(--dark);
            color: white;
            text-align: center;
            padding: 20px 0;
            margin-top: 40px;
        }
        
        .login-form {
            max-width: 400px;
            margin: 50px auto;
            background: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .login-form h2 {
            text-align: center;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .hidden {
            display: none;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .stat-card {
            background: white;
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }
        
        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--secondary);
        }
        
        .stat-label {
            font-size: 0.9rem;
            color: #7f8c8d;
        }
        
        .search-box {
            margin-bottom: 20px;
        }
        
        .search-box input {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        
        .admin-announcement-item {
            background: #f8f9fa;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            border-left: 4px solid var(--secondary);
        }
        
        .admin-announcement-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .admin-announcement-title {
            font-weight: bold;
            color: var(--primary);
        }
        
        .admin-announcement-actions {
            display: flex;
            gap: 10px;
        }
        
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 20px;
            border-radius: 4px;
            color: white;
            font-weight: 500;
            z-index: 1000;
            opacity: 0;
            transform: translateY(-20px);
            transition: opacity 0.3s, transform 0.3s;
        }
        
        .notification.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .notification.success {
            background: var(--success);
        }
        
        .notification.error {
            background: var(--accent);
        }
        
        @media (max-width: 768px) {
            .main-content {
                flex-direction: column;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .stats {
                grid-template-columns: 1fr;
            }
            
            .admin-announcement-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .admin-announcement-actions {
                width: 100%;
                justify-content: flex-end;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">🏫</div>
                    <div class="logo-text">
                        <h1>SMA NEGERI 1 MAJU JAYA</h1>
                        <p>Portal Pengumuman Resmi Sekolah</p>
                    </div>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="active" id="nav-home">Beranda</a></li>
                        <li><a href="#" id="nav-announcements">Pengumuman</a></li>
                        <li><a href="#" id="nav-calendar">Kalender</a></li>
                        <li><a href="#" id="nav-admin">Admin</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <div class="container">
        <!-- Beranda -->
        <div id="home-page">
            <div class="stats">
                <div class="stat-card">
                    <div class="stat-number" id="total-announcements">12</div>
                    <div class="stat-label">Total Pengumuman</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="important-announcements">3</div>
                    <div class="stat-label">Pengumuman Penting</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="this-month">5</div>
                    <div class="stat-label">Bulan Ini</div>
                </div>
            </div>

            <div class="main-content">
                <div class="announcements">
                    <h2 class="section-title">Pengumuman Terbaru</h2>
                    <div class="search-box">
                        <input type="text" id="search-input" placeholder="Cari pengumuman...">
                    </div>
                    <div id="announcements-list">
                        <!-- Pengumuman akan dimuat di sini -->
                    </div>
                </div>
                
                <div class="sidebar">
                    <h2 class="section-title">Kategori</h2>
                    <ul style="list-style: none;">
                        <li style="margin-bottom: 10px;"><a href="#" class="category-filter" data-category="all" style="text-decoration: none; color: var(--secondary);">Semua Pengumuman</a></li>
                        <li style="margin-bottom: 10px;"><a href="#" class="category-filter" data-category="academic" style="text-decoration: none; color: var(--secondary);">Akademik</a></li>
                        <li style="margin-bottom: 10px;"><a href="#" class="category-filter" data-category="activity" style="text-decoration: none; color: var(--secondary);">Kegiatan</a></li>
                        <li style="margin-bottom: 10px;"><a href="#" class="category-filter" data-category="important" style="text-decoration: none; color: var(--secondary);">Penting</a></li>
                        <li style="margin-bottom: 10px;"><a href="#" class="category-filter" data-category="general" style="text-decoration: none; color: var(--secondary);">Umum</a></li>
                    </ul>
                    
                    <h2 class="section-title" style="margin-top: 30px;">Kalender</h2>
                    <div id="calendar" style="background: #f8f9fa; padding: 15px; border-radius: 8px;">
                        <div style="text-align: center; font-weight: bold; margin-bottom: 10px;" id="calendar-month">Oktober 2023</div>
                        <div style="display: grid; grid-template-columns: repeat(7, 1fr); gap: 5px; text-align: center;" id="calendar-days">
                            <!-- Tanggal akan diisi dengan JavaScript -->
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Panel Admin -->
        <div class="admin-panel hidden" id="admin-panel">
            <h2 class="section-title">Panel Admin</h2>
            
            <div class="login-form hidden" id="login-form">
                <h2>Login Admin</h2>
                <div class="form-group">
                    <label for="username">Username</label>
                    <input type="text" id="username" class="form-control" placeholder="Masukkan username">
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" class="form-control" placeholder="Masukkan password">
                </div>
                <button class="btn btn-primary" id="login-btn">Login</button>
                <p style="margin-top: 15px; text-align: center; font-size: 0.9rem;">
                    <strong>Demo Login:</strong><br>
                    Username: admin<br>
                    Password: admin123
                </p>
            </div>
            
            <div class="admin-content hidden" id="admin-content">
                <div class="admin-actions">
                    <button class="btn btn-primary" id="add-new-btn"><i class="fas fa-plus"></i> Tambah Pengumuman Baru</button>
                    <button class="btn btn-warning" id="logout-btn"><i class="fas fa-sign-out-alt"></i> Logout</button>
                </div>
                
                <div class="admin-form hidden" id="announcement-form">
                    <h3 style="margin-bottom: 15px;" id="form-title">Tambah Pengumuman Baru</h3>
                    <div class="form-group">
                        <label for="announcement-title">Judul Pengumuman</label>
                        <input type="text" id="announcement-title" class="form-control" placeholder="Masukkan judul pengumuman">
                    </div>
                    <div class="form-group">
                        <label for="announcement-content">Isi Pengumuman</label>
                        <textarea id="announcement-content" class="form-control" placeholder="Tulis isi pengumuman di sini"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="announcement-category">Kategori</label>
                        <select id="announcement-category" class="form-control">
                            <option value="general">Umum</option>
                            <option value="academic">Akademik</option>
                            <option value="important">Penting</option>
                            <option value="activity">Kegiatan</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="announcement-date">Tanggal</label>
                        <input type="date" id="announcement-date" class="form-control">
                    </div>
                    <div class="admin-actions">
                        <button class="btn btn-primary" id="save-announcement">Simpan Pengumuman</button>
                        <button class="btn btn-danger" id="cancel-edit">Batal</button>
                    </div>
                </div>
                
                <h3 style="margin-top: 30px;">Daftar Pengumuman</h3>
                <div class="search-box">
                    <input type="text" id="admin-search-input" placeholder="Cari pengumuman...">
                </div>
                <div id="admin-announcements-list">
                    <!-- Daftar pengumuman untuk admin akan dimuat di sini -->
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <p>&copy; 2023 SMA Negeri 1 Maju Jaya. Semua hak dilindungi.</p>
            <p>Jl. Pendidikan No. 123, Kota Maju Jaya | Telp: (021) 123456 | Email: info@sman1majujaya.sch.id</p>
        </div>
    </footer>

    <!-- Notifikasi -->
    <div class="notification hidden" id="notification"></div>

    <script>
        // Data pengumuman contoh
        let announcements = [
            {
                id: 1,
                title: "Pembagian Rapor Semester Ganjil",
                content: "Pembagian rapor semester ganjil akan dilaksanakan pada hari Jumat, 15 Desember 2023 pukul 08.00 WIB di aula sekolah. Orang tua/wali murid diharapkan hadir.",
                date: "2023-12-10",
                category: "academic"
            },
            {
                id: 2,
                title: "Libur Semester Ganjil",
                content: "Libur semester ganjil akan dimulai dari tanggal 18 Desember 2023 hingga 6 Januari 2024. Proses belajar mengajar akan dimulai kembali pada tanggal 8 Januari 2024.",
                date: "2023-12-08",
                category: "academic"
            },
            {
                id: 3,
                title: "Peringatan Hari Guru Nasional",
                content: "Dalam rangka memperingati Hari Guru Nasional, sekolah akan mengadakan upacara bendera pada hari Sabtu, 25 November 2023. Semua siswa diwajibkan mengenakan seragam lengkap.",
                date: "2023-11-20",
                category: "activity"
            },
            {
                id: 4,
                title: "Perubahan Jadwal Ujian Akhir Semester",
                content: "Dengan ini diumumkan bahwa jadwal Ujian Akhir Semester (UAS) mengalami perubahan. Silakan lihat jadwal terbaru di papan pengumuman sekolah atau website resmi.",
                date: "2023-11-15",
                category: "important"
            }
        ];

        // Variabel global
        let currentEditingId = null;
        let currentCategoryFilter = 'all';
        let currentSearchTerm = '';

        // Fungsi untuk menampilkan notifikasi
        function showNotification(message, type = 'success') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.className = `notification ${type}`;
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // Fungsi untuk memformat tanggal
        function formatDate(dateString) {
            const options = { day: 'numeric', month: 'short', year: 'numeric' };
            return new Date(dateString).toLocaleDateString('id-ID', options);
        }

        // Fungsi untuk menampilkan pengumuman
        function displayAnnouncements(filteredAnnouncements = null) {
            const announcementsList = document.getElementById('announcements-list');
            announcementsList.innerHTML = '';
            
            const announcementsToDisplay = filteredAnnouncements || announcements;
            
            if (announcementsToDisplay.length === 0) {
                announcementsList.innerHTML = '<p style="text-align: center; padding: 20px; color: #7f8c8d;">Tidak ada pengumuman yang ditemukan.</p>';
                return;
            }
            
            announcementsToDisplay.forEach(announcement => {
                const categoryClass = `category-${announcement.category}`;
                const categoryText = getCategoryText(announcement.category);
                
                const announcementElement = document.createElement('div');
                announcementElement.className = 'announcement-card';
                announcementElement.innerHTML = `
                    <div class="announcement-header">
                        <h3 class="announcement-title">${announcement.title}</h3>
                        <span class="announcement-date">${formatDate(announcement.date)}</span>
                    </div>
                    <div class="announcement-content">
                        ${announcement.content}
                    </div>
                    <span class="announcement-category ${categoryClass}">${categoryText}</span>
                `;
                
                announcementsList.appendChild(announcementElement);
            });
            
            updateStats();
        }

        // Fungsi untuk mendapatkan teks kategori
        function getCategoryText(category) {
            switch(category) {
                case 'academic': return 'Akademik';
                case 'important': return 'Penting';
                case 'activity': return 'Kegiatan';
                default: return 'Umum';
            }
        }

        // Fungsi untuk memperbarui statistik
        function updateStats() {
            document.getElementById('total-announcements').textContent = announcements.length;
            
            const importantCount = announcements.filter(a => a.category === 'important').length;
            document.getElementById('important-announcements').textContent = importantCount;
            
            // Hitung pengumuman bulan ini
            const currentMonth = new Date().getMonth();
            const currentYear = new Date().getFullYear();
            const thisMonthCount = announcements.filter(a => {
                const announcementDate = new Date(a.date);
                return announcementDate.getMonth() === currentMonth && announcementDate.getFullYear() === currentYear;
            }).length;
            
            document.getElementById('this-month').textContent = thisMonthCount;
        }

        // Fungsi untuk menampilkan panel admin
        function showAdminPanel() {
            document.getElementById('home-page').classList.add('hidden');
            document.getElementById('admin-panel').classList.remove('hidden');
            
            // Cek apakah admin sudah login
            const isLoggedIn = localStorage.getItem('adminLoggedIn') === 'true';
            
            if (isLoggedIn) {
                document.getElementById('login-form').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
                displayAdminAnnouncements();
            } else {
                document.getElementById('login-form').classList.remove('hidden');
                document.getElementById('admin-content').classList.add('hidden');
            }
        }

        // Fungsi untuk menampilkan beranda
        function showHomePage() {
            document.getElementById('home-page').classList.remove('hidden');
            document.getElementById('admin-panel').classList.add('hidden');
            displayAnnouncements();
        }

        // Fungsi untuk menampilkan daftar pengumuman di panel admin
        function displayAdminAnnouncements(filteredAnnouncements = null) {
            const adminList = document.getElementById('admin-announcements-list');
            adminList.innerHTML = '';
            
            const announcementsToDisplay = filteredAnnouncements || announcements;
            
            if (announcementsToDisplay.length === 0) {
                adminList.innerHTML = '<p style="text-align: center; padding: 20px; color: #7f8c8d;">Tidak ada pengumuman yang ditemukan.</p>';
                return;
            }
            
            announcementsToDisplay.forEach(announcement => {
                const categoryText = getCategoryText(announcement.category);
                
                const announcementElement = document.createElement('div');
                announcementElement.className = 'admin-announcement-item';
                announcementElement.innerHTML = `
                    <div class="admin-announcement-header">
                        <div class="admin-announcement-title">${announcement.title}</div>
                        <div class="admin-announcement-actions">
                            <button class="btn btn-primary" onclick="editAnnouncement(${announcement.id})"><i class="fas fa-edit"></i> Edit</button>
                            <button class="btn btn-danger" onclick="deleteAnnouncement(${announcement.id})"><i class="fas fa-trash"></i> Hapus</button>
                        </div>
                    </div>
                    <div class="announcement-content">
                        ${announcement.content}
                    </div>
                    <div style="margin-top: 10px; display: flex; justify-content: space-between; align-items: center;">
                        <span class="announcement-category">${categoryText}</span>
                        <span class="announcement-date">${formatDate(announcement.date)}</span>
                    </div>
                `;
                
                adminList.appendChild(announcementElement);
            });
        }

        // Fungsi untuk menambah pengumuman
        function addAnnouncement() {
            const title = document.getElementById('announcement-title').value;
            const content = document.getElementById('announcement-content').value;
            const category = document.getElementById('announcement-category').value;
            const date = document.getElementById('announcement-date').value;
            
            if (!title || !content || !date) {
                showNotification('Semua field harus diisi!', 'error');
                return;
            }
            
            const newAnnouncement = {
                id: announcements.length > 0 ? Math.max(...announcements.map(a => a.id)) + 1 : 1,
                title: title,
                content: content,
                date: date,
                category: category
            };
            
            announcements.unshift(newAnnouncement);
            saveToLocalStorage();
            displayAnnouncements();
            displayAdminAnnouncements();
            
            // Reset form
            document.getElementById('announcement-title').value = '';
            document.getElementById('announcement-content').value = '';
            document.getElementById('announcement-category').value = 'general';
            document.getElementById('announcement-date').value = '';
            document.getElementById('announcement-form').classList.add('hidden');
            
            showNotification('Pengumuman berhasil ditambahkan!');
        }

        // Fungsi untuk mengedit pengumuman
        function editAnnouncement(id) {
            const announcement = announcements.find(a => a.id === id);
            if (!announcement) return;
            
            document.getElementById('announcement-title').value = announcement.title;
            document.getElementById('announcement-content').value = announcement.content;
            document.getElementById('announcement-category').value = announcement.category;
            document.getElementById('announcement-date').value = announcement.date;
            
            document.getElementById('form-title').textContent = 'Edit Pengumuman';
            document.getElementById('announcement-form').classList.remove('hidden');
            
            currentEditingId = id;
        }

        // Fungsi untuk menyimpan perubahan pengumuman
        function saveAnnouncement() {
            if (currentEditingId === null) {
                addAnnouncement();
                return;
            }
            
            const title = document.getElementById('announcement-title').value;
            const content = document.getElementById('announcement-content').value;
            const category = document.getElementById('announcement-category').value;
            const date = document.getElementById('announcement-date').value;
            
            if (!title || !content || !date) {
                showNotification('Semua field harus diisi!', 'error');
                return;
            }
            
            const index = announcements.findIndex(a => a.id === currentEditingId);
            if (index !== -1) {
                announcements[index] = {
                    ...announcements[index],
                    title,
                    content,
                    category,
                    date
                };
                
                saveToLocalStorage();
                displayAnnouncements();
                displayAdminAnnouncements();
                
                // Reset form
                document.getElementById('announcement-form').classList.add('hidden');
                currentEditingId = null;
                
                showNotification('Pengumuman berhasil diperbarui!');
            }
        }

        // Fungsi untuk menghapus pengumuman
        function deleteAnnouncement(id) {
            if (confirm('Apakah Anda yakin ingin menghapus pengumuman ini?')) {
                announcements = announcements.filter(a => a.id !== id);
                saveToLocalStorage();
                displayAnnouncements();
                displayAdminAnnouncements();
                showNotification('Pengumuman berhasil dihapus!');
            }
        }

        // Fungsi untuk login admin
        function loginAdmin() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            // Untuk demo, username dan password adalah "admin" dan "admin123"
            if (username === 'admin' && password === 'admin123') {
                localStorage.setItem('adminLoggedIn', 'true');
                document.getElementById('login-form').classList.add('hidden');
                document.getElementById('admin-content').classList.remove('hidden');
                displayAdminAnnouncements();
                showNotification('Login berhasil!');
            } else {
                showNotification('Username atau password salah!', 'error');
            }
        }

        // Fungsi untuk logout admin
        function logoutAdmin() {
            localStorage.setItem('adminLoggedIn', 'false');
            document.getElementById('login-form').classList.remove('hidden');
            document.getElementById('admin-content').classList.add('hidden');
            document.getElementById('announcement-form').classList.add('hidden');
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
            showNotification('Anda telah logout.');
        }

        // Fungsi untuk menyimpan data ke localStorage
        function saveToLocalStorage() {
            localStorage.setItem('announcements', JSON.stringify(announcements));
        }

        // Fungsi untuk memuat data dari localStorage
        function loadFromLocalStorage() {
            const savedAnnouncements = localStorage.getItem('announcements');
            if (savedAnnouncements) {
                announcements = JSON.parse(savedAnnouncements);
            }
        }

        // Fungsi untuk mencari pengumuman
        function searchAnnouncements() {
            const searchTerm = currentSearchTerm.toLowerCase();
            const filtered = announcements.filter(announcement => 
                announcement.title.toLowerCase().includes(searchTerm) || 
                announcement.content.toLowerCase().includes(searchTerm)
            );
            
            if (currentCategoryFilter !== 'all') {
                return filtered.filter(announcement => announcement.category === currentCategoryFilter);
            }
            
            return filtered;
        }

        // Fungsi untuk membuat kalender
        function renderCalendar() {
            const now = new Date();
            const monthNames = ["Januari", "Februari", "Maret", "April", "Mei", "Juni",
                "Juli", "Agustus", "September", "Oktober", "November", "Desember"
            ];
            
            document.getElementById('calendar-month').textContent = `${monthNames[now.getMonth()]} ${now.getFullYear()}`;
            
            const firstDay = new Date(now.getFullYear(), now.getMonth(), 1);
            const lastDay = new Date(now.getFullYear(), now.getMonth() + 1, 0);
            
            let calendarHTML = '';
            
            // Hari dalam minggu
            const daysOfWeek = ['M', 'S', 'S', 'R', 'K', 'J', 'S'];
            daysOfWeek.forEach(day => {
                calendarHTML += `<div style="font-weight: bold;">${day}</div>`;
            });
            
            // Spasi untuk hari pertama
            for (let i = 0; i < firstDay.getDay(); i++) {
                calendarHTML += `<div></div>`;
            }
            
            // Tanggal
            for (let i = 1; i <= lastDay.getDate(); i++) {
                const isToday = i === now.getDate();
                calendarHTML += `<div style="${isToday ? 'background: var(--secondary); color: white; border-radius: 50%;' : ''}">${i}</div>`;
            }
            
            document.getElementById('calendar-days').innerHTML = calendarHTML;
        }

        // Event listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Muat data dari localStorage
            loadFromLocalStorage();
            
            // Tampilkan halaman beranda
            showHomePage();
            
            // Render kalender
            renderCalendar();
            
            // Navigasi
            document.getElementById('nav-home').addEventListener('click', function(e) {
                e.preventDefault();
                showHomePage();
            });
            
            document.getElementById('nav-admin').addEventListener('click', function(e) {
                e.preventDefault();
                showAdminPanel();
            });
            
            // Login button
            document.getElementById('login-btn').addEventListener('click', loginAdmin);
            
            // Logout button
            document.getElementById('logout-btn').addEventListener('click', logoutAdmin);
            
            // Tambah pengumuman baru
            document.getElementById('add-new-btn').addEventListener('click', function() {
                document.getElementById('form-title').textContent = 'Tambah Pengumuman Baru';
                document.getElementById('announcement-form').classList.remove('hidden');
                document.getElementById('announcement-title').value = '';
                document.getElementById('announcement-content').value = '';
                document.getElementById('announcement-category').value = 'general';
                document.getElementById('announcement-date').value = '';
                currentEditingId = null;
            });
            
            // Simpan pengumuman
            document.getElementById('save-announcement').addEventListener('click', saveAnnouncement);
            
            // Batal edit
            document.getElementById('cancel-edit').addEventListener('click', function() {
                document.getElementById('announcement-form').classList.add('hidden');
                currentEditingId = null;
            });
            
            // Filter kategori
            document.querySelectorAll('.category-filter').forEach(filter => {
                filter.addEventListener('click', function(e) {
                    e.preventDefault();
                    currentCategoryFilter = this.getAttribute('data-category');
                    
                    // Update tampilan filter aktif
                    document.querySelectorAll('.category-filter').forEach(f => {
                        f.style.fontWeight = 'normal';
                    });
                    this.style.fontWeight = 'bold';
                    
                    const filtered = searchAnnouncements();
                    displayAnnouncements(filtered);
                });
            });
            
            // Pencarian
            document.getElementById('search-input').addEventListener('input', function() {
                currentSearchTerm = this.value;
                const filtered = searchAnnouncements();
                displayAnnouncements(filtered);
            });
            
            // Pencarian di admin
            document.getElementById('admin-search-input').addEventListener('input', function() {
                const searchTerm = this.value.toLowerCase();
                const filtered = announcements.filter(announcement => 
                    announcement.title.toLowerCase().includes(searchTerm) || 
                    announcement.content.toLowerCase().includes(searchTerm)
                );
                displayAdminAnnouncements(filtered);
            });
            
            // Set tanggal default ke hari ini
            document.getElementById('announcement-date').valueAsDate = new Date();
        });
    </script>
</body>
</html> 
