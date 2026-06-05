<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Aysan Nazarmohammadi — AI Research Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@300;400;500&family=Instrument+Sans:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet" />
<style>
  :root {
    --bg: #0b0f0e;
    --surface: #111816;
    --card: #151c1a;
    --border: #1f2b28;
    --accent: #3dffa0;
    --accent2: #00c9ff;
    --accent3: #a78bfa;
    --accent4: #fb923c;
    --text: #e8ede9;
    --muted: #6b7d74;
    --serif: 'DM Serif Display', Georgia, serif;
    --sans: 'Instrument Sans', sans-serif;
    --mono: 'DM Mono', monospace;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 1000; opacity: 0.35;
  }
  .glow-orb { position: fixed; border-radius: 50%; filter: blur(130px); pointer-events: none; z-index: 0; opacity: 0.1; }
  .g1 { width: 700px; height: 700px; background: var(--accent);  top: -250px; right: -150px; }
  .g2 { width: 500px; height: 500px; background: var(--accent2); bottom: 5%; left: -180px; }
  .g3 { width: 400px; height: 400px; background: var(--accent3); top: 45%; right: 5%; }
 
  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    padding: 1rem 0;
    backdrop-filter: blur(24px);
    background: rgba(11,15,14,0.75);
    border-bottom: 1px solid var(--border);
  }
  nav .inner { max-width: 1140px; margin: 0 auto; padding: 0 2rem; display: flex; align-items: center; justify-content: space-between; }
  .nav-logo { font-family: var(--mono); font-size: 0.82rem; color: var(--accent); letter-spacing: 0.1em; text-decoration: none; }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a { font-size: 0.78rem; font-weight: 500; letter-spacing: 0.07em; text-transform: uppercase; color: var(--muted); text-decoration: none; transition: color 0.2s; }
  .nav-links a:hover { color: var(--text); }
 
  /* ── LAYOUT ── */
  .container { max-width: 1140px; margin: 0 auto; padding: 0 2rem; position: relative; z-index: 2; }
  section { padding: 6rem 0; }
  .divider { height: 1px; background: linear-gradient(90deg, transparent, var(--border), transparent); }
  .section-label {
    font-family: var(--mono); font-size: 0.7rem; color: var(--accent);
    letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 0.9rem;
    display: flex; align-items: center; gap: 0.75rem;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); max-width: 60px; }
  h2 { font-family: var(--serif); font-size: clamp(2rem, 4vw, 3rem); line-height: 1.1; margin-bottom: 3rem; letter-spacing: -0.02em; }
  h2 em { font-style: italic; color: var(--accent); }
 
  /* ── HERO ── */
  header { min-height: 100vh; display: flex; align-items: center; padding: 9rem 0 5rem; }
  .hero-grid { display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 5rem; align-items: center; }
  .hero-eyebrow {
    font-family: var(--mono); font-size: 0.76rem; color: var(--accent);
    letter-spacing: 0.16em; text-transform: uppercase; margin-bottom: 1.5rem;
    display: flex; align-items: center; gap: 0.75rem;
    opacity: 0; animation: fadeUp 0.8s 0.2s forwards;
  }
  .hero-eyebrow::before { content: ''; display: inline-block; width: 28px; height: 1px; background: var(--accent); }
  h1 { font-family: var(--serif); font-size: clamp(3.2rem, 6vw, 5.2rem); line-height: 1.05; letter-spacing: -0.02em; margin-bottom: 1.4rem; opacity: 0; animation: fadeUp 0.8s 0.35s forwards; }
  h1 em { font-style: italic; color: transparent; -webkit-text-stroke: 1px var(--accent); }
  .hero-quote {
    font-family: var(--serif); font-style: italic; font-size: 1rem;
    color: var(--muted); border-left: 2px solid var(--accent); padding-left: 1rem;
    margin-bottom: 1.5rem; line-height: 1.6;
    opacity: 0; animation: fadeUp 0.8s 0.45s forwards;
  }
  .hero-desc { font-size: 1rem; color: var(--muted); max-width: 460px; margin-bottom: 2.5rem; opacity: 0; animation: fadeUp 0.8s 0.55s forwards; }
  .hero-cta { display: flex; gap: 1rem; flex-wrap: wrap; opacity: 0; animation: fadeUp 0.8s 0.65s forwards; }
  .btn { display: inline-flex; align-items: center; gap: 0.5rem; padding: 0.72rem 1.4rem; border-radius: 4px; font-size: 0.84rem; font-weight: 600; letter-spacing: 0.04em; text-decoration: none; transition: all 0.2s; cursor: pointer; }
  .btn-primary { background: var(--accent); color: #000; border: 1px solid var(--accent); }
  .btn-primary:hover { background: transparent; color: var(--accent); }
  .btn-ghost { background: transparent; color: var(--text); border: 1px solid var(--border); }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); }
 
  /* Hero right stats */
  .hero-right { opacity: 0; animation: fadeIn 1s 0.85s forwards; }
  .stat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 0.9rem; }
  .stat-card {
    background: var(--card); border: 1px solid var(--border); border-radius: 8px; padding: 1.4rem;
    position: relative; overflow: hidden; transition: border-color 0.3s;
  }
  .stat-card:hover { border-color: var(--accent); }
  .stat-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; }
  .c1::before { background: var(--accent); }
  .c2::before { background: var(--accent2); }
  .c3::before { background: var(--accent3); }
  .c4::before { background: var(--accent4); }
  .stat-num { font-family: var(--serif); font-size: 2rem; line-height: 1; margin-bottom: 0.35rem; }
  .stat-label { font-family: var(--mono); font-size: 0.68rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.08em; }
  .stat-wide { grid-column: span 2; background: linear-gradient(135deg, var(--card), #0e2820); }
  .focus-label { font-family: var(--mono); font-size: 0.65rem; color: var(--accent); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 0.5rem; }
  .focus-text { font-size: 0.86rem; color: var(--text); line-height: 1.55; }
 
  /* ── INTERESTS ── */
  .interests { display: flex; flex-wrap: wrap; gap: 0.55rem; margin-bottom: 0; }
  .pill {
    font-family: var(--mono); font-size: 0.7rem; padding: 0.35rem 0.85rem;
    border-radius: 100px; border: 1px solid var(--border); color: var(--muted);
    background: var(--card); letter-spacing: 0.04em; transition: all 0.2s; cursor: default;
  }
  .pill:hover { border-color: var(--accent); color: var(--accent); }
 
  /* ── WHAT I DO ── */
  .do-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1rem; }
  .do-card {
    background: var(--card); border: 1px solid var(--border); border-radius: 8px; padding: 1.4rem;
    transition: border-color 0.3s, transform 0.3s;
  }
  .do-card:hover { border-color: var(--accent); transform: translateY(-2px); }
  .do-icon { font-size: 1.4rem; margin-bottom: 0.75rem; }
  .do-title { font-size: 0.9rem; font-weight: 600; margin-bottom: 0.4rem; color: var(--text); }
  .do-desc { font-size: 0.8rem; color: var(--muted); line-height: 1.55; }
 
  /* ── EXPERIENCE ── */
  .exp-list { display: flex; flex-direction: column; gap: 2.5rem; }
  .exp-item { display: grid; grid-template-columns: 190px 1fr; gap: 2rem; padding-bottom: 2.5rem; border-bottom: 1px solid var(--border); }
  .exp-item:last-child { border-bottom: none; }
  .exp-date { font-family: var(--mono); font-size: 0.73rem; color: var(--muted); padding-top: 0.15rem; letter-spacing: 0.04em; line-height: 1.6; }
  .exp-role { font-size: 1rem; font-weight: 600; margin-bottom: 0.2rem; }
  .exp-org { font-family: var(--mono); font-size: 0.75rem; color: var(--accent); margin-bottom: 0.3rem; }
  .exp-collab { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); margin-bottom: 0.9rem; font-style: italic; }
  .exp-bullets { list-style: none; display: flex; flex-direction: column; gap: 0.5rem; }
  .exp-bullets li { font-size: 0.86rem; color: var(--muted); padding-left: 1.3rem; position: relative; line-height: 1.6; }
  .exp-bullets li::before { content: '→'; position: absolute; left: 0; color: var(--accent); font-size: 0.72rem; top: 0.15rem; }
 
  /* ── PROJECTS ── */
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(330px, 1fr)); gap: 1.4rem; }
  .proj-card {
    background: var(--card); border: 1px solid var(--border); border-radius: 10px; padding: 1.8rem;
    display: flex; flex-direction: column; transition: border-color 0.3s, transform 0.3s; position: relative; overflow: hidden;
  }
  .proj-card:hover { border-color: var(--accent); transform: translateY(-3px); }
  .proj-badge { display: inline-block; font-family: var(--mono); font-size: 0.63rem; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.28rem 0.65rem; border-radius: 3px; margin-bottom: 1.1rem; width: fit-content; }
  .b-bio { background: rgba(61,255,160,0.1); color: var(--accent); }
  .b-ml  { background: rgba(0,201,255,0.1);  color: var(--accent2); }
  .b-fin { background: rgba(167,139,250,0.1);color: var(--accent3); }
  .b-nlp { background: rgba(251,146,60,0.1); color: var(--accent4); }
  .b-bot { background: rgba(251,146,60,0.08); color: #fbbf24; }
  .proj-title { font-family: var(--serif); font-size: 1.15rem; line-height: 1.3; margin-bottom: 0.7rem; }
  .proj-desc { font-size: 0.84rem; color: var(--muted); margin-bottom: 1.2rem; flex: 1; line-height: 1.6; }
  .proj-tags { display: flex; flex-wrap: wrap; gap: 0.35rem; margin-bottom: 1.1rem; }
  .tag { font-family: var(--mono); font-size: 0.62rem; padding: 0.2rem 0.5rem; background: var(--border); border-radius: 3px; color: var(--muted); }
  .proj-links { display: flex; gap: 0.9rem; }
  .proj-link { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); text-decoration: none; display: flex; align-items: center; gap: 0.3rem; transition: color 0.2s; }
  .proj-link:hover { color: var(--accent); }
  .proj-link.disabled { pointer-events: none; opacity: 0.5; }
 
  /* ── EDUCATION ── */
  .edu-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.4rem; }
  .edu-card { background: var(--card); border: 1px solid var(--border); border-radius: 10px; padding: 2rem; transition: border-color 0.3s; }
  .edu-card:hover { border-color: var(--accent2); }
  .edu-degree { font-family: var(--serif); font-size: 1.15rem; margin-bottom: 0.35rem; }
  .edu-school { font-family: var(--mono); font-size: 0.73rem; color: var(--accent2); margin-bottom: 0.2rem; letter-spacing: 0.04em; }
  .edu-year { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); margin-bottom: 0.9rem; }
  .edu-notes { font-size: 0.83rem; color: var(--muted); line-height: 1.65; }
 
  /* ── SKILLS ── */
  .skills-bg { background: var(--surface); }
  .skills-wrap { display: grid; grid-template-columns: repeat(auto-fill, minmax(230px, 1fr)); gap: 1.2rem; }
  .skill-group { background: var(--card); border: 1px solid var(--border); border-radius: 8px; padding: 1.4rem; }
  .skill-group-title { font-family: var(--mono); font-size: 0.68rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--accent); margin-bottom: 0.9rem; padding-bottom: 0.7rem; border-bottom: 1px solid var(--border); }
  .skill-chips { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .chip { font-family: var(--mono); font-size: 0.68rem; padding: 0.28rem 0.55rem; background: var(--bg); border: 1px solid var(--border); border-radius: 3px; color: var(--muted); transition: all 0.2s; }
  .chip:hover { border-color: var(--accent); color: var(--text); }
 
  /* ── PUBLICATIONS ── */
  .pub-list { display: flex; flex-direction: column; gap: 0.9rem; }
  .pub-item { background: var(--card); border: 1px solid var(--border); border-left: 3px solid var(--accent3); border-radius: 0 8px 8px 0; padding: 1.4rem; }
  .pub-item.talk   { border-left-color: var(--accent2); }
  .pub-item.report { border-left-color: var(--accent4); }
  .pub-item.writing{ border-left-color: var(--accent); }
  .pub-type { font-family: var(--mono); font-size: 0.62rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.35rem; }
  .pub-title { font-size: 0.92rem; font-weight: 600; margin-bottom: 0.25rem; line-height: 1.5; }
  .pub-meta { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); }
  .pub-link { display: inline-block; margin-top: 0.5rem; font-family: var(--mono); font-size: 0.7rem; color: var(--accent); text-decoration: none; }
  .pub-link:hover { text-decoration: underline; }
 
  /* ── CERTIFICATIONS ── */
  .cert-row { display: flex; flex-wrap: wrap; gap: 1rem; }
  .cert-card { background: var(--card); border: 1px solid var(--border); border-radius: 8px; padding: 1.2rem 1.5rem; display: flex; align-items: center; gap: 1rem; transition: border-color 0.3s; }
  .cert-card:hover { border-color: var(--accent3); }
  .cert-icon { font-size: 1.5rem; }
  .cert-name { font-size: 0.88rem; font-weight: 600; }
  .cert-issuer { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); }
 
  /* ── CONTACT ── */
  .contact-bg { background: linear-gradient(135deg, #0b0f0e 0%, #0d1a15 100%); border-top: 1px solid var(--border); }
  .contact-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start; }
  .contact-heading { font-family: var(--serif); font-size: clamp(2.4rem, 5vw, 3.8rem); line-height: 1.1; letter-spacing: -0.02em; margin-bottom: 1rem; }
  .contact-heading em { font-style: italic; color: var(--accent); }
  .contact-sub { font-size: 0.92rem; color: var(--muted); margin-bottom: 2rem; line-height: 1.65; }
  .contact-links { display: flex; flex-direction: column; gap: 0.7rem; }
  .contact-link { display: flex; align-items: center; gap: 0.9rem; padding: 0.9rem 1.1rem; background: var(--card); border: 1px solid var(--border); border-radius: 8px; text-decoration: none; color: var(--text); font-size: 0.86rem; transition: all 0.2s; }
  .contact-link:hover { border-color: var(--accent); color: var(--accent); }
  .contact-icon { width: 32px; height: 32px; background: var(--border); border-radius: 5px; display: flex; align-items: center; justify-content: center; font-size: 0.85rem; flex-shrink: 0; font-family: var(--mono); }
 
  /* ── REFS ── */
  .ref-list { display: flex; flex-direction: column; gap: 0.8rem; }
  .ref-card { background: var(--card); border: 1px solid var(--border); border-radius: 8px; padding: 1.1rem 1.3rem; transition: border-color 0.3s; }
  .ref-card:hover { border-color: var(--accent3); }
  .ref-name { font-weight: 600; font-size: 0.88rem; margin-bottom: 0.25rem; }
  .ref-title { font-size: 0.76rem; color: var(--muted); line-height: 1.5; }
 
  /* ── FOOTER ── */
  footer { padding: 2rem 0; border-top: 1px solid var(--border); text-align: center; }
  footer p { font-family: var(--mono); font-size: 0.7rem; color: var(--muted); }
  footer span { color: var(--accent); }
 
  /* ── ANIMATIONS ── */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(22px); } to { opacity: 1; transform: none; } }
  @keyframes fadeIn  { from { opacity: 0; } to { opacity: 1; } }
  .reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.65s ease, transform 0.65s ease; }
  .reveal.visible { opacity: 1; transform: none; }
 
  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    .hero-grid, .contact-inner, .edu-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    .exp-item { grid-template-columns: 1fr; gap: 0.5rem; }
    .nav-links { gap: 1.2rem; }
  }
