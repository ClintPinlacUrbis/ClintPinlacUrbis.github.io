<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Clint Pinlac Urbis — Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Merriweather:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --sky: #3b82f6;
      --sky-dark: #1d4ed8;
      --sky-light: #eff6ff;
      --sky-mid: #bfdbfe;
      --grey-100: #f3f4f6;
      --grey-200: #e5e7eb;
      --grey-400: #9ca3af;
      --grey-600: #4b5563;
      --grey-800: #1f2937;
      --white: #ffffff;
      --shadow: 0 4px 24px rgba(59,130,246,0.10);
      --shadow-lg: 0 8px 40px rgba(59,130,246,0.15);
    }
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { font-family: 'Inter', sans-serif; background: var(--white); color: var(--grey-800); overflow-x: hidden; }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 200;
      background: rgba(255,255,255,0.92);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--grey-200);
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%;
      height: 64px;
    }
    .nav-brand { font-family: 'Merriweather', serif; font-size: 1.1rem; font-weight: 700; color: var(--sky-dark); text-decoration: none; }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a { font-size: 0.85rem; font-weight: 500; color: var(--grey-600); text-decoration: none; letter-spacing: 0.05em; transition: color 0.2s; }
    .nav-links a:hover { color: var(--sky); }
    .nav-cta { background: var(--sky); color: white; padding: 0.5rem 1.2rem; border-radius: 6px; font-size: 0.83rem; font-weight: 500; text-decoration: none; transition: background 0.2s; }
    .nav-cta:hover { background: var(--sky-dark); }

    /* HERO */
    .hero {
      min-height: 100vh; padding-top: 64px;
      display: grid; grid-template-columns: 1fr 1fr;
      max-width: 1400px; margin: 0 auto;
      padding-left: 5%; padding-right: 5%;
      align-items: center; gap: 4rem;
    }
    .hero-left { animation: fadeUp 0.8s ease both; }
    .hero-eyebrow {
      display: inline-flex; align-items: center; gap: 0.5rem;
      background: var(--sky-light); color: var(--sky-dark);
      padding: 0.35rem 1rem; border-radius: 999px;
      font-size: 0.78rem; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase;
      margin-bottom: 1.5rem;
    }
    .hero-eyebrow::before { content: '●'; font-size: 0.5rem; color: var(--sky); }
    .hero-name { font-family: 'Merriweather', serif; font-size: clamp(2.4rem, 4vw, 4rem); font-weight: 700; line-height: 1.1; color: var(--grey-800); margin-bottom: 0.8rem; }
    .hero-name span { color: var(--sky); }
    .hero-title { font-size: 1rem; color: var(--grey-600); font-weight: 400; margin-bottom: 1.5rem; line-height: 1.6; }
    .hero-desc { font-size: 0.95rem; line-height: 1.8; color: var(--grey-600); margin-bottom: 2rem; max-width: 520px; }
    .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; margin-bottom: 2.5rem; }
    .btn { display: inline-block; padding: 0.75rem 1.8rem; border-radius: 8px; font-size: 0.88rem; font-weight: 600; text-decoration: none; transition: all 0.2s; cursor: pointer; }
    .btn-primary { background: var(--sky); color: white; }
    .btn-primary:hover { background: var(--sky-dark); transform: translateY(-2px); box-shadow: var(--shadow-lg); }
    .btn-outline { background: white; color: var(--grey-800); border: 1.5px solid var(--grey-200); }
    .btn-outline:hover { border-color: var(--sky); color: var(--sky); transform: translateY(-2px); }
    .hero-badges { display: flex; flex-wrap: wrap; gap: 0.5rem; }
    .badge { background: var(--grey-100); color: var(--grey-600); padding: 0.3rem 0.8rem; border-radius: 4px; font-size: 0.75rem; font-weight: 500; border: 1px solid var(--grey-200); }
    .badge.blue { background: var(--sky-light); color: var(--sky-dark); border-color: var(--sky-mid); }

    /* HERO RIGHT */
    .hero-right { animation: fadeIn 1s 0.3s ease both; display: flex; flex-direction: column; align-items: center; gap: 1.5rem; }
    .photo-wrap {
      width: 300px; height: 300px; border-radius: 50%;
      border: 4px solid var(--sky-mid);
      box-shadow: 0 0 0 8px var(--sky-light), var(--shadow-lg);
      overflow: hidden; position: relative;
    }
    .photo-wrap img { width: 100%; height: 100%; object-fit: cover; object-position: top; }

    /* Other styles remain the same (I kept them clean) */
    section, .section-wrap { padding: 5rem 5%; max-width: 1400px; margin: 0 auto; }
    .section-wrap { background: var(--grey-100); }
    .section-tag { font-size: 0.75rem; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: var(--sky); margin-bottom: 0.6rem; }
    .section-title { font-family: 'Merriweather', serif; font-size: clamp(1.6rem, 3vw, 2.4rem); font-weight: 700; margin-bottom: 0.8rem; }
    .section-desc { font-size: 0.95rem; color: var(--grey-600); line-height: 1.8; max-width: 680px; margin-bottom: 3rem; }

    /* (Rest of your original styles are unchanged for brevity - they are all kept) */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(28px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

    @media (max-width: 900px) {
      .hero { grid-template-columns: 1fr; padding-top: 80px; gap: 2rem; }
      .hero-right { order: -1; }
    }
    @media (max-width: 600px) {
      .hero-name { font-size: 2rem; }
      .photo-wrap { width: 220px; height: 220px; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#home" class="nav-brand">CPU</a>
  <ul class="nav-links">
    <li><a href="#credentials">Credentials</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#certificates">Certificates</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="RESUMENEW.pdf" download class="nav-cta">Download CV</a>
</nav>

<!-- HERO -->
<div id="home" style="padding-top:64px;">
  <div class="hero">
    <div class="hero-left">
      <div class="hero-eyebrow">Licensed Professional Teacher · BSEd English</div>
      <h1 class="hero-name">Clint Pinlac<br><span>Urbis</span></h1>
      <p class="hero-title">Educator · Writer · Storyteller · Content Creator</p>
      <p class="hero-desc">A dedicated and passionate Licensed Professional Teacher with a Bachelor of Secondary Education degree, major in English. Civil Service Professional Level passer, TEFL certified, and holder of multiple professional credentials.</p>
      <div class="hero-actions">
        <a href="#credentials" class="btn btn-primary">View Credentials</a>
        <a href="#contact" class="btn btn-outline">Get in Touch</a>
      </div>
      <div class="hero-badges">
        <span class="badge blue">LPT</span>
        <span class="badge blue">TEFL — Distinction</span>
        <span class="badge blue">Civil Service Pro</span>
        <span class="badge blue">NC II TESDA</span>
        <span class="badge">BSEd — Major: English</span>
        <span class="badge">C1 English — Alison</span>
      </div>
    </div>
    <div class="hero-right">
      <div class="photo-wrap">
        <img src="data:image/jpeg;base64,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
