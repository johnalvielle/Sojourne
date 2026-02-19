<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sojourne News | Global Perspective</title>

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,400&display=swap" rel="stylesheet" />

  <style>
    /* ===== Brand Palette (from logo) =====
       Deep Navy   #252958
       Orange      #E2841C
       White       #FDFDFD
       Gray-Blue   #9396AC (supporting)
    ====================================== */
    :root {
      --primary: #252958;     /* Deep Navy */
      --accent:  #E2841C;     /* Orange */
      --white:   #FDFDFD;     /* Brand white */
      --light-bg:#F6F7FA;     /* Soft light based on gray-blue tint */
      --text-dark:#1A1A1A;    /* Body copy for readability */
      --text-grey:#666A75;    /* Muted text aligned with gray-blue family */
      --border:  #E2E5EF;     /* Light border derived from gray-blue */
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
    }
    .top-bar span { margin: 0 10px; cursor: pointer; }
    .top-bar span:hover { color: var(--accent); }

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
    }

    .nav-links { display: flex; gap: 2rem; }

    .nav-links a {
      display: block;
      padding: 1rem 0;
      font-weight: 600;
      font-size: 0.95rem;
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

    /* --- Breaking News Banner --- */
    .breaking-news {
      background: var(--primary);
      color: var(--white);
      padding: 0.8rem;
      text-align: center;
      font-weight: 600;
    }
    .breaking-news span {
      background: var(--accent);
      padding: 0.2rem 0.6rem;
      margin-right: 10px;
      border-radius: 3px;
      font-size: 0.8rem;
      color: var(--white);
    }

    /* --- Hero Section --- */
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
      transition: background 0.3s;
    }
    .read-more:hover { background: var(--accent); }

    /* --- Articles Grid --- */
    .section-title {
      font-size: 1.5rem;
      border-left: 4px solid var(--accent);
      padding-left: 1rem;
      margin-bottom: 1.5rem;
    }

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
      cursor: pointer;
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
      color: #9aa0b3; /* subtle grey-blue */
      display: flex;
      justify-content: space-between;
    }

    .category-label {
      color: var(--accent);
      font-weight: 700;
      text-transform: uppercase;
      font-size: 0.75rem;
      margin-bottom: 0.5rem;
      display: block;
    }

    /* --- Sidebar --- */
    aside {
      background: var(--light-bg);
      padding: 1.5rem;
      border-radius: 8px;
      height: fit-content;
      position: sticky;
      top: 100px;
    }

    aside h3 {
      border-bottom: 2px solid var(--accent);
      padding-bottom: 0.5rem;
      margin-bottom: 1.5rem;
      font-size: 1.2rem;
    }

    .sidebar-list li {
      margin-bottom: 1rem;
      border-bottom: 1px solid #dde2ef;
      padding-bottom: 1rem;
      cursor: pointer;
      transition: opacity 0.3s;
    }

    .sidebar-list li:hover { opacity: 0.7; }
    .sidebar-list li:last-child { border-bottom: none; }

    .sidebar-list .rank {
      color: var(--accent);
      font-weight: 900;
      font-size: 1.2rem;
      margin-right: 8px;
    }

    .sidebar-list h4 {
      font-size: 1rem;
      font-family: 'Inter', sans-serif;
      font-weight: 600;
      margin-bottom: 0.3rem;
      display: inline;
    }

    .sidebar-list small {
      display: block;
      color: var(--text-grey);
      font-size: 0.8rem;
      margin-top: 0.3rem;
    }

    /* --- Newsletter --- */
    .newsletter-box {
      background: var(--primary);
      color: var(--white);
      padding: 1.5rem;
      border-radius: 8px;
      margin-top: 2rem;
      text-align: center;
    }
    .newsletter-box h4 { color: var(--white); margin-bottom: 0.5rem; }
    .newsletter-box p { font-size: 0.85rem; margin-bottom: 10px; }
    .news