</style>
</head>
<body>
 
<div class="glow-orb g1"></div>
<div class="glow-orb g2"></div>
<div class="glow-orb g3"></div>
 
<!-- NAV -->
<nav>
  <div class="inner">
    <a class="nav-logo" href="#">AN //</a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#experience">Research</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#publications">Writing</a></li>
      <li><a href="#skills">Stack</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</nav>
 
<!-- ── HERO ── -->
<header id="about">
  <div class="container">
    <div class="hero-grid">
      <div>
        <div class="hero-eyebrow">AI Research Engineer</div>
        <h1>Aysan<br /><em>Nazarmo&shy;hammadi</em></h1>
        <p class="hero-quote">"I don't wait for tools to exist. I build them — from a real problem, for real people, starting with myself."</p>
        <p class="hero-desc">I design systems that think, retrieve, and act — not just predict. My work lives at the intersection of <strong>Agentic AI</strong>, <strong>LLM systems</strong>, and high-stakes environments where getting it wrong actually matters.</p>
        <div class="hero-cta">
          <a href="mailto:aysan.nazarmohamady@yahoo.com" class="btn btn-primary">Get in Touch</a>
          <a href="https://github.com/aysannazarmohamady" target="_blank" rel="noopener" class="btn btn-ghost">GitHub ↗</a>
        </div>
      </div>
      <div class="hero-right">
        <div class="stat-grid">
          <div class="stat-card c1">
            <div class="stat-num">450+</div>
            <div class="stat-label">Models Benchmarked</div>
          </div>
          <div class="stat-card c2">
            <div class="stat-num">7+</div>
            <div class="stat-label">Years in AI/NLP</div>
          </div>
          <div class="stat-card c3">
            <div class="stat-num">99%+</div>
            <div class="stat-label">Text Detection Acc.</div>
          </div>
          <div class="stat-card c4">
            <div class="stat-num">131K</div>
            <div class="stat-label">Clinical Records Built</div>
          </div>
          <div class="stat-card stat-wide">
            <div class="focus-label">Current Focus</div>
            <div class="focus-text">Clinical Trial AI · Systematic Literature Review · Pharmacovigilance Automation · Oncology Viz</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</header>
 
