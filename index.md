<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#fff9fc">
  <meta name="description" content="Minnette Johnson is a graduate student from Belize exploring software engineering, research, and thoughtful technical decisions.">
  <title>Minnette Johnson | Graduate Portfolio</title>
  <style>
    :root {
      --paper: #fffafd;
      --white: #ffffff;
      --lavender: #eee6f7;
      --lavender-deep: #d9c7eb;
      --pink: #f7e3eb;
      --pink-deep: #d99bb5;
      --plum: #4b3a52;
      --ink: #403744;
      --muted: #756b79;
      --line: #eadfe9;
      --accent: #87689c;
      --accent-dark: #654b78;
      --serif: Georgia, "Times New Roman", serif;
      --sans: "Segoe UI", Arial, Helvetica, sans-serif;
      --content: 1120px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 90px; }
    body {
      margin: 0;
      background: var(--paper);
      color: var(--ink);
      font-family: var(--sans);
      font-size: 16px;
      line-height: 1.75;
      -webkit-font-smoothing: antialiased;
    }
    img { display: block; max-width: 100%; }
    a { color: var(--accent-dark); text-decoration-thickness: 1px; text-underline-offset: 4px; }
    a:hover { color: #a45f82; }
    a:focus-visible { outline: 3px solid var(--pink-deep); outline-offset: 4px; }
    .container { width: min(var(--content), calc(100% - 48px)); margin-inline: auto; }
    .skip-link {
      position: absolute; left: 12px; top: -60px; z-index: 10;
      background: var(--white); padding: 10px 14px; border-radius: 10px;
    }
    .skip-link:focus { top: 12px; }

    /* Header */
    .site-header {
      position: sticky; top: 0; z-index: 5;
      background: rgba(255, 250, 253, 0.94);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(234, 223, 233, .85);
    }
    .nav {
      min-height: 82px; display: flex; align-items: center;
      justify-content: space-between; gap: 28px;
    }
    .brand { color: var(--plum); text-decoration: none; font-weight: 700; letter-spacing: -.02em; }
    .brand small { display: block; color: var(--muted); font-size: 11px; line-height: 1.2; font-weight: 500; letter-spacing: .08em; text-transform: uppercase; }
    .nav-links { display: flex; align-items: center; gap: clamp(16px, 3vw, 32px); }
    .nav-links a { color: var(--muted); text-decoration: none; font-size: 13px; font-weight: 600; }
    .nav-links a:hover { color: var(--accent-dark); }
    .nav-links .github-link { border: 1px solid var(--lavender-deep); border-radius: 999px; padding: 8px 14px; color: var(--accent-dark); }

    /* Intro */
    .hero { overflow: hidden; position: relative; padding: clamp(64px, 9vw, 112px) 0 clamp(70px, 9vw, 110px); }
    .hero-grid {
      display: grid; grid-template-columns: minmax(0, 1.15fr) minmax(270px, .85fr);
      align-items: center; gap: clamp(44px, 8vw, 100px);
    }
    .eyebrow {
      display: inline-flex; align-items: center; gap: 10px;
      margin-bottom: 20px; color: var(--accent-dark);
      font-size: 11px; font-weight: 700; letter-spacing: .16em; text-transform: uppercase;
    }
    .eyebrow::before { content: ""; width: 28px; height: 1px; background: var(--pink-deep); }
    h1, h2, h3, p { margin-top: 0; }
    h1 {
      max-width: 680px; margin-bottom: 23px; color: var(--plum);
      font-family: var(--serif); font-size: clamp(44px, 6.4vw, 76px);
      line-height: 1.06; letter-spacing: -.045em; font-weight: 500;
    }
    h1 em { color: var(--accent); font-weight: 500; }
    .hero-copy { max-width: 610px; color: var(--muted); font-size: clamp(16px, 1.6vw, 18px); }
    .hero-copy strong { color: var(--plum); font-weight: 650; }
    .hero-actions { display: flex; align-items: center; flex-wrap: wrap; gap: 22px; margin-top: 30px; }
    .primary-link {
      display: inline-block; padding: 12px 20px; border-radius: 999px;
      background: var(--plum); color: white; font-size: 13px; font-weight: 650;
      text-decoration: none; transition: transform .18s ease, background .18s ease;
    }
    .primary-link:hover { color: white; background: var(--accent-dark); transform: translateY(-2px); }
    .text-link { font-size: 13px; font-weight: 650; text-decoration: none; }

    .portrait-wrap { position: relative; width: min(100%, 360px); justify-self: center; }
    .portrait-wrap::before {
      content: ""; position: absolute; inset: -18px 22px 22px -18px;
      background: var(--lavender); border-radius: 48% 48% 28px 28px; transform: rotate(-4deg);
    }
    .portrait-wrap::after {
      content: ""; position: absolute; width: 74px; height: 74px; right: -19px; top: 26px;
      border-radius: 50%; background: var(--pink); z-index: 0;
    }
    .portrait-frame {
      position: relative; z-index: 1; height: 410px; overflow: hidden;
      border: 8px solid var(--white); border-radius: 48% 48% 22px 22px;
      background: linear-gradient(150deg, #f8e8f0, #e6ddf2 70%, #f9f2f6);
      box-shadow: 0 20px 55px rgba(81, 56, 87, .10);
    }
    .portrait-frame img { width: 100%; height: 100%; object-fit: cover; object-position: center 35%; }
    .portrait-placeholder {
      display: none; width: 100%; height: 100%; place-items: center; text-align: center;
      padding: 30px; color: var(--plum);
      background: radial-gradient(circle at 25% 22%, #fff7fb, transparent 40%), linear-gradient(150deg, #f8e8f0, #e6ddf2);
    }
    .portrait-placeholder .initials { display: grid; place-items: center; width: 110px; height: 110px; margin: 0 auto 18px; border-radius: 50%; background: rgba(255,255,255,.68); font-family: var(--serif); font-size: 40px; color: var(--accent-dark); }
    .portrait-placeholder p { font-size: 12px; line-height: 1.5; color: var(--muted); }
    .photo-note { margin: 18px 0 0; text-align: center; color: var(--muted); font-size: 11px; position: relative; z-index: 1; }

    /* Small personal detail strip */
    .personal-strip { background: linear-gradient(100deg, #f4edf9 0%, #fff0f5 100%); border-block: 1px solid #efe4ef; }
    .personal-strip-inner { display: flex; align-items: center; justify-content: center; gap: 12px 34px; flex-wrap: wrap; padding: 18px 0; color: var(--plum); font-size: 12px; letter-spacing: .03em; }
    .personal-strip span { display: inline-flex; align-items: center; gap: 9px; }
    .personal-strip span::before { content: "✧"; color: #b77999; font-size: 16px; }

    /* Shared sections */
    section.content-section { padding: clamp(66px, 8vw, 100px) 0; }
    .section-heading { max-width: 720px; margin-bottom: 38px; }
    .section-label { margin-bottom: 12px; color: var(--accent-dark); font-size: 11px; font-weight: 750; letter-spacing: .17em; text-transform: uppercase; }
    h2 { color: var(--plum); font-family: var(--serif); font-size: clamp(33px, 4.3vw, 48px); font-weight: 500; line-height: 1.16; letter-spacing: -.03em; margin-bottom: 16px; }
    .section-intro { max-width: 660px; color: var(--muted); margin-bottom: 0; }

    /* Decision record */
    .records-section { background: var(--white); border-block: 1px solid var(--line); }
    .record {
      display: grid; grid-template-columns: 66px minmax(0, 1fr) auto;
      gap: 24px; align-items: start; padding: 30px 0;
      border-top: 1px solid var(--line);
    }
    .record-number { color: #b789a1; font-family: var(--serif); font-size: 24px; line-height: 1.4; }
    .record-meta { margin-bottom: 7px; color: var(--accent-dark); font-size: 11px; font-weight: 750; letter-spacing: .11em; text-transform: uppercase; }
    .record h3 { margin-bottom: 9px; color: var(--plum); font-family: var(--serif); font-size: 25px; font-weight: 500; line-height: 1.3; }
    .record p { max-width: 690px; margin-bottom: 0; color: var(--muted); }
    .record-link { white-space: nowrap; align-self: center; font-size: 13px; font-weight: 700; text-decoration: none; }
    .coming-note { margin-top: 25px; color: var(--muted); font-size: 13px; }

    /* Philosophy */
    .philosophy-section { position: relative; }
    .philosophy-layout { display: grid; grid-template-columns: minmax(0, .78fr) minmax(0, 1.22fr); gap: clamp(40px, 9vw, 110px); align-items: start; }
    .philosophy-quote {
      margin: 0; padding: 28px 30px 30px; border-radius: 4px 28px 4px 28px;
      background: linear-gradient(135deg, #f0e7f8, #fff0f5);
      color: var(--plum); font-family: var(--serif); font-size: clamp(24px, 3vw, 33px); line-height: 1.42;
    }
    .philosophy-quote::before { content: "“"; display: block; color: #b77999; font-size: 46px; line-height: .8; margin-bottom: 12px; }
    .philosophy-copy p { color: var(--muted); }
    .philosophy-copy p:last-child { margin-bottom: 0; }

    /* About / future */
    .about-section { background: #fff5f9; border-top: 1px solid #f0e2eb; }
    .about-grid { display: grid; grid-template-columns: minmax(0, 1fr) minmax(240px, .7fr); gap: clamp(40px, 8vw, 95px); align-items: start; }
    .about-copy p { max-width: 690px; color: var(--muted); }
    .future-note { padding: 26px 27px; background: rgba(255,255,255,.74); border-left: 3px solid var(--pink-deep); }
    .future-note .mini-label { margin-bottom: 10px; color: var(--accent-dark); font-size: 10px; font-weight: 750; letter-spacing: .15em; text-transform: uppercase; }
    .future-note p { margin-bottom: 0; color: var(--muted); font-size: 14px; }

    /* Footer */
    footer { padding: 28px 0; background: var(--paper); }
    .footer-row { display: flex; justify-content: space-between; align-items: center; gap: 18px; }
    .footer-row p { margin: 0; color: var(--muted); font-size: 12px; }
    .footer-links { display: flex; gap: 20px; }
    .footer-links a { color: var(--muted); font-size: 12px; text-decoration: none; }

    @media (max-width: 760px) {
      .container { width: min(var(--content), calc(100% - 36px)); }
      .nav { padding: 16px 0; min-height: unset; align-items: flex-start; flex-direction: column; gap: 13px; }
      .nav-links { width: 100%; gap: 16px 20px; flex-wrap: wrap; }
      .nav-links a { font-size: 12px; }
      .hero-grid { grid-template-columns: 1fr; gap: 48px; }
      .hero-copy { max-width: 100%; }
      .portrait-wrap { width: min(78%, 320px); }
      .portrait-frame { height: 365px; }
      .record { grid-template-columns: 36px minmax(0, 1fr); gap: 14px; }
      .record-link { grid-column: 2; justify-self: start; margin-top: 7px; }
      .philosophy-layout, .about-grid { grid-template-columns: 1fr; gap: 28px; }
      .philosophy-quote { max-width: 580px; }
    }
    @media (max-width: 460px) {
      h1 { font-size: 45px; }
      .hero { padding-top: 54px; }
      .personal-strip-inner { justify-content: flex-start; gap: 7px 18px; }
      .record h3 { font-size: 22px; }
      .footer-row { align-items: flex-start; flex-direction: column; }
    }
    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { transition: none !important; }
    }
  </style>
</head>
<body>
  <a class="skip-link" href="#main">Skip to content</a>

  <header class="site-header">
    <nav class="nav container" aria-label="Main navigation">
      <a class="brand" href="#home">
        Minnette Johnson
        <small>Software Engineering Portfolio</small>
      </a>
      <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#portfolio">Portfolio</a>
        <a href="#philosophy">My approach</a>
        <a href="#about">About</a>
        <a class="github-link" href="https://github.com/minnettejohnson-dot" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
      </div>
    </nav>
  </header>

  <main id="main">
    <section class="hero" id="home">
      <div class="container hero-grid">
        <div class="hero-text">
          <div class="eyebrow">Graduate Student · Software Engineering</div>
          <h1>Hi, I’m <em>Minnette.</em></h1>
          <div class="hero-copy">
            <p>I’m a <strong>graduate student from Belize</strong>, interested in how thoughtful software engineering can solve real problems and how the decisions behind a system shape the people who use it.</p>
            <p>I’m currently pursuing a <strong>Master of Science in Software Engineering (MSSE) at <a href="https://www.regis.edu/academics/majors-and-programs/graduate/software-engineering-ms" target="_blank" rel="noopener noreferrer">Regis University</a></strong>. This site brings together selected coursework, the technical decisions I make, and the lessons I take with me as I grow. I’m interested not only in how software works, but in why one approach makes more sense than another—and who benefits from the choices we make.</p>
          </div>
          <div class="hero-actions">
            <a class="primary-link" href="#portfolio">Explore my work</a>
            <a class="text-link" href="#philosophy">A little about how I think →</a>
          </div>
        </div>

        <div class="portrait-wrap">
          <div class="portrait-frame">
            <img src="minnette.jpg" alt="Portrait of Minnette Johnson" onerror="this.style.display='none'; this.nextElementSibling.style.display='grid';">
            <div class="portrait-placeholder" aria-label="Photo placeholder">
              <div>
                <div class="initials" aria-hidden="true">MJ</div>
                <p>Your photo goes here.<br>Upload a portrait named <strong>minnette.jpg</strong>.</p>
              </div>
            </div>
          </div>
          <p class="photo-note">A little corner of my journey, from Belize and beyond.</p>
        </div>
      </div>
    </section>

    <div class="personal-strip" aria-label="Portfolio themes">
      <div class="container personal-strip-inner">
        <span>Learning with intention</span>
        <span>Thoughtful technical decisions</span>
        <span>Room to keep growing</span>
      </div>
    </div>

    <section class="content-section records-section" id="portfolio">
      <div class="container">
        <div class="section-heading">
          <div class="section-label">Selected graduate work</div>
          <h2>Decisions worth documenting.</h2>
          <p class="section-intro">My portfolio decision records capture more than a final answer. They make space for the problem, the alternatives I considered, the reasons behind a choice, and what I learned along the way.</p>
        </div>

        <article class="record">
          <div class="record-number" aria-hidden="true">01</div>
          <div>
            <div class="record-meta">MSSE-601 · Software Engineering Foundations</div>
            <h3>Hybrid Modular Architecture</h3>
            <p>This decision record explores a hybrid modular monolith with an independently deployed Telemetry Service. It looks at the options, why this approach was selected, and the trade-offs that come with the decision.</p>
          </div>
          <a class="record-link" href="msse601/MSSE601-ADR-hybrid-architecture.md">Read the record ↗</a>
        </article>

        <p class="coming-note">This collection will grow as I move through the programme. I’ll add new records when there is a decision or lesson worth revisiting.</p>
      </div>
    </section>

    <section class="content-section philosophy-section" id="philosophy">
      <div class="container philosophy-layout">
        <div>
          <div class="section-label">My approach</div>
          <h2>The answer matters.<br>The thinking matters, too.</h2>
        </div>
        <div class="philosophy-copy">
          <blockquote class="philosophy-quote">I want to remember not only what I chose, but why it made sense at the time.</blockquote>
          <div style="height: 24px"></div>
          <p>Software engineering asks us to make choices, often without a perfect option. I’m learning to slow down enough to ask better questions, compare alternatives fairly, and think about what a decision means beyond the code itself.</p>
          <p>For me, documenting the process is part of the learning. It gives me something honest to look back on: what I understood, what I missed, and how my thinking changes as I gain experience. I don’t expect to have every answer. I do want to stay curious, be willing to reconsider, and keep getting better at the work.</p>
        </div>
      </div>
    </section>

    <section class="content-section about-section" id="about">
      <div class="container about-grid">
        <div class="about-copy">
          <div class="section-label">A little more about me</div>
          <h2>Rooted in Belize.<br>Still curious about what’s next.</h2>
          <p>Belize is home, and this portfolio is one small part of a much bigger learning journey. Through my graduate studies, I’m building a record of the questions I ask, the decisions I take responsibility for, and the skills I’m developing along the way.</p>
          <p>I hope this site will become a useful record of my growth—not a showcase of perfect work, but a place where the learning is visible, too.</p>
        </div>
        <aside class="future-note">
          <div class="mini-label">Looking a little further ahead</div>
          <p>Looking further ahead, I hope to pursue a PhD in Computer Science, with room to explore how computing, AI, and learning can support people. It is a goal I’m working toward one step at a time. For now, I’m focused on building a strong foundation, staying curious, and learning as much as I can along the way.</p>
        </aside>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-row">
      <p>© <span id="year">2026</span> Minnette Johnson · Made as part of my learning journey.</p>
      <div class="footer-links">
        <a href="#home">Back to top ↑</a>
        <a href="https://github.com/minnettejohnson-dot" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
      </div>
    </div>
  </footer>
  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
