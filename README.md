---
layout: null
---
<div id="portfolio">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Leo Zheng Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@100..125,500..800&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap">
<style>
/* Layout: drafting-sheet portfolio. A title-block hero, then white sections on a faint light-blue grid,
   projects laid out as Goal / Tasks / Impact case studies with photo slots. */
:root {
  --bg: #ffffff;
  --surface: #eef6fc;        /* light blue band */
  --sky: #a9d6f3;            /* light blue fill */
  --sky-strong: #5fb3e6;     /* light blue accent line */
  --link: #0b5f96;           /* readable blue for text links */
  --ink: #0b0f14;            /* black */
  --muted: #4b5966;
  --line: #cfe3f2;
  --grid: rgba(95, 179, 230, 0.10);
  --photo-bg: #f4f9fd;
  --btn-ink: #ffffff;
  --display: "Archivo", "Helvetica Neue", Arial, sans-serif;
  --body: "IBM Plex Sans", "Segoe UI", Roboto, Arial, sans-serif;
  --mono: "IBM Plex Mono", ui-monospace, "SFMono-Regular", Menlo, Consolas, monospace;
  --step-0: 1rem;
  --step-1: 1.25rem;
  --step-2: 1.6rem;
  --step-3: clamp(1.9rem, 4vw, 2.4rem);
  --step-4: clamp(2.6rem, 7vw, 4.25rem);
  --maxw: 1120px;
}
/* Single light theme: the page stays white for every viewer, including dark-mode systems. */
* { box-sizing: border-box; }
html { scroll-behavior: smooth; }
@media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } * { transition: none !important; } }
body {
  background: var(--bg);
  color: var(--ink);
  font-family: var(--body);
  font-size: var(--step-0);
  line-height: 1.6;
}
body::before { content: ""; position: fixed; inset: 0 0 auto; height: env(safe-area-inset-top, 0px); z-index: 10; background: var(--bg); }
a { color: var(--link); text-underline-offset: 3px; }
a:focus-visible, button:focus-visible { outline: 3px solid var(--sky-strong); outline-offset: 3px; border-radius: 4px; }
h1, h2, h3 { font-family: var(--display); text-wrap: balance; line-height: 1.1; margin: 0; }
p { margin: 0; }
ul { margin: 0; padding: 0; }
.wrap {
  max-width: var(--maxw);
  margin-inline: auto;
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
}
.skip { position: absolute; left: -9999px; }
.skip:focus { left: 16px; top: 16px; z-index: 50; background: var(--ink); color: var(--bg); padding: 8px 14px; }
/* ---------- Header ---------- */
.site-header {
  position: sticky; top: env(safe-area-inset-top, 0px); z-index: 20;
  background: color-mix(in srgb, var(--bg) 92%, transparent);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid var(--line);
}
.site-header .wrap { display: flex; align-items: center; justify-content: space-between; gap: 16px; padding-block: 12px; }
.brand { font-family: var(--display); font-weight: 750; font-stretch: 112%; color: var(--ink); text-decoration: none; letter-spacing: 0.01em; white-space: nowrap; }
.brand span { color: var(--sky-strong); }
.nav { display: flex; gap: 4px; overflow-x: auto; min-width: 0; scrollbar-width: none; }
.nav a { color: var(--ink); text-decoration: none; font-size: 0.9rem; font-weight: 500; padding: 6px 10px; border-radius: 6px; white-space: nowrap; }
.nav a:hover { background: var(--surface); }
/* ---------- Hero ---------- */
.hero {
  background-color: var(--bg);
  border-bottom: 1px solid var(--line);
}
.hero .wrap { display: grid; grid-template-columns: 1.25fr 1fr; gap: 48px; align-items: center; padding-block: 72px 64px; }
.hero-copy { display: grid; gap: 20px; min-width: 0; }
.eyebrow { font-family: var(--mono); font-size: 0.78rem; letter-spacing: 0.08em; text-transform: uppercase; color: var(--muted); }
.hero h1 { font-size: var(--step-4); font-weight: 800; font-stretch: 115%; letter-spacing: -0.01em; }
.hero h1 .underline { box-shadow: inset 0 -0.28em 0 var(--sky); }
.lede { font-size: var(--step-1); color: var(--muted); max-width: 34em; }
.actions { display: flex; flex-wrap: wrap; gap: 12px; }
.btn { display: inline-flex; align-items: center; gap: 8px; padding: 11px 18px; border-radius: 8px; font-weight: 600; font-size: 0.95rem; text-decoration: none; border: 1.5px solid var(--ink); transition: transform .15s ease; }
.btn.primary { background: var(--ink); color: var(--btn-ink); }
.btn.secondary { background: transparent; color: var(--ink); }
.btn:hover { transform: translateY(-1px); }
.hero-card { display: grid; border: 1.5px solid var(--ink); background: var(--bg); min-width: 0; }
.hero-card .photo { border: 0; border-bottom: 1.5px solid var(--ink); border-radius: 0; aspect-ratio: 4 / 3; }
/* Title block, styled after an engineering drawing */
.title-block { display: grid; grid-template-columns: 1fr 1fr; font-family: var(--mono); font-size: 0.82rem; margin: 0; }
.title-block div { padding: 8px 12px; border-right: 1px solid var(--ink); border-bottom: 1px solid var(--ink); display: grid; gap: 2px; min-width: 0; }
.title-block div:nth-child(2n) { border-right: 0; }
.title-block div:nth-last-child(-n+2) { border-bottom: 0; }
.title-block dt { font-size: 0.66rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); }
.title-block dd { margin: 0; font-weight: 500; overflow-wrap: anywhere; }
/* ---------- Sections ---------- */
section { scroll-margin-top: 72px; }
.section { padding-block: 80px; }
.section.alt { background: var(--bg); border-block: 1px solid var(--line); }
.section-head { display: grid; gap: 10px; margin-bottom: 40px; max-width: 46rem; }
.section-head.tight { margin-bottom: 0; }
.section-head h2 { font-size: var(--step-3); font-weight: 750; font-stretch: 110%; }
.section-head p { color: var(--muted); }
/* ---------- Photo placeholder ---------- */
.photo {
  position: relative; width: 100%; max-width: 100%; aspect-ratio: 16 / 10;
  border: 1.5px dashed var(--sky-strong); border-radius: 10px;
  background:
    linear-gradient(var(--grid) 1px, transparent 1px) 0 0 / 16px 16px,
    linear-gradient(90deg, var(--grid) 1px, transparent 1px) 0 0 / 16px 16px,
    var(--photo-bg);
  display: grid; place-items: center; overflow: hidden; margin: 0;
}
.photo img { width: 100%; height: 100%; object-fit: cover; display: block; }
.photo figcaption { display: grid; justify-items: center; gap: 8px; padding: 16px; text-align: center; color: var(--muted); font-family: var(--mono); font-size: 0.78rem; line-height: 1.4; }
.photo svg { width: 34px; height: 34px; color: var(--sky-strong); }
.photo.square { aspect-ratio: 1 / 1; }
.photo.tall { aspect-ratio: 4 / 5; }
/* ---------- About ---------- */
.about { display: grid; grid-template-columns: 1fr 1.4fr; gap: 48px; align-items: start; }
.about-text { display: grid; gap: 16px; max-width: 38rem; min-width: 0; }
.about-text p { font-size: 1.05rem; }
.facts { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1px; background: var(--line); border: 1px solid var(--line); margin-top: 8px; }
.facts div { background: var(--bg); padding: 16px; display: grid; gap: 4px; }
.facts strong { font-family: var(--display); font-size: var(--step-2); font-weight: 750; font-variant-numeric: tabular-nums; }
.facts span { font-size: 0.82rem; color: var(--muted); }
/* ---------- Goals ---------- */
.goals { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
.goal { background: var(--bg); border: 1px solid var(--line); border-top: 4px solid var(--sky-strong); padding: 24px; display: grid; gap: 10px; align-content: start; }
.goal .when { font-family: var(--mono); font-size: 0.75rem; letter-spacing: 0.08em; text-transform: uppercase; color: var(--muted); }
.goal h3 { font-size: var(--step-1); font-weight: 700; }
.goal ul { list-style: none; display: grid; gap: 8px; }
.goal li { padding-left: 18px; position: relative; }
.goal li::before { content: ""; position: absolute; left: 0; top: 0.62em; width: 8px; height: 8px; border: 1.5px solid var(--sky-strong); border-radius: 50%; }
/* ---------- Projects ---------- */
.projects { display: grid; gap: 72px; }
.project { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: start; }
.project:nth-child(even) .project-media { order: 2; }
.project-media { display: grid; gap: 12px; min-width: 0; }
.thumbs { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.project-body { display: grid; gap: 18px; min-width: 0; }
.meta { display: flex; flex-wrap: wrap; gap: 8px 16px; font-family: var(--mono); font-size: 0.78rem; color: var(--muted); }
.project h3 { font-size: var(--step-2); font-weight: 750; font-stretch: 108%; }
.tags { display: flex; flex-wrap: wrap; gap: 6px; list-style: none; }
.tags li { font-size: 0.78rem; font-weight: 500; padding: 3px 10px; border-radius: 999px; background: var(--surface); border: 1px solid var(--line); }
.gti { display: grid; gap: 14px; margin: 0; }
.gti > div { display: grid; grid-template-columns: 84px 1fr; gap: 12px; padding-top: 14px; border-top: 1px solid var(--line); }
.gti dt { font-family: var(--mono); font-size: 0.72rem; letter-spacing: 0.1em; text-transform: uppercase; font-weight: 500; color: var(--muted); padding-top: 3px; }
.gti dd { margin: 0; min-width: 0; }
.gti ul { padding-left: 18px; display: grid; gap: 6px; }
.impact { display: flex; flex-wrap: wrap; gap: 10px; }
.metric { background: var(--surface); border: 1px solid var(--line); border-radius: 8px; padding: 10px 14px; display: grid; gap: 2px; min-width: 0; flex: 1 1 140px; }
.metric strong { font-family: var(--display); font-size: 1.35rem; font-weight: 750; font-variant-numeric: tabular-nums; line-height: 1.15; }
.metric span { font-size: 0.82rem; color: var(--muted); line-height: 1.35; }
/* ---------- Experience ---------- */
.timeline { list-style: none; display: grid; border-left: 2px solid var(--sky-strong); margin: 0 0 0 6px; padding: 0; }
.job { position: relative; padding: 0 0 40px 32px; display: grid; grid-template-columns: 1fr 220px; gap: 12px 32px; }
.job:last-child { padding-bottom: 0; }
.job::before { content: ""; position: absolute; left: -8px; top: 6px; width: 14px; height: 14px; border-radius: 50%; background: var(--bg); border: 2px solid var(--ink); }
.job-main { display: grid; gap: 8px; min-width: 0; align-content: start; }
.job h3 { font-size: var(--step-1); font-weight: 700; }
.job .org { color: var(--muted); font-size: 0.95rem; }
.job ul { padding-left: 18px; display: grid; gap: 6px; }
.job-side { display: grid; gap: 10px; align-content: start; }
.job-side .dates { font-family: var(--mono); font-size: 0.8rem; color: var(--muted); }
.job-side .photo { aspect-ratio: 4 / 3; }
/* ---------- Skills ---------- */
.skills { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
.skill-group { display: grid; gap: 14px; align-content: start; padding: 24px; background: var(--bg); border: 1px solid var(--line); }
.skill-group h3 { font-size: 1.05rem; font-weight: 700; }
.chips { display: flex; flex-wrap: wrap; gap: 8px; list-style: none; }
.chips li { font-size: 0.88rem; padding: 5px 12px; border: 1px solid var(--ink); border-radius: 6px; }
.chips li.cert { background: var(--sky); border-color: var(--sky); font-weight: 600; }
/* ---------- Contact ---------- */
.contact { display: grid; grid-template-columns: 1.2fr 1fr; gap: 48px; align-items: start; }
.contact-list { list-style: none; display: grid; border-top: 1px solid var(--line); }
.contact-list li { display: grid; grid-template-columns: 110px 1fr auto; align-items: center; gap: 12px; padding: 14px 0; border-bottom: 1px solid var(--line); }
.contact-list .k { font-family: var(--mono); font-size: 0.75rem; letter-spacing: 0.08em; text-transform: uppercase; color: var(--muted); }
.contact-list .v { min-width: 0; overflow-wrap: anywhere; }
.copy { font: 500 0.8rem var(--body); padding: 6px 12px; border: 1px solid var(--ink); background: transparent; color: var(--ink); border-radius: 6px; cursor: pointer; }
.copy:hover { background: var(--bg); }
footer { border-top: 1px solid var(--line); }
footer .wrap { display: flex; flex-wrap: wrap; justify-content: space-between; gap: 8px 24px; padding-block: 28px; font-size: 0.85rem; color: var(--muted); }
/* ---------- Responsive ---------- */
@media (max-width: 900px) {
  .hero .wrap, .about, .contact { grid-template-columns: 1fr; gap: 36px; }
  .hero .wrap { padding-block: 48px; }
  .goals, .skills { grid-template-columns: 1fr; }
  .project { grid-template-columns: 1fr; gap: 24px; }
  .project:nth-child(even) .project-media { order: 0; }
  .job { grid-template-columns: 1fr; }
  .job-side .photo { max-width: 360px; }
  .about .photo.tall { max-width: 420px; }
}
@media (max-width: 560px) {
  .section { padding-block: 56px; }
  .facts { grid-template-columns: 1fr 1fr; }
  .gti > div { grid-template-columns: 1fr; gap: 6px; }
  .contact-list li { grid-template-columns: 1fr auto; }
  .contact-list .k { grid-column: 1 / -1; }
  .nav a { padding: 6px 8px; font-size: 0.85rem; }
}
</style>
<style>html,body{margin:0}img{max-width:100%}</style>
<!--
  HOW TO EDIT THIS TEMPLATE
  - Text: change any text directly. Sections are marked with "SECTION:" comments.
  - Photos: each photo slot is a <figure class="photo">. To add a real photo, replace the
    <figcaption>...</figcaption> inside it with:  <img src="your-photo.jpg" alt="Describe the photo">
  - Add a project: copy one <article class="project"> block and edit it.
  - Colors and fonts: change the variables at the top of the <style> block.
-->
<a class="skip" target="_self" href="#main" target="_self">Skip to content</a>
<!-- SECTION: Header / navigation -->
<header class="site-header">
  <div class="wrap">
    <nav class="nav" aria-label="Main">
      <a target="_self" href="#about">About</a>
      <a target="_self" href="#goals">Goals</a>
      <a target="_self" href="#projects">Projects</a>
      <a target="_self" href="#experience">Experience</a>
      <a target="_self" href="#skills">Skills</a>
      <a target="_self" href="#contact">Contact</a>
    </nav>
  </div>
</header>
<main id="main">
<!-- SECTION: Hero -->
<section class="hero" id="top" aria-labelledby="hero-title">
  <div class="wrap">
    <div class="hero-copy">
      <p class="eyebrow">Mechanical Engineering · Washington University in St. Louis</p>
      <h1 id="hero-title">Leo <span class="underline">Zheng</span></h1>
      <p class="lede">Second-year mechanical engineering student. I design parts in SolidWorks, test them with FEA, and machine them myself on the mill and lathe.</p>
      <div class="actions">
        <a class="btn primary" target="_self" href="#projects">View projects</a>
        <a class="btn secondary" target="_self" href="#contact">Get in touch</a>
      </div>
    </div>
    <div class="hero-card">
      <figure class="photo">
        <!-- Replace this figcaption with: <img src="headshot.jpg" alt="Headshot of Leo Zheng"> -->
        <figcaption>
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><circle cx="12" cy="9" r="4"/><path d="M4 21c1.5-4 4.5-6 8-6s6.5 2 8 6"/></svg>
          Headshot photo
        </figcaption>
      </figure>
      <dl class="title-block" aria-label="Summary">
        <div><dt>Drawn by</dt><dd>L. Zheng</dd></div>
        <div><dt>Discipline</dt><dd>Mechanical Eng.</dd></div>
        <div><dt>Institution</dt><dd>WashU St. Louis</dd></div>
        <div><dt>Expected grad</dt><dd>May 2029</dd></div>
        <div><dt>GPA</dt><dd>4.00 · Dean's List</dd></div>
        <div><dt>Certification</dt><dd>CSWA</dd></div>
      </dl>
    </div>
  </div>
</section>
<!-- SECTION: About -->
<section class="section" id="about" aria-labelledby="about-title">
  <div class="wrap about">
    <figure class="photo tall">
      <!-- Suggested: you at the mill, lathe, or with the rover -->
      <figcaption>
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="12" cy="12" r="3.5"/><path d="M8 5l1.5-2h5L16 5"/></svg>
        Photo: you at work in the machine shop or lab
      </figcaption>
    </figure>
    <div class="about-text">
      <div class="section-head tight">
        <p class="eyebrow">About</p>
        <h2 id="about-title">From CAD model to finished part</h2>
      </div>
      <p>I'm a mechanical engineering student at Washington University in St. Louis, from Kansas City, Missouri. I like seeing a design all the way through: modeling it, checking it with simulation, and then making it on the shop floor.</p>
      <p>I'm on the rover chassis team for WashU Robotics, where I design wheels and suspension parts for the University Rover Challenge. I'm also a teaching assistant in the university machine shop. Last summer I worked as a manual machine operator, holding tolerances of ±0.005 in on production parts.</p>
      <div class="facts">
        <div><strong>4.00</strong><span>GPA, Dean's List</span></div>
        <div><strong>CSWA</strong><span>SolidWorks certified</span></div>
        <div><strong>2029</strong><span>Expected B.S. in ME</span></div>
      </div>
    </div>
  </div>
</section>
<!-- SECTION: Goals (edit these to match your plans) -->
<section class="section alt" id="goals" aria-labelledby="goals-title">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">Goals</p>
      <h2 id="goals-title">Where I'm headed</h2>
      <p>What I'm working toward this year, next, and after graduation.</p>
    </div>
    <div class="goals">
      <article class="goal">
        <p class="when">This year</p>
        <h3>Build depth in design</h3>
        <ul>
          <li>Earn the CSWP certification in SolidWorks</li>
          <li>Take ownership of a full rover chassis subsystem</li>
          <li>Keep a 4.00 GPA through core ME courses</li>
        </ul>
      </article>
      <article class="goal">
        <p class="when">Next year</p>
        <h3>Gain industry experience</h3>
        <ul>
          <li>Land a mechanical design or manufacturing internship</li>
          <li>Apply GD&amp;T and DFM on real production parts</li>
          <li>Lead a design review for the rover team</li>
        </ul>
      </article>
      <article class="goal">
        <p class="when">After graduation</p>
        <h3>Design hardware that ships</h3>
        <ul>
          <li>Work in product design, robotics, or advanced manufacturing</li>
          <li>Work toward a PE license</li>
          <li>Mentor younger engineers, as I do in the shop now</li>
        </ul>
      </article>
    </div>
  </div>
</section>
<!-- SECTION: Projects. Each project: Goal / Tasks / Impact + photo slots -->
<section class="section" id="projects" aria-labelledby="projects-title">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">Projects</p>
      <h2 id="projects-title">Selected work</h2>
      <p>Each project lists the goal, what I did, and the measured result.</p>
    </div>
    <div class="projects">
      <!-- PROJECT 1 -->
      <article class="project">
        <div class="project-media">
          <figure class="photo">
            <figcaption>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="12" cy="12" r="3.5"/><path d="M8 5l1.5-2h5L16 5"/></svg>
              Main photo: rover with custom wheels
            </figcaption>
          </figure>
          <div class="thumbs">
            <figure class="photo square"><figcaption>CAD: multipart wheel assembly</figcaption></figure>
            <figure class="photo square"><figcaption>FEA: tire displacement plot</figcaption></figure>
          </div>
        </div>
        <div class="project-body">
          <div class="meta"><span>WashU Robotics · University Rover Challenge</span><span>Sep 2025 – Present</span></div>
          <h3>Rover Wheel &amp; Shock-Absorbing Tire</h3>
          <ul class="tags"><li>SolidWorks</li><li>FEA</li><li>3D printing</li><li>Machining</li></ul>
          <dl class="gti">
            <div><dt>Goal</dt><dd>Give the six-wheeled rocker-bogie rover more grip on steep, rough terrain and absorb impacts through the tire itself.</dd></div>
            <div><dt>Tasks</dt><dd><ul>
              <li>Designed and 3D printed a multipart wheel that assembles around an ODrive motor</li>
              <li>Ran FEA on relief-hole patterns in an aperture tire and tuned the geometry so it only starts compressing under 20 lb</li>
              <li>Drafted SolidWorks drawings for rocker-bogie chassis parts and machined them to spec</li>
            </ul></dd></div>
            <div><dt>Impact</dt><dd>
              <div class="impact">
                <div class="metric"><strong>~20°</strong><span>steeper terrain the rover can climb</span></div>
                <div class="metric"><strong>20 lb</strong><span>designed compression threshold</span></div>
              </div>
            </dd></div>
          </dl>
        </div>
      </article>
      <!-- PROJECT 2 -->
      <article class="project">
        <div class="project-media">
          <figure class="photo">
            <figcaption>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="12" cy="12" r="3.5"/><path d="M8 5l1.5-2h5L16 5"/></svg>
              Main photo: watercraft on the water
            </figcaption>
          </figure>
          <div class="thumbs">
            <figure class="photo square"><figcaption>Intake &amp; collection system</figcaption></figure>
            <figure class="photo square"><figcaption>Electronics: Raspberry Pi + L298N</figcaption></figure>
          </div>
        </div>
        <div class="project-body">
          <div class="meta"><span>PLTW Engineering Design · Kansas City, MO</span><span>Aug 2024 – May 2025</span></div>
          <h3>Remote-Controlled Water Surface Cleanup Device</h3>
          <ul class="tags"><li>Product design</li><li>Raspberry Pi</li><li>3D printing</li><li>Motor control</li></ul>
          <dl class="gti">
            <div><dt>Goal</dt><dd>Build a remotely operated boat that collects floating trash from ponds and lakes.</dd></div>
            <div><dt>Tasks</dt><dd><ul>
              <li>Designed the hull, intake, and collection system with custom 3D-printed parts</li>
              <li>Wired and programmed the drive with a Raspberry Pi and an L298N motor controller</li>
              <li>Built, tested, and iterated the full watercraft</li>
            </ul></dd></div>
            <div><dt>Impact</dt><dd>
              <div class="impact">
                <div class="metric"><strong>~5 lb</strong><span>of surface trash collected per trip</span></div>
                <div class="metric"><strong>Top 10</strong><span>of 78 projects, PLTW 2025 competition</span></div>
              </div>
            </dd></div>
          </dl>
        </div>
      </article>
      <!-- PROJECT 3 -->
      <article class="project">
        <div class="project-media">
          <figure class="photo">
            <figcaption>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><rect x="3" y="5" width="18" height="14" rx="2"/><circle cx="12" cy="12" r="3.5"/><path d="M8 5l1.5-2h5L16 5"/></svg>
              Main photo: robot on the competition field
            </figcaption>
          </figure>
          <div class="thumbs">
            <figure class="photo square"><figcaption>Double reverse 4-bar lift</figcaption></figure>
            <figure class="photo square"><figcaption>Team at MOKC Championship</figcaption></figure>
          </div>
        </div>
        <div class="project-body">
          <div class="meta"><span>Belton Robotics · FIRST Tech Challenge</span><span>Aug 2024 – May 2025</span></div>
          <h3>FTC Robot: Autonomous &amp; Maintenance</h3>
          <ul class="tags"><li>Programming</li><li>Mecanum drive</li><li>Troubleshooting</li><li>Leadership</li></ul>
          <dl class="gti">
            <div><dt>Goal</dt><dd>As Auto Programming &amp; Maintenance Lead, score as many autonomous points as possible and keep the robot running through every match.</dd></div>
            <div><dt>Tasks</dt><dd><ul>
              <li>Programmed the autonomous routine for a mecanum-wheeled robot with a double reverse 4-bar lift</li>
              <li>Inspected and repaired mechanical and electrical components between matches</li>
            </ul></dd></div>
            <div><dt>Impact</dt><dd>
              <div class="impact">
                <div class="metric"><strong>#1</strong><span>average auto points in MO/KS for half the season</span></div>
                <div class="metric"><strong>4th</strong><span>place, FTC MOKC Championship (semi-finals)</span></div>
              </div>
            </dd></div>
          </dl>
        </div>
      </article>
      <!-- PROJECT 4 -->
      <article class="project">
        <div class="project-media">
          <figure class="photo">
            <figcaption>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><path d="M4 19V5M4 19h16"/><path d="M7 15l4-4 3 3 5-6"/></svg>
              Screenshot: map of transmission over time
            </figcaption>
          </figure>
          <div class="thumbs">
            <figure class="photo square"><figcaption>Trend chart with policy events</figcaption></figure>
            <figure class="photo square"><figcaption>Code excerpt</figcaption></figure>
          </div>
        </div>
        <div class="project-body">
          <div class="meta"><span>Software project · St. Louis, MO</span><span>Jan 2026 – May 2026</span></div>
          <h3>COVID-19 Infection Simulator</h3>
          <ul class="tags"><li>Python</li><li>Data analysis</li><li>Visualization</li></ul>
          <dl class="gti">
            <div><dt>Goal</dt><dd>Show how COVID-19 spread geographically over time and how public health measures lined up with changes in transmission.</dd></div>
            <div><dt>Tasks</dt><dd><ul>
              <li>Wrote a Python program that pulls data from official COVID-19 databases</li>
              <li>Mapped transmission progression for any selected time period</li>
              <li>Plotted trend lines marked with major events such as mask mandates</li>
            </ul></dd></div>
            <div><dt>Impact</dt><dd>
              <div class="impact">
                <div class="metric"><strong>Policy view</strong><span>supports analysis of how well health policies worked</span></div>
              </div>
            </dd></div>
          </dl>
        </div>
      </article>
    </div>
  </div>
</section>
<!-- SECTION: Experience -->
<section class="section alt" id="experience" aria-labelledby="exp-title">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">Experience</p>
      <h2 id="exp-title">Work &amp; volunteering</h2>
    </div>
    <ol class="timeline">
      <li class="job">
        <div class="job-main">
          <h3>Machine Shop Teaching Assistant</h3>
          <p class="org">Washington University in St. Louis · St. Louis, MO</p>
          <ul>
            <li>Teach students to run the TRAK knee mill, vertical and horizontal bandsaws, and Clausing lathe, with a 100% pass rate</li>
            <li>Guide students through 6 machining projects, including ProtoTRAK CNC programming, with 0 injuries</li>
          </ul>
        </div>
        <div class="job-side">
          <p class="dates">Jan 2026 – Present</p>
          <figure class="photo"><figcaption>Photo: WashU machine shop</figcaption></figure>
        </div>
      </li>
      <li class="job">
        <div class="job-main">
          <h3>Manual Machine Operator</h3>
          <p class="org">Venture Industrial Products · Lee's Summit, MO</p>
          <ul>
            <li>Processed and inspected 300+ custom metal parts a day on knee mills, flat finishers, and turret punch presses, raising production by about 15%</li>
            <li>Read engineering drawings and checked parts with calipers, gauges, and optical comparators to hold ±0.005 in tolerances</li>
          </ul>
        </div>
        <div class="job-side">
          <p class="dates">May 2026 – Aug 2026</p>
          <figure class="photo"><figcaption>Photo: finished parts</figcaption></figure>
        </div>
      </li>
      <li class="job">
        <div class="job-main">
          <h3>Digital Literacy Mentor (Volunteer)</h3>
          <p class="org">Welcome Wellness, Tech Tutor · Belton, MO</p>
          <ul>
            <li>Tutored 4 senior citizens one-on-one and in groups on smartphones and computers, so they could use online banking and healthcare services on their own</li>
          </ul>
        </div>
        <div class="job-side">
          <p class="dates">Mar 2025 – May 2025</p>
        </div>
      </li>
    </ol>
  </div>
</section>
<!-- SECTION: Skills -->
<section class="section" id="skills" aria-labelledby="skills-title">
  <div class="wrap">
    <div class="section-head">
      <p class="eyebrow">Skills</p>
      <h2 id="skills-title">Tools I use</h2>
    </div>
    <div class="skills">
      <div class="skill-group">
        <h3>Software &amp; programming</h3>
        <ul class="chips">
          <li class="cert">SOLIDWORKS (CSWA)</li><li>Autodesk Fusion</li><li>FEA</li><li>Python</li><li>C++</li><li>Microsoft Office</li>
        </ul>
      </div>
      <div class="skill-group">
        <h3>Machining &amp; fabrication</h3>
        <ul class="chips">
          <li>ProtoTRAK CNC</li><li>TRAK 2OP</li><li>Lathe</li><li>Knee mill</li><li>Bandsaw</li><li>3D printing</li><li>Component design</li>
        </ul>
      </div>
      <div class="skill-group">
        <h3>Leadership &amp; communication</h3>
        <ul class="chips">
          <li>Leadership</li><li>Mentoring</li><li>Project management</li><li>Communication</li><li>Documentation</li>
        </ul>
      </div>
    </div>
  </div>
</section>
<!-- SECTION: Contact -->
<section class="section alt" id="contact" aria-labelledby="contact-title">
  <div class="wrap contact">
    <div class="section-head tight">
      <p class="eyebrow">Contact</p>
      <h2 id="contact-title">Let's talk</h2>
      <p>I'm looking for mechanical design and manufacturing internships. Reach out by email or LinkedIn.</p>
    </div>
    <ul class="contact-list">
      <li>
        <span class="k">Email</span>
        <span class="v" id="email">lz.leo.zheng@gmail.com</span>
        <button class="copy" type="button" id="copy-email" data-target="email">Copy</button>
      </li>
      <li>
        <span class="k">LinkedIn</span>
        <span class="v"><a href="https://www.linkedin.com/in/lzleozheng" target="_blank" rel="noopener">linkedin.com/in/lzleozheng</a></span>
        <span></span>
      </li>
      <li>
        <span class="k">Location</span>
        <span class="v">St. Louis, MO · Kansas City, MO</span>
        <span></span>
      </li>
    </ul>
  </div>
</section>
</main>
<footer>
  <div class="wrap">
    <span>© 2026 Leo Zheng</span>
    <span>Last updated November 2026</span>
  </div>
</footer>
<script>
document.querySelectorAll('.copy').forEach(function (btn) {
  btn.addEventListener('click', function () {
    var el = document.getElementById(btn.dataset.target);
    var text = el.textContent.trim();
    function done(msg) { btn.textContent = msg; setTimeout(function () { btn.textContent = 'Copy'; }, 1800); }
    function fallback() {
      var r = document.createRange(); r.selectNodeContents(el);
      var s = window.getSelection(); s.removeAllRanges(); s.addRange(r);
      done('Selected');
    }
    try {
      navigator.clipboard.writeText(text).then(function () { done('Copied'); }, fallback);
    } catch (e) { fallback(); }
  });
});
</script>
</div>