<!-- ── INTERESTS ── -->
<div class="divider"></div>
<section style="padding:2.5rem 0;">
  <div class="container">
    <div class="interests">
      <span class="pill">Agentic AI Systems</span>
      <span class="pill">Large Language Models</span>
      <span class="pill">Retrieval-Augmented Generation</span>
      <span class="pill">Conversational AI</span>
      <span class="pill">Scientific Literature Mining</span>
      <span class="pill">Knowledge Grounding</span>
      <span class="pill">Hallucination Reduction</span>
      <span class="pill">Pharmacovigilance</span>
      <span class="pill">Trustworthy AI</span>
      <span class="pill">Persian NLP</span>
    </div>
  </div>
</section>
<div class="divider"></div>
 
<!-- ── WHAT I DO ── -->
<section style="padding:4rem 0; background:var(--surface);">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Capabilities</div>
      <h2>What I <em>Actually Do</em></h2>
    </div>
    <div class="do-grid reveal">
      <div class="do-card">
        <div class="do-icon">🧩</div>
        <div class="do-title">Design Agentic Systems</div>
        <div class="do-desc">LLM architectures for clinical trial data analysis and systematic literature review — end-to-end, production-grade.</div>
      </div>
      <div class="do-card">
        <div class="do-icon">🔍</div>
        <div class="do-title">Build RAG Pipelines</div>
        <div class="do-desc">Queryable, reproducible systems that don't hallucinate silently. Grounded in real corpora and evaluated rigorously.</div>
      </div>
      <div class="do-card">
        <div class="do-icon">📊</div>
        <div class="do-title">Benchmark LLMs at Scale</div>
        <div class="do-desc">450+ models evaluated under strict reproducibility protocols. AUC/ROC, retrieval accuracy, and clinical validity.</div>
      </div>
      <div class="do-card">
        <div class="do-icon">⚡</div>
        <div class="do-title">Automate Knowledge Work</div>
        <div class="do-desc">Workflows humans shouldn't do manually: NLP pipelines, pharmacovigilance tools, report generation systems.</div>
      </div>
      <div class="do-card">
        <div class="do-icon">🔬</div>
        <div class="do-title">Investigate LLM Failures</div>
        <div class="do-desc">Where and why models fail — and why it matters when they do. Hallucination analysis, edge case profiling.</div>
      </div>
    </div>
  </div>
