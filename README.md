<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Ansa Mubasher</title>
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,600;1,400&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg:        #fdf6f0;
  --bg2:       #fef9f5;
  --rose:      #f2a8b8;
  --rose-deep: #e07d95;
  --lavender:  #c9b8e8;
  --lav-deep:  #9b82d4;
  --mint:      #a8d8c8;
  --mint-deep: #6bbaa4;
  --peach:     #f5c5a3;
  --sky:       #b3d4f0;
  --sand:      #e8d9c8;
  --text:      #3a2e2e;
  --muted:     #8a7a7a;
  --border:    #e8ddd8;
  --card:      #fffaf8;
  --mono:      'DM Mono', monospace;
  --serif:     'Lora', serif;
  --sans:      'DM Sans', sans-serif;
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: var(--sans);
  font-size: 14px;
  line-height: 1.65;
  min-height: 100vh;
}

/* subtle paper texture overlay */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='400' height='400' filter='url(%23n)' opacity='0.025'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 0;
}

.wrapper {
  max-width: 880px;
  margin: 0 auto;
  padding: 48px 24px 64px;
  position: relative;
  z-index: 1;
}

/* ─── HEADER ─── */
.header {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 28px;
  align-items: center;
  margin-bottom: 52px;
  padding-bottom: 40px;
  border-bottom: 1.5px dashed var(--border);
}

@media (max-width: 520px) { .header { grid-template-columns: 1fr; } }

.avatar {
  width: 88px; height: 88px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--rose) 0%, var(--lavender) 50%, var(--mint) 100%);
  display: flex; align-items: center; justify-content: center;
  font-family: var(--serif);
  font-size: 26px;
  font-weight: 600;
  color: #fff;
  box-shadow: 0 4px 24px rgba(194,140,160,0.25);
  flex-shrink: 0;
  position: relative;
}

.avatar::after {
  content: '';
  position: absolute;
  inset: -3px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--rose), var(--lavender), var(--mint));
  z-index: -1;
  opacity: 0.4;
  filter: blur(6px);
}

.header-text h1 {
  font-family: var(--serif);
  font-size: 28px;
  font-weight: 600;
  color: var(--text);
  letter-spacing: -0.3px;
  line-height: 1.2;
}

.header-text h1 em {
  font-style: italic;
  color: var(--rose-deep);
}

.role-chip {
  display: inline-block;
  margin-top: 8px;
  font-family: var(--mono);
  font-size: 11px;
  font-weight: 500;
  color: var(--lav-deep);
  background: #f0ebfc;
  border: 1px solid var(--lavender);
  border-radius: 100px;
  padding: 3px 12px;
  letter-spacing: 0.02em;
}

.tagline {
  margin-top: 10px;
  color: var(--muted);
  font-size: 13.5px;
  font-weight: 300;
  max-width: 500px;
}

/* ─── SECTION LABEL ─── */
.section { margin-bottom: 48px; }

.section-label {
  font-family: var(--serif);
  font-size: 18px;
  font-weight: 600;
  font-style: italic;
  color: var(--text);
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.section-label .dot {
  display: inline-block;
  width: 8px; height: 8px;
  border-radius: 50%;
  flex-shrink: 0;
}

/* ─── TECH STACK ─── */
.stack-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
  gap: 10px;
}

.stack-card {
  background: var(--card);
  border: 1.5px solid var(--border);
  border-radius: 14px;
  padding: 14px 16px 16px;
  position: relative;
  overflow: hidden;
}

.stack-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  border-radius: 14px 14px 0 0;
}

.stack-card.c1::before { background: var(--rose); }
.stack-card.c2::before { background: var(--peach); }
.stack-card.c3::before { background: var(--lavender); }
.stack-card.c4::before { background: var(--mint); }
.stack-card.c5::before { background: var(--sky); }
.stack-card.c6::before { background: var(--sand); }

.stack-card .cat {
  font-family: var(--mono);
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 8px;
}

