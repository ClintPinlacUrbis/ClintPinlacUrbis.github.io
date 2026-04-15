[index (1).html](https://github.com/user-attachments/files/26735388/index.1.html)
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
    .hero-info-cards { display: grid; grid-template-columns: 1fr 1fr; gap: 0.8rem; width: 100%; max-width: 360px; }
    .info-card { background: var(--grey-100); border: 1px solid var(--grey-200); border-radius: 10px; padding: 1rem; text-align: center; }
    .info-card .num { font-size: 1.5rem; font-weight: 700; color: var(--sky); font-family: 'Merriweather', serif; }
    .info-card .lbl { font-size: 0.72rem; color: var(--grey-400); text-transform: uppercase; letter-spacing: 0.08em; margin-top: 0.2rem; }

    /* SECTION */
    section { padding: 5rem 5%; max-width: 1400px; margin: 0 auto; }
    .section-wrap { padding: 5rem 5%; background: var(--grey-100); }
    .section-wrap > div { max-width: 1400px; margin: 0 auto; }
    .section-tag { font-size: 0.75rem; font-weight: 600; letter-spacing: 0.15em; text-transform: uppercase; color: var(--sky); margin-bottom: 0.6rem; }
    .section-title { font-family: 'Merriweather', serif; font-size: clamp(1.6rem, 3vw, 2.4rem); font-weight: 700; margin-bottom: 0.8rem; }
    .section-desc { font-size: 0.95rem; color: var(--grey-600); line-height: 1.8; max-width: 680px; margin-bottom: 3rem; }

    /* CREDENTIALS GRID */
    .cred-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.2rem; }
    .cred-card { background: white; border: 1.5px solid var(--grey-200); border-radius: 12px; padding: 1.6rem; transition: all 0.25s; }
    .cred-card:hover { border-color: var(--sky-mid); box-shadow: var(--shadow); transform: translateY(-3px); }
    .cred-icon { font-size: 1.8rem; margin-bottom: 0.8rem; }
    .cred-card h3 { font-size: 0.95rem; font-weight: 600; margin-bottom: 0.4rem; color: var(--grey-800); }
    .cred-card p { font-size: 0.83rem; color: var(--grey-600); line-height: 1.65; }
    .cred-pill { display: inline-block; margin-top: 0.9rem; padding: 0.25rem 0.75rem; background: var(--sky-light); color: var(--sky-dark); border-radius: 999px; font-size: 0.7rem; font-weight: 600; letter-spacing: 0.05em; }

    /* SKILLS */
    .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1.5rem; }
    .skill-group { background: white; border: 1.5px solid var(--grey-200); border-radius: 12px; padding: 1.6rem; }
    .skill-group h3 { font-size: 0.95rem; font-weight: 600; margin-bottom: 1rem; padding-bottom: 0.8rem; border-bottom: 2px solid var(--sky-light); color: var(--sky-dark); display: flex; align-items: center; gap: 0.5rem; }
    .skill-list { list-style: none; display: flex; flex-direction: column; gap: 0.55rem; }
    .skill-list li { font-size: 0.87rem; color: var(--grey-600); display: flex; align-items: center; gap: 0.6rem; }
    .skill-list li::before { content: ''; display: block; width: 6px; height: 6px; border-radius: 50%; background: var(--sky); flex-shrink: 0; }

    /* EXPERIENCE */
    .exp-card { background: white; border: 1.5px solid var(--grey-200); border-radius: 12px; padding: 2rem; margin-bottom: 1.2rem; }
    .exp-card h3 { font-size: 1rem; font-weight: 600; color: var(--grey-800); }
    .exp-card .org { font-size: 0.88rem; color: var(--sky); font-weight: 500; margin-top: 0.2rem; }
    .exp-card .date { font-size: 0.8rem; color: var(--grey-400); margin-top: 0.2rem; }
    .exp-card p { font-size: 0.87rem; color: var(--grey-600); line-height: 1.75; margin-top: 0.8rem; }

    /* CERTIFICATES */
    .cert-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 1.2rem; }
    .cert-item { background: white; border: 1.5px solid var(--grey-200); border-radius: 12px; overflow: hidden; transition: all 0.25s; cursor: pointer; }
    .cert-item:hover { border-color: var(--sky-mid); box-shadow: var(--shadow-lg); transform: translateY(-3px); }
    .cert-header { background: linear-gradient(135deg, var(--sky-light), var(--sky-mid)); padding: 1.2rem 1.4rem; }
    .cert-header .org { font-size: 0.7rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--sky-dark); }
    .cert-header h4 { font-size: 0.95rem; font-weight: 600; color: var(--grey-800); margin-top: 0.3rem; line-height: 1.4; }
    .cert-body { padding: 1rem 1.4rem; display: flex; justify-content: space-between; align-items: center; }
    .cert-body .date { font-size: 0.78rem; color: var(--grey-400); }
    .cert-body .type-pill { font-size: 0.7rem; font-weight: 600; padding: 0.2rem 0.6rem; background: var(--sky-light); color: var(--sky-dark); border-radius: 999px; }

    /* RESUME */
    .resume-box {
      background: linear-gradient(135deg, var(--sky), var(--sky-dark));
      border-radius: 16px; padding: 3rem; display: flex;
      align-items: center; justify-content: space-between; gap: 2rem; flex-wrap: wrap;
    }
    .resume-box h3 { font-family: 'Merriweather', serif; font-size: 1.5rem; font-weight: 700; color: white; margin-bottom: 0.5rem; }
    .resume-box p { font-size: 0.9rem; color: rgba(255,255,255,0.8); max-width: 480px; line-height: 1.7; }
    .btn-white { background: white; color: var(--sky-dark); padding: 0.85rem 2rem; border-radius: 8px; font-weight: 700; font-size: 0.88rem; text-decoration: none; white-space: nowrap; transition: all 0.2s; }
    .btn-white:hover { box-shadow: 0 4px 20px rgba(0,0,0,0.2); transform: translateY(-2px); }

    /* CONTACT */
    .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 1rem; }
    .contact-card { background: white; border: 1.5px solid var(--grey-200); border-radius: 12px; padding: 1.5rem; display: flex; align-items: center; gap: 1rem; text-decoration: none; color: var(--grey-800); transition: all 0.2s; }
    .contact-card:hover { border-color: var(--sky-mid); box-shadow: var(--shadow); transform: translateY(-2px); color: var(--sky-dark); }
    .contact-icon { width: 44px; height: 44px; background: var(--sky-light); border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 1.2rem; flex-shrink: 0; }
    .contact-card strong { display: block; font-size: 0.85rem; font-weight: 600; }
    .contact-card span { font-size: 0.78rem; color: var(--grey-400); margin-top: 0.1rem; display: block; }

    /* ABOUT DARK */
    .about-section { background: var(--grey-800); padding: 5rem 5%; }
    .about-inner { max-width: 1400px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; }
    .about-section .section-tag { color: var(--sky-mid); }
    .about-section .section-title { color: white; }
    .about-text p { font-size: 0.95rem; line-height: 1.85; color: rgba(255,255,255,0.7); margin-bottom: 1rem; }
    .about-text strong { color: var(--sky-mid); font-weight: 500; }
    .stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .stat-box { background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1); border-radius: 12px; padding: 1.5rem; text-align: center; }
    .stat-num { font-family: 'Merriweather', serif; font-size: 1.8rem; font-weight: 700; color: var(--sky-mid); display: block; }
    .stat-lbl { font-size: 0.72rem; color: rgba(255,255,255,0.4); text-transform: uppercase; letter-spacing: 0.08em; margin-top: 0.3rem; display: block; }

    /* FOOTER */
    footer { background: var(--grey-800); border-top: 1px solid rgba(255,255,255,0.06); text-align: center; padding: 1.5rem; font-size: 0.78rem; color: rgba(255,255,255,0.3); }

    /* ANIMATIONS */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(28px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      .hero { grid-template-columns: 1fr; padding-top: 80px; gap: 2rem; }
      .hero-right { order: -1; }
      .about-inner { grid-template-columns: 1fr; }
      .nav-links { display: none; }
    }
    @media (max-width: 600px) {
      .hero-name { font-size: 2rem; }
      .photo-wrap { width: 220px; height: 220px; }
      .resume-box { flex-direction: column; text-align: center; }
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
      <p class="hero-desc">A dedicated and passionate Licensed Professional Teacher with a Bachelor of Secondary Education degree, major in English. Civil Service Professional Level passer, TEFL certified, and holder of multiple professional credentials — committed to inspiring learners through language, literature, and creative expression.</p>
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
        <img src="data:image/jpeg;base64,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" alt="Clint Pinlac Urbis"/>
      </div>
      <div class="hero-info-cards">
        <div class="info-card"><div class="num">10+</div><div class="lbl">Certifications</div></div>
        <div class="info-card"><div class="num">LPT</div><div class="lbl">Board Passer 2024</div></div>
        <div class="info-card"><div class="num">83.6%</div><div class="lbl">LET Rating</div></div>
        <div class="info-card"><div class="num">TEFL</div><div class="lbl">With Distinction</div></div>
      </div>
    </div>
  </div>
</div>

<!-- CREDENTIALS -->
<div class="section-wrap" id="credentials">
  <div>
    <p class="section-tag">Professional Credentials</p>
    <h2 class="section-title">Licenses & Achievements</h2>
    <p class="section-desc">A comprehensive set of professional credentials earned through dedication, hard work, and a passion for lifelong learning.</p>
    <div class="cred-grid">
      <div class="cred-card">
        <div class="cred-icon">🎓</div>
        <h3>Bachelor of Secondary Education</h3>
        <p>Major in English — PHINMA University of Pangasinan, Arellano St., Dagupan City. Foundational degree in English language pedagogy, literature, and communication.</p>
        <span class="cred-pill">Academic Degree</span>
      </div>
      <div class="cred-card">
        <div class="cred-icon">📋</div>
        <h3>Licensed Professional Teacher</h3>
        <p>Board Passer of the September 2024 Licensure Examination for Professional Teachers (Secondary Level). General Average: 83.60% — PASSED.</p>
        <span class="cred-pill">PRC License</span>
      </div>
      <div class="cred-card">
        <div class="cred-icon">🏛️</div>
        <h3>Civil Service — Professional Level</h3>
        <p>Passed the Career Service Professional Examination with a rating of 80.15 on March 26, 2023, in Lingayen, Pangasinan. Issued by the Civil Service Commission.</p>
        <span class="cred-pill">CSC Eligibility</span>
      </div>
      <div class="cred-card">
        <div class="cred-icon">🌍</div>
        <h3>TEFL Certificate — With Distinction</h3>
        <p>120-Hour Teaching English as a Foreign Language Course completed with Distinction, issued by TEFL Professional Institute – Teacher Record (March 2025).</p>
        <span class="cred-pill">International Cert</span>
      </div>
      <div class="cred-card">
        <div class="cred-icon">⚡</div>
        <h3>NC II — Electrical Installation & Maintenance</h3>
        <p>National Certificate II issued by TESDA (September 2023). Valid until September 2028. Demonstrates technical vocational competency in electrical systems.</p>
        <span class="cred-pill">TESDA NC II</span>
      </div>
      <div class="cred-card">
        <div class="cred-icon">🏅</div>
        <h3>Diploma in English — C1 Level</h3>
        <p>Completed Diploma in English C1 Level on Alison (December 2025) with a Final Assessment Score of 88%. Total CPD Hours: 12–14 hours.</p>
        <span class="cred-pill">C1 Advanced</span>
      </div>
    </div>
  </div>
</div>

<!-- SKILLS -->
<section id="skills">
  <p class="section-tag">Expertise & Abilities</p>
  <h2 class="section-title">Skills & Specializations</h2>
  <p class="section-desc">A diverse blend of language, creativity, and technical expertise developed through formal education, certifications, and personal passion.</p>
  <div class="skills-grid">
    <div class="skill-group">
      <h3>✍️ Language & Writing</h3>
      <ul class="skill-list">
        <li>Academic & Creative Writing</li>
        <li>Content Creation & Copywriting</li>
        <li>Script Writing & Storytelling</li>
        <li>Literary Critique & Analysis</li>
        <li>Film & Movie Critique</li>
        <li>English Grammar (B1–C1 Level)</li>
        <li>English for Business & Tourism</li>
      </ul>
    </div>
    <div class="skill-group">
      <h3>🎭 Arts & Performance</h3>
      <ul class="skill-list">
        <li>Theater Arts</li>
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
        <li>Social-Emotional Learning (SEL)</li>
        <li>Multimedia-based Instruction</li>
        <li>Senior Tutoring — PHINMA Univ.</li>
      </ul>
    </div>
    <div class="skill-group">
      <h3>💼 Professional Skills</h3>
      <ul class="skill-list">
        <li>Report Writing & Presenting</li>
        <li>Critical Thinking</li>
        <li>Microsoft Office (Excel, PowerPoint)</li>
        <li>Time Management</li>
        <li>Adaptability & Self-Motivation</li>
        <li>Organisational Skills</li>
      </ul>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<div class="section-wrap">
  <div>
    <p class="section-tag">Experience</p>
    <h2 class="section-title">Work & Teaching Experience</h2>
    <p class="section-desc">Hands-on experience in education and academic support that shaped a strong foundation in English instruction.</p>
    <div class="exp-card">
      <h3>Teaching Intern — English, Grade 8</h3>
      <div class="org">Dagupan City National High School</div>
      <div class="date">January 2024 – April 2024</div>
      <p>Developed and implemented instructional materials for five sections of Grade 8 students. Prepared comprehensive lesson plans and designed diverse teaching resources. Created and presented PowerPoint presentations aligned with learning objectives. Applied instructional theories and strategies to facilitate effective student learning. Actively collaborated in the weekly Reading Comprehension program, providing support to learners developing their foundational reading skills.</p>
    </div>
    <div class="exp-card">
      <h3>Senior Tutor</h3>
      <div class="org">PHINMA University of Pangasinan</div>
      <div class="date">2023</div>
      <p>Provided academic tutoring and support to fellow university students, reinforcing subject knowledge and study skills as a Senior Tutor program participant.</p>
    </div>
  </div>
</div>

<!-- CERTIFICATES -->
<section id="certificates">
  <p class="section-tag">Training & Development</p>
  <h2 class="section-title">Certificates & Trainings</h2>
  <p class="section-desc">A growing collection of professional development certificates that reflect a commitment to continuous learning across diverse fields.</p>
  <div class="cert-grid">
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">PRC — Professional Regulation Commission</div>
        <h4>Licensure Examination for Teachers — Secondary (LET)</h4>
      </div>
      <div class="cert-body"><span class="date">September 2024 · 83.60% Average</span><span class="type-pill">PASSED</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">Civil Service Commission Philippines</div>
        <h4>Career Service Professional Examination — Certification of Eligibility</h4>
      </div>
      <div class="cert-body"><span class="date">March 26, 2023 · Rating: 80.15</span><span class="type-pill">Eligible</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">TEFL Professional Institute — Teacher Record</div>
        <h4>Teaching English as a Foreign Language (TEFL) — 120 Hours</h4>
      </div>
      <div class="cert-body"><span class="date">March 2025 · Cert No. TR7507044214</span><span class="type-pill">Distinction</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">TESDA — Technical Education & Skills Development Authority</div>
        <h4>National Certificate II — Electrical Installation and Maintenance</h4>
      </div>
      <div class="cert-body"><span class="date">September 17, 2023 · Valid until Sept 2028</span><span class="type-pill">NC II</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">Alison Online Education</div>
        <h4>Diploma in English — C1 Level (Equivalent to IELTS 7.5)</h4>
      </div>
      <div class="cert-body"><span class="date">December 12, 2025 · Score: 88%</span><span class="type-pill">C1 Level</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">Knowledge Channel Foundation</div>
        <h4>Empowering Schools through Multimedia: Using Knowledge Channel Video Lessons</h4>
      </div>
      <div class="cert-body"><span class="date">December 6, 2025 · 2.0 CPD Units</span><span class="type-pill">CPD</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">Udemy</div>
        <h4>Past Perfect Perfectly Easy: B1-Level English Grammar (ESL)</h4>
      </div>
      <div class="cert-body"><span class="date">November 17, 2025 · 2.5 Hours</span><span class="type-pill">Completion</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">TESDA Online Program</div>
        <h4>English for Business and Entrepreneurship</h4>
      </div>
      <div class="cert-body"><span class="date">December 17, 2025</span><span class="type-pill">Completion</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">TESDA Online Program</div>
        <h4>English for Tourism Professionals</h4>
      </div>
      <div class="cert-body"><span class="date">January 3, 2026</span><span class="type-pill">Completion</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">TESDA Online Program</div>
        <h4>English for Science, Technology, Engineering and Mathematics (eSTEM)</h4>
      </div>
      <div class="cert-body"><span class="date">December 22, 2025</span><span class="type-pill">Completion</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">TESDA Online Program</div>
        <h4>English as a Medium of Instruction</h4>
      </div>
      <div class="cert-body"><span class="date">December 18, 2025</span><span class="type-pill">Completion</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">DepEd NEAP & Gokongwei Brothers Foundation</div>
        <h4>ARAL Series: Master Class on Social-Emotional Learning (SEL) for Remediation</h4>
      </div>
      <div class="cert-body"><span class="date">Feb 14, 21 & 28, 2026 · 5 CPD Units</span><span class="type-pill">CPD</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">Quezon City Public Library & Pinay German Tutor</div>
        <h4>Free Online Basic German Language Class</h4>
      </div>
      <div class="cert-body"><span class="date">January 26, 2026</span><span class="type-pill">Attendance</span></div>
    </div>
    <div class="cert-item">
      <div class="cert-header">
        <div class="org">Quezon City Public Library & Jellyfish Education</div>
        <h4>Free Basic Japanese Language Class</h4>
      </div>
      <div class="cert-body"><span class="date">March 26, 2026</span><span class="type-pill">Participation</span></div>
    </div>
  </div>
</section>

<!-- RESUME -->
<div style="padding: 0 5% 5rem; max-width:1400px; margin:0 auto;">
  <div class="resume-box">
    <div>
      <h3>Download My Resume</h3>
      <p>Get a complete overview of my qualifications, experience, credentials, and achievements in a professionally formatted document.</p>
    </div>
    <a href="RESUMENEW.pdf" download class="btn-white">⬇ Download CV (PDF)</a>
  </div>
</div>

<!-- ABOUT -->
<div class="about-section" id="about">
  <div class="about-inner">
    <div class="about-text">
      <p class="section-tag">About Me</p>
      <h2 class="section-title" style="color:white; margin-bottom:1.5rem;">Educator. Writer. Storyteller.</h2>
      <p>I am <strong>Clint Pinlac Urbis</strong>, a Licensed Professional Teacher and a Bachelor of Secondary Education graduate, major in English, from PHINMA University of Pangasinan. I am based in Dagupan City, Pangasinan, Philippines.</p>
      <p>Beyond my teaching credentials, I am a creator at heart. I have a background in <strong>theater arts</strong>, script writing, and storytelling — believing that education and storytelling are two sides of the same coin, both seeking to illuminate truth and inspire others.</p>
      <p>Equipped with a <strong>TEFL certificate (with Distinction)</strong>, Civil Service Professional Level eligibility, and a TESDA NC II, I bring a versatile and well-rounded professional profile committed to lifelong learning and impactful teaching.</p>
    </div>
    <div class="stat-grid">
      <div class="stat-box"><span class="stat-num">83.6%</span><span class="stat-lbl">LET Board Rating</span></div>
      <div class="stat-box"><span class="stat-num">80.15</span><span class="stat-lbl">Civil Service Rating</span></div>
      <div class="stat-box"><span class="stat-num">88%</span><span class="stat-lbl">C1 English Score</span></div>
      <div class="stat-box"><span class="stat-num">14+</span><span class="stat-lbl">Certifications Earned</span></div>
    </div>
  </div>
</div>

<!-- CONTACT -->
<section id="contact">
  <p class="section-tag">Get In Touch</p>
  <h2 class="section-title">Contact Me</h2>
  <p class="section-desc">Whether you're looking for an English educator, content writer, or a creative collaborator, I'd love to hear from you.</p>
  <div class="contact-grid">
    <a href="tel:+639271460731" class="contact-card">
      <div class="contact-icon">📞</div>
      <div><strong>Phone / Mobile</strong><span>+63 927 146 0731</span></div>
    </a>
    <a href="mailto:clinturbis725@yahoo.com" class="contact-card">
      <div class="contact-icon">✉️</div>
      <div><strong>Email Address</strong><span>clinturbis725@yahoo.com</span></div>
    </a>
    <a href="https://github.com/yourusername" class="contact-card" target="_blank">
      <div class="contact-icon">💻</div>
      <div><strong>GitHub Portfolio</strong><span>github.com/yourusername</span></div>
    </a>
    <div class="contact-card">
      <div class="contact-icon">📍</div>
      <div><strong>Location</strong><span>220 Carael West, Dagupan City, Pangasinan</span></div>
    </div>
  </div>
</section>

<footer>
  © 2026 Clint Pinlac Urbis · Licensed Professional Teacher · BSEd English · Dagupan City, Pangasinan
</footer>

</body>
</html>
