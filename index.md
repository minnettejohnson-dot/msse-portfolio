<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Minnette Johnson | MSSE Portfolio</title>
  <meta name="description" content="Graduate portfolio of Minnette Johnson, documenting software engineering projects and technical decisions.">

  <style>
    :root {
      --navy: #192c46;
      --gold: #b99a62;
      --background: #fbfbfa;
      --white: #ffffff;
      --text: #303946;
      --muted: #697383;
      --border: #e6e8eb;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text);
      background: var(--background);
      line-height: 1.75;
      font-size: 15px;
    }

    a {
      color: var(--navy);
      text-decoration: none;
    }

    a:hover {
      color: #99783f;
    }

    .container {
      width: min(960px, 88%);
      margin: auto;
    }

    /* Header */

    header {
      background: var(--white);
      border-bottom: 1px solid var(--border);
    }

    nav {
      min-height: 76px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 24px;
    }

    .brand {
      font-size: 16px;
      font-weight: 700;
      color: var(--navy);
    }

    .brand span {
      color: var(--gold);
    }

    .nav-links {
      display: flex;
      gap: 25px;
      font-size: 13px;
    }

    /* Introduction */

    .intro {
      padding: 95px 0 75px;
      border-bottom: 1px solid var(--border);
    }

    .kicker {
      color: #8b7041;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      font-weight: 700;
      margin-bottom: 19px;
    }

    h1 {
      color: var(--navy);
      font-size: clamp(35px, 5vw, 49px);
      line-height: 1.2;
      letter-spacing: -1.2px;
      font-weight: 650;
      margin-bottom: 22px;
    }

    .intro p {
      max-width: 690px;
      color: var(--muted);
      font-size: 16px;
      margin-bottom: 16px;
    }

    .intro .details {
      margin-top: 25px;
      font-size: 13px;
      color: var(--muted);
    }

    .details span {
      color: var(--gold);
      padding: 0 8px;
    }

    /* Main content */

    section {
      padding: 65px 0;
      border-bottom: 1px solid var(--border);
    }

    .section-label {
      color: #8b7041;
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      margin-bottom: 9px;
    }

    h2 {
      color: var(--navy);
      font-size: 27px;
      font-weight: 650;
      margin-bottom: 13px;
    }

    .section-intro {
      max-width: 650px;
      color: var(--muted);
      margin-bottom: 30px;
    }

    /* Project */

    .project {
      background: var(--white);
      border: 1px solid var(--border);
      padding: 28px 30px;
      border-radius: 5px;
    }

    .project-meta {
      color: #8b7041;
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 1px;
      text-transform: uppercase;
      margin-bottom: 9px;
    }

    .project h3 {
      color: var(--navy);
      font-size: 20px;
      margin-bottom: 12px;
    }

    .project p {
      color: var(--muted);
      margin-bottom: 17px;
      max-width: 720px;
    }

    .project-link {
      display: inline-block;
      font-size: 13px;
      font-weight: 700;
      border-bottom: 1px solid var(--gold);
      padding-bottom: 3px;
    }

    .note {
      margin-top: 23px;
      font-size: 13px;
      color: var(--muted);
    }

    /* About */

    .about p {
      max-width: 740px;
      color: var(--muted);
      margin-bottom: 17px;
    }

    /* Footer */

    footer {
      padding: 27px 0;
      background: var(--white);
    }

    .footer-content {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      align-items: center;
    }

    footer p,
    footer a {
      color: var(--muted);
      font-size: 12px;
    }

    @media (max-width: 600px) {
      nav {
        padding: 18px 0;
        align-items: flex-start;
        flex-direction: column;
        gap: 12px;
      }

      .nav-links {
        flex-wrap: wrap;
        gap: 17px;
      }

      .intro {
        padding: 65px 0 50px;
      }

      section {
        padding: 48px 0;
      }

      .project {
        padding: 22px;
      }

      .footer-content {
        align-items: flex-start;
        flex-direction: column;
      }
    }
  </style>
</head>

<body>

  <header>
    <nav class="container">
      <a class="brand" href="#home">Minnette Johnson<span>.</span></a>

      <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#portfolio">Portfolio</a>
        <a href="#about">About</a>
        <a href="https://github.com/minnettejohnson-dot"
           target="_blank" rel="noopener noreferrer">GitHub ↗</a>
      </div>
    </nav>
  </header>

  <main>

    <div class="intro" id="home">
      <div class="container">

        <div class="kicker">
          Master of Science in Software Engineering
        </div>

        <h1>Software Engineering Portfolio</h1>

        <p>
          Welcome to my portfolio. I'm Minnette Johnson, and this is
          where I document selected work and technical decisions from
          my graduate studies in software engineering.
        </p>

        <p>
          Each decision record captures a problem, the options I
          considered, the reasoning behind my decision, and what I
          learned from the process.
        </p>

        <div class="details">
          Graduate Studies <span>•</span>
          Technical Decisions <span>•</span>
          Project Documentation
        </div>

      </div>
    </div>

    <section id="portfolio">
      <div class="container">

        <div class="section-label">Coursework</div>
        <h2>Portfolio Decision Records</h2>

        <p class="section-intro">
          A collection of individual records documenting the
          engineering decisions I work through during my program.
          I'll continue adding to this collection as I progress
          through my courses.
        </p>

        <article class="project">
          <div class="project-meta">MSSE-601 · Software Engineering Foundations</div>

          <h3>Hybrid Modular Architecture</h3>

          <p>
            This record documents my architectural decision involving
            a hybrid modular monolith with an independently deployed
            Telemetry Service. It examines the alternatives, the
            reasoning behind the selection, and the associated trade-offs.
          </p>

          <a class="project-link"
             href="msse601/MSSE601-ADR-hybrid-architecture.md">
            Read the decision record →
          </a>
        </article>

        <p class="note">
          More records will be added as I complete work throughout
          the program.
        </p>

      </div>
    </section>

    <section id="about">
      <div class="container about">

        <div class="section-label">About</div>
        <h2>A little about this portfolio</h2>

        <p>
          I created this site to keep my graduate work organized in
          one place and to build a record of the decisions I make
          throughout my software engineering studies.
        </p>

        <p>
          My focus is on understanding the reasoning behind technical
          choices, documenting alternatives, and learning to evaluate
          solutions beyond whether they simply work.
        </p>

        <p>
          This portfolio will grow alongside my studies, with each
          entry reflecting the work and learning from a particular
          course or project.
        </p>

      </div>
    </section>

  </main>

  <footer>
    <div class="container footer-content">
      <p>© 2026 Minnette Johnson · Software Engineering Portfolio</p>
      <a href="#home">Back to top ↑</a>
    </div>
  </footer>

</body>
</html>