</section>
 
<!-- ── EXPERIENCE ── -->
<section id="experience">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Experience</div>
      <h2>Research &amp; <em>Industry</em></h2>
    </div>
    <div class="exp-list">
 
      <div class="exp-item reveal">
        <div>
          <div class="exp-date">Sep 2025 – Present</div>
        </div>
        <div>
          <div class="exp-role">AI Research Engineer</div>
          <div class="exp-org">Predex Biopharma</div>
          <div class="exp-collab">In collaboration with Dr. Samad Jahandideh, Director of Data Science & AI, Patient Safety · AstraZeneca, MD, USA</div>
          <ul class="exp-bullets">
            <li>Benchmarked LLM performance (Claude, Gemini, GPT-4) against citation-based ranking for systematic literature review in CAR-T cell therapy safety — AUC/ROC analysis across Python and R.</li>
            <li>Developed a multi-agent AI research agent for systematic retrieval and synthesis of clinical literature on EGFR inhibitor-associated nephrotoxicity — integrating PubMed API, Google Scholar, and LLM-based analysis.</li>
            <li>Built a clinical trial data visualization pipeline: automated swimmer, waterfall, and spider plots from CDISC-structured trial data for oncology cohorts.</li>
            <li>Built a MedDRA terminology comparison tool for pharmacovigilance — automated detection of new Preferred Terms across SMQ versions to support drug safety monitoring.</li>
          </ul>
        </div>
      </div>
 
      <div class="exp-item reveal">
        <div>
          <div class="exp-date">2018 – 2025</div>
        </div>
        <div>
          <div class="exp-role">AI & Data R&D Specialist</div>
          <div class="exp-org">ISNA — Iranian Students' News Agency</div>
          <ul class="exp-bullets">
            <li>Designed KarISNA: a data-driven journalist performance framework with 39 KPIs; linear regression for feature selection on one year of editorial data; hierarchical clustering (HCA) for 10-level classification — findings informed ISNA's editorial policy.</li>
            <li>Authored the technical specification for ISNA's Persian-language RAG-based AI chatbot grounded in ISNA's news archive.</li>
            <li>Deployed a Persian NLP analytics pipeline (n-gram extraction, language detection, engagement classification) for social media monitoring — reduced 2–3 hour daily reporting to automated output serving 200+ monthly users.</li>
            <li>Instructed a training course on data analysis and Google Analytics 4.</li>
          </ul>
        </div>
      </div>
 
      <div class="exp-item reveal">
        <div>
          <div class="exp-date">2022 – Present</div>
        </div>
        <div>
          <div class="exp-role">PC Member & Speaker</div>
          <div class="exp-org">IRNOG — Iranian Internet Network Operators Group (affiliated with RIPE NCC)</div>
          <ul class="exp-bullets">
            <li>Delivered "Agentic AI for Network Automation" at IRNOG7, Isfahan — 2025. <a href="https://labs.ripe.net" target="_blank" rel="noopener" style="color:var(--accent); font-family:var(--mono); font-size:0.72rem;">↗ RIPE Labs</a></li>
            <li>Delivered "Benefits of AI in Network Management" at IRNOG5, Tehran — 2024.</li>
            <li>Developed a Telegram-based event registration and authentication bot for conference management.</li>
          </ul>
        </div>
      </div>
 
    </div>
  </div>
