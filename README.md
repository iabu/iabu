<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Buku Saku Gizi</title>
  <style>
    :root {
      --primary: #FF6B6B;
      --secondary: #4ECDC4;
      --accent: #FFE66D;
      --text: #2C3E50;
      --page: #fff;
      --shadow: rgba(0,0,0,0.1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Comic Sans MS', 'Segoe UI', system-ui, sans-serif;
    }

    body {
      background: #f0f2f5;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 2rem 1rem;
      color: var(--text);
      background: linear-gradient(135deg, #FFE66D 0%, #4ECDC4 100%);
    }

    .book-container {
      max-width: 1200px;
      width: 100%;
      display: flex;
      justify-content: center;
      perspective: 2000px;
    }

    .book {
      background: var(--page);
      position: relative;
      width: 100%;
      max-width: 800px;
      height: 80vh;
      transform-style: preserve-3d;
      transition: transform 0.5s;
      box-shadow: 0 0 20px var(--shadow);
      border-radius: 20px;
      background-image: url("data:image/svg+xml,%3Csvg width='52' height='26' viewBox='0 0 52 26' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ff6b6b' fill-opacity='0.05'%3E%3Cpath d='M10 10c0-2.21-1.79-4-4-4-3.314 0-6-2.686-6-6h2c0 2.21 1.79 4 4 4 3.314 0 6 2.686 6 6 0 2.21 1.79 4 4 4 3.314 0 6 2.686 6 6 0 2.21 1.79 4 4 4v2c-3.314 0-6-2.686-6-6 0-2.21-1.79-4-4-4-3.314 0-6-2.686-6-6zm25.464-1.95l8.486 8.486-1.414 1.414-8.486-8.486 1.414-1.414z' /%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    }

    .page {
      position: absolute;
      width: 100%;
      height: 100%;
      padding: 2rem 3rem;
      background: var(--page);
      overflow-y: auto;
      display: none;
      transform-origin: left center;
      transition: transform 0.5s;
      border-radius: 20px;
    }

    .page.active {
      display: block;
    }

    .page-content {
      max-width: 600px;
      margin: 0 auto;
    }

    .decoration-top {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 10px;
      background: linear-gradient(90deg, var(--primary), var(--secondary));
      border-radius: 20px 20px 0 0;
    }

    .decoration-bottom {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 10px;
      background: linear-gradient(90deg, var(--secondary), var(--primary));
      border-radius: 0 0 20px 20px;
    }

    .page-number {
      position: absolute;
      bottom: 2rem;
      width: 100%;
      text-align: center;
      font-size: 1.2rem;
      color: var(--primary);
      font-weight: bold;
    }

    .mascot {
      position: absolute;
      bottom: 20px;
      right: 20px;
      width: 100px;
      height: 100px;
      background: url('/api/placeholder/100/100') center/cover;
      animation: bounce 2s infinite;
    }

    h1 {
      color: var(--primary);
      font-size: 2.5rem;
      margin-bottom: 1.5rem;
      text-align: center;
      text-shadow: 2px 2px 0 var(--accent);
    }

    h2 {
      color: var(--secondary);
      font-size: 1.8rem;
      margin: 1.5rem 0 1rem;
      border-bottom: 3px dashed var(--accent);
      padding-bottom: 0.5rem;
    }

    p {
      margin-bottom: 1rem;
      line-height: 1.6;
      font-size: 1.1rem;
    }

    ul {
      margin: 1rem 0;
      padding-left: 1.5rem;
      list-style: none;
    }

    li {
      margin-bottom: 1rem;
      padding-left: 2rem;
      position: relative;
    }

    li:before {
      content: '🌟';
      position: absolute;
      left: 0;
    }

    .image-container {
      width: 200px;
      height: 200px;
      margin: 1rem auto;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 5px 15px var(--shadow);
      transform: rotate(-3deg);
      transition: transform 0.3s;
    }

    .image-container:hover {
      transform: rotate(0) scale(1.05);
    }

    .navigation {
      display: flex;
      gap: 1rem;
      margin-top: 2rem;
    }

    button {
      background: var(--primary);
      color: white;
      border: none;
      padding: 1rem 2rem;
      border-radius: 50px;
      cursor: pointer;
      transition: transform 0.3s, opacity 0.3s;
      font-size: 1.1rem;
      font-weight: bold;
      box-shadow: 0 4px 0 darken(var(--primary), 10%);
    }

    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 0 darken(var(--primary), 10%);
    }

    button:active {
      transform: translateY(2px);
      box-shadow: 0 2px 0 darken(var(--primary), 10%);
    }

    button:disabled {
      background: #ccc;
      transform: none;
      box-shadow: none;
    }

    .progress {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background: var(--primary);
      color: white;
      padding: 0.8rem 1.5rem;
      border-radius: 20px;
      font-size: 1.1rem;
      box-shadow: 0 4px 10px var(--shadow);
      animation: float 3s infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    /* Fun decorative elements */
    .corner-decoration {
      position: absolute;
      width: 50px;
      height: 50px;
      background: var(--accent);
      opacity: 0.2;
      border-radius: 50%;
    }

    .corner-decoration.top-left { top: 20px; left: 20px; }
    .corner-decoration.top-right { top: 20px; right: 20px; }
    .corner-decoration.bottom-left { bottom: 20px; left: 20px; }
    .corner-decoration.bottom-right { bottom: 20px; right: 20px; }

    @media (max-width: 768px) {
      .book {
        height: 70vh;
      }

      .page {
        padding: 1.5rem;
      }

      h1 {
        font-size: 2rem;
      }

      h2 {
        font-size: 1.5rem;
      }

      .image-container {
        width: 150px;
        height: 150px;
      }
    }
  </style>
</head>
<body>
  <div class="progress">Halaman <span id="currentPage">1</span> dari <span id="totalPages">5</span></div>
  
  <div class="book-container">
    <div class="book" id="book">
      <div class="page active" id="page1">
        <div class="decoration-top"></div>
        <div class="decoration-bottom"></div>
        <div class="corner-decoration top-left"></div>
        <div class="corner-decoration top-right"></div>
        <div class="corner-decoration bottom-left"></div>
        <div class="corner-decoration bottom-right"></div>
        
        <div class="page-content">
          <h1>Triple Burden of Malnutrition</h1>
          
          <div class="image-container">
            <img src="/api/placeholder/200/200" alt="Nutrition Balance" />
          </div>
          
          <h2>✨ Undernutrition</h2>
          <div class="image-container">
            <img src="/api/placeholder/200/200" alt="Undernutrition" />
          </div>
          <ul>
            <li>Stunting: Anak tumbuh pendek</li>
            <li>Wasting: Anak terlalu kurus</li>
            <li>Underweight: Berat badan kurang</li>
          </ul>
        </div>
        <div class="page-number">1</div>
        <div class="mascot"></div>
      </div>

      <!-- Similar structure for other pages... -->
      <!-- Pages 2-5 would follow the same pattern with appropriate content and images -->

    </div>
  </div>

  <div class="navigation">
    <button id="prevBtn" onclick="changePage(-1)" disabled>← Kembali</button>
    <button id="nextBtn" onclick="changePage(1)">Lanjut →</button>
  </div>

  <script>
    let currentPage = 1;
    const totalPages = 5;

    function changePage(direction) {
      const oldPage = document.getElementById(`page${currentPage}`);
      currentPage += direction;
      const newPage = document.getElementById(`page${currentPage}`);
      
      oldPage.classList.remove('active');
      newPage.classList.add('active');
      
      document.getElementById('currentPage').textContent = currentPage;
      
      document.getElementById('prevBtn').disabled = currentPage === 1;
      document.getElementById('nextBtn').disabled = currentPage === totalPages;
      
      const book = document.getElementById('book');
      book.style.transform = `rotateY(${direction * -2}deg)`;
      setTimeout(() => {
        book.style.transform = 'rotateY(0)';
      }, 200);
    }

    // Add touch swipe functionality
    let touchStartX = 0;
    const book = document.getElementById('book');

    book.addEventListener('touchstart', e => {
      touchStartX = e.touches[0].clientX;
    });

    book.addEventListener('touchend', e => {
      const touchEndX = e.changedTouches[0].clientX;
      const diff = touchStartX - touchEndX;

      if (Math.abs(diff) > 50) {
        if (diff > 0 && currentPage < totalPages) {
          changePage(1);
        } else if (diff < 0 && currentPage > 1) {
          changePage(-1);
        }
      }
    });
  </script>
</body>
</html>
