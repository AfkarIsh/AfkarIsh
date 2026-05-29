<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>GitHub Profile — Ishaq Afkar</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --surface2: #1c2128;
    --border: #30363d;
    --text: #c9d1d9;
    --muted: #8b949e;
    --faint: #484f58;
    --red: #E24B4A;
    --blue: #1BA0D7;
    --purple: #bc8cff;
    --green: #3fb950;
    --orange: #ffa657;
    --yellow: #e3b341;
    --cyan: #39d353;
    --font: 'Fira Code', 'JetBrains Mono', monospace;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font);
    font-size: 14px;
    line-height: 1.7;
    min-height: 100vh;
  }

  /* TAB BAR */
  .tab-bar {
    display: flex;
    gap: 4px;
    padding: 16px 20px 0;
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .tab {
    padding: 8px 18px;
    border: 1px solid var(--border);
    border-bottom: none;
    border-radius: 6px 6px 0 0;
    background: var(--bg);
    color: var(--muted);
    cursor: pointer;
    font-family: var(--font);
    font-size: 13px;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .tab:hover { color: var(--text); background: var(--surface2); }
  .tab.active {
    background: var(--bg);
    color: var(--text);
    border-bottom: 1px solid var(--bg);
    margin-bottom: -1px;
  }
  .tab-dot { width: 8px; height: 8px; border-radius: 50%; }
  .dot-preview { background: var(--green); }
  .dot-code { background: var(--blue); }
  .dot-snake { background: var(--purple); }

  /* TAB PANELS */
  .tab-panel { display: none; }
  .tab-panel.active { display: block; }

  /* PREVIEW PANEL */
  .preview {
    max-width: 860px;
    margin: 0 auto;
    padding: 32px 24px 64px;
  }

  /* HEADER WAVE */
  .wave-header {
    width: 100%;
    background: linear-gradient(135deg, #0d1117 0%, #1a0533 40%, #0a1628 70%, #0d1117 100%);
    border-radius: 8px 8px 0 0;
    padding: 40px 24px 32px;
    text-align: center;
    position: relative;
    overflow: hidden;
    margin-bottom: 0;
    border: 1px solid var(--border);
    border-bottom: none;
  }
  .wave-header::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 60% 50% at 50% 0%, rgba(188,140,255,0.15) 0%, transparent 70%),
                radial-gradient(ellipse 40% 30% at 20% 100%, rgba(27,160,215,0.1) 0%, transparent 60%),
                radial-gradient(ellipse 40% 30% at 80% 100%, rgba(226,75,74,0.1) 0%, transparent 60%);
    pointer-events: none;
  }
  .wave-particles {
    position: absolute;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
  }
  .particle {
    position: absolute;
    width: 2px;
    height: 2px;
    border-radius: 50%;
    background: var(--purple);
    opacity: 0;
    animation: float-up 4s ease-in-out infinite;
  }
  @keyframes float-up {
    0% { opacity: 0; transform: translateY(0) scale(1); }
    30% { opacity: 0.6; }
    70% { opacity: 0.3; }
    100% { opacity: 0; transform: translateY(-60px) scale(0.5); }
  }
  .wave-name {
    font-size: 32px;
    font-weight: 700;
    background: linear-gradient(90deg, var(--blue), var(--purple), var(--red));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
    position: relative;
  }
  .wave-sub {
    color: var(--muted);
    font-size: 13px;
    letter-spacing: 0.5px;
    position: relative;
  }

  /* TYPING ANIMATION */
  .typing-wrapper {
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: none;
    border-bottom: none;
    padding: 12px 24px;
    text-align: center;
  }
  .typing-text {
    color: var(--purple);
    font-size: 15px;
    font-weight: 600;
    display: inline-block;
    border-right: 2px solid var(--purple);
    white-space: nowrap;
    overflow: hidden;
    animation: blink 0.8s step-end infinite;
    min-height: 24px;
  }
  @keyframes blink { 50% { border-color: transparent; } }

  /* BADGES ROW */
  .badges-row {
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: none;
    border-bottom: none;
    padding: 10px 24px;
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    justify-content: center;
  }
  .badge {
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.3px;
    white-space: nowrap;
  }
  .badge-blue { background: rgba(27,160,215,0.15); color: var(--blue); border: 1px solid rgba(27,160,215,0.3); }
  .badge-red { background: rgba(226,75,74,0.15); color: var(--red); border: 1px solid rgba(226,75,74,0.3); }
  .badge-purple { background: rgba(188,140,255,0.15); color: var(--purple); border: 1px solid rgba(188,140,255,0.3); }
  .badge-green { background: rgba(63,185,80,0.15); color: var(--green); border: 1px solid rgba(63,185,80,0.3); }
  .badge-orange { background: rgba(255,166,87,0.15); color: var(--orange); border: 1px solid rgba(255,166,87,0.3); }

  /* MAIN CONTENT BOX */
  .content-box {
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: none;
    border-radius: 0 0 8px 8px;
    padding: 28px 28px 36px;
    margin-bottom: 20px;
  }

  /* SECTION HEADERS */
  .section-title {
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
    margin: 28px 0 14px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .section-title:first-child { margin-top: 0; }
  .section-line { flex: 1; height: 1px; background: linear-gradient(90deg, var(--border), transparent); }

  /* TREE STRUCTURE */
  .tree { font-size: 13px; line-height: 2; }
  .tree-line { display: flex; gap: 0; }
  .tree-connector { color: var(--faint); white-space: pre; }
  .tree-content { flex: 1; }
  .tree-highlight { color: var(--cyan); font-weight: 600; }
  .tree-label { color: var(--muted); }
  .tree-value { color: var(--text); }
  .tree-link { color: var(--blue); text-decoration: none; }
  .tree-link:hover { text-decoration: underline; }

  /* PROGRESS BARS */
  .skill-table { width: 100%; border-collapse: collapse; }
  .skill-row { display: flex; align-items: center; gap: 12px; margin-bottom: 10px; }
  .skill-name { width: 220px; flex-shrink: 0; color: var(--muted); font-size: 12px; }
  .skill-bar-bg {
    flex: 1;
    height: 10px;
    background: var(--surface2);
    border-radius: 20px;
    overflow: hidden;
    position: relative;
    border: 1px solid var(--border);
  }
  .skill-bar-fill {
    height: 100%;
    border-radius: 20px;
    width: 0%;
    transition: width 1.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }
  .skill-bar-fill::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(90deg, transparent 0%, rgba(255,255,255,0.25) 50%, transparent 100%);
    animation: shimmer 2.5s ease-in-out infinite;
  }
  @keyframes shimmer {
    0% { transform: translateX(-100%); }
    100% { transform: translateX(100%); }
  }
  .bar-blue { background: linear-gradient(90deg, #1565c0, var(--blue)); }
  .bar-red { background: linear-gradient(90deg, #8b1a1a, var(--red)); }
  .bar-purple { background: linear-gradient(90deg, #5a2080, var(--purple)); }
  .bar-green { background: linear-gradient(90deg, #1a5c28, var(--green)); }
  .skill-pct {
    width: 34px;
    text-align: right;
    font-size: 12px;
    color: var(--text);
    font-weight: 600;
    flex-shrink: 0;
  }
  .skill-category {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 1.2px;
    text-transform: uppercase;
    margin: 16px 0 8px;
    padding: 3px 10px;
    border-radius: 4px;
    display: inline-block;
  }
  .cat-blue { color: var(--blue); background: rgba(27,160,215,0.1); }
  .cat-red { color: var(--red); background: rgba(226,75,74,0.1); }
  .cat-purple { color: var(--purple); background: rgba(188,140,255,0.1); }

  /* TOOLS */
  .tools-grid { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px; }
  .tool-chip {
    padding: 5px 14px;
    border-radius: 6px;
    font-size: 12px;
    font-weight: 600;
    border: 1px solid;
    transition: all 0.2s;
    cursor: default;
  }
  .tool-chip:hover { transform: translateY(-2px); filter: brightness(1.2); }

  /* PROJECTS */
  .project-item {
    display: flex;
    gap: 12px;
    padding: 12px 14px;
    border-radius: 6px;
    border: 1px solid var(--border);
    margin-bottom: 8px;
    background: var(--surface2);
    transition: border-color 0.2s, transform 0.2s;
  }
  .project-item:hover { border-color: var(--purple); transform: translateX(4px); }
  .project-icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; }
  .project-body {}
  .project-title { color: var(--text); font-weight: 600; font-size: 13px; }
  .project-desc { color: var(--muted); font-size: 11px; margin-top: 3px; }
  .project-tags { display: flex; flex-wrap: wrap; gap: 4px; margin-top: 6px; }
  .project-tag {
    padding: 1px 7px;
    border-radius: 20px;
    font-size: 10px;
    background: rgba(188,140,255,0.12);
    color: var(--purple);
    border: 1px solid rgba(188,140,255,0.2);
  }

  /* EXPERIENCE + EDUCATION */
  .timeline-item { display: flex; gap: 0; margin-bottom: 6px; font-size: 13px; }
  .tl-connector { color: var(--faint); white-space: pre; flex-shrink: 0; }
  .tl-body {}
  .tl-title { color: var(--cyan); font-weight: 600; }
  .tl-sub { color: var(--muted); font-size: 11px; margin-top: 2px; }

  /* QUOTE */
  .quote-block {
    border-left: 3px solid var(--purple);
    padding: 10px 16px;
    margin: 20px 0;
    background: rgba(188,140,255,0.05);
    border-radius: 0 6px 6px 0;
  }
  .quote-block p { color: var(--muted); font-style: italic; font-size: 13px; }
  .quote-block cite { color: var(--purple); font-size: 11px; display: block; margin-top: 4px; }

  /* STATS CARDS */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin: 16px 0;
  }
  .stats-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
    transition: border-color 0.3s;
  }
  .stats-card:hover { border-color: var(--purple); }
  .stats-card img {
    width: 100%;
    display: block;
  }
  .stats-card-placeholder {
    padding: 20px;
    text-align: center;
    color: var(--faint);
    font-size: 12px;
  }

  /* WAVE FOOTER */
  .wave-footer {
    height: 60px;
    background: linear-gradient(135deg, #0d1117 0%, #1a0533 40%, #0a1628 70%, #0d1117 100%);
    border-radius: 0 0 8px 8px;
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid var(--border);
    border-top: 1px solid var(--border);
  }
  .wave-footer::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 80% 100% at 50% 100%, rgba(188,140,255,0.2) 0%, transparent 70%);
  }
  .footer-quote {
    color: var(--purple);
    font-size: 12px;
    font-style: italic;
    position: relative;
    opacity: 0.8;
  }

  /* CODE PANEL */
  .code-panel {
    padding: 0;
    background: var(--bg);
  }
  .code-toolbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 20px;
    background: var(--surface);
    border-bottom: 1px solid var(--border);
  }
  .code-lang { color: var(--muted); font-size: 12px; }
  .copy-btn {
    padding: 5px 14px;
    border-radius: 6px;
    background: rgba(188,140,255,0.15);
    color: var(--purple);
    border: 1px solid rgba(188,140,255,0.3);
    font-family: var(--font);
    font-size: 12px;
    cursor: pointer;
    transition: all 0.2s;
  }
  .copy-btn:hover { background: rgba(188,140,255,0.25); }
  .copy-btn.copied { color: var(--green); border-color: var(--green); background: rgba(63,185,80,0.15); }
  .code-block {
    padding: 24px;
    overflow-x: auto;
    font-size: 12.5px;
    line-height: 1.8;
    color: var(--text);
    white-space: pre;
    max-height: calc(100vh - 140px);
    overflow-y: auto;
  }
  .code-block .cm { color: var(--muted); }
  .code-block .kw { color: var(--red); }
  .code-block .str { color: var(--green); }
  .code-block .hl { color: var(--purple); }
  .code-block .lk { color: var(--blue); }

  /* SNAKE PANEL */
  .snake-panel {
    padding: 40px 24px;
    max-width: 700px;
    margin: 0 auto;
  }
  .snake-title {
    font-size: 18px;
    font-weight: 700;
    color: var(--purple);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .step-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px 20px;
    margin-bottom: 12px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }
  .step-num {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    background: rgba(188,140,255,0.15);
    border: 1px solid var(--purple);
    color: var(--purple);
    font-weight: 700;
    font-size: 13px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }
  .step-body { flex: 1; }
  .step-title { color: var(--text); font-weight: 600; margin-bottom: 6px; }
  .step-code {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 10px 14px;
    font-size: 11.5px;
    color: var(--green);
    overflow-x: auto;
    white-space: pre;
    margin-top: 8px;
  }
  .step-desc { color: var(--muted); font-size: 12px; line-height: 1.6; }
</style>
</head>
<body>

<!-- TAB BAR -->
<div class="tab-bar">
  <button class="tab active" onclick="switchTab('preview', this)">
    <span class="tab-dot dot-preview"></span> Live preview
  </button>
  <button class="tab" onclick="switchTab('code', this)">
    <span class="tab-dot dot-code"></span> README.md code
  </button>
  <button class="tab" onclick="switchTab('snake', this)">
    <span class="tab-dot dot-snake"></span> Snake action
  </button>
</div>

<!-- ============ PREVIEW PANEL ============ -->
<div id="tab-preview" class="tab-panel active">
<div class="preview">

  <!-- WAVE HEADER -->
  <div class="wave-header">
    <div class="wave-particles" id="particles"></div>
    <div class="wave-name">👋 Hi, I'm Ishaq Afkar</div>
    <div class="wave-sub">🟣 Purple Teamer · SOC Analyst · Cybersecurity Researcher</div>
  </div>

  <!-- TYPING -->
  <div class="typing-wrapper">
    <span class="typing-text" id="typing"></span>
  </div>

  <!-- BADGES -->
  <div class="badges-row">
    <span class="badge badge-purple">🟣 Purple Team</span>
    <span class="badge badge-blue">🔵 SOC Analyst</span>
    <span class="badge badge-red">🔴 Ethical Hacker</span>
    <span class="badge badge-green">🌍 Colombo, Sri Lanka</span>
    <span class="badge badge-orange">🎓 BTEC HND Cybersecurity</span>
    <span class="badge badge-blue">💼 Open to SOC Roles</span>
  </div>

  <!-- MAIN CONTENT -->
  <div class="content-box">

    <!-- ABOUT -->
    <div class="section-title">🧠 About Me <span class="section-line"></span></div>
    <div class="tree">
      <div class="tree-line"><span class="tree-connector">┌─ </span><span class="tree-highlight">Cybersecurity Analyst (Junior)</span><span class="tree-label"> · SOC Enthusiast · Purple Teamer</span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>📍 Rajagiriya, Colombo, Sri Lanka</span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>🎓 BTEC HND Digital Technology (Cybersecurity) — Nebula Institute</span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>🔍 Open to SOC Analyst / Security Operations roles</span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>📬 <a href="mailto:ishaqafkar123@gmail.com" class="tree-link">ishaqafkar123@gmail.com</a></span></div>
      <div class="tree-line"><span class="tree-connector">└─ </span><span>🔗 <a href="https://linkedin.com/in/afkarish" class="tree-link" target="_blank">linkedin.com/in/afkarish</a></span></div>
    </div>

    <!-- CERTS -->
    <div class="section-title">🛡️ Certifications <span class="section-line"></span></div>
    <div style="margin-bottom:6px"><span class="skill-category cat-blue">🔵 Blue Team</span></div>
    <div class="tools-grid" style="margin-bottom:12px">
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Cisco CyberOps Associate</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">TryHackMe SOC L1</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Splunk SIEM Champion</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Harvard CS50 Cyber</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Forage Datacom Sim</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Forage Deloitte Sim</span>
    </div>
    <div style="margin-bottom:6px"><span class="skill-category cat-red">🔴 Red Team</span></div>
    <div class="tools-grid" style="margin-bottom:12px">
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">Cisco Ethical Hacker</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">HackTheBox</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">ZTM Bug Bounty</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">ZTM AI Ethical Hacking</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">CodeRed Web Hacking</span>
    </div>
    <div style="margin-bottom:6px"><span class="skill-category cat-purple">🟣 Cloud & AI</span></div>
    <div class="tools-grid">
      <span class="tool-chip" style="color:var(--purple);border-color:rgba(188,140,255,0.35);background:rgba(188,140,255,0.08)">CCNA x3</span>
      <span class="tool-chip" style="color:var(--purple);border-color:rgba(188,140,255,0.35);background:rgba(188,140,255,0.08)">AWS GenAI Practitioner</span>
      <span class="tool-chip" style="color:var(--purple);border-color:rgba(188,140,255,0.35);background:rgba(188,140,255,0.08)">Google Cloud AI</span>
      <span class="tool-chip" style="color:var(--purple);border-color:rgba(188,140,255,0.35);background:rgba(188,140,255,0.08)">Anthropic Agent Skills</span>
      <span class="tool-chip" style="color:var(--purple);border-color:rgba(188,140,255,0.35);background:rgba(188,140,255,0.08)">Kaggle AI Agents</span>
    </div>

    <!-- TOOLS -->
    <div class="section-title">🔧 Security Tools <span class="section-line"></span></div>
    <div class="tools-grid">
      <span class="tool-chip" style="color:var(--orange);border-color:rgba(255,166,87,0.35);background:rgba(255,166,87,0.08)">Splunk</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Wireshark</span>
      <span class="tool-chip" style="color:var(--text);border-color:var(--border);background:var(--surface2)">Nmap</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">Burp Suite</span>
      <span class="tool-chip" style="color:var(--cyan);border-color:rgba(57,211,83,0.35);background:rgba(57,211,83,0.08)">Kali Linux</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Maltego</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">Metasploit</span>
      <span class="tool-chip" style="color:var(--green);border-color:rgba(63,185,80,0.35);background:rgba(63,185,80,0.08)">Active Directory</span>
    </div>

    <!-- DEV STACK -->
    <div class="section-title">💻 Dev Stack <span class="section-line"></span></div>
    <div class="tools-grid">
      <span class="tool-chip" style="color:#61dafb;border-color:rgba(97,218,251,0.35);background:rgba(97,218,251,0.08)">React</span>
      <span class="tool-chip" style="color:var(--green);border-color:rgba(63,185,80,0.35);background:rgba(63,185,80,0.08)">Node.js</span>
      <span class="tool-chip" style="color:var(--red);border-color:rgba(226,75,74,0.35);background:rgba(226,75,74,0.08)">Laravel</span>
      <span class="tool-chip" style="color:var(--blue);border-color:rgba(27,160,215,0.35);background:rgba(27,160,215,0.08)">Python</span>
      <span class="tool-chip" style="color:var(--green);border-color:rgba(63,185,80,0.35);background:rgba(63,185,80,0.08)">Bash</span>
      <span class="tool-chip" style="color:var(--yellow);border-color:rgba(227,179,65,0.35);background:rgba(227,179,65,0.08)">JavaScript</span>
    </div>

    <!-- SKILL PROGRESS -->
    <div class="section-title">🎯 Skill Levels <span class="section-line"></span></div>

    <div class="skill-category cat-blue">🔵 Blue Team / Defensive</div>
    <div id="skills-blue" style="margin-top:10px"></div>

    <div class="skill-category cat-red" style="margin-top:6px">🔴 Red Team / Offensive</div>
    <div id="skills-red" style="margin-top:10px"></div>

    <div class="skill-category cat-purple" style="margin-top:6px">🟣 Scripting & Dev</div>
    <div id="skills-purple" style="margin-top:10px"></div>

    <!-- PROJECTS -->
    <div class="section-title">📂 Key Projects <span class="section-line"></span></div>

    <div class="project-item">
      <div class="project-icon">🔍</div>
      <div class="project-body">
        <div class="project-title">Splunk SIEM Challenge — Haxcamp</div>
        <div class="project-desc">SPL queries · multi-stage attack tracing · JSON log parsing · brute force → backdoor timeline</div>
        <div class="project-tags">
          <span class="project-tag">Splunk</span><span class="project-tag">SPL</span><span class="project-tag">SIEM</span><span class="project-tag">Log Analysis</span>
        </div>
      </div>
    </div>
    <div class="project-item">
      <div class="project-icon">🛡️</div>
      <div class="project-body">
        <div class="project-title">Datacom Cyber Sim — Forage</div>
        <div class="project-desc">GRC risk report · security posture improvement · compliance-focused incident documentation</div>
        <div class="project-tags">
          <span class="project-tag">GRC</span><span class="project-tag">Risk Assessment</span><span class="project-tag">Compliance</span>
        </div>
      </div>
    </div>
    <div class="project-item">
      <div class="project-icon">🕵️</div>
      <div class="project-body">
        <div class="project-title">Deloitte Cyber Sim — Forage</div>
        <div class="project-desc">Breach investigation · threat modelling · client-ready GRC risk report</div>
        <div class="project-tags">
          <span class="project-tag">Threat Modelling</span><span class="project-tag">GRC</span><span class="project-tag">Advisory</span>
        </div>
      </div>
    </div>
    <div class="project-item">
      <div class="project-icon">💻</div>
      <div class="project-body">
        <div class="project-title">HackTheBox — Starting Point Track</div>
        <div class="project-desc">Enumeration → privilege escalation → post-exploitation on real machines</div>
        <div class="project-tags">
          <span class="project-tag">Nmap</span><span class="project-tag">Metasploit</span><span class="project-tag">Linux</span><span class="project-tag">Privesc</span>
        </div>
      </div>
    </div>
    <div class="project-item">
      <div class="project-icon">🌐</div>
      <div class="project-body">
        <div class="project-title">Eco Travels — Victrix</div>
        <div class="project-desc">React · Node.js · Laravel · SSL/TLS · DNS config · Secure Auth Flows</div>
        <div class="project-tags">
          <span class="project-tag">React</span><span class="project-tag">Node.js</span><span class="project-tag">Laravel</span><span class="project-tag">SSL/TLS</span>
        </div>
      </div>
    </div>

    <!-- EXPERIENCE -->
    <div class="section-title">💼 Experience <span class="section-line"></span></div>
    <div class="tree" style="font-size:13px">
      <div class="tree-line">
        <span class="tree-connector">├─ </span>
        <span><span style="color:var(--cyan);font-weight:600">Victrix</span> · Graphic Designer & Web Developer · <span style="color:var(--muted)">Oct 2025 – Apr 2026</span></span>
      </div>
      <div class="tree-line">
        <span class="tree-connector">│  </span>
        <span style="color:var(--muted);font-size:12px">React · Node.js · Laravel · SSL/TLS · DNS · Secure Auth Flows</span>
      </div>
      <div class="tree-line">
        <span class="tree-connector">└─ </span>
        <span><span style="color:var(--cyan);font-weight:600">SLIDA</span> · Graphic Design Trainee · <span style="color:var(--muted)">Apr 2025 – Oct 2025</span></span>
      </div>
    </div>

    <!-- EDUCATION -->
    <div class="section-title">🎓 Education <span class="section-line"></span></div>
    <div class="tree" style="font-size:12.5px">
      <div class="tree-line"><span class="tree-connector">├─ </span><span>BTEC HND Digital Technology (Cybersecurity) — Nebula Institute · <span style="color:var(--muted)">2025–Present</span></span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>NVQ Level 4 Computer Graphic Design — NAITA · <span style="color:var(--muted)">2024–2026</span></span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>CAIT — Nebula Institute of Technology · <span style="color:var(--muted)">2022</span></span></div>
      <div class="tree-line"><span class="tree-connector">├─ </span><span>Windows Network Administration — Turnkey IT Campus · <span style="color:var(--muted)">2022</span></span></div>
      <div class="tree-line"><span class="tree-connector">└─ </span><span>G.C.E. Ordinary Level — Royal College, Colombo · <span style="color:var(--muted)">2019</span></span></div>
    </div>

    <!-- QUOTE -->
    <div class="quote-block" style="margin-top:28px">
      <p>"Security is not a product, but a process."</p>
      <cite>— Bruce Schneier</cite>
    </div>

    <!-- STATS NOTE -->
    <div style="margin-top:24px;padding:12px 16px;background:var(--surface2);border:1px solid var(--border);border-radius:6px;font-size:12px;color:var(--muted)">
      📊 GitHub stats · streak · trophies · snake animation → see <span style="color:var(--blue)">README.md tab ↑</span>
    </div>

  </div><!-- end content-box -->

  <!-- FOOTER WAVE -->
  <div class="wave-footer">
    <span class="footer-quote">🟣 "Attack to understand. Defend to protect."</span>
  </div>

</div>
</div>

<!-- ============ CODE PANEL ============ -->
<div id="tab-code" class="tab-panel">
<div class="code-panel">
<div class="code-toolbar">
  <span class="code-lang">README.md — GitHub Markdown</span>
  <button class="copy-btn" id="copyBtn" onclick="copyCode()">📋 Copy all</button>
</div>
<pre class="code-block" id="codeBlock"><span class="cm">&lt;!-- WAVE HEADER --&gt;</span>
<span class="hl">&lt;div align="center"&gt;</span>

<span class="lk">&lt;img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=180&section=header&text=Ishaq%20Afkar&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=32&desc=Cybersecurity%20Analyst%20%7C%20Purple%20Teamer&descAlignY=52&descSize=18" width="100%"/&gt;</span>

<span class="cm">&lt;!-- TYPING ANIMATION --&gt;</span>
<span class="lk">&lt;img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=800&color=A855F7&center=true&vCenter=true&width=700&height=50&lines=🛡️+SOC+Analyst+%7C+Threat+Hunter;🔴+Ethical+Hacking+%7C+Pentesting;🔵+SIEM+%7C+Splunk+%7C+Log+Analysis;🟣+Purple+Teamer+—+Attack+%26+Defend;💻+HackTheBox+%7C+TryHackMe+SOC+L1" alt="Typing SVG"/&gt;</span>

<span class="lk">&lt;img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&style=for-the-badge&color=7c3aed&label=PROFILE+VIEWS"/&gt;</span>

<span class="hl">&lt;/div&gt;</span>

---

<span class="cm">## 🧠 About Me</span>

```python
class PurpleTeamer:
    name       = "Ishaq Afkar"
    role       = "Cybersecurity Analyst (Junior)"
    location   = "Colombo, Sri Lanka 🇱🇰"
    team       = "🟣 Purple Team — I attack to understand how to defend"
    blue_team  = ["SIEM", "Splunk", "Log Analysis", "Incident Response", "GRC"]
    red_team   = ["Nmap", "Burp Suite", "Metasploit", "Ethical Hacking", "Web Security"]
    scripting  = ["Python", "Bash", "JavaScript", "React", "Node.js"]
    currently  = "HND Cybersecurity @ Nebula Institute"
    goal       = "Join a SOC team in monitoring & incident response"
```

---

<span class="cm">## 🛡️ Certifications</span>

<span class="cm">**🔵 Blue Team**</span>
<span class="hl">![CyberOps](https://img.shields.io/badge/Cisco-CyberOps%20Associate-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white)</span>
<span class="hl">![THM SOC](https://img.shields.io/badge/TryHackMe-SOC%20Level%201-1BA0D7?style=for-the-badge&logo=tryhackme&logoColor=white)</span>
<span class="hl">![Splunk](https://img.shields.io/badge/Haxcamp-Splunk%20SIEM%20Champion-1BA0D7?style=for-the-badge)</span>
<span class="hl">![CS50](https://img.shields.io/badge/Harvard-CS50%20Cybersecurity-1BA0D7?style=for-the-badge)</span>
<span class="hl">![Datacom](https://img.shields.io/badge/Forage-Datacom%20Cyber%20Sim-1BA0D7?style=for-the-badge)</span>
<span class="hl">![Deloitte](https://img.shields.io/badge/Forage-Deloitte%20Cyber%20Sim-1BA0D7?style=for-the-badge)</span>

<span class="cm">**🔴 Red Team**</span>
<span class="hl">![Ethical Hacker](https://img.shields.io/badge/Cisco-Ethical%20Hacker-E24B4A?style=for-the-badge&logo=cisco&logoColor=white)</span>
<span class="hl">![HTB](https://img.shields.io/badge/HackTheBox-Starting%20Point-E24B4A?style=for-the-badge&logo=hackthebox&logoColor=white)</span>
<span class="hl">![ZTM Bug Bounty](https://img.shields.io/badge/ZTM-Bug%20Bounty%20%26%20Pentest-E24B4A?style=for-the-badge)</span>
<span class="hl">![ZTM AI](https://img.shields.io/badge/ZTM-AI%20for%20Ethical%20Hacking-E24B4A?style=for-the-badge)</span>
<span class="hl">![CodeRed](https://img.shields.io/badge/CodeRed-Web%20Hacking%20%26%20Pentest-E24B4A?style=for-the-badge)</span>

<span class="cm">**🟣 Cloud, Network & AI**</span>
<span class="hl">![CCNA](https://img.shields.io/badge/Cisco-CCNA%20Trilogy-bc8cff?style=for-the-badge&logo=cisco&logoColor=white)</span>
<span class="hl">![AWS](https://img.shields.io/badge/AWS-Cloud%20Quest%20GenAI-bc8cff?style=for-the-badge&logo=amazon-aws&logoColor=white)</span>
<span class="hl">![GCP](https://img.shields.io/badge/Google%20Cloud-Skill%20Badges-bc8cff?style=for-the-badge&logo=google-cloud&logoColor=white)</span>
<span class="hl">![Anthropic](https://img.shields.io/badge/Anthropic-Agent%20Skills-bc8cff?style=for-the-badge)</span>
<span class="hl">![Kaggle](https://img.shields.io/badge/Kaggle-AI%20Agents%20Intensive-bc8cff?style=for-the-badge&logo=kaggle&logoColor=white)</span>

---

<span class="cm">## 🔧 Security Tools</span>

<span class="hl">![Splunk](https://img.shields.io/badge/Splunk-000000?style=for-the-badge&logo=splunk&logoColor=white)</span>
<span class="hl">![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)</span>
<span class="hl">![Kali](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kali-linux&logoColor=white)</span>
<span class="hl">![Burp](https://img.shields.io/badge/Burp_Suite-FF6633?style=for-the-badge)</span>
<span class="hl">![Metasploit](https://img.shields.io/badge/Metasploit-2A2A2A?style=for-the-badge)</span>
<span class="hl">![Nmap](https://img.shields.io/badge/Nmap-214478?style=for-the-badge)</span>

---

<span class="cm">## 🎯 Skill Levels</span>

<span class="cm">&gt; **🔵 Blue Team**</span>

<span class="hl">![SIEM](https://img.shields.io/badge/SIEM%20%26%20Splunk-88%25-1BA0D7?style=flat-square&labelColor=0d1117)</span>
`████████████████████░░` 88%

<span class="hl">![Log Analysis](https://img.shields.io/badge/Log%20Analysis-85%25-1BA0D7?style=flat-square&labelColor=0d1117)</span>
`███████████████████░░░` 85%

<span class="hl">![IR](https://img.shields.io/badge/Incident%20Response-75%25-1BA0D7?style=flat-square&labelColor=0d1117)</span>
`█████████████████░░░░░` 75%

<span class="hl">![GRC](https://img.shields.io/badge/GRC%20%26%20Compliance-78%25-1BA0D7?style=flat-square&labelColor=0d1117)</span>
`█████████████████░░░░░` 78%

<span class="cm">&gt; **🔴 Red Team**</span>

<span class="hl">![Nmap Recon](https://img.shields.io/badge/Nmap%20%26%20Recon-80%25-E24B4A?style=flat-square&labelColor=0d1117)</span>
`██████████████████░░░░` 80%

<span class="hl">![Burp](https://img.shields.io/badge/Burp%20Suite-72%25-E24B4A?style=flat-square&labelColor=0d1117)</span>
`████████████████░░░░░░` 72%

<span class="hl">![Web Hacking](https://img.shields.io/badge/Web%20Hacking-72%25-E24B4A?style=flat-square&labelColor=0d1117)</span>
`████████████████░░░░░░` 72%

<span class="hl">![MSF](https://img.shields.io/badge/Metasploit-65%25-E24B4A?style=flat-square&labelColor=0d1117)</span>
`██████████████░░░░░░░░` 65%

<span class="cm">&gt; **🟣 Scripting & Dev**</span>

<span class="hl">![Python](https://img.shields.io/badge/Python-75%25-bc8cff?style=flat-square&labelColor=0d1117)</span>
`█████████████████░░░░░` 75%

<span class="hl">![Bash](https://img.shields.io/badge/Bash%20Scripting-70%25-bc8cff?style=flat-square&labelColor=0d1117)</span>
`████████████████░░░░░░` 70%

<span class="hl">![React Node](https://img.shields.io/badge/React%20%2F%20Node.js-75%25-bc8cff?style=flat-square&labelColor=0d1117)</span>
`█████████████████░░░░░` 75%

---

<span class="cm">## 📂 Key Projects</span>

| Project | Description | Tags |
|---|---|---|
| 🔍 Splunk SIEM Lab | SPL queries · attack timelines · JSON parsing | Splunk · SPL |
| 🛡️ Datacom GRC Sim | Risk report · posture improvement | GRC · Risk |
| 🕵️ Deloitte Cyber Sim | Breach investigation · threat modelling | Advisory |
| 💻 HackTheBox Starting Point | Enum → Privesc → Post-exploitation | Nmap · MSF |
| 🌐 Eco Travels (Victrix) | React · Node.js · Laravel · SSL/TLS | Web Dev |

---

<span class="cm">## 💼 Experience</span>

```
├─ Victrix · Graphic Designer & Web Developer · Oct 2025 – Apr 2026
│  React · Node.js · Laravel · SSL/TLS · DNS · Secure Auth Flows
└─ SLIDA · Graphic Design Trainee · Apr 2025 – Oct 2025
```

---

<span class="cm">## 🎓 Education</span>

```
├─ BTEC HND Digital Technology (Cybersecurity) — Nebula Institute · 2025–Present
├─ NVQ Level 4 Computer Graphic Design — NAITA · 2024–2026
├─ CAIT — Nebula Institute of Technology · 2022
├─ Windows Network Administration — Turnkey IT Campus · 2022
└─ G.C.E. Ordinary Level — Royal College, Colombo · 2019
```

---

<span class="cm">## 📈 GitHub Stats</span>

<span class="hl">&lt;div align="center"&gt;</span>

<span class="lk">&lt;img src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight&title_color=bc8cff&icon_color=E24B4A&text_color=c9d1d9&bg_color=0d1117&border_color=30363d" height="170"/&gt;</span>
<span class="lk">&lt;img src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=tokyonight&title_color=bc8cff&text_color=c9d1d9&bg_color=0d1117&border_color=30363d" height="170"/&gt;</span>

<span class="lk">&lt;img src="https://streak-stats.demolab.com?user=YOUR_USERNAME&theme=tokyonight&ring=bc8cff&fire=E24B4A&currStreakLabel=1BA0D7&border=30363d&background=0D1117" height="170"/&gt;</span>

<span class="hl">&lt;/div&gt;</span>

---

<span class="cm">&gt; "Security is not a product, but a process." — Bruce Schneier</span>

<span class="hl">&lt;div align="center"&gt;</span>
<span class="lk">&lt;img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer&animation=twinkling" width="100%"/&gt;</span>
<span class="cm">&lt;em&gt;🟣 "Attack to understand. Defend to protect."&lt;/em&gt;</span>
<span class="hl">&lt;/div&gt;</span></pre>
</div>
</div>

<!-- ============ SNAKE PANEL ============ -->
<div id="tab-snake" class="tab-panel">
<div class="snake-panel">
  <div class="snake-title">🐍 Snake Animation Setup</div>

  <div class="step-card">
    <div class="step-num">1</div>
    <div class="step-body">
      <div class="step-title">Create the workflow folder</div>
      <div class="step-desc">In your username repo, create this exact folder path:</div>
      <div class="step-code">.github/workflows/snake.yml</div>
    </div>
  </div>

  <div class="step-card">
    <div class="step-num">2</div>
    <div class="step-body">
      <div class="step-title">Paste this into snake.yml</div>
      <div class="step-code">name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}</div>
    </div>
  </div>

  <div class="step-card">
    <div class="step-num">3</div>
    <div class="step-body">
      <div class="step-title">Run it manually once</div>
      <div class="step-desc">Go to your repo → Actions tab → "Generate Snake Animation" → Run workflow. Wait ~30 seconds.</div>
    </div>
  </div>

  <div class="step-card">
    <div class="step-num">4</div>
    <div class="step-body">
      <div class="step-title">Add to your README.md</div>
      <div class="step-code">&lt;picture&gt;
  &lt;source media="(prefers-color-scheme: dark)"
    srcset="https://raw.githubusercontent.com/YOUR_USERNAME/YOUR_USERNAME/output/github-contribution-grid-snake-dark.svg"&gt;
  &lt;img alt="Snake animation"
    src="https://raw.githubusercontent.com/YOUR_USERNAME/YOUR_USERNAME/output/github-contribution-grid-snake.svg"&gt;
&lt;/picture&gt;</div>
      <div class="step-desc" style="margin-top:8px">Replace <span style="color:var(--purple)">YOUR_USERNAME</span> with your actual GitHub username (in 4 places).</div>
    </div>
  </div>

  <div style="margin-top:24px;padding:14px 18px;background:rgba(57,211,83,0.08);border:1px solid rgba(57,211,83,0.2);border-radius:8px;font-size:12px;color:var(--green)">
    ✅ After setup: the snake runs every 12 hours automatically and updates your contribution graph animation.
  </div>
</div>
</div>

<script>
// TAB SWITCHING
function switchTab(name, btn) {
  document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById('tab-' + name).classList.add('active');
  btn.classList.add('active');
}

// PARTICLES
(function(){
  const c = document.getElementById('particles');
  for(let i = 0; i < 20; i++){
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.left = Math.random()*100+'%';
    p.style.top = (30+Math.random()*70)+'%';
    p.style.animationDelay = (Math.random()*4)+'s';
    p.style.animationDuration = (3+Math.random()*3)+'s';
    const colors = ['#bc8cff','#1BA0D7','#E24B4A','#3fb950'];
    p.style.background = colors[Math.floor(Math.random()*colors.length)];
    c.appendChild(p);
  }
})();

// TYPING ANIMATION
(function(){
  const lines = [
    '🛡️ SOC Analyst | Threat Hunter',
    '🔴 Ethical Hacking | Pentesting',
    '🔵 SIEM | Splunk | Log Analysis',
    '🟣 Purple Teamer — Attack & Defend',
    '💻 HackTheBox | TryHackMe SOC L1',
    '🎓 Cisco CyberOps | Ethical Hacker',
    '🌐 Colombo, Sri Lanka 🇱🇰'
  ];
  const el = document.getElementById('typing');
  let li = 0, ci = 0, del = false;
  function tick(){
    const txt = lines[li];
    if(!del){
      el.textContent = txt.slice(0, ++ci);
      if(ci >= txt.length){ del=true; setTimeout(tick,2200); return; }
    } else {
      el.textContent = txt.slice(0, --ci);
      if(ci === 0){ del=false; li=(li+1)%lines.length; setTimeout(tick,400); return; }
    }
    setTimeout(tick, del ? 35 : 60);
  }
  tick();
})();

// SKILL BARS
const skills = {
  blue: [
    {name:'SIEM / Splunk / SPL', pct:88},
    {name:'Threat Detection & Log Analysis', pct:85},
    {name:'Incident Response', pct:75},
    {name:'GRC / Risk Assessment', pct:78},
  ],
  red: [
    {name:'Nmap / Wireshark / Recon', pct:80},
    {name:'Ethical Hacking / Burp / MSF', pct:72},
    {name:'Web Hacking / Bug Bounty', pct:72},
    {name:'OSINT / Maltego', pct:68},
  ],
  purple: [
    {name:'Python / Bash Scripting', pct:75},
    {name:'JavaScript', pct:65},
    {name:'React / Node.js / Laravel', pct:75},
  ]
};
const barColors = { blue:'bar-blue', red:'bar-red', purple:'bar-purple' };

function buildBars(team){
  const container = document.getElementById('skills-'+team);
  skills[team].forEach(s => {
    const row = document.createElement('div');
    row.className = 'skill-row';
    row.innerHTML = `
      <div class="skill-name">${s.name}</div>
      <div class="skill-bar-bg">
        <div class="skill-bar-fill ${barColors[team]}" data-pct="${s.pct}"></div>
      </div>
      <div class="skill-pct">${s.pct}%</div>`;
    container.appendChild(row);
  });
}
['blue','red','purple'].forEach(buildBars);

// ANIMATE BARS ON SCROLL
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if(entry.isIntersecting){
      document.querySelectorAll('.skill-bar-fill').forEach(bar => {
        bar.style.width = bar.dataset.pct + '%';
      });
    }
  });
}, {threshold: 0.1});
setTimeout(()=>{
  const barsSection = document.getElementById('skills-blue');
  if(barsSection) observer.observe(barsSection);
  // Also trigger after 600ms for immediate view
  setTimeout(()=>{
    document.querySelectorAll('.skill-bar-fill').forEach(bar => {
      bar.style.width = bar.dataset.pct + '%';
    });
  }, 600);
},100);

// COPY CODE
function copyCode(){
  const code = document.getElementById('codeBlock').innerText;
  navigator.clipboard.writeText(code).then(()=>{
    const btn = document.getElementById('copyBtn');
    btn.textContent = '✅ Copied!';
    btn.classList.add('copied');
    setTimeout(()=>{ btn.textContent='📋 Copy all'; btn.classList.remove('copied'); }, 2500);
  });
}
</script>
</body>
</html>