</section>
 
<!-- ── PROJECTS ── -->
<section id="projects" style="background:var(--surface);">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Work</div>
      <h2>Featured <em>Projects</em></h2>
    </div>
    <div class="projects-grid">
 
      <div class="proj-card reveal">
        <span class="proj-badge b-bio">Biopharma · Agents</span>
        <div class="proj-title">EGFR Research Agent</div>
        <p class="proj-desc">Multi-agent system for systematic retrieval and synthesis of clinical literature on EGFR inhibitor-associated nephrotoxicity — integrating PubMed API, Google Scholar, and LLM-based analysis.</p>
        <div class="proj-tags"><span class="tag">LangGraph</span><span class="tag">RAG</span><span class="tag">Qdrant</span><span class="tag">PubMed API</span></div>
        <div class="proj-links">
          <a href="https://github.com/aysannazarmohamady/egfr-research-agent" target="_blank" rel="noopener" class="proj-link">↗ GitHub</a>
        </div>
      </div>
 
      <div class="proj-card reveal">
        <span class="proj-badge b-bio">Oncology · CDISC</span>
        <div class="proj-title">ONCVIZ-001</div>
        <p class="proj-desc">Synthetic ADaM-compliant Phase II/III clinical trial dataset (400 patients, 131,690 records across 13 ADaM domains) — a standardized benchmark for oncology data visualization reproducibility. Manuscript in preparation.</p>
        <div class="proj-tags"><span class="tag">ADaM/CDISC</span><span class="tag">R</span><span class="tag">Python</span><span class="tag">Oncology</span></div>
        <div class="proj-links">
          <a href="https://github.com/aysannazarmohamady" target="_blank" rel="noopener" class="proj-link">↗ GitHub</a>
          <span class="proj-link disabled">Manuscript in prep.</span>
        </div>
      </div>
 
      <div class="proj-card reveal">
        <span class="proj-badge b-ml">NLP · ML</span>
        <div class="proj-title">AI Text Detective</div>
        <p class="proj-desc">Ensemble classifier (Logistic Regression, XGBoost, SMOTE) achieving 99%+ accuracy in distinguishing AI-generated from human-written text — investigated discriminative linguistic features and readability metrics across an imbalanced corpus.</p>
        <div class="proj-tags"><span class="tag">XGBoost</span><span class="tag">SMOTE</span><span class="tag">Scikit-learn</span><span class="tag">NLP</span></div>
        <div class="proj-links">
          <a href="https://medium.com/@aysan.nazarmohamady" target="_blank" rel="noopener" class="proj-link">↗ Medium</a>
          <a href="https://github.com/aysannazarmohamady" target="_blank" rel="noopener" class="proj-link">↗ GitHub</a>
        </div>
      </div>
 
      <div class="proj-card reveal">
        <span class="proj-badge b-fin">Finance · DL</span>
        <div class="proj-title">Bitcoin Forecasting System</div>
        <p class="proj-desc">End-to-end LSTM-based forecasting pipeline combining time-series analysis with technical indicators (RSI, MACD, Bollinger Bands) for automated next-day Bitcoin price prediction and trading signals.</p>
        <div class="proj-tags"><span class="tag">LSTM</span><span class="tag">PyTorch</span><span class="tag">RSI/MACD</span><span class="tag">Time Series</span></div>
        <div class="proj-links">
          <a href="https://github.com/aysannazarmohamady" target="_blank" rel="noopener" class="proj-link">↗ GitHub</a>
        </div>
      </div>
 
      <div class="proj-card reveal">
        <span class="proj-badge b-nlp">Persian NLP</span>
        <div class="proj-title">ISNA Automation Suite</div>
        <p class="proj-desc">4 NLP platforms serving 200+ monthly users at Iran's national news agency — report generation reduced from days to minutes; social media monitoring, language detection, and engagement classification.</p>
        <div class="proj-tags"><span class="tag">Python</span><span class="tag">NLP</span><span class="tag">Streamlit</span><span class="tag">n-gram</span></div>
        <div class="proj-links">
          <span class="proj-link disabled">Internal · Policy Impact</span>
        </div>
      </div>
 
      <div class="proj-card reveal">
        <span class="proj-badge b-bot">Automation · Bot</span>
        <div class="proj-title">Telegram Trend Bot</div>
        <p class="proj-desc">Real-time Google Trends monitoring bot with automatic updates every few hours — built for conference management and event registration authentication at IRNOG.</p>
        <div class="proj-tags"><span class="tag">Python</span><span class="tag">Telegram API</span><span class="tag">Google Trends</span></div>
        <div class="proj-links">
          <a href="https://github.com/aysannazarmohamady" target="_blank" rel="noopener" class="proj-link">↗ GitHub</a>
        </div>
      </div>
 
    </div>
  </div>