.stack-card.c1 .cat { color: var(--rose-deep); }
.stack-card.c2 .cat { color: #c07840; }
.stack-card.c3 .cat { color: var(--lav-deep); }
.stack-card.c4 .cat { color: var(--mint-deep); }
.stack-card.c5 .cat { color: #4d8fcc; }
.stack-card.c6 .cat { color: #9a8060; }

.stack-card .items {
  color: var(--text);
  font-size: 12.5px;
  line-height: 1.85;
}

/* ─── PROJECTS ─── */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

@media (max-width: 560px) { .projects-grid { grid-template-columns: 1fr; } }

.proj {
  background: var(--card);
  border: 1.5px solid var(--border);
  border-radius: 16px;
  padding: 20px;
  transition: transform 0.18s, box-shadow 0.18s;
  cursor: default;
}

.proj:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 28px rgba(180,140,160,0.18);
}

.proj-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 10px;
}

.proj-icon {
  width: 36px; height: 36px;
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 18px;
  flex-shrink: 0;
}

.proj.p1 .proj-icon { background: #fde8ed; }
.proj.p2 .proj-icon { background: #eee8fb; }
.proj.p3 .proj-icon { background: #e6f5f0; }
.proj.p4 .proj-icon { background: #fdf0e6; }
.proj.p5 .proj-icon { background: #e8f2fb; }

.proj h3 {
  font-family: var(--sans);
  font-size: 13.5px;
  font-weight: 600;
  color: var(--text);
  line-height: 1.3;
}

.proj p {
  font-size: 12.5px;
  color: var(--muted);
  line-height: 1.65;
  font-weight: 300;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
  margin-top: 12px;
}

.tag {
  font-family: var(--mono);
  font-size: 10px;
  font-weight: 500;
  padding: 3px 9px;
  border-radius: 100px;
  border: 1px solid;
}

.proj.p1 .tag { background: #fde8ed; color: var(--rose-deep); border-color: var(--rose); }
.proj.p2 .tag { background: #eee8fb; color: var(--lav-deep); border-color: var(--lavender); }
.proj.p3 .tag { background: #e6f5f0; color: var(--mint-deep); border-color: var(--mint); }
.proj.p4 .tag { background: #fdf0e6; color: #c07840; border-color: var(--peach); }
.proj.p5 .tag { background: #e8f2fb; color: #4d8fcc; border-color: var(--sky); }

/* ─── LEADERSHIP ─── */
.leadership-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 10px;
}

.lead-item {
  background: var(--card);
  border: 1.5px solid var(--border);
  border-radius: 12px;
  padding: 13px 16px;
  font-size: 13px;
  color: var(--text);
  display: flex;
  align-items: center;
  gap: 10px;
}

.lead-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  flex-shrink: 0;
}

/* ─── SNAKE SECTION ─── */
.snake-section {
  margin-bottom: 48px;
}

.snake-wrap {
  background: var(--card);
  border: 1.5px solid var(--border);
  border-radius: 16px;
  padding: 24px 20px 16px;
  overflow: hidden;
}

canvas#snake {
  display: block;
  width: 100%;
  height: auto;
  border-radius: 8px;
}

.snake-legend {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-top: 14px;
  align-items: center;
}

.snake-legend span {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 5px;
}

.swatch {
  width: 10px; height: 10px;
  border-radius: 2px;
  display: inline-block;
}

/* ─── CONNECT ─── */
.connect-row {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.pill {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  background: var(--card);
  border: 1.5px solid var(--border);
  border-radius: 100px;
  padding: 9px 18px;
  font-size: 13px;
  color: var(--text);
  text-decoration: none;
  font-family: var(--sans);
  font-weight: 500;
  transition: background 0.18s, border-color 0.18s, transform 0.15s;
}

.pill:hover {
  background: #fde8ed;
  border-color: var(--rose);
  transform: translateY(-1px);
}

/* ─── FOOTER ─── */
.footer {
  margin-top: 48px;
  padding-top: 24px;
  border-top: 1.5px dashed var(--border);
  text-align: center;
  font-family: var(--serif);
  font-style: italic;
  font-size: 13.5px;
  color: var(--muted);
}
</style>
</head>
<body>
<div class="wrapper">

  <!-- HEADER -->
  <header class="header">
    <div class="avatar">AM</div>
    <div class="header-text">
      <h1>Hi, I'm <em>Ansa Mubasher</em> 👋</h1>
      <div class="role-chip">CS Undergraduate @ FAST NUCES Lahore</div>
      <p class="tagline">Building full-stack applications, AI-powered products, and automation systems that solve real-world problems.</p>
    </div>
  </header>

  <!-- TECH STACK -->
  <section class="section">
    <div class="section-label">
      <span class="dot" style="background:var(--lavender)"></span>
      Tech Stack
    </div>
    <div class="stack-grid">
      <div class="stack-card c1">
        <div class="cat">Languages</div>
        <div class="items">Python · JavaScript · Java · C++ · SQL</div>
      </div>
      <div class="stack-card c2">
        <div class="cat">Backend & APIs</div>
        <div class="items">Node.js · Express.js · FastAPI · Flask · REST APIs · JWT</div>
      </div>
      <div class="stack-card c3">
        <div class="cat">Frontend</div>
        <div class="items">React · Next.js · HTML · CSS</div>
      </div>
      <div class="stack-card c4">
        <div class="cat">Databases</div>
        <div class="items">MongoDB · ChromaDB</div>
      </div>
      <div class="stack-card c5">
        <div class="cat">AI / ML</div>
        <div class="items">LangChain · Hugging Face · PyTorch · Scikit-Learn · Pandas · NumPy</div>
      </div>
      <div class="stack-card c6">
        <div class="cat">Tools</div>
        <div class="items">Git · GitHub · Postman · n8n</div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section">
    <div class="section-label">
      <span class="dot" style="background:var(--rose)"></span>
      Featured Projects
    </div>
    <div class="projects-grid">

      <div class="proj p1">
        <div class="proj-header">
          <div class="proj-icon">🤖</div>
          <h3>AI Emotional Assistant</h3>
        </div>
        <p>Full-stack emotional support platform combining stress prediction, empathetic dialogue, and personalized guidance.</p>
        <div class="tags">
          <span class="tag">MERN</span>
          <span class="tag">Flask</span>
          <span class="tag">BlenderBot</span>
          <span class="tag">FLAN-T5</span>
        </div>
      </div>

      <div class="proj p2">
        <div class="proj-header">
          <div class="proj-icon">🎯</div>
          <h3>AI Career Assistant</h3>
        </div>
        <p>Career platform with semantic resume-job matching, AI resume rewriting, ATS scoring, and cover letter generation.</p>
        <div class="tags">
          <span class="tag">FastAPI</span>
          <span class="tag">Node.js</span>
          <span class="tag">Sentence Transformers</span>
          <span class="tag">Mistral</span>
        </div>
      </div>

      <div class="proj p3">
        <div class="proj-header">
          <div class="proj-icon">📚</div>
          <h3>Research Assistant (RAG)</h3>
        </div>
        <p>Retrieval-Augmented Generation assistant for context-aware Q&amp;A using open-source LLMs and vector search.</p>
        <div class="tags">
          <span class="tag">LangChain</span>
          <span class="tag">ChromaDB</span>
          <span class="tag">Sentence Transformers</span>
        </div>
      </div>

      <div class="proj p4">
        <div class="proj-header">
          <div class="proj-icon">💼</div>
          <h3>FAST Freelancing Platform</h3>
        </div>
        <p>MERN-based marketplace with authentication, protected APIs, bid management, and responsive user workflows.</p>
        <div class="tags">
          <span class="tag">MongoDB</span>
          <span class="tag">Express</span>
          <span class="tag">React</span>
          <span class="tag">Node.js</span>
        </div>
      </div>

      <div class="proj p5">
        <div class="proj-header">
          <div class="proj-icon">⚡</div>
          <h3>Work Automation Agent</h3>
        </div>
        <p>Automation workflows integrating Gmail and Google Calendar through n8n to streamline repetitive tasks.</p>
        <div class="tags">
          <span class="tag">n8n</span>
          <span class="tag">Gmail API</span>
          <span class="tag">Google Calendar</span>
        </div>
      </div>

    </div>
  </section>

  <!-- CONTRIBUTION SNAKE -->
  <section class="section snake-section">
    <div class="section-label">
      <span class="dot" style="background:var(--mint)"></span>
      Contribution Activity
    </div>
    <div class="snake-wrap">
      <canvas id="snake" width="840" height="128"></canvas>
      <div class="snake-legend">
        <span><span class="swatch" style="background:#f0e8e8"></span> No contributions</span>
        <span><span class="swatch" style="background:#f2c4cc"></span> Low</span>
        <span><span class="swatch" style="background:#e8a0b0"></span> Medium</span>
        <span><span class="swatch" style="background:#d4607c"></span> High</span>
        <span style="margin-left:auto;font-size:9px;letter-spacing:0.04em">CONTRIBUTIONS · LAST 52 WEEKS</span>
      </div>
    </div>
  </section>

  <!-- LEADERSHIP -->
  <section class="section">
    <div class="section-label">
      <span class="dot" style="background:var(--peach)"></span>
      Leadership &amp; Activities
    </div>
    <div class="leadership-grid">
      <div class="lead-item"><span class="lead-dot" style="background:var(--rose)"></span> ACM Assistant Vice President</div>
      <div class="lead-item"><span class="lead-dot" style="background:var(--lavender)"></span> SOFTEC Competition Head</div>
      <div class="lead-item"><span class="lead-dot" style="background:var(--mint)"></span> FAST Dean's List Honoree</div>
      <div class="lead-item"><span class="lead-dot" style="background:var(--peach)"></span> Technical Event Organizer</div>
    </div>
  </section>

  <!-- CONNECT -->
  <section class="section">
    <div class="section-label">
      <span class="dot" style="background:var(--sky)"></span>
      Let's Connect
    </div>
    <div class="connect-row">
      <a class="pill" href="mailto:ansamubasher@gmail.com">📧 ansamubasher@gmail.com</a>
      <a class="pill" href="#">💼 LinkedIn</a>
      <a class="pill" href="#">🌐 Portfolio</a>
      <a class="pill" href="#">💻 GitHub</a>
    </div>
  </section>

  <footer class="footer">
    Building software, AI systems, and products that create meaningful impact.
  </footer>

</div>

<script>
// ─── CONTRIBUTION SNAKE ANIMATION ───
(function() {
  const canvas = document.getElementById('snake');
  const ctx = canvas.getContext('2d');

  const COLS = 52;
  const ROWS = 7;
  const PAD  = 3;

  // ── build a plausible contribution grid ──
  const grid = [];
  for (let c = 0; c < COLS; c++) {
    grid[c] = [];
    for (let r = 0; r < ROWS; r++) {
      // weighted random: heavier toward recent weeks
      const bias = 0.3 + 0.5 * (c / COLS);
      const rand = Math.random();
      if (rand > bias + 0.35) grid[c][r] = 0;
      else if (rand > bias + 0.15) grid[c][r] = 1;
      else if (rand > bias - 0.05) grid[c][r] = 2;
      else grid[c][r] = 3;
    }
  }

  // ── cell colours (pastel rose scale) ──
  const CELL_COLORS = ['#f5eced', '#f2c4cc', '#e8a0b0', '#d4607c'];
  const SNAKE_COLOR = '#d4607c';
  const SNAKE_HEAD  = '#a63050';
  const SNAKE_EYE   = '#fff';

  // ── sizing ──
  function getCell() {
    const W = canvas.clientWidth || canvas.width;
    const cell = Math.floor((W - PAD) / COLS) - PAD;
    return Math.max(cell, 6);
  }

  function resize() {
    const W = canvas.clientWidth || 840;
    const cell = getCell();
    canvas.width  = W;
    canvas.height = ROWS * (cell + PAD) + PAD + 1;
  }

  // ── snake path: visits every non-zero cell ──
  function buildPath() {
    const path = [];
    for (let c = 0; c < COLS; c++) {
      const rows = c % 2 === 0
        ? Array.from({length: ROWS}, (_, i) => i)
        : Array.from({length: ROWS}, (_, i) => ROWS - 1 - i);
      for (const r of rows) {
        if (grid[c][r] > 0) path.push([c, r]);
      }
    }
    return path;
  }

  const path = buildPath();

  // ── animation state ──
  const SNAKE_LEN = 10; // segments visible
  let head = 0;

  function cellPos(c, r) {
    const cell = getCell();
    return {
      x: PAD + c * (cell + PAD),
      y: PAD + r * (cell + PAD),
      s: cell
    };
  }

  function draw(ts) {
    resize();
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    const cell = getCell();

    // draw all cells
    for (let c = 0; c < COLS; c++) {
      for (let r = 0; r < ROWS; r++) {
        const {x, y, s} = cellPos(c, r);
        ctx.fillStyle = CELL_COLORS[grid[c][r]];
        ctx.beginPath();
        ctx.roundRect(x, y, s, s, 2);
        ctx.fill();
      }
    }

    // draw snake body
    const snakeIdxs = [];
    for (let i = 0; i < SNAKE_LEN; i++) {
      const idx = (head - i + path.length * 1000) % path.length;
      snakeIdxs.push(idx);
    }

    snakeIdxs.reverse().forEach((idx, i) => {
      const [c, r] = path[idx];
      const {x, y, s} = cellPos(c, r);
      const alpha = 0.4 + 0.6 * (i / SNAKE_LEN);
      ctx.globalAlpha = alpha;
      ctx.fillStyle = SNAKE_COLOR;
      ctx.beginPath();
      ctx.roundRect(x - 1, y - 1, s + 2, s + 2, 3);
      ctx.fill();
    });

    ctx.globalAlpha = 1;

    // draw head
    const [hc, hr] = path[head % path.length];
    const {x: hx, y: hy, s: hs} = cellPos(hc, hr);
    ctx.fillStyle = SNAKE_HEAD;
    ctx.beginPath();
    ctx.roundRect(hx - 2, hy - 2, hs + 4, hs + 4, 4);
    ctx.fill();

    // eye
    ctx.fillStyle = SNAKE_EYE;
    ctx.beginPath();
    ctx.arc(hx + hs * 0.65, hy + hs * 0.3, hs * 0.15, 0, Math.PI * 2);
    ctx.fill();

    // advance head every ~80ms
    if (!draw._last || ts - draw._last > 80) {
      head = (head + 1) % path.length;
      draw._last = ts;
    }

    requestAnimationFrame(draw);
  }

  resize();
  requestAnimationFrame(draw);
})();
</script>
</body>
</html>
