<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Fifi's Drag Race Season 4 | Sojourner News</title>

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,400&display=swap" rel="stylesheet" />

  <!-- FontAwesome for Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    /* ===== Brand Palette =====
       Deep Navy   #252958
       Orange      #E2841C
       White       #FDFDFD
       Gray-Blue   #9396AC
    ====================================== */
    :root {
      --primary: #252958;
      --accent:  #E2841C;
      --white:   #FDFDFD;
      --light-bg:#F6F7FA;
      --text-dark:#1A1A1A;
      --text-grey:#666A75;
      --border:  #E2E5EF;
    }
.brand-logo {
  height: 60px; /* Adjust height as needed */
  width: auto;
}
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--white);
      color: var(--text-dark);
      line-height: 1.6;
    }

    h1, h2, h3, h4, h5 {
      font-family: 'Merriweather', serif;
      color: var(--primary);
    }

    a { text-decoration: none; color: inherit; }
    ul { list-style: none; }

    /* --- Top Bar --- */
    .top-bar {
      background-color: var(--primary);
      color: var(--white);
      font-size: 0.8rem;
      padding: 0.5rem 0;
      text-align: center;
      display: flex;
      justify-content: center;
      gap: 20px;
    }
    .top-bar span { cursor: pointer; }
    .top-bar span:hover { color: var(--accent); }

    /* --- Header --- */
    header {
      background: var(--white);
      padding: 1rem 0;
      border-bottom: 1px solid var(--border);
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    }

    .header-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .brand {
      font-size: 1.8rem;
      font-weight: 900;
      font-family: 'Merriweather', serif;
      color: var(--primary);
      letter-spacing: -1px;
    }
    .brand span { color: var(--accent); }

    .menu-toggle {
      display: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--primary);
    }

    .header-actions button {
      background: var(--primary);
      color: var(--white);
      border: none;
      padding: 0.6rem 1.2rem;
      font-weight: 600;
      cursor: pointer;
      border-radius: 4px;
      transition: background 0.3s;
    }
    .header-actions button:hover { background: var(--accent); }

    /* --- Navigation --- */
    nav {
      background: var(--white);
      border-bottom: 3px solid var(--accent);
    }

    .nav-container {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: center;
      position: relative;
    }

    .nav-links { 
      display: flex; 
      gap: 2rem; 
    }

    .nav-links a {
      display: block;
      padding: 1rem 0;
      font-weight: 600;
      font-size: 0.9rem;
      text-transform: uppercase;
      color: var(--text-dark);
      position: relative;
      transition: color 0.3s;
      cursor: pointer;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--accent);
      transition: width 0.3s;
    }

    .nav-links a:hover, .nav-links a.active { color: var(--primary); }
    .nav-links a:hover::after, .nav-links a.active::after { width: 100%; }

    /* --- Mobile Nav --- */
    @media (max-width: 768px) {
      .menu-toggle { display: block; }
      .nav-links {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        background: var(--white);
        flex-direction: column;
        border-bottom: 1px solid var(--border);
        box-shadow: 0 5px 10px rgba(0,0,0,0.1);
        z-index: 999;
      }
      .nav-links.show { display: flex; }
      .nav-links a { padding: 1rem; border-bottom: 1px solid #eee; }
    }

    /* --- Main Layout --- */
    .container {
      max-width: 1000px; /* Narrower for reading */
      margin: 2rem auto;
      padding: 0 1rem;
      display: grid;
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    /* --- Article Header --- */
    .article-header {
      text-align: center;
      margin-bottom: 2rem;
    }

    .category-tag {
      color: var(--accent);
      font-weight: 700;
      text-transform: uppercase;
      font-size: 0.9rem;
      letter-spacing: 1px;
      margin-bottom: 1rem;
      display: block;
    }

    .article-header h1 {
      font-size: 2.5rem;
      line-height: 1.2;
      margin-bottom: 1rem;
    }

    .article-meta {
      color: var(--text-grey);
      font-size: 0.9rem;
      margin-bottom: 1.5rem;
    }

    .article-meta i { margin-right: 5px; color: var(--accent); }

    /* --- Hero Image --- */
    .article-hero-img {
      width: 100%;
      height: 500px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 2rem;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }

    /* --- Article Content --- */
    .article-content {
      font-size: 1.1rem;
      line-height: 1.8;
      color: var(--text-dark);
      max-width: 800px;
      margin: 0 auto;
    }

    .article-content p {
      margin-bottom: 1.5rem;
    }

    .article-content strong {
      color: var(--primary);
    }

    .quote {
      border-left: 4px solid var(--accent);
      padding-left: 1.5rem;
      margin: 2rem 0;
      font-style: italic;
      color: var(--text-grey);
      font-size: 1.2rem;
    }

    .source {
      margin-top: 2rem;
      padding-top: 1rem;
      border-top: 1px solid var(--border);
      font-weight: 600;
      color: var(--primary);
    }

    /* --- Share Buttons --- */
    .share-buttons {
      margin-top: 2rem;
      display: flex;
      gap: 10px;
    }

    .share-btn {
      padding: 0.5rem 1rem;
      border: 1px solid var(--border);
      border-radius: 4px;
      cursor: pointer;
      transition: all 0.3s;
      font-size: 0.9rem;
    }

    .share-btn:hover {
      background: var(--primary);
      color: var(--white);
      border-color: var(--primary);
    }

    /* --- Newsletter --- */
    .newsletter-box {
      background: var(--primary);
      color: var(--white);
      padding: 2rem;
      border-radius: 8px;
      margin-top: 3rem;
      text-align: center;
    }
    .newsletter-box h4 { color: var(--white); margin-bottom: 0.5rem; }
    .newsletter-box p { font-size: 0.9rem; margin-bottom: 15px; }
    .newsletter-box input {
      width: 100%;
      max-width: 300px;
      padding: 0.6rem;
      margin-bottom: 0.5rem;
      border: none;
      border-radius: 4px;
    }
    .newsletter-box button {
      width: 100%;
      max-width: 300px;
      background: var(--accent);
      color: var(--white);
      border: none;
      padding: 0.6rem;
      font-weight: bold;
      border-radius: 4px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .newsletter-box button:hover { background: #c87112; }

    /* --- Footer --- */
    footer {
      background: var(--primary);
      color: var(--white);
      padding: 3rem 1rem;
      margin-top: 3rem;
      text-align: center;
    }

    .footer-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 2rem;
    }

    .footer-col { text-align: left; }
    .footer-col h4 { color: var(--accent); margin-bottom: 1rem; }
    .footer-col a { color: #cfd5e6; display: block; margin-bottom: 0.5rem; }
    .footer-col a:hover { color: var(--accent); }

    .copyright {
      margin-top: 2rem;
      padding-top: 1rem;
      border-top: 1px solid rgba(255,255,255,0.1);
      font-size: 0.9rem;
      color: #cfd5e6;
    }

    /* --- Responsive --- */
    @media (max-width: 768px) {
      .article-header h1 { font-size: 1.8rem; }
      .article-hero-img { height: 250px; }
      .container { padding: 0 1rem; }
    }
  </style>
</head>
<body>

  <!-- Top Info Bar -->
  <div class="top-bar">
    <span id="current-date"></span>
    <span>Manila, PH: 88°F</span>
    <span onclick="scrollToSubscribe()">Subscribe</span>
    <span>Login</span>
  </div>

  <!-- Header -->
  <header>
    <div class="header-container">
      <img src="Sojourne.jpeg" alt="Sojourner News Logo" class="brand-logo">
      <div class="header-actions">
        <i class="fas fa-bars menu-toggle" onclick="toggleMenu()"></i>
        <button onclick="scrollToSubscribe()">Subscribe</button>
      </div>
    </div>
  </header>

  <!-- Navigation -->
  <nav>
    <div class="nav-container">
      <div class="nav-links" id="nav-links">
        <a href="#" onclick="filterCategory('all')">Home</a>
        <a href="#">World</a>
        <a href="#">Entertainment</a>
        <a href="#">Culture</a>
        <a href="#">Politics</a>
        <a href="#">Tech</a>
        <a href="#">Sports</a>
      </div>
    </div>
  </nav>

  <!-- Main Content -->
  <div class="container">
    
    <!-- Article Header -->
    <header class="article-header">
      <span class="category-tag">Entertainment & Culture</span>
      <h1>Fifi's Drag Race Season 4: Celebration of Artistry, Inclusivity, and Fierce Self-Expression</h1>
      <div class="article-meta">
        <span><i class="far fa-clock"></i> October 21, 2025</span> &nbsp;|&nbsp; 
        <span><i class="far fa-user"></i> By Princess Louise Gonzales</span>
      </div>
    </header>

    <!-- Hero Image -->
    <img src="fifidragrace.jpg" alt="Fifi's Drag Race Season 4" class="article-hero-img">

    <!-- Article Body -->
    <article class="article-content">
      <p>Fifi's Drag Race successfully concluded its fourth season, produced by the Broadcasting students from the Hostel of Bulacan State University. The event once again proved to be a vibrant platform for creativity, inclusivity, and empowerment—celebrating the artistry and individuality of every performer who graced the stage.</p>

      <p>Extraordinary, colorful, and dazzling showcases filled the venue with confidence, glamour, and fierce performances. Each contestant brought their unique style and charisma, captivating the audience with stunning looks and exceptional talent. From extravagant costumes to powerful lip-sync numbers, every act embodied passion, creativity, and authenticity—the true essence of drag.</p>

      <blockquote class="quote">
        "Hosted by Madam Fifi, the competition highlighted the importance of self-expression and freedom, giving performers the space to shine unapologetically."
      </blockquote>

      <p>Adding to the excitement, one of the previous season's standout candidates made a special appearance to show support and inspire the new batch of drag artists. The grand finale, held on Friday, October 10, transformed the venue into a dazzling stage of color, energy, and pride.</p>

      <p>The event concluded with a grand awarding ceremony that honored the top performers who impressed the judges with their skill, creativity, and stage presence.</p>

      <p>After weeks of preparation and breathtaking performances, <strong>VANILLAUXXE</strong> emerged as the new Fifi's Drag Race Season 4 Superstar, marking the end of yet another unforgettable season that celebrated not just drag but the power of being unapologetically yourself.</p>

      <div class="source">via Princess Louise Gonzales</div>

      <!-- Share Buttons -->
      <div class="share-buttons">
        <div class="share-btn"><i class="fab fa-facebook-f"></i> Share</div>
        <div class="share-btn"><i class="fab fa-twitter"></i> Tweet</div>
        <div class="share-btn"><i class="fab fa-linkedin-in"></i> Share</div>
      </div>
    </article>

    <!-- Newsletter -->
    <div class="newsletter-box" id="newsletter">
      <h4>Subscribe to Sojourner News</h4>
      <p>Get the latest entertainment news and updates delivered to your inbox.</p>
      <form onsubmit="handleSubscribe(event)">
        <input type="email" placeholder="Your email address" required />
        <button type="submit">Subscribe Now</button>
      </form>
    </div>

  </div>

  <!-- Footer -->
  <footer>
    <div class="footer-grid">
      <div class="footer-col">
        <h4>SojournerNews</h4>
        <p style="color: #cfd5e6; font-size: 0.9rem;">
          Delivering global perspectives with integrity and depth.
        </p>
      </div>
      <div class="footer-col">
        <h4>Sections</h4>
        <a href="#">World</a>
        <a href="#">Entertainment</a>
        <a href="#">Politics</a>
        <a href="#">Business</a>
      </div>
      <div class="footer-col">
        <h4>About</h4>
        <a href="#">Our Story</a>
        <a href="#">Careers</a>
        <a href="#">Contact</a>
      </div>
      <div class="footer-col">
        <h4>Follow Us</h4>
        <a href="#"><i class="fab fa-facebook"></i> Facebook</a>
        <a href="#"><i class="fab fa-twitter"></i> Twitter</a>
        <a href="#"><i class="fab fa-instagram"></i> Instagram</a>
      </div>
    </div>
    <div class="copyright">
      &copy; 2026 SojournerNews. All Rights Reserved.
    </div>
  </footer>

  <script>
    // --- Set Current Date ---
    const dateElement = document.getElementById('current-date');
    const options = { weekday:
      <script>
    // --- Set Current Date ---
    const dateElement = document.getElementById('current-date');
    const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
    dateElement.textContent = new Date().toLocaleDateString('en-US', options);

    // --- Toggle Mobile Menu ---
    function toggleMenu() {
      const navLinks = document.getElementById('nav-links');
      navLinks.classList.toggle('show');
    }

    // --- Scroll to Subscribe ---
    function scrollToSubscribe() {
      document.getElementById('newsletter').scrollIntoView({ behavior: 'smooth' });
    }

    // --- Handle Newsletter Subscribe ---
    function handleSubscribe(event) {
      event.preventDefault();
      const email = event.target.querySelector('input').value;
      alert('Thank you for subscribing! \nEmail: ' + email);
      event.target.reset();
    }
  </script>

</body>
</html>