</section>
 
<!-- ── PUBLICATIONS & WRITING ── -->
<section id="publications">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Output</div>
      <h2>Publications &amp; <em>Writing</em></h2>
    </div>
    <div class="pub-list reveal">
      <div class="pub-item">
        <div class="pub-type">Manuscript in Preparation</div>
        <div class="pub-title">ONCVIZ-001: A Synthetic ADaM-Compliant Dataset and Reference Framework for Oncology Data Visualization</div>
        <div class="pub-meta">Nazarmohammadi, A. — 2026</div>
      </div>
      <div class="pub-item">
        <div class="pub-type">Manuscript in Preparation</div>
        <div class="pub-title">Optimizing LLM Validation and Reproducibility in Clinical Applications</div>
        <div class="pub-meta">Nazarmohammadi, A.</div>
      </div>
      <div class="pub-item">
        <div class="pub-type">Manuscript — Early Stage</div>
        <div class="pub-title">Token Efficiency and Response Quality Across Claude Model Versions: A Life Science Benchmark</div>
        <div class="pub-meta">Nazarmohammadi, A.</div>
      </div>
      <div class="pub-item talk">
        <div class="pub-type">Conference Talk · IRNOG7, Isfahan — 2025</div>
        <div class="pub-title">Agentic AI for Network Automation</div>
        <div class="pub-meta">Iranian Internet Network Operators Group</div>
        <a href="https://irnog.net" target="_blank" rel="noopener" class="pub-link">↗ IRNOG · RIPE Labs</a>
      </div>
      <div class="pub-item talk">
        <div class="pub-type">Conference Talk · IRNOG5, Tehran — 2024</div>
        <div class="pub-title">Benefits of AI in Network Management</div>
        <div class="pub-meta">Iranian Internet Network Operators Group</div>
      </div>
      <div class="pub-item report">
        <div class="pub-type">Technical Report — ResearchGate, 2023</div>
        <div class="pub-title">What Is ChatGPT Doing and Why Does It Work?</div>
        <a href="https://www.researchgate.net" target="_blank" rel="noopener" class="pub-link">↗ ResearchGate</a>
      </div>
      <div class="pub-item writing">
        <div class="pub-type">Medium Writing</div>
        <div class="pub-title">Context Engineering vs Prompt Engineering · What Google's Prompt Book Didn't Tell You · Building an AI Text Detective</div>
        <div class="pub-meta">Published on Medium</div>
        <a href="https://medium.com/@aysan.nazarmohamady" target="_blank" rel="noopener" class="pub-link">↗ medium.com/@aysan.nazarmohamady</a>
      </div>
    </div>
  </div>
