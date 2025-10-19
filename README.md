<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Post 2 - ERD & Normalisasi</title>
  <style>
    :root{
      --pink:#ff8fb1;
      --ungu:#8b5cf6;
      --abu:#8d7792;
      --hitam:#0b0b0b;
      --biru:#4da6ff;
      --glass: rgba(255,255,255,0.6);
      --card-shadow: 0 8px 24px rgba(11,11,11,0.12);
      font-family: 'Poppins', Inter, ui-sans-serif, system-ui;
    }

    *{box-sizing:border-box}
    html,body{
      height:100%;
      margin:0;
      background:linear-gradient(180deg,#8268ac,#000000);
      color:var(--hitam)
    }

    .container{
      max-width:980px;
      margin:28px auto;
      padding:20px;
    }

    header{
      display:flex;
      align-items:center;
      gap:18px;
      padding:18px;
      border-radius:18px;
      background:linear-gradient(90deg,rgba(238, 230, 255, 0.829),rgba(144, 89, 154, 0.708));
      box-shadow:var(--card-shadow)
    }

    .avatar{
      width:100px;
      height:100px;
      border-radius:18px;
      overflow:hidden;
      flex:0 0 100px;
      background:linear-gradient(135deg,var(--pink),var(--ungu));
      display:grid;
      place-items:center;
      border:4px solid rgba(255,255,255,0.6);
    }

    .avatar img{width:100%;height:100%;object-fit:cover;display:block}
    .profile-info h1{margin:0;font-size:1.25rem;color:#371b5e}
    .profile-info p{margin:6px 0 0;color:#371b5e}
    .badges{margin-top:8px;display:flex;flex-wrap:wrap;gap:8px;color:#371b5e}
    .badge{background:#e6e6e9;padding:6px 10px;border-radius:999px;font-size:12px}

    /* Navbar */
    .navbar {
      background: linear-gradient(90deg, #a855f7, #ec4899);
      color: white;
      padding: 12px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-radius: 0 0 12px 12px;
    }
    .navbar .logo { font-weight: bold; font-size: 18px; }
    .navbar ul { list-style: none; display: flex; gap: 16px; margin: 0; padding: 0; }
    .navbar ul li a { color: white; text-decoration: none; font-weight: 600; }
    .navbar ul li a:hover { text-decoration: underline; }

    /* Konten */
    .post {
      background:linear-gradient(180deg,rgba(255, 255, 255, 0.8),rgba(208, 195, 220, 0.7));
      border-radius:14px;
      box-shadow:var(--card-shadow);
      padding:20px;
      margin-top:20px;
    }
    .post h1, .post h2, .post h3 { color:#dc27b5; margin-top:0; }
    .post p { line-height:1.6; color:#222; }
    .post ul { margin:10px 0 10px 20px; }
    .post li { margin-bottom:6px; }

    .img-container{text-align:center;margin:16px 0;}
    .img-container img{max-width:80%;border-radius:10px;box-shadow:0 0 20px rgba(56,182,255,0.25);border:1px solid rgba(56,182,255,0.2);transition:transform .3s ease;}
    .img-container img:hover{transform:scale(1.03);box-shadow:0 0 25px rgba(56,182,255,0.4);}
    .img-caption{font-size:20px;color:#9aa8bf;margin-top:6px;font-style:italic;}

    iframe {
      display:block;
      margin:20px auto;
      border-radius:14px;
      box-shadow:0 0 25px rgba(255,192,203,0.4);
    }

    pre {
      background: #f3e5f5;
      padding: 10px;
      border-radius: 10px;
      overflow-x: auto;
      color: #6f42c1;
      font-weight: bold;
    }

    /* TABLE STYLE */
    table {
      width: 100%;
      border-collapse: collapse;
      margin: 15px 0;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }
    table th {
      background: linear-gradient(90deg, #a855f7, #ec4899);
      color: white;
      padding: 10px;
      text-align: center;
      font-size: 14px;
    }
    table td {
      background: rgba(255,255,255,0.8);
      padding: 10px;
      border-bottom: 1px solid rgba(0,0,0,0.05);
      text-align: center;
      font-size: 14px;
    }
    table tr:hover td {
      background: rgba(255,240,250,0.8);
    }

    footer{margin-top:20px;text-align:center;color:#ccc;font-size:13px}
  </style>
</head>

<body>
  <!-- Navbar -->
  <nav class="navbar">
    <div class="logo">🌸 My Blog</div>
    <ul>
      <li><a href="index.html">Home</a></li>
      <li><a href="profile.html">Profile</a></li>
      <li><a href="blog.html">Tugas Blog</a></li>
    </ul>
  </nav>

  <div class="container">
    <header>
      <div class="avatar">
        <img src="foto1.jpg" alt="Foto Profil" class="profile-img">
      </div>
      <div class="profile-info">
        <h1>KAISHA KAMILA PUSPITO</h1>
        <p>Teknik Informatika UBP Karawang</p>
        <div class="badges">
          <span class="badge">NIM : 24416255201028</span>
          <span class="badge">if24.kaishapuspito@mhs.ubpkarawang.ac.id</span>
          <span class="badge">Basis Data</span>
        </div>
      </div>
    </header>

    <!-- POST 1 -->
    <div class="post">
      <h1>🩺 Post 1: Contoh penerapan ERD Intersection (5 kasus) </h1>
      <p>Berikut penjelasan singkat melalui video pembelajaran dan beberapa ilustrasi pendukung:</p>

      <!-- Video YouTube -->
       <h3>1. Penjelasan Sistem Manajemen Rumah Sakit</h3>
      <iframe width="560" height="315" src="https://www.youtube.com/embed/n7jqsydeKMk?si=Giagw2arh8Hwfgw8"
        title="Video ERD Keys" frameborder="0" allowfullscreen> 
        <p class="img-caption">Video Penjelasan ERD Intersection</p>
      </iframe>

      <!-- Gambar tambahan -->
       <h3>2. Tabel Sistem Informasi Perpustakaan Digital</h3>
      <div class="img-container">
        <img src="tabel2.png" alt="ERD Apotek">
        <p class="img-caption">Gambar 1: Sistem Informasi Perpustakaan Digital</p>
      </div>
      <h3>3. Tabel Sistem E-Commerce Fashion Store</h3>
      <div class="img-container">
        <img src="tabel3.png" alt="ERD Apotek">
        <p class="img-caption">Gambar 2: Sistem E-Commerce Fashion Store</p>
      </div>
      <h3>4. Tabel Sistem Akademik Kampus</h3>
      <div class="img-container">
        <img src="tabel4.png" alt="ERD Apotek">
        <p class="img-caption">Gambar 4: Sistem Akademik Kampus</p>
      </div>
      <h3>5. Tabel Sistem Reservasi Hotel</h3>
      <div class="img-container">
        <img src="tabel5.png" alt="ERD Apotek">
        <p class="img-caption">Gambar 5: Sistem Reservasi Hotel</p>
      </div>
    </div>
    

    <!-- POST 2 -->
    <div class="post">
      <h1>🧩 Post 2: Apa Itu Normalisasi pada ERD?</h1>

      <h2>📘 Pengertian Normalisasi</h2>
      <p>Normalisasi adalah proses penyusunan tabel dalam database agar data tersimpan dengan efisien dan tidak terjadi pengulangan (redundansi). Proses ini dilakukan setelah pembuatan ERD untuk memastikan data ditempatkan secara logis dan terhubung dengan baik. Tujuannya agar database lebih rapi, konsisten, dan mudah dipelihara.</p>

      <h2>🎯 Tujuan Normalisasi</h2>
      <ul>
        <li>Menghilangkan data yang berulang.</li>
        <li>Menjaga konsistensi dan keakuratan data.</li>
        <li>Mempermudah proses update, insert, dan delete.</li>
        <li>Membuat database lebih efisien dan cepat diakses.</li>
        <li>Memastikan hubungan antar tabel tetap logis.</li>
      </ul>

      <h2>🧱 Tahapan Normalisasi (Normal Form)</h2>
      <h3>🔹 1NF — First Normal Form</h3>
      <p>Setiap atribut hanya boleh berisi satu nilai (atomic). Tidak boleh ada kolom yang menampung banyak data.</p>
      <p><em>Contoh:</em> Jika satu kolom “NoTelepon” berisi banyak nomor, pisahkan jadi tabel baru.</p>

      <h3>🔹 2NF — Second Normal Form</h3>
      <p>Sudah memenuhi 1NF dan semua kolom non-key harus bergantung penuh pada primary key.</p>

      <h3>🔹 3NF — Third Normal Form</h3>
      <p>Sudah memenuhi 2NF dan tidak boleh ada kolom non-key yang bergantung pada kolom non-key lainnya.</p>

      <h2>🧮 Contoh Kasus Sebelum Dinormalisasi</h2>
      <table>
        <thead>
          <tr>
            <th>NIM</th>
            <th>Nama</th>
            <th>KodeMK</th>
            <th>NamaMK</th>
            <th>Dosen</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>001</td><td>Budi</td><td>MK01</td><td>Basis Data</td><td>Ibu Sari</td></tr>
          <tr><td>002</td><td>Sinta</td><td>MK02</td><td>Algoritma</td><td>Pak Budi</td></tr>
        </tbody>
      </table>

      <p><strong>Masalah:</strong> Data dosen bisa berulang pada setiap baris mata kuliah yang sama, dan kalau nama dosen berubah, semua baris harus diubah satu per satu.</p>

      <h2>💡 Setelah Dinormalisasi (3NF)</h2>
      <h3>🧑‍🎓 Tabel Mahasiswa</h3>
      <table>
        <thead>
          <tr><th>NIM</th><th>Nama</th></tr>
        </thead>
        <tbody>
          <tr><td>001</td><td>Budi</td></tr>
          <tr><td>002</td><td>Sinta</td></tr>
        </tbody>
      </table>

      <h3>📘 Tabel Mata Kuliah</h3>
      <table>
        <thead>
          <tr><th>KodeMK</th><th>NamaMK</th><th>Dosen</th></tr>
        </thead>
        <tbody>
          <tr><td>MK01</td><td>Basis Data</td><td>Ibu Sari</td></tr>
          <tr><td>MK02</td><td>Algoritma</td><td>Pak Budi</td></tr>
        </tbody>
      </table>

      <h3>📋 Tabel KRS (Relasi Intersection)</h3>
      <table>
        <thead>
          <tr><th>NIM</th><th>KodeMK</th></tr>
        </thead>
        <tbody>
          <tr><td>001</td><td>MK01</td></tr>
          <tr><td>002</td><td>MK02</td></tr>
        </tbody>
      </table>

      <h2>🧠 Kesimpulan</h2>
      <ul>
        <li>Normalisasi mengatur struktur database agar efisien.</li>
        <li>Menghindari duplikasi data.</li>
        <li>Menjaga hubungan antar entitas tetap logis dan mudah diatur.</li>
      </ul>
    </div>

    <footer>
      © 2025 Blog Basis Data | Kaisha | 
      <a href="https://www.ubpkarawang.ac.id" target="_blank" style="color:#fff">UBP Karawang</a>
    </footer>
  </div>
</body>
</html>
