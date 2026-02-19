<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sojourner News | Global Perspective</title>
  
  <!-- Fonts: Merriweather for headings, Inter for body -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,400&display=swap" rel="stylesheet">

  <style>
    :root {
      --primary: #060221; /* Blue Magenta */
      --accent: #F19808;  /* Gamboge */
      --light-bg: #f4f4f4;
      --white: #ffffff;
      --text-dark: #1a1a1a;
      --text-grey: #666;
      --border: #e0e0e0;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: #fcfcfc;
      color: var(--text-dark);
      line-height: 1.6;
    }

    h1, h2, h3, h4, h5 {
      font-family: 'Merriweather', serif;
      color: var(--primary);
    }

    a { text-decoration: none; color: inherit; transition: 0.3s; }
    ul { list-style: none; }

    /* --- Top Bar --- */
    .top-bar {
      background-color: var(--primary);
      color: var(--white);
      font-size: 0.8rem;
      padding: 0.5rem 0;
      text-align: center;
    }
    .top-bar span { margin: 0 10px; }

    /* --- Header --- */
    header {
      background: var(--white);
      padding: 1.5rem 0;
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
      font-size: 2rem;
      font-weight: 900;
      font-family: 'Merriweather', serif;
      color: var(--primary);
      letter-spacing: -1px;
    }

    .brand span { color: var(--accent); }

    .header-actions button {
      background: var(--primary);
      color: var(--white);
      border: none;
      padding: 0.5rem 1rem;
      font-weight: 600;
      cursor: pointer;
      border-radius: 4px;
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
      font-size: 0.95rem;
      text-transform: uppercase;
      color: var(--text-dark);
      position: relative;
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

    .nav-links a:hover { color: var(--primary); }
    .nav-links a:hover::after { width: 100%; }

    /* --- Main Layout --- */
    .container {
      max-width: 1200px;
      margin: 2rem auto;
      padding: 0 1rem;
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 2rem;
    }

    /* --- Hero Section (Featured) --- */
    .hero-section {
      grid-column: 1 / -1;
      display: grid;
      grid-template-columns: 1.5fr 1fr;
      gap: 1.5rem;
      margin-bottom: 2rem;
      border-bottom: 1px solid var(--border);
      padding-bottom: 2rem;
    }

    .hero-img {
      width: 100%;
      height: 400px;
      object-fit: cover;
      border-radius: 8px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }

    .hero-content {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .category-tag {
      color: var(--accent);
      font-weight: 700;
      text-transform: uppercase;
      font-size: 0.8rem;
      letter-spacing: 1px;
      margin-bottom: 0.5rem;
    }

    .hero-content h1 {
      font-size: 2.5rem;
      line-height: 1.2;
      margin-bottom: 1rem;
    }

    .hero-content p {
      color: var(--text-grey);
      font-size: 1.1rem;
      margin-bottom: 1.5rem;
    }

    .read-more {
      display: inline-block;
      padding: 0.7rem 1.5rem;
      background: var(--primary);
      color: var(--white);
      font-weight: 600;
      border-radius: 4px;
    }
    .read-more:hover { background: var(--accent); }

    /* --- Articles Grid --- */
    .articles-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1.5rem;
    }

    .news-card {
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: 8px;
      overflow: hidden;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .news-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    }

    .news-card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }

    .card-content { padding: 1.2rem; }

    .card-content h3 {
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
      line-height: 1.4;
    }

    .card-content p {
      font-size: 0.9rem;
      color: var(--text-grey);
      margin-bottom: 1rem;
    }

    .meta {
      font-size: 0.8rem;
      color: #999;
      display: flex;
      justify-content: space-between;
    }

    /* --- Sidebar --- */
    aside {
      background: var(--light-bg);
      padding: 1.5rem;
      border-radius: 8px;
      height: fit-content;
    }

    aside h3 {
      border-bottom: 2px solid var(--accent);
      padding-bottom: 0.5rem;
      margin-bottom: 1.5rem;
      font-size: 1.2rem;
    }

    .sidebar-list li {
      margin-bottom: 1rem;
      border-bottom: 1px solid #ddd;
      padding-bottom: 1rem;
    }

    .sidebar-list h4 {
      font-size: 1rem;
      font-family: 'Inter', sans-serif;
      font-weight: 600;
      margin-bottom: 0.3rem;
    }

    .newsletter-box {
      background: var(--primary);
      color: var(--white);
      padding: 1.5rem;
      border-radius: 8px;
      margin-top: 2rem;
      text-align: center;
    }
    .newsletter-box h4 { color: var(--white); margin-bottom: 0.5rem; }
    .newsletter-box input {
      width: 100%;
      padding: 0.5rem;
      margin-bottom: 0.5rem;
      border: none;
      border-radius: 4px;
    }
    .newsletter-box button {
      width: 100%;
      background: var(--accent);
      color: var(--white);
      border: none;
      padding: 0.5rem;
      font-weight: bold;
 4px;
      border-radius:      cursor: pointer;
    }

    /* --- Footer --- */
    footer {
      background: var(--primary);
      color: var(--white);
      padding: 3rem 1rem;
      margin-top: 3rem;
    }

    .footer-grid {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 2rem;
    }

    .footer-col h4 {
      color: var(--accent);
      margin-bottom: 1rem;
      font-family: 'Inter', sans-serif;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .footer-col ul li { margin-bottom: 0.5rem; }
    .footer-col a:hover { color: var(--accent); }

    .copyright {
      text-align: center;
      margin-top: 2rem;
      padding-top: 1rem;
      border-top: 1px solid rgba(255,255,255,0.1);
      font-size: 0.9rem;
      color: #ccc;
    }

    /* --- Mobile Responsiveness --- */
    @media (max-width: 768px) {
      .hero-section { grid-template-columns: 1fr; }
      .hero-img { height: 250px; }
      .container { grid-template-columns: 1fr; }
      .articles-grid { grid-template-columns: 1fr; }
      .nav-links { display: none; } /* Hidden on mobile for simplicity */
      .brand { font-size: 1.5rem; }
    }
  </style>
</head>
<body>

  <!-- Top Info Bar -->
  <div class="top-bar">
    <span id="current-date"></span>
    <span>New York, NY: 72°F</span>
    <span>Subscribe</span>
    <span>Login</span>
  </div>

  <!-- Header -->
  <header>
    <div class="header-container">
      <div class="brand">Sojourner<span>News</span></div>
      <div class="header-actions">
        <button>Subscribe</button>
      </div>
    </div>
  </header>

  <!-- Navigation -->
  <nav>
    <div class="nav-container">
      <div class="nav-links">
        <a href="#">Home</a>
        <a href="#">World</a>
        <a href="#">Politics</a>
        <a href="#">Business</a>
        <a href="#">Tech</a>
        <a href="#">Science</a>
        <a href="#">Health</a>
        <a href="#">Sports</a>
      </div>
    </div>
  </nav>

  <!-- Main Content -->
  <div class="container">
    
    <!-- Left Column (Main News) -->
    <main>
      <!-- Hero / Top Story -->
      <section class="hero-section">
        <img src="https://images.unsplash.com/photo-1504711434969-e33886168f5c?q=80&w=1000&auto=format&fit=crop" alt="Main News" class="hero-img">
        <div class="hero-content">
          <div class="category-tag">Technology</div>
          <h1>The Future of AI: How Machine Learning is Reshaping Industries</h1>
          <p>Artificial intelligence continues to revolutionize the way businesses operate, from healthcare to finance. Experts weigh in on what's next.</p>
          <a href="#" class="read-more">Read Full Story</a>
        </div>
      </section>

      <!-- Secondary Articles Grid -->
      <h2 style="margin-bottom: 1rem;">Latest Stories</h2>
      <div class="articles-grid">
        
        <!-- Article 1 -->
        <article class="news-card">
          <img src="https://images.unsplash.com/photo-1526304640152-d4619684e484?q=80&w=600&auto=format&fit=crop" alt="Business News">
          <div class="card-content">
            <span style="color: var(--accent); font-weight: bold; font-size: 0.75rem; text-transform: uppercase;">Business</span>
            <h3>Global Markets Rally Amid Economic Optimism</h3>
            <p>Stock markets around the world saw significant gains as investors respond to positive economic data.</p>
            <div class="meta">
              <span>2 hours ago</span>
              <span>5 min read</span>
            </div>
          </div>
        </article>

        <!-- Article 2 -->
        <article class="news-card">
          <img src="https://images.unsplash.com/photo-1461896836934-ffe607ba8211?q=80&w=600&auto=format&fit=crop" alt="Sports News">
          <div class="card-content">
            <span style="color: var(--accent); font-weight: bold; font-size: 0.75rem; text-transform: uppercase;">Sports</span>
            <h3>Championship Finals: A Historic Night for Athletics</h3>
            <p>Records were broken and history was made in what experts are calling the greatest finale in decades.</p>
            <div class="meta">
              <span>4 hours ago</span>
              <span>3 min read</span>
            </div>
          </div>
        </article>

        <!-- Article 3 -->
        <article class="news-card">
          <img src="https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?q=80&w=600&auto=format&fit=crop" alt="Health News">
          <div class="card-content">
            <span style="color: var(--accent); font-weight: bold; font-size: 0.75rem; text-transform: uppercase;">Health</span>
            <h3>New Study Reveals Breakthrough in Cancer Research</h3>
            <p>Scientists have identified a promising new treatment method that shows incredible results in early trials.</p>
            <div class="meta">
              <span>6 hours ago</span>
              <span>8 min read</span>
            </div>
          </div>
        </article>

        <!-- Article 4 -->
        <article class="news-card">
          <img src="https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=600&auto=format&fit=crop" alt="Tech News">
          <div class="card-content">
            <span style="color: var(--accent); font-weight: bold; font-size: 0.75rem; text-transform: uppercase;">Technology</span>
            <h3>Next Gen Smartphones: What to Expect in 2026</h3>
            <p>Leaked details suggest the next wave of flagship devices will focus on sustainable materials.</p>
            <div class="meta">
              <span>8 hours ago</span>
              <span>4 min read</span>
            </div>
          </div>
        </article>

      </div>
    </main>

    <!-- Right Sidebar -->
    <aside>
      <h3>Trending Now</h3>
      <ul class="sidebar-list">
        <li>
          <span style="color: var(--accent); font-weight: bold;">01</span>
          <h4>Climate Summit Reaches Historic Agreement</h4>
          <small>World leaders commit to new carbon targets</small>
        </li>
        <li>
          <span style="color: var(--accent); font-weight: bold;">02</span>
          <h4>Space Tourism Takes Off with First Commercial Flight</h4>
          <small>Private citizens reach the edge of space</small>
        </li>
        <li>
          <span style="color: var(--accent); font-weight: bold;">03</span>
          <h4>Crypto Markets See Unexpected Volatility</h4>
          <small>Investors cautious amid new regulations</small>
        </li>
        <li>
          <span style="color: var(--accent); font-weight: bold;">04</span>
          <h4>New Art Exhibit Draws Record Crowds</h4>
          <small>Modern museum welcomes largest attendance</small>
        </li>
        <li>
          <span style="color: var(--accent); font-weight: bold;">05</span>
          <h4>Electric Vehicles Outsell Gas Cars in Europe</h4>
          <small>A major milestone for green transportation</small>
        </li>
      </ul>

      <!-- Newsletter Box -->
      <div class="newsletter-box">
        <h4>The Daily Briefing</h4>
        <p style="font-size: 0.85rem; margin-bottom: 10px;">Get the most important stories delivered to your inbox every morning.</p>
        <form onsubmit="event.preventDefault(); alert('Thanks for subscribing!');">
          <input type="email" placeholder="Your email address" required>
          <button type="submit">Subscribe</button>
        </form>