</section>
 
<!-- ── EDUCATION ── -->
<section id="education" style="background:var(--surface);">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Background</div>
      <h2>Education</h2>
    </div>
    <div class="edu-grid reveal">
      <div class="edu-card">
        <div class="edu-degree">MSc in Computer Science</div>
        <div class="edu-school">Shahid Beheshti University, Iran</div>
        <div class="edu-year">2021 – 2023</div>
        <div class="edu-notes">
          Seminar: sentiment analysis of financial news using VADER; investigated correlation between media sentiment and Tesla stock returns (supervised by Dr. Hadi Farahani).<br /><br />
          Presented analysis of LLM mechanics (Dr. Ali Katanforush); organized public online webinar during early ChatGPT adoption — 2023.
        </div>
      </div>
      <div class="edu-card">
        <div class="edu-degree">BSc in Software Engineering</div>
        <div class="edu-school">Ale Taha University, Iran</div>
        <div class="edu-year">2016 – 2020</div>
        <div class="edu-notes">
          Research paper: algorithmic error analysis in Persian news search engines — keyword-based misclassification, duplicate content handling, journalist survey and source code analysis (supervised by Dr. Ali Khosravi).<br /><br />
          Peer-teaching session on blockchain fundamentals; translated and presented academic paper on Business Intelligence in banking (text mining, LDA, fraud detection).
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ── SKILLS ── -->
<section id="skills">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Stack</div>
      <h2>Technical <em>Skills</em></h2>
    </div>
    <div class="skills-wrap reveal">
      <div class="skill-group">
        <div class="skill-group-title">AI & Agents</div>
        <div class="skill-chips">
          <span class="chip">LangChain</span><span class="chip">LangGraph</span><span class="chip">RAG</span><span class="chip">Multi-Agent</span><span class="chip">OpenAI</span><span class="chip">Hugging Face</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">ML / DL</div>
        <div class="skill-chips">
          <span class="chip">PyTorch</span><span class="chip">TensorFlow</span><span class="chip">Scikit-learn</span><span class="chip">XGBoost</span><span class="chip">MLflow</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Languages</div>
        <div class="skill-chips">
          <span class="chip">Python</span><span class="chip">R</span><span class="chip">SQL</span><span class="chip">C++</span><span class="chip">Go</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">NLP</div>
        <div class="skill-chips">
          <span class="chip">NLTK</span><span class="chip">VADER</span><span class="chip">n-gram</span><span class="chip">Text Classification</span><span class="chip">Persian NLP</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Vector & Search</div>
        <div class="skill-chips">
          <span class="chip">Qdrant</span><span class="chip">FAISS</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Clinical / Data</div>
        <div class="skill-chips">
          <span class="chip">ADaM/CDISC</span><span class="chip">MedDRA</span><span class="chip">PubMed API</span><span class="chip">Pandas</span><span class="chip">NumPy</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Engineering</div>
        <div class="skill-chips">
          <span class="chip">Docker</span><span class="chip">FastAPI</span><span class="chip">Streamlit</span><span class="chip">n8n</span><span class="chip">AWS</span><span class="chip">Git</span><span class="chip">Linux</span>
        </div>
      </div>
    </div>
 
    <!-- Certifications -->
    <div style="margin-top:3rem;" class="reveal">
      <div class="section-label" style="margin-bottom:1.2rem;">Certifications</div>
      <div class="cert-row">
        <div class="cert-card">
          <div class="cert-icon">🏅</div>
          <div>
            <div class="cert-name">Network Automation Professional</div>
            <div class="cert-issuer">Arista Networks · 2025</div>
          </div>
        </div>
        <div class="cert-card">
          <div class="cert-icon">🏅</div>
          <div>
            <div class="cert-name">Introduction to Generative AI</div>
            <div class="cert-issuer">Google Cloud / Coursera · 2023</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ── CONTACT ── -->
