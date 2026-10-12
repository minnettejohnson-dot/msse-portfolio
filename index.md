
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Minnette Johnson | Software Engineering Portfolio</title>

  <meta name="description"
        content="Minnette Johnson's Software Engineering graduate portfolio, documenting architectural decisions, engineering practices, and graduate work.">

  <style>
    :root {
      --navy: #14243b;
      --navy-light: #203955;
      --gold: #bd9955;
      --gold-light: #f3ebdc;
      --background: #f8f9fb;
      --white: #ffffff;
      --text: #253247;
      --muted: #68758a;
      --border: #e4e8ee;
      --radius: 16px;
      --shadow: 0 12px 35px rgba(20, 36, 59, 0.07);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 90px;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI",
                   Roboto, Helvetica, Arial, sans-serif;
      background: var(--background);
      color: var(--text);
      line-height: 1.7;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(1120px, 90%);
      margin: 0 auto;
    }

    /* Navigation */

    header {
      background: rgba(255, 255, 255, 0.96);
      border-bottom: 1px solid var(--border);
      position: sticky;
      top: 0;
      z-index: 10;
      backdrop-filter: blur(12px);
    }

    nav {
      min-height: 76px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 24px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 750;
      color: var(--navy);
    }

    .brand-mark {
      display: grid;
      place-items: center;
      width: 43px;
      height: 43px;
      border-radius: 10px;
      background: var(--navy);
      color: var(--white);
      font-size: 15px;
      letter-spacing: 1px;
      border-bottom: 3px solid var(--gold);
    }

    .brand-text small {
      display: block;
      font-size: 11px;
      font-weight: 500;
      color: var(--muted);
      letter-spacing: 1.2px;
      text-transform: uppercase;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 27px;
      font-size: 14px;
      font-weight: 550;
      color: var(--muted);
    }

    .nav-links a:hover {
      color: var(--gold);
    }

    /* Hero */

    .hero {
      padding: 105px 0 90px;
      background:
        radial-gradient(circle at 90% 10%, #eee6d7 0, transparent 28%),
        linear-gradient(135deg, #ffffff 0%, #f5f7fa 100%);
      border-bottom: 1px solid var(--border);
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      align-items: center;
      gap: 70px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 22px;
      color: #94713a;
      font-size: 12px;
      font-weight: 750;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    .eyebrow::before {
      content: "";
      width: 28px;
      height: 2px;
      background: var(--gold);
    }

    h1 {
      max-width: 700px;
      color: var(--navy);
      font-size: clamp(42px, 5.2vw, 66px);
      line-height: 1.1;
      letter-spacing: -2.5px;
      margin-bottom: 24px;
    }

    .hero-description {
      max-width: 590px;
      color: var(--muted);
      font-size: 17px;
      margin-bottom: 30px;
    }

    .hero-description strong {
      color: var(--navy);
    }

    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .button {
      display: inline-block;
      padding: 13px 21px;
      border-radius: 8px;
      font-size: 14px;
      font-weight: 650;
      transition: transform 0.2s, background 0.2s;
    }

    .button:hover {
      transform: translateY(-2px);
    }

    .button-primary {
      background: var(--navy);
      color: var(--white);
    }

    .button-primary:hover {
      background: var(--navy-light);
    }

    .button-secondary {
      border: 1px solid #cbd2dc;
      background: var(--white);
      color: var(--navy);
    }

    /* Architecture illustration */

    .architecture {
      padding: 28px;
      background: rgba(255, 255, 255, 0.88);
      border: 1px solid var(--border);
      border-radius: 20px;
      box-shadow: var(--shadow);
    }

    .architecture-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 26px;
      gap: 12px;
    }

    .architecture-top h2 {
      font-size: 14px;
      color: var(--navy);
    }

    .status {
      color: #58785d;
      font-size: 11px;
      font-weight: 700;
      background: #e9f3e9;
      border-radius: 20px;
      padding: 5px 9px;
    }

    .architecture-block {
      padding: 17px;
      margin-bottom: 12px;
      border: 1px solid #dce3eb;
      border-radius: 10px;
      background: #f8fafc;
    }

    .architecture-block.primary {
      background: var(--navy);
      color: var(--white);
      border-color: var(--navy);
    }

    .architecture-block.gold {
      background: var(--gold-light);
      border-color: #e5d4b5;
    }

    .architecture-block strong {
      display: block;
      font-size: 13px;
      margin-bottom: 3px;
    }

    .architecture-block span {
      display: block;
      font-size: 11px;
      opacity: 0.8;
    }

    .connector {
      width: 1px;
      height: 19px;
      margin: -12px auto 0;
      background: #c7ced9;
    }

    .architecture-note {
      margin-top: 18px;
      padding-top: 16px;
      border-top: 1px solid var(--border);
      color: var(--muted);
      font-size: 12px;
      text-align: center;
    }

    /* Main sections */

    section.content-section {
      padding: 85px 0;
    }

    .section-heading {
      max-width: 650px;
      margin-bottom: 38px;
    }

    .section-heading h2 {
      color: var(--navy);
      font-size: clamp(29px, 3vw, 39px);
      line-height: 1.2;
      letter-spacing: -1px;
      margin-bottom: 13px;
    }

    .section-heading p {
      color: var(--muted);
      font-size: 15px;
    }

    .work-card {
      padding: 35px;
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: center;
      gap: 30px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 17px;
    }

    .tag {
      display: inline-block;
      padding: 5px 10px;
      background: var(--gold-light);
      color: #765b2c;
      border-radius: 5px;
      font-size: 11px;
      font-weight: 750;
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }

    .tag.neutral {
      background: #edf1f6;
      color: #52627a;
    }

    .work-card h3 {
      color: var(--navy);
      font-size: 25px;
      margin-bottom: 12px;
    }

    .work-card p {
      max-width: 670px;
      color: var(--muted);
      font-size: 15px;
      margin-bottom: 19px;
    }

    .text-link {
      display: inline-block;
      color: var(--navy);
      font-size: 14px;
      font-weight: 750;
    }

    .text-link:hover {
      color: #94713a;
    }

    .work-number {
      color: #e8e0d2;
      font-size: 65px;
      font-weight: 800;
      letter-spacing: -4px;
    }

    /* Engineering principles */

    .principles {
      background: #eef2f7;
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .principle-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .principle-card {
      padding: 27px;
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: 12px;
    }

    .principle-number {
      display: inline-block;
      color: #a27d3e;
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 1px;
      margin-bottom: 15px;
    }

    .principle-card h3 {
      color: var(--navy);
      font-size: 18px;
      margin-bottom: 10px;
    }

    .principle-card p {
      color: var(--muted);
      font-size: 14px;
    }

    /* About */

    .about-panel {
      display: grid;
      grid-template-columns: 0.7fr 1.3fr;
      gap: 45px;
      align-items: start;
    }

    .about-label {
      color: #94713a;
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    .about-panel h2 {
      color: var(--navy);
      font-size: 32px;
      line-height: 1.25;
      margin-top: 10px;
    }

    .about-copy p {
      color: var(--muted);
      margin-bottom: 16px;
      font-size: 15px;
    }

    /* Footer */

    footer {
      background: var(--navy);
      color: var(--white);
      padding: 32px 0;
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
    }

    footer p {
      font-size: 13px;
      color: #c1ccda;
    }

    footer a {
      color: #e8d4ad;
      font-size: 13px;
    }

    /* Mobile */

    @media (max-width: 800px) {
      .hero {
        padding: 70px 0;
      }

      .hero-grid,
      .about-panel {
        grid-template-columns: 1fr;
        gap: 40px;
      }

      .principle-grid {
        grid-template-columns: 1fr;
      }

      .work-card {
        grid-template-columns: 1fr;
        padding: 26px;
      }

      .work-number {
        display: none;
      }

      .nav-links {
        gap: 14px;
        font-size: 12px;
      }

      .brand-text small {
        display: none;
      }

      .footer-inner {
        align-items: flex-start;
        flex-direction: column;
      }
    }

    @media (max-width: 480px) {
      nav {
        align-items: flex-start;
        padding: 15px 0;
        flex-direction: column;
      }

      .nav-links {
        flex-wrap: wrap;
      }

      h1 {
        letter-spacing: -1.5px;
      }

      .architecture {
        padding: 19px;
      }

      section.content-section {
        padding: 60px 0;
      }
    }
  </style>
</head>

<body>

  <header>
    <nav class="container">
      <a class="brand" href="#home" aria-label="Minnette Johnson home">
        <span class="brand-mark">MJ</span>
        <span class="brand-text">
          Minnette Johnson
          <small>Software Engineering</small>
        </span>
      </a>

      <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#work">Decision Records</a>
        <a href="#about">About</a>
        <a href="https://github.com/" target="_blank"
           rel="noopener noreferrer">GitHub ↗</a>
      </div>
    </nav>
  </header>

  <main>

    <section class="hero" id="home">
      <div class="container hero-grid">

        <div>
          <div class="eyebrow">
            Graduate Engineering Portfolio
          </div>

          <h1>Engineering decisions. Thoughtfully made.</h1>

          <p class="hero-description">
            I'm <strong>Minnette Johnson</strong>, a graduate student
            pursuing a Master of Science in Software Engineering.
            This portfolio documents the decisions, trade-offs, and
            engineering practices shaping my development as a software
            engineering professional.
          </p>

          <div class="buttons">
            <a class="button button-primary" href="#work">
              Explore Decision Records →
            </a>

            <a class="button button-secondary"
               href="https://github.com/" target="_blank"
               rel="noopener noreferrer">
              View GitHub Profile
            </a>
          </div>
        </div>

        <div class="architecture">
          <div class="architecture-top">
            <h2>Architecture in Practice</h2>
            <span class="status">MSSE-601</span>
          </div>

          <div class="architecture-block primary">
            <strong>Application Layer</strong>
            <span>Interfaces and application workflows</span>
          </div>

          <div class="connector"></div>

          <div class="architecture-block">
            <strong>Core Modules</strong>
            <span>Modularity, maintainability, and clear boundaries</span>
          </div>

          <div class="connector"></div>

          <div class="architecture-block gold">
            <strong>Independent Telemetry Service</strong>
            <span>Separate deployment and operational responsibilities</span>
          </div>

          <p class="architecture-note">
            Architecture · Trade-offs · Evidence · Decision-making
          </p>
        </div>

      </div>
    </section>

    <section class="content-section" id="work">
      <div class="container">

        <div class="section-heading">
          <div class="eyebrow">Selected Work</div>
          <h2>Decisions behind the design.</h2>
          <p>
            Each Portfolio Decision Record captures an engineering
            decision, the alternatives considered, the rationale
            behind the outcome, and the consequences that follow.
          </p>
        </div>

        <article class="work-card">
          <div>
            <div class="tags">
              <span class="tag">MSSE-601</span>
              <span class="tag neutral">Software Architecture</span>
            </div>

            <h3>Hybrid Modular Architecture</h3>

            <p>
              A decision record examining a hybrid modular monolith
              with an independently deployed Telemetry Service,
              including architectural trade-offs, modularity,
              deployment independence, and maintainability.
            </p>

            <a class="text-link"
               href="msse601/MSSE601-ADR-hybrid-architecture.md">
              Read Decision Record →
            </a>
          </div>

          <div class="work-number">01</div>
        </article>

      </div>
    </section>

    <section class="content-section principles">
      <div class="container">

        <div class="section-heading">
          <div class="eyebrow">Engineering Philosophy</div>
          <h2>How I approach engineering.</h2>
          <p>
            Good engineering is not just about making something work.
            It is about understanding why a solution makes sense.
          </p>
        </div>

        <div class="principle-grid">

          <article class="principle-card">
            <span class="principle-number">01 / EVIDENCE</span>
            <h3>Reason with evidence</h3>
            <p>
              Evaluate requirements, constraints, and available
              evidence before committing to a technical direction.
            </p>
          </article>

          <article class="principle-card">
            <span class="principle-number">02 / TRADE-OFFS</span>
            <h3>Make trade-offs explicit</h3>
            <p>
              Compare alternatives honestly, recognizing that every
              architectural choice introduces benefits and costs.
            </p>
          </article>

          <article class="principle-card">
            <span class="principle-number">03 / GROWTH</span>
            <h3>Learn through iteration</h3>
            <p>
              Document outcomes, reflect on assumptions, and refine
              engineering decisions as requirements and knowledge evolve.
            </p>
          </article>

        </div>
      </div>
    </section>

    <section class="content-section" id="about">
      <div class="container about-panel">

        <div>
          <div class="about-label">About This Portfolio</div>
          <h2>Learning to design beyond the code.</h2>
        </div>

        <div class="about-copy">
          <p>
            This portfolio is part of my Master of Science in Software
            Engineering journey. It brings together individual decision
            records that document my reasoning, contributions, and
            development as an engineer.
          </p>

          <p>
            My focus is on thoughtful architecture, clear technical
            communication, maintainable systems, and responsible
            engineering practices.
          </p>

          <p>
            Each record is intended to provide evidence of the work
            I personally drove, the alternatives I evaluated, and the
            lessons I take forward.
          </p>
        </div>

      </div>
    </section>

  </main>

  <footer>
    <div class="container footer-inner">
      <p>© 2026 Minnette Johnson · Software Engineering Portfolio</p>
      <a href="#home">Back to top ↑</a>
    </div>
  </footer>

</body>
</html>
