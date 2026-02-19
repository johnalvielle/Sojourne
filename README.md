<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sojourner News</title>

  <!-- Fonts (optional, professional look) -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Newsreader:opsz,wght@6..72,600;6..72,700&display=swap" rel="stylesheet">

  <style>
    :root{
      --ink:#060221;              /* Blue-Magenta (brand) */
      --brand:#F19808;            /* Gamboge (accent) */
      --bg:#f9f9fb;
      --panel:#ffffff;
      --muted:#6b7280;
      --muted-2:#9aa0ad;
      --shadow:0 6px 20px rgba(0,0,0,0.08);
      --radius:14px;
      --radius-sm:10px;
      --maxw:1200px;
    }

    @media (prefers-color-scheme: dark){
      :root{
        --bg:#0e0f14;
        --panel:#141622;
        --muted:#c9cedb;
        --muted-2:#97a0b6;
        --shadow:0 8px 30px rgba(0,0,0,0.45);
      }
    }

    *{box-sizing:border-box}
    html,body{margin:0;padding:0}
    body{
      font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      background:var(--bg);
      color:var(--ink);
      line-height:1.55;
    }
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block}

    /* Header / Top Bar */
    .topbar{
      background:var(--ink);
      color:#fff;
    }
    .wrap{
      max-width:var(--maxw);
      margin-inline:auto;
      padding-inline:20px;
    }
    .brand{
      display:flex;align-items:center;gap:12px;
    }
    .brand__logo{
      inline-size:40px;block-size:40px;border-radius:8px;
      background:linear-gradient(135deg,var(--brand),#ffcc6a);
      display:grid;place-items:center;color:#1b0b00;font-weight:800;
      box-shadow:var(--shadow);
      flex:0 0 40px;
    }
    .brand__name{
      margin:0;
      font-family: Newsreader, Georgia, 'Times New Roman', serif;
      font-size: clamp(1.6rem, 2.2vw, 2.2rem);
      letter-spacing:.3px;
    }
    .brand__tagline{
      margin:0;color:#ffcf88;font-style:italic;font-size:.95rem;
    }

    header{
      padding:18px 0 14px;
    }

    /* Nav */
    .nav{
      position:sticky;top:0;z-index:50;
      background:var(--brand);
      box-shadow:var(--shadow);
    }
    .nav__row{
      display:flex;align-items:center;justify-content:space-between;gap:12px;
      padding-block:10px;
    }
    .menu{
      display:flex;gap:18px;align-items:center;font-weight:700;
    }
    .menu a{
      color:#fff;position:relative;display:inline-block;padding:6px 4px;
    }
    .menu a::after{
      content:"";position:absolute;left:0;bottom:-3px;height:2px;width:0;background:#fff;
      transition:width .25s ease;
    }
    .menu a:hover::after,.menu a[aria-current="page"]::after{width:100%}
    .hamburger{
      display:none;border:none;background:transparent;color:#fff;font-size:1.4rem;cursor:pointer
    }

    /* Search */
    .search{
      display:flex;align-items:center;gap:8px;background:rgba(255,255,255,.2);
      padding:6px 10px;border-radius:999px;backdrop-filter:blur(6px)
    }
    .search input{
      border:none;outline:none;background:transparent;color:#fff;min-width:220px;
    }
    .search input::placeholder{color:#fff;opacity:.9}
    .search button{
      border:none;background:#fff;color:#7a4600;font-weight:700;padding:6px 12px;border-radius:999px;cursor:pointer
    }

    /* Hero */
    .hero{
      margin:18px auto 22px;max-width:var(--maxw);padding-inline:20px;
    }
    .hero-card{
      display:grid;grid-template-columns:2fr 1.3fr;gap:18px;
      background:var(--panel);border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow)
    }
    .hero-media{
      position:relative
    }
    .hero-media img{
      inline-size:100%;block-size:100%;object-fit:cover;aspect-ratio:16/9
    }
    .hero-overlay{
      position:absolute;inset:auto 0 0 0;padding:18px;background:linear-gradient(to top, rgba(0,0,0,.55), rgba(0,0,0,0));
      color:#fff
    }
    .pill{
      display:inline-block;background:rgba(0,0,0,.6);border:1px solid rgba(255,255,255,.35);
      color:#fff;padding:6px 10px;border-radius:999px;font-size:.8rem
    }
    .hero-title{
      margin:.6rem 0 .3rem;font-family: Newsreader, Georgia, serif;
      font-size:clamp(1.3rem,2.8vw,2rem);line-height:1.25
    }
    .hero-meta{font-size:.9rem;color:#e8eaf0}

    .hero-body{
      padding:20px 20px 16px;
      display:flex;flex-direction:column;gap:12px;justify-content:center
    }
    .hero-body p{color:var(--muted);margin:0}
    .cta{
      display:inline-flex;align-items:center;gap:8px;
      background:var(--ink);color:#fff;border-radius:10px;padding:10px 14px;
      width:max-content;box-shadow:var(--shadow)
    }
    .cta:hover{opacity:.9}

    /* Main Grid */
    main{
      max-width:var(--maxw);
      margin-inline:auto;
      padding:8px 20px 32px;
      display:grid;grid-template-columns:2.2fr 1fr;gap:20px;
    }

    /* Cards */
    .card{
