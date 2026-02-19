<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sojourner News</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f9f9f9;
      color: #060221; /* Blue Magenta */
    }

    header {
      background-color: #060221; /* Blue Magenta */
      color: white;
      padding: 1rem;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 2.5rem;
    }

    header p {
      margin: 0.3rem 0 0;
      font-style: italic;
      font-size: 1.2rem;
      color: #F19808; /* Gamboge accent for tagline */
    }

    nav {
      background-color: #F19808; /* Gamboge */
      display: flex;
      justify-content: center;
      padding: 0.5rem;
    }

    nav a {
      color: white;
      text-decoration: none;
      margin: 0 1rem;
      font-weight: bold;
    }

    nav a:hover {
      text-decoration: underline;
    }

    main {
      display: grid;
      grid-template-columns: 2fr 1fr;
      gap: 1rem;
      padding: 1rem;
    }

    article {
      background: white;
      padding: 1rem;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    article h2 {
      color: #060221;
    }

    aside {
      background: #fff;
      padding: 1rem;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    footer {
      background-color: #060221;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Sojourner News</h1>
    <p>news that follows people</p>
  </header>

  <nav>
    <a href="#">Home</a>
    <a href="#">World</a>
    <a href="#">Politics</a>
    <a href="#">Business</a>
    <a href="#">Lifestyle</a>
    <a href="#">Sports</a>
  </nav>

  <main>
    <section>
      <article>
        <h2>Top Story Headline</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
        This is where your main news article would go.</p>
      </article>

      <article>
        <h2>Secondary Story</h2>
        <p>Another important news item with a short description.</p>
      </article>
    </section>

    <aside>
      <h3>Latest Updates</h3>
      <ul>
        <li>Breaking news item #1</li>
        <li>Breaking news item #2</li>
        <li>Breaking news item #3</li>
      </ul>
    </aside>
  </main>

  <footer>
    <p>&copy; 2026 Sojourner News. All rights reserved.</p>
  </footer>
</body>
</html>
