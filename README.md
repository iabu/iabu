<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Buku Saku Gizi</title>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.css" rel="stylesheet">
  <style>
    :root {
      --primary: #2ECC71;
      --secondary: #27AE60;
      --accent: #F1C40F;
      --text: #2C3E50;
      --light: #ECF0F1;
      --white: #FFFFFF;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', system-ui, sans-serif;
    }

    body {
      color: var(--text);
      line-height: 1.6;
    }

    /* Navigation */
    nav {
      background: var(--white);
      padding: 1rem 5%;
      position: fixed;
      width: 100%;
      top: 0;
      z-index: 1000;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--primary);
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .logo::before {
      content: '🥗';
      font-size: 1.8rem;
    }

    .menu {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .menu a {
      text-decoration: none;
      color: var(--text);
      font-weight: 500;
      transition: color 0.3s;
      position: relative;
    }

    .menu a:hover {
      color: var(--primary);
    }

    .menu a::after {
      content: '';
      position: absolute;
      width: 0;
      height: 2px;
      bottom: -5px;
      left: 0;
      background-color: var(--primary);
      transition: width 0.3s;
    }

    .menu a:hover::after {
      width: 100%;
    }

    /* Hero Section */
    .hero {
      min-height: 100vh;
      background: linear-gradient(135deg, rgba(46, 204, 113, 0.1), rgba(241, 196, 15, 0.1));
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 5rem 1rem;
    }

    .hero-content {
      max-width: 800px;
      padding: 2rem;
    }

    .hero h1 {
      font-size: 3.5rem;
      margin-bottom: 1rem;
      color: var(--text);
      animation: fadeInUp 1s ease;
    }

    .hero p {
      font-size: 1.5rem;
      margin-bottom: 2rem;
      color: var(--text);
      opacity: 0.9;
    }

    /* Materi Section */
    .materi {
      padding: 5rem 5%;
      background: var(--white);
    }

    .materi h2 {
      text-align: center;
      font-size: 2.5rem;
      margin-bottom: 3rem;
      color: var(--text);
    }

    .materi-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }

    .card {
      background: var(--white);
      border-radius: 15px;
      padding: 2rem;
      text-align: center;
      transition: transform 0.3s, box-shadow 0.3s;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
      cursor: pointer;
    }

    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 25px rgba(0,0,0,0.15);
    }

    .card h3 {
      font-size: 1.5rem;
      margin-bottom: 1rem;
      color: var(--primary);
    }

    .card p {
      margin-bottom: 1.5rem;
      color: var(--text);
      opacity: 0.9;
    }

    /* Buttons */
    button {
      background: var(--primary);
      color: white;
      border: none;
      padding: 1rem 2rem;
      border-radius: 50px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: transform 0.3s, background 0.3s;
    }

    button:hover {
      background: var(--secondary);
      transform: scale(1.05);
    }

    /* Footer */
    footer {
      background: var(--text);
      color: var(--light);
      text-align: center;
      padding: 2rem;
    }

    /* Animations */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Mobile Responsive */
    @media (max-width: 768px) {
      .menu {
        display: none;
      }

      .hero h1 {
        font-size: 2.5rem;
      }

      .hero p {
        font-size: 1.2rem;
      }

      .materi {
        padding: 3rem 1rem;
      }
    }
  </style>
</head>
<body>
  <header>
    <nav>
      <div class="logo">Buku Saku Gizi</div>
      <ul class="menu">
        <li><a href="#home">Beranda</a></li>
        <li><a href="#materi">Materi</a></li>
        <li><a href="#tips">Tips</a></li>
        <li><a href="#kuis">Kuis</a></li>
        <li><a href="#tentang">Tentang Kami</a></li>
      </ul>
    </nav>
  </header>

  <section id="home" class="hero">
    <div class="hero-content" data-aos="fade-up">
      <h1>Membangun Generasi Sehat</h1>
      <p>Dimulai dari Gizi yang Tepat!</p>
      <button onclick="scrollToSection('materi')">Pelajari Sekarang</button>
    </div>
  </section>

  <section id="materi" class="materi">
    <h2 data-aos="fade-up">Materi Utama</h2>
    <div class="materi-grid">
      <div class="card" data-aos="fade-up" data-aos-delay="100">
        <h3>Triple Burden</h3>
        <p>Tiga masalah besar gizi di Indonesia yang perlu kita ketahui dan atasi bersama.</p>
        <button>Baca Selengkapnya</button>
      </div>
      <div class="card" data-aos="fade-up" data-aos-delay="200">
        <h3>Stunting</h3>
        <p>Kenali dan cegah pertumbuhan terhambat pada anak sejak dini.</p>
        <button>Baca Selengkapnya</button>
      </div>
      <div class="card" data-aos="fade-up" data-aos-delay="300">
        <h3>Pemenuhan Nutrisi</h3>
        <p>Panduan lengkap gizi sesuai usia anak untuk tumbuh kembang optimal.</p>
        <button>Baca Selengkapnya</button>
      </div>
    </div>
  </section>

  <footer>
    <p>&copy; 2024 Buku Saku Gizi - Semua Hak Dilindungi</p>
  </footer>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.js"></script>
  <script>
    // Initialize AOS
    AOS.init({
      duration: 1000,
      once: true
    });

    // Smooth scroll function
    function scrollToSection(sectionId) {
      document.getElementById(sectionId).scrollIntoView({
        behavior: 'smooth'
      });
    }

    // Add shadow to navbar on scroll
    window.addEventListener('scroll', function() {
      const nav = document.querySelector('nav');
      if (window.scrollY > 50) {
        nav.style.boxShadow = '0 2px 10px rgba(0,0,0,0.1)';
      } else {
        nav.style.boxShadow = 'none';
      }
    });
  </script>
</body>
</html>