<section id="contact" class="contact-bg">
  <div class="container">
    <div class="contact-inner">
      <div class="reveal">
        <h2 class="contact-heading">Let's <em>connect.</em></h2>
        <p class="contact-sub">Open to research collaborations, AI/NLP roles, and conversations about agentic systems, clinical AI, and building tools that actually matter.</p>
        <div class="contact-links">
          <a href="mailto:aysan.nazarmohamady@yahoo.com" class="contact-link">
            <div class="contact-icon">✉</div>
            <span>aysan.nazarmohamady@yahoo.com</span>
          </a>
          <a href="https://linkedin.com/in/aysan-nazarmohammadi-0b72b51a6/" target="_blank" rel="noopener" class="contact-link">
            <div class="contact-icon">in</div>
            <span>LinkedIn</span>
          </a>
          <a href="https://github.com/aysannazarmohamady" target="_blank" rel="noopener" class="contact-link">
            <div class="contact-icon">&lt;/&gt;</div>
            <span>github.com/aysannazarmohamady</span>
          </a>
          <a href="https://medium.com/@aysan.nazarmohamady" target="_blank" rel="noopener" class="contact-link">
            <div class="contact-icon">M</div>
            <span>medium.com/@aysan.nazarmohamady</span>
          </a>
          <a href="https://twitter.com/I_am_Aysan" target="_blank" rel="noopener" class="contact-link">
            <div class="contact-icon">𝕏</div>
            <span>@I_am_Aysan</span>
          </a>
        </div>
      </div>
      <div class="reveal">
        <div class="section-label" style="margin-bottom:1.2rem;">References</div>
        <div class="ref-list">
          <div class="ref-card">
            <div class="ref-name">Dr. Samad Jahandideh</div>
            <div class="ref-title">Director of Data Science & AI, Patient Safety · AstraZeneca, Gaithersburg MD, USA</div>
          </div>
          <div class="ref-card">
            <div class="ref-name">Dr. Ali Khosravi</div>
            <div class="ref-title">Assistant Professor, Computer Engineering · University of Tehran, Iran</div>
          </div>
          <div class="ref-card">
            <div class="ref-name">Milad Afshari</div>
            <div class="ref-title">Co-founder & PC Chair, IRNOG · PC Member, RIPE NCC</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<footer>
  <p>© 2026 <span>Aysan Nazarmohammadi</span> &nbsp;·&nbsp; AI Research Engineer &nbsp;·&nbsp; Built with intention</p>
</footer>
 
<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 70);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.07 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
 
