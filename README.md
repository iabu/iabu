<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Buku Saku Gizi</title>
  <style>
    :root {
      --primary: #2ECC71;
      --text: #2C3E50;
      --page: #fff;
      --shadow: rgba(0,0,0,0.1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', system-ui, sans-serif;
    }

    body {
      background: #f0f2f5;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 2rem 1rem;
      color: var(--text);
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
      height: 600px;
      transform-style: preserve-3d;
      transition: transform 0.5s;
      box-shadow: 0 0 20px var(--shadow);
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
    }

    .page.active {
      display: block;
    }

    .page-content {
      max-width: 600px;
      margin: 0 auto;
    }

    .page-number {
      position: absolute;
      bottom: 2rem;
      width: 100%;
      text-align: center;
      font-size: 0.9rem;
      color: #666;
    }

    h1 {
      color: var(--primary);
      font-size: 2rem;
      margin-bottom: 1.5rem;
    }

    h2 {
      color: var(--primary);
      font-size: 1.5rem;
      margin: 1.5rem 0 1rem;
    }

    p {
      margin-bottom: 1rem;
      line-height: 1.6;
    }

    ul {
      margin: 1rem 0;
      padding-left: 1.5rem;
    }

    li {
      margin-bottom: 0.5rem;
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
      padding: 0.8rem 1.5rem;
      border-radius: 50px;
      cursor: pointer;
      transition: transform 0.3s, opacity 0.3s;
    }

    button:hover {
      opacity: 0.9;
      transform: scale(1.05);
    }

    button:disabled {
      background: #ccc;
      cursor: not-allowed;
      transform: none;
    }

    .progress {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background: var(--primary);
      color: white;
      padding: 0.5rem 1rem;
      border-radius: 20px;
      font-size: 0.9rem;
    }

    @media (max-width: 768px) {
      .book {
        height: 500px;
      }

      .page {
        padding: 1.5rem;
      }

      h1 {
        font-size: 1.5rem;
      }

      h2 {
        font-size: 1.2rem;
      }
    }
  </style>
</head>
<body>
  <div class="progress">Halaman <span id="currentPage">1</span> dari <span id="totalPages">5</span></div>
  
  <div class="book-container">
    <div class="book" id="book">
      <div class="page active" id="page1">
        <div class="page-content">
          <h1>Triple Burden of Malnutrition</h1>
          <p>Nutritional problems in children in Indonesia often do not stand alone. There are three major problems called the Triple Burden of Malnutrition, namely:</p>
          
          <h2>Undernutrition:</h2>
          <p>Children who lack nutritious food can experience:</p>
          <ul>
            <li><strong>Stunting:</strong> Children grow short due to long-term malnutrition.</li>
            <li><strong>Wasting:</strong> Children are too thin for their height.</li>
            <li><strong>Underweight:</strong> Children's weight is too low for their age.</li>
          </ul>
          
          <h2>Overnutrition:</h2>
          <p>Children who eat too many high-calorie but low-nutrient foods can lead to obesity, risking serious diseases like diabetes or high blood pressure.</p>
        </div>
        <div class="page-number">Halaman 1</div>
      </div>

      <div class="page" id="page2">
        <div class="page-content">
          <h1>Apa itu Stunting?</h1>
          <p>Stunting is one of the most serious forms of malnutrition in Indonesia. Children who experience stunting usually:</p>
          <ul>
            <li>Grow shorter than children their age.</li>
            <li>Have stunted brain development, so their learning ability is lower.</li>
            <li>Are at risk of experiencing health problems as adults.</li>
          </ul>

          <h2>Causes of stunting:</h2>
          <ul>
            <li>Not enough nutritious food, especially in the First 1000 Days of Life.</li>
            <li>Improper parenting, such as not providing exclusive breastfeeding.</li>
            <li>Poor sanitation, such as unclean drinking water.</li>
          </ul>
        </div>
        <div class="page-number">Halaman 2</div>
      </div>

      <div class="page" id="page3">
        <div class="page-content">
          <h1>Pemenuhan Nutrisi Setiap Tahap</h1>
          
          <h2>0-6 bulan:</h2>
          <p>Provide exclusive breastfeeding. Breast milk contains all the nutrients a baby needs.</p>
          
          <h2>6-12 bulan:</h2>
          <p>Add Complementary Foods (MPASI). Ensure MPASI contains iron, protein, and vitamins.</p>
          
          <h2>1-2 tahun:</h2>
          <p>Children start eating family food. Provide a variety of foods like rice, meat, fish, vegetables.</p>
          
          <h2>2-5 tahun:</h2>
          <p>Children need to learn to eat with a regular and nutritious pattern.</p>
        </div>
        <div class="page-number">Halaman 3</div>
      </div>

      <div class="page" id="page4">
        <div class="page-content">
          <h1>Tips Pengasuhan Gizi</h1>
          
          <h2>Menangani Anak Susah Makan:</h2>
          <ul>
            <li>Don't force your child to eat</li>
            <li>Serve food with an attractive appearance</li>
            <li>Make mealtime a fun moment</li>
          </ul>

          <h2>Membangun Kebiasaan Makan Sehat:</h2>
          <ul>
            <li>Involve children in preparing food</li>
            <li>Give examples of healthy eating patterns</li>
            <li>Limit sweet snacks and fried foods</li>
          </ul>
        </div>
        <div class="page-number">Halaman 4</div>
      </div>

      <div class="page" id="page5">
        <div class="page-content">
          <h1>Mitos & Fakta Tentang Gizi</h1>
          
          <h2>Mitos 1:</h2>
          <p><strong>Mitos:</strong> Fat children are healthy.<br>
          <strong>Fakta:</strong> Fat children are at higher risk of developing diseases.</p>
          
          <h2>Mitos 2:</h2>
          <p><strong>Mitos:</strong> Children who don't like vegetables don't need to eat them.<br>
          <strong>Fakta:</strong> Children still need to learn to eat vegetables.</p>
          
          <h2>Mitos 3:</h2>
          <p><strong>Mitos:</strong> Formula milk is as good as breast milk.<br>
          <strong>Fakta:</strong> Breast milk remains the best choice.</p>
        </div>
        <div class="page-number">Halaman 5</div>
      </div>
    </div>
  </div>

  <div class="navigation">
    <button id="prevBtn" onclick="changePage(-1)" disabled>← Sebelumnya</button>
    <button id="nextBtn" onclick="changePage(1)">Selanjutnya →</button>
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
      
      // Update buttons
      document.getElementById('prevBtn').disabled = currentPage === 1;
      document.getElementById('nextBtn').disabled = currentPage === totalPages;
      
      // Add page turn animation
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

      if (Math.abs(diff) > 50) { // Minimum swipe distance
        if (diff > 0 && currentPage < totalPages) { // Swipe left
          changePage(1);
        } else if (diff < 0 && currentPage > 1) { // Swipe right
          changePage(-1);
        }
      }
    });
  </script>
</body>
</html>
