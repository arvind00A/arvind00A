<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Arvind Kumar — ASP.NET Core Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --surface2: #16161f;
    --border: #1e1e2e;
    --accent: #7c3aed;
    --accent2: #06b6d4;
    --accent3: #f59e0b;
    --text: #e2e8f0;
    --muted: #64748b;
    --dot-net: #512bd4;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: 
      linear-gradient(rgba(124,58,237,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,58,237,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events: none;
    z-index: 0;
  }

  /* Glow orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
  }
  .orb-1 { width: 500px; height: 500px; background: rgba(124,58,237,0.12); top: -100px; right: -100px; }
  .orb-2 { width: 400px; height: 400px; background: rgba(6,182,212,0.08); bottom: 100px; left: -100px; }
  .orb-3 { width: 300px; height: 300px; background: rgba(245,158,11,0.06); top: 50%; left: 50%; transform: translate(-50%,-50%); }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: center;
    margin-bottom: 60px;
    padding-bottom: 40px;
    border-bottom: 1px solid var(--border);
  }

  .header-left { animation: fadeUp 0.6s ease both; }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(124,58,237,0.15);
    border: 1px solid rgba(124,58,237,0.3);
    color: #a78bfa;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 100px;
    margin-bottom: 16px;
    letter-spacing: 0.05em;
  }
  .badge::before { content: '●'; font-size: 8px; color: #7c3aed; animation: pulse 2s infinite; }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.4rem, 6vw, 3.8rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
  }
  h1 .hi { color: var(--muted); font-weight: 400; font-size: 0.6em; display: block; letter-spacing: 0; }
  h1 .name { 
    background: linear-gradient(135deg, #fff 30%, #a78bfa 70%, #06b6d4);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }

  .role-line {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 14px;
    color: var(--muted);
    font-size: 15px;
  }
  .role-line .dot-net-badge {
    background: rgba(81,43,212,0.2);
    border: 1px solid rgba(81,43,212,0.4);
    color: #818cf8;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 4px;
  }

  .views-badge {
    margin-top: 14px;
    display: inline-block;
  }
  .views-badge img { border-radius: 4px; }

  /* Avatar area */
  .avatar-wrap {
    position: relative;
    animation: fadeUp 0.6s 0.2s ease both;
  }
  .avatar-wrap img {
    width: 180px;
    height: 180px;
    border-radius: 20px;
    object-fit: cover;
    border: 2px solid var(--border);
    display: block;
  }
  .avatar-ring {
    position: absolute;
    inset: -8px;
    border-radius: 26px;
    border: 1px solid rgba(124,58,237,0.3);
    pointer-events: none;
  }
  .avatar-ring::before {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 30px;
    border: 1px solid rgba(124,58,237,0.1);
  }
  .avatar-corner {
    position: absolute;
    width: 12px; height: 12px;
    border-color: var(--accent);
    border-style: solid;
  }
  .avatar-corner.tl { top: -8px; left: -8px; border-width: 2px 0 0 2px; border-radius: 3px 0 0 0; }
  .avatar-corner.tr { top: -8px; right: -8px; border-width: 2px 2px 0 0; border-radius: 0 3px 0 0; }
  .avatar-corner.bl { bottom: -8px; left: -8px; border-width: 0 0 2px 2px; border-radius: 0 0 0 3px; }
  .avatar-corner.br { bottom: -8px; right: -8px; border-width: 0 2px 2px 0; border-radius: 0 0 3px 0; }

  /* ── SOCIAL LINKS ── */
  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--accent2);
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 20px;
    color: #fff;
  }

  .socials-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
    margin-bottom: 50px;
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .social-card {
    display: flex;
    align-items: center;
    gap: 12px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 14px 16px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.2s ease;
    position: relative;
    overflow: hidden;
  }
  .social-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, transparent, rgba(124,58,237,0.04));
    opacity: 0;
    transition: opacity 0.2s;
  }
  .social-card:hover { border-color: rgba(124,58,237,0.4); transform: translateY(-2px); }
  .social-card:hover::before { opacity: 1; }

  .social-icon {
    width: 36px; height: 36px;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
  }
  .social-icon.twitter { background: rgba(29,161,242,0.15); color: #1da1f2; }
  .social-icon.github { background: rgba(255,255,255,0.08); color: #fff; }
  .social-icon.linkedin { background: rgba(10,102,194,0.2); color: #0a66c2; }
  .social-icon.email { background: rgba(234,67,53,0.15); color: #ea4335; }

  .social-info { min-width: 0; }
  .social-platform { font-size: 11px; color: var(--muted); font-family: 'Space Mono', monospace; }
  .social-handle { font-size: 13px; color: var(--text); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; font-weight: 500; }

  .arrow { margin-left: auto; color: var(--muted); font-size: 14px; opacity: 0; transition: opacity 0.2s; }
  .social-card:hover .arrow { opacity: 1; }

  /* ── SKILLS ── */
  .skills-section { margin-bottom: 50px; animation: fadeUp 0.6s 0.4s ease both; }

  .skills-tabs {
    display: flex;
    gap: 4px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 4px;
    margin-bottom: 20px;
    width: fit-content;
  }
  .tab-btn {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 7px 16px;
    border-radius: 7px;
    border: none;
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    transition: all 0.2s;
    letter-spacing: 0.03em;
  }
  .tab-btn.active { background: var(--accent); color: #fff; }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 8px;
  }

  .skill-chip {
    display: flex;
    align-items: center;
    gap: 8px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 14px;
    font-size: 13px;
    font-weight: 500;
    transition: all 0.2s;
    cursor: default;
  }
  .skill-chip:hover { border-color: rgba(124,58,237,0.4); background: var(--surface2); transform: translateY(-1px); }
  .skill-chip .dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }
  .dot-purple { background: #7c3aed; }
  .dot-cyan { background: #06b6d4; }
  .dot-amber { background: #f59e0b; }
  .dot-green { background: #10b981; }
  .dot-pink { background: #ec4899; }

  /* ── TECH STACK VISUAL ── */
  .tech-visual {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    margin-bottom: 50px;
    animation: fadeUp 0.6s 0.5s ease both;
    position: relative;
    overflow: hidden;
  }
  .tech-visual::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
  }

  .tech-stack-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 12px;
  }
  .tech-badge {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 5px 12px;
    border-radius: 6px;
    letter-spacing: 0.03em;
    border: 1px solid;
    transition: all 0.2s;
  }
  .tech-badge:hover { transform: scale(1.05); }
  .tech-badge.csharp { background: rgba(124,58,237,0.12); border-color: rgba(124,58,237,0.3); color: #a78bfa; }
  .tech-badge.dotnet { background: rgba(81,43,212,0.12); border-color: rgba(81,43,212,0.35); color: #818cf8; }
  .tech-badge.frontend { background: rgba(245,158,11,0.1); border-color: rgba(245,158,11,0.3); color: #fbbf24; }
  .tech-badge.db { background: rgba(16,185,129,0.1); border-color: rgba(16,185,129,0.3); color: #34d399; }
  .tech-badge.tool { background: rgba(6,182,212,0.1); border-color: rgba(6,182,212,0.3); color: #22d3ee; }

  /* ── GOALS ── */
  .goals-section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    animation: fadeUp 0.6s 0.6s ease both;
    position: relative;
    overflow: hidden;
  }
  .goals-section::after {
    content: '';
    position: absolute;
    bottom: -40px; right: -40px;
    width: 150px; height: 150px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(124,58,237,0.1), transparent);
    pointer-events: none;
  }

  .goal-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 14px 0;
    border-bottom: 1px solid var(--border);
  }
  .goal-item:last-child { border-bottom: none; padding-bottom: 0; }

  .goal-num {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    background: rgba(124,58,237,0.1);
    border: 1px solid rgba(124,58,237,0.2);
    width: 26px; height: 26px;
    border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    margin-top: 1px;
  }
  .goal-text { font-size: 14px; line-height: 1.5; }
  .goal-text strong { color: #fff; font-weight: 600; }

  /* ── GITHUB STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 50px;
    animation: fadeUp 0.6s 0.55s ease both;
  }
  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 16px;
    text-align: center;
    transition: all 0.2s;
  }
  .stat-card:hover { border-color: rgba(124,58,237,0.3); transform: translateY(-2px); }
  .stat-num { font-family: 'Syne', sans-serif; font-size: 2rem; font-weight: 800; color: #fff; }
  .stat-label { font-size: 11px; color: var(--muted); font-family: 'Space Mono', monospace; margin-top: 4px; letter-spacing: 0.05em; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    margin-top: 60px;
    padding-top: 30px;
    border-top: 1px solid var(--border);
    color: var(--muted);
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    animation: fadeUp 0.6s 0.7s ease both;
  }

  /* animations */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  @media (max-width: 600px) {
    .header { grid-template-columns: 1fr; }
    .avatar-wrap { display: none; }
    .socials-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr; }
  }

  /* Tab panel */
  .tab-panel { display: none; }
  .tab-panel.active { display: block; }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">

  <!-- HEADER -->
  <header class="header">
    <div class="header-left">
      <div class="badge">Available for opportunities</div>
      <h1>
        <span class="hi">👋 Hi, I'm</span>
        <span class="name">Arvind Kumar</span>
      </h1>
      <div class="role-line">
        <span class="dot-net-badge">.NET</span>
        ASP.NET Core Developer
      </div>
      <div class="views-badge">
        <img src="https://komarev.com/ghpvc/?username=arvind00a&label=Profile+views&color=7c3aed&style=flat-square" alt="Profile Views">
      </div>
    </div>
    <div class="avatar-wrap">
      <img src="https://user-images.githubusercontent.com/74038190/229223263-cf2e4b07-2615-4f87-9c38-e37600f8381a.gif" alt="Coding">
      <div class="avatar-ring"></div>
      <div class="avatar-corner tl"></div>
      <div class="avatar-corner tr"></div>
      <div class="avatar-corner bl"></div>
      <div class="avatar-corner br"></div>
    </div>
  </header>

  <!-- SOCIAL LINKS -->
  <div class="section-label">Connect</div>
  <h2 class="section-title">📫 Let's Connect</h2>
  <div class="socials-grid">
    <a class="social-card" href="https://twitter.com/arvind01A" target="_blank">
      <div class="social-icon twitter">𝕏</div>
      <div class="social-info">
        <div class="social-platform">Twitter / X</div>
        <div class="social-handle">@arvind01A</div>
      </div>
      <span class="arrow">↗</span>
    </a>
    <a class="social-card" href="https://github.com/arvind00A" target="_blank">
      <div class="social-icon github">⌥</div>
      <div class="social-info">
        <div class="social-platform">GitHub</div>
        <div class="social-handle">github.com/arvind00A</div>
      </div>
      <span class="arrow">↗</span>
    </a>
    <a class="social-card" href="https://linkedin.com/in/arvind00" target="_blank">
      <div class="social-icon linkedin">in</div>
      <div class="social-info">
        <div class="social-platform">LinkedIn</div>
        <div class="social-handle">linkedin.com/in/arvind00</div>
      </div>
      <span class="arrow">↗</span>
    </a>
    <a class="social-card" href="mailto:arvind.kr0024@gmail.com">
      <div class="social-icon email">@</div>
      <div class="social-info">
        <div class="social-platform">Email</div>
        <div class="social-handle">arvind.kr0024@gmail.com</div>
      </div>
      <span class="arrow">↗</span>
    </a>
  </div>

  <!-- TECH VISUAL -->
  <div class="section-label">Technology</div>
  <div class="tech-visual">
    <div class="section-title" style="margin-bottom:0; font-size:1.2rem;">🛠 Full Stack at a Glance</div>
    <div class="tech-stack-row">
      <span class="tech-badge csharp">C#</span>
      <span class="tech-badge dotnet">.NET Core</span>
      <span class="tech-badge dotnet">ASP.NET Core</span>
      <span class="tech-badge dotnet">ASP.NET MVC</span>
      <span class="tech-badge dotnet">EF Core</span>
      <span class="tech-badge dotnet">RESTful API</span>
      <span class="tech-badge dotnet">ASP.NET Web API</span>
      <span class="tech-badge dotnet">LINQ</span>
      <span class="tech-badge dotnet">Multithreading</span>
      <span class="tech-badge frontend">HTML5</span>
      <span class="tech-badge frontend">CSS</span>
      <span class="tech-badge frontend">Bootstrap</span>
      <span class="tech-badge frontend">Materialize CSS</span>
      <span class="tech-badge frontend">Material UI</span>
      <span class="tech-badge db">MS SQL</span>
      <span class="tech-badge db">MySQL</span>
      <span class="tech-badge db">PostgreSQL</span>
      <span class="tech-badge db">Oracle</span>
      <span class="tech-badge tool">Git</span>
      <span class="tech-badge tool">GitHub</span>
      <span class="tech-badge tool">Postman</span>
      <span class="tech-badge tool">Kestrel</span>
    </div>
  </div>

  <!-- SKILLS DETAIL -->
  <div class="section-label">Expertise</div>
  <h2 class="section-title">🎯 Skills Breakdown</h2>
  <div class="skills-section">
    <div class="skills-tabs">
      <button class="tab-btn active" onclick="switchTab('backend')">Backend</button>
      <button class="tab-btn" onclick="switchTab('frontend')">Frontend</button>
      <button class="tab-btn" onclick="switchTab('db')">Databases</button>
      <button class="tab-btn" onclick="switchTab('tools')">Tools</button>
    </div>

    <div id="panel-backend" class="tab-panel active">
      <div class="skills-grid">
        <div class="skill-chip"><span class="dot dot-purple"></span> C#</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> .NET Core</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> ASP.NET Core</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> ASP.NET Core MVC</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> Entity Framework Core</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> RESTful API</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> ASP.NET Web API</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> Multithreading</div>
        <div class="skill-chip"><span class="dot dot-purple"></span> LINQ</div>
      </div>
    </div>
    <div id="panel-frontend" class="tab-panel">
      <div class="skills-grid">
        <div class="skill-chip"><span class="dot dot-amber"></span> HTML5</div>
        <div class="skill-chip"><span class="dot dot-amber"></span> CSS</div>
        <div class="skill-chip"><span class="dot dot-amber"></span> Bootstrap</div>
        <div class="skill-chip"><span class="dot dot-amber"></span> Materialize CSS</div>
        <div class="skill-chip"><span class="dot dot-amber"></span> Material UI</div>
      </div>
    </div>
    <div id="panel-db" class="tab-panel">
      <div class="skills-grid">
        <div class="skill-chip"><span class="dot dot-green"></span> MS SQL</div>
        <div class="skill-chip"><span class="dot dot-green"></span> MySQL</div>
        <div class="skill-chip"><span class="dot dot-green"></span> Oracle</div>
        <div class="skill-chip"><span class="dot dot-green"></span> PostgreSQL</div>
      </div>
    </div>
    <div id="panel-tools" class="tab-panel">
      <div class="skills-grid">
        <div class="skill-chip"><span class="dot dot-cyan"></span> GitHub</div>
        <div class="skill-chip"><span class="dot dot-cyan"></span> Git</div>
        <div class="skill-chip"><span class="dot dot-cyan"></span> Postman</div>
        <div class="skill-chip"><span class="dot dot-cyan"></span> Kestrel Web Server</div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section-label">At a Glance</div>
  <div class="stats-row">
    <div class="stat-card">
      <div class="stat-num">9+</div>
      <div class="stat-label">Technologies</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">4</div>
      <div class="stat-label">Databases</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">∞</div>
      <div class="stat-label">Lines to Write</div>
    </div>
  </div>

  <!-- GOALS -->
  <div class="section-label">Roadmap</div>
  <h2 class="section-title">🎯 Goals</h2>
  <div class="goals-section">
    <div class="goal-item">
      <div class="goal-num">01</div>
      <div class="goal-text">Continuously <strong>improve programming skills</strong> through practice and learning new .NET patterns</div>
    </div>
    <div class="goal-item">
      <div class="goal-num">02</div>
      <div class="goal-text">Work on <strong>real-world projects and case studies</strong> to build production-grade experience</div>
    </div>
    <div class="goal-item">
      <div class="goal-num">03</div>
      <div class="goal-text">Land a professional <strong>.NET Developer role</strong> and contribute to meaningful software products</div>
    </div>
  </div>

  <div class="footer">
    <p>arvind.kr0024@gmail.com · Built with ❤️ & C#</p>
  </div>

</div>

<script>
  function switchTab(tab) {
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
    event.target.classList.add('active');
    document.getElementById('panel-' + tab).classList.add('active');
  }
</script>
</body>
</html>
