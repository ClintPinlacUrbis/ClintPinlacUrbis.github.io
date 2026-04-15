<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Clint Pinlac Urbis — Educator & Writer</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --ink: #1a1208;
      --cream: #f5f0e8;
      --gold: #b8860b;
      --gold-light: #d4a017;
      --rust: #8b3a1f;
      --sage: #4a5e4a;
      --paper: #ede8dc;
      --muted: #7a6e5f;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background-color: var(--cream);
      color: var(--ink);
      overflow-x: hidden;
    }

    /* NOISE TEXTURE OVERLAY */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 1000;
      opacity: 0.4;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.2rem 4rem;
      background: rgba(245, 240, 232, 0.85);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(184, 134, 11, 0.2);
      z-index: 100;
    }

    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
      font-weight: 700;
      letter-spacing: 0.05em;
      color: var(--ink);
      text-decoration: none;
    }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.82rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      text-decoration: none;
      color: var(--muted);
      transition: color 0.3s;
    }

    .nav-links a:hover { color: var(--gold); }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      padding-top: 80px;
    }

    .hero-left {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 6rem 4rem 6rem 6rem;
      position: relative;
    }

    .hero-left::after {
      content: '';
      position: absolute;
      right: 0; top: 15%; bottom: 15%;
      width: 1px;
      background: linear-gradient(to bottom, transparent, var(--gold), transparent);
    }

    .hero-eyebrow {
      font-size: 0.75rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.5rem;
      animation: fadeUp 0.8s ease both;
    }

    .hero-name {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 5vw, 4.8rem);
      font-weight: 700;
      line-height: 1.05;
      margin-bottom: 0.5rem;
      animation: fadeUp 0.8s 0.1s ease both;
    }

    .hero-name em {
      font-style: italic;
      color: var(--rust);
    }

    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
      font-style: italic;
      color: var(--muted);
      margin-bottom: 2rem;
      animation: fadeUp 0.8s 0.2s ease both;
    }

    .hero-desc {
      font-size: 0.97rem;
      line-height: 1.85;
      color: #4a3f30;
      max-width: 480px;
      margin-bottom: 2.5rem;
      animation: fadeUp 0.8s 0.3s ease both;
    }

    .hero-cta {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      animation: fadeUp 0.8s 0.4s ease both;
    }

    .btn {
      display: inline-block;
      padding: 0.8rem 2rem;
      font-size: 0.82rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      text-decoration: none;
      border-radius: 2px;
      transition: all 0.3s;
      cursor: pointer;
    }

    .btn-primary {
      background: var(--gold);
      color: white;
      border: 1px solid var(--gold);
    }

    .btn-primary:hover {
      background: var(--gold-light);
      border-color: var(--gold-light);
      transform: translateY(-2px);
    }

    .btn-outline {
      background: transparent;
      color: var(--ink);
      border: 1px solid var(--ink);
    }

    .btn-outline:hover {
      background: var(--ink);
      color: var(--cream);
      transform: translateY(-2px);
    }

    .hero-right {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 6rem 6rem 6rem 4rem;
      position: relative;
      animation: fadeIn 1s 0.5s ease both;
    }

    .hero-card {
      background: var(--paper);
      border: 1px solid rgba(184, 134, 11, 0.25);
      padding: 3rem;
      width: 100%;
      max-width: 380px;
      position: relative;
    }

    .hero-card::before {
      content: '"';
      font-family: 'Playfair Display', serif;
      font-size: 8rem;
      color: var(--gold);
      opacity: 0.15;
      position: absolute;
      top: -1.5rem;
      left: 1.5rem;
      line-height: 1;
    }

    .hero-card p {
      font-family: 'Playfair Display', serif;
      font-style: italic;
      font-size: 1.05rem;
      line-height: 1.7;
      color: var(--ink);
    }

    .hero-card-tag {
      margin-top: 1.5rem;
      font-size: 0.75rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--gold);
    }

    .hero-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-top: 2rem;
      width: 100%;
      max-width: 380px;
    }

    .badge {
      font-size: 0.72rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 0.4rem 0.9rem;
      border: 1px solid var(--gold);
      color: var(--gold);
      border-radius: 1px;
    }

    /* SECTION COMMON */
    section {
      padding: 6rem 6rem;
    }

    .section-label {
      font-size: 0.72rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.8rem;
    }

    .section-heading {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 3.5vw, 3rem);
      font-weight: 700;
      margin-bottom: 1rem;
      line-height: 1.15;
    }

    .section-sub {
      font-size: 0.97rem;
      color: var(--muted);
      max-width: 560px;
      line-height: 1.8;
      margin-bottom: 3.5rem;
    }

    /* CREDENTIALS */
    #credentials {
      background: var(--paper);
      border-top: 1px solid rgba(184,134,11,0.15);
      border-bottom: 1px solid rgba(184,134,11,0.15);
    }

    .cred-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 2rem;
    }

    .cred-card {
      background: var(--cream);
      border: 1px solid rgba(184,134,11,0.2);
      padding: 2rem;
      position: relative;
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .cred-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 12px 30px rgba(26,18,8,0.1);
    }

    .cred-icon {
      font-size: 1.8rem;
      margin-bottom: 1rem;
    }

    .cred-card h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    .cred-card p {
      font-size: 0.85rem;
      color: var(--muted);
      line-height: 1.65;
    }

    .cred-tag {
      display: inline-block;
      margin-top: 1rem;
      font-size: 0.68rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--rust);
      border-bottom: 1px solid var(--rust);
      padding-bottom: 1px;
    }

    /* SKILLS */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 3rem;
    }

    .skill-group h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.2rem;
      font-weight: 700;
      margin-bottom: 1.2rem;
      padding-bottom: 0.7rem;
      border-bottom: 1px solid rgba(184,134,11,0.3);
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .skill-list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    .skill-list li {
      font-size: 0.9rem;
      color: var(--ink);
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .skill-list li::before {
      content: '→';
      color: var(--gold);
      font-size: 0.85rem;
    }

    /* ABOUT */
    #about {
      background: var(--ink);
      color: var(--cream);
    }

    #about .section-label { color: var(--gold-light); }

    #about .section-sub { color: rgba(245,240,232,0.6); }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
    }

    .about-text p {
      font-size: 0.97rem;
      line-height: 1.9;
      color: rgba(245,240,232,0.8);
      margin-bottom: 1.2rem;
    }

    .about-text strong { color: var(--gold-light); font-weight: 500; }

    .about-stats {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
    }

    .stat-box {
      border: 1px solid rgba(184,134,11,0.3);
      padding: 1.8rem;
      text-align: center;
    }

    .stat-number {
      font-family: 'Playfair Display', serif;
      font-size: 2.5rem;
      font-weight: 700;
      color: var(--gold-light);
      display: block;
    }

    .stat-label {
      font-size: 0.78rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: rgba(245,240,232,0.5);
      margin-top: 0.4rem;
    }

    /* CONTACT */
    #contact {
      text-align: center;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      flex-wrap: wrap;
      margin-top: 2rem;
    }

    .contact-link {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      font-size: 0.85rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      text-decoration: none;
      color: var(--ink);
      padding: 0.9rem 1.8rem;
      border: 1px solid var(--ink);
      transition: all 0.3s;
    }

    .contact-link:hover {
      background: var(--gold);
      border-color: var(--gold);
      color: white;
    }

    /* DIVIDER */
    .ornament {
      text-align: center;
      color: var(--gold);
      font-size: 1.2rem;
      letter-spacing: 0.5rem;
      padding: 1rem 0;
      opacity: 0.5;
    }

    /* FOOTER */
    footer {
      background: var(--ink);
      color: rgba(245,240,232,0.4);
      text-align: center;
      padding: 2rem;
      font-size: 0.78rem;
      letter-spacing: 0.1em;
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      nav { padding: 1.2rem 2rem; }
      .nav-links { gap: 1.5rem; }

      .hero {
        grid-template-columns: 1fr;
      }
      .hero-left {
        padding: 6rem 2rem 2rem;
      }
      .hero-left::after { display: none; }
      .hero-right {
        padding: 2rem 2rem 4rem;
        align-items: flex-start;
      }
      section { padding: 4rem 2rem; }

      .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    }

    @media (max-width: 600px) {
      .nav-links { display: none; }
      .hero-name { font-size: 2.4rem; }
      .stat-box { padding: 1.2rem; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a href="#" class="nav-logo">CPU</a>
    <ul class="nav-links">
      <li><a href="#credentials">Credentials</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero" id="home">
    <div class="hero-left">
      <p class="hero-eyebrow">Portfolio & Professional Profile</p>
      <h1 class="hero-name">Clint Pinlac<br><em>Urbis</em></h1>
      <p class="hero-title">Licensed Professional Teacher · English Educator · Writer</p>
      <p class="hero-desc">
        A Bachelor of Secondary Education graduate, major in English, with a deep passion for language, literature, and the craft of storytelling. Driven by a commitment to lifelong learning and a versatile set of professional credentials.
      </p>
      <div class="hero-cta">
        <a href="#credentials" class="btn btn-primary">View Credentials</a>
        <a href="#contact" class="btn btn-outline">Get in Touch</a>
      </div>
    </div>

    <div class="hero-right">
      <div class="hero-card">
        <p>Language is not just a subject to be taught — it is a world to be explored, a bridge between minds, and the most powerful tool a human being can wield.</p>
        <p class="hero-card-tag">— Clint Pinlac Urbis</p>
      </div>
      <div class="hero-badges">
        <span class="badge">LPT</span>
        <span class="badge">TEFL Certified</span>
        <span class="badge">Civil Service Passer</span>
        <span class="badge">NC II</span>
        <span class="badge">BSEd English</span>
      </div>
    </div>
  </section>

  <!-- CREDENTIALS -->
  <section id="credentials">
    <p class="section-label">Professional Credentials</p>
    <h2 class="section-heading">Licenses & Certifications</h2>
    <p class="section-sub">A collection of professional achievements and certifications that reflect a commitment to excellence, versatility, and continuous growth.</p>

    <div class="cred-grid">

      <div class="cred-card">
        <div class="cred-icon">🎓</div>
        <h3>Bachelor of Secondary Education</h3>
        <p>Major in English. Foundational academic degree providing deep expertise in English language, literature, pedagogy, and communication.</p>
        <span class="cred-tag">Academic Degree</span>
      </div>

      <div class="cred-card">
        <div class="cred-icon">📋</div>
        <h3>Licensed Professional Teacher</h3>
        <p>Passed the Licensure Examination for Teachers (LET), the national board exam for all professional educators in the Philippines.</p>
        <span class="cred-tag">PRC License</span>
      </div>

      <div class="cred-card">
        <div class="cred-icon">🏛️</div>
        <h3>Civil Service — Professional Level</h3>
        <p>Passer of the Civil Service Commission (CSC) examination at the Professional level, qualifying for government service positions.</p>
        <span class="cred-tag">CSC Eligibility</span>
      </div>

      <div class="cred-card">
        <div class="cred-icon">🌍</div>
        <h3>TEFL Certificate</h3>
        <p>Teaching English as a Foreign Language (TEFL) certification, qualifying for English language instruction to non-native speakers globally.</p>
        <span class="cred-tag">International Certification</span>
      </div>

      <div class="cred-card">
        <div class="cred-icon">⚡</div>
        <h3>NC II — Electrical Installation & Maintenance</h3>
        <p>National Certificate II in Electrical Installation and Maintenance issued by TESDA, reflecting technical vocational competency.</p>
        <span class="cred-tag">TESDA Certification</span>
      </div>

      <div class="cred-card">
        <div class="cred-icon">📜</div>
        <h3>Other Professional Certificates</h3>
        <p>Holder of various additional professional development certificates, reflecting a dedication to broadening knowledge and expertise across multiple disciplines.</p>
        <span class="cred-tag">Continuous Learning</span>
      </div>

    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills" style="background: var(--paper); border-top: 1px solid rgba(184,134,11,0.15); border-bottom: 1px solid rgba(184,134,11,0.15);">
    <p class="section-label">Expertise & Abilities</p>
    <h2 class="section-heading">Skills & Specializations</h2>
    <p class="section-sub">A blend of language, creativity, and technical expertise — developed through formal education, certifications, and personal passion.</p>

    <div class="skills-grid">

      <div class="skill-group">
        <h3>✍️ Language & Writing</h3>
        <ul class="skill-list">
          <li>Academic & Creative Writing</li>
          <li>Content Creation & Copywriting</li>
          <li>Script Writing & Storytelling</li>
          <li>Literary Critique & Analysis</li>
          <li>Film & Movie Critique</li>
          <li>English Language Instruction</li>
        </ul>
      </div>

      <div class="skill-group">
        <h3>🎭 Arts & Performance</h3>
        <ul class="skill-list">
          <li>Theater Arts Experience</li>
          <li>Script & Story Writing</li>
          <li>Narrative Development</li>
          <li>Dramatic Interpretation</li>
          <li>Creative Direction</li>
        </ul>
      </div>

      <div class="skill-group">
        <h3>📚 Education & Teaching</h3>
        <ul class="skill-list">
          <li>Lesson Planning & Curriculum Design</li>
          <li>TEFL / ESL Instruction</li>
          <li>Secondary Education (English)</li>
          <li>Classroom Management</li>
          <li>Educational Content Development</li>
        </ul>
      </div>

    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="about-grid">
      <div class="about-text">
        <p class="section-label">About Me</p>
        <h2 class="section-heading" style="color: var(--cream);">Educator.<br>Writer.<br>Storyteller.</h2>
        <p>I am <strong>Clint Pinlac Urbis</strong>, a Licensed Professional Teacher with a Bachelor of Secondary Education degree, majoring in English. My journey has been shaped by a love for language — from reading classic literature to writing original scripts and stories for the stage.</p>
        <p>Beyond the classroom, I am a creator. I have explored <strong>theater arts</strong>, written scripts and stories, and developed a keen eye for film and literary critique. I believe that education and storytelling are two sides of the same coin — both seek to illuminate truth and inspire others.</p>
        <p>Equipped with a <strong>TEFL certificate</strong>, Civil Service eligibility, and NC II credentials, I bring a versatile and well-rounded professional profile ready to serve students, organizations, and communities.</p>
      </div>
      <div class="about-stats">
        <div class="stat-box">
          <span class="stat-number">5+</span>
          <span class="stat-label">Certifications Earned</span>
        </div>
        <div class="stat-box">
          <span class="stat-number">LPT</span>
          <span class="stat-label">Licensed Professional Teacher</span>
        </div>
        <div class="stat-box">
          <span class="stat-number">TEFL</span>
          <span class="stat-label">Internationally Certified</span>
        </div>
        <div class="stat-box">
          <span class="stat-number">BSEd</span>
          <span class="stat-label">Major in English</span>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <p class="section-label">Let's Connect</p>
    <h2 class="section-heading">Get in Touch</h2>
    <p class="section-sub" style="margin: 0 auto 2.5rem; text-align:center;">
      Whether you're looking for an English educator, content writer, or a creative collaborator — I'd love to hear from you.
    </p>

    <div class="contact-links">
      <a href="mailto:your@email.com" class="contact-link">✉️ Email Me</a>
      <a href="https://github.com/yourusername" class="contact-link" target="_blank">⌥ GitHub</a>
      <a href="https://linkedin.com/in/yourprofile" class="contact-link" target="_blank">in LinkedIn</a>
    </div>
  </section>

  <div class="ornament">✦ &nbsp; ✦ &nbsp; ✦</div>

  <!-- FOOTER -->
  <footer>
    <p>© 2026 Clint Pinlac Urbis &nbsp;·&nbsp; Licensed Professional Teacher &nbsp;·&nbsp; BSEd English</p>
  </footer>

</body>
</html>
