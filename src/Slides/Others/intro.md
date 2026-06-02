---
theme: default
title: Python Basics & Syntax
titleTemplate: '%s — Python Fundamentals'
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
transition: slide-left
mdc: true
colorSchema: light
fonts:
  sans: 'Nunito'
  mono: 'Fira Code'
---

<style>
/* ============================================================
   GLOBAL DESIGN SYSTEM — matches Slide2.vue palette
   ============================================================ */
:root {
  --red:       #ef5050;
  --red-dark:  #c73c3c;
  --red-light: #fff0f0;
  --red-soft:  #fde8e8;
  --navy:      #1a1f36;
  --navy-mid:  #2d3561;
  --slate:     #4a5568;
  --muted:     #718096;
  --bg:        #f7f8fc;
  --white:     #ffffff;
  --border:    #e2e8f0;
  --green:     #38a169;
  --orange:    #dd6b20;
  --blue:      #3182ce;
  --yellow:    #d69e2e;
  --shadow-sm: 0 1px 4px rgba(0,0,0,.08);
  --shadow-md: 0 4px 16px rgba(0,0,0,.12);
  --radius:    10px;
  --radius-lg: 16px;
}

/* ── Slidev canvas ───────────────────────────────────────── */
.slidev-layout {
  font-family: 'Nunito', sans-serif;
  background: var(--bg);
  color: var(--navy);
}

/* ── Top navbar — mirrors Slide2.vue .navbar ─────────────── */
.slide-navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: transparent;
  padding: 0 0 12px 0;
  margin-bottom: 14px;
  border: 1px solid var(--red);
}
.slide-navbar .nav-title {
  background: var(--red);
  color: #fff;
  font-size: 1.15rem;
  font-weight: 800;
  padding: 5px 18px;
  border-radius: 6px;
  letter-spacing: 0.4px;
}
.slide-navbar .nav-badge {
  background: var(--navy);
  color: #fff;
  font-size: 0.68rem;
  font-weight: 700;
  padding: 3px 10px;
  border-radius: 20px;
  letter-spacing: 1px;
  text-transform: uppercase;
}

/* ── Cards ───────────────────────────────────────────────── */
.card {
  background: var(--white);
  border-radius: var(--radius);
  padding: 14px 18px;
  box-shadow: var(--shadow-sm);
  border: 1px solid var(--border);
}
.card-red {
  background: var(--red-soft);
  border: 1px solid var(--red);
}
.card-navy {
  background: var(--navy);
  color: #fff;
  border-radius: var(--radius);
  padding: 14px 18px;
}
.card-green {
  background: #f0fff4;
  border: 1px solid var(--green);
}
.card-blue {
  background: #ebf8ff;
  border: 1px solid var(--blue);
}
.card-orange {
  background: #fffaf0;
  border: 1px solid var(--orange);
}

/* ── Feature pill ────────────────────────────────────────── */
.pill {
  display: inline-block;
  padding: 4px 14px;
  border-radius: 20px;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.5px;
}
.pill-red    { background: var(--red-soft);  color: var(--red-dark); }
.pill-navy   { background: #eef0f8;          color: var(--navy-mid); }
.pill-green  { background: #f0fff4;          color: var(--green); }
.pill-orange { background: #fffaf0;          color: var(--orange); }
.pill-blue   { background: #ebf8ff;          color: var(--blue); }

/* ── Section label ───────────────────────────────────────── */
.section-label {
  font-size: 0.62rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: var(--red);
  margin-bottom: 4px;
}

/* ── Output box ──────────────────────────────────────────── */
.output-box {
  background: #1a1f36;
  color: #a8ff78;
  font-family: 'Fira Code', monospace;
  font-size: 0.78rem;
  border-radius: var(--radius);
  padding: 14px 18px;
  border: 1px solid #a8ff78;
  line-height: 1.7;
}
.output-box .prompt { color: #61dafb; }
.output-box .comment { color: #636e80; }

/* ── Step flow ───────────────────────────────────────────── */
.step-flow {
  display: flex;
  align-items: center;
  gap: 6px;
  flex-wrap: wrap;
}
.step-box {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 8px 14px;
  font-size: 0.75rem;
  font-weight: 700;
  text-align: center;
  min-width: 80px;
  position: relative;
}
.step-box.active { border-color: var(--red); background: var(--red-soft); color: var(--red-dark); }
.step-arrow { color: var(--muted); font-size: 1.1rem; font-weight: 900; }

/* ── Comparison table ────────────────────────────────────── */
.cmp-table { width: 100%; border-collapse: collapse; font-size: 0.75rem; }
.cmp-table th {
  background: var(--navy);
  color: #fff;
  padding: 7px 12px;
  text-align: left;
  font-weight: 700;
}
.cmp-table td { padding: 7px 12px; border-bottom: 1px solid var(--border); }
.cmp-table tr:nth-child(even) td { background: #f7f8fc; }
.cmp-table .yes { color: var(--green); font-weight: 700; }
.cmp-table .no  { color: var(--red);   font-weight: 700; }

/* ── Activity box ────────────────────────────────────────── */
.activity-box {
  background: linear-gradient(135deg, #1a1f36 0%, #2d3561 100%);
  color: #fff;
  border-radius: var(--radius-lg);
  padding: 20px 24px;
}
.activity-box .act-title {
  font-size: 1rem;
  font-weight: 800;
  color: #ffd166;
  margin-bottom: 10px;
}
.activity-box .act-task {
  background: rgba(255,255,255,.08);
  border-radius: var(--radius);
  padding: 10px 14px;
  font-size: 0.78rem;
  margin-bottom: 8px;
  border: 1px solid #ffd166;
}
.activity-box .hint {
  font-size: 0.68rem;
  color: rgba(255,255,255,.55);
  margin-top: 4px;
}

/* ── Syntax diagram ──────────────────────────────────────── */
.syntax-row {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-wrap: wrap;
  font-family: 'Fira Code', monospace;
  font-size: 0.8rem;
}
.syn-keyword  { background: #fde8e8; color: var(--red-dark);  padding: 3px 10px; border-radius: 5px; font-weight: 700; }
.syn-varname  { background: #ebf8ff; color: #2b6cb0;          padding: 3px 10px; border-radius: 5px; }
.syn-operator { background: #fffaf0; color: var(--orange);    padding: 3px 10px; border-radius: 5px; font-weight: 700; }
.syn-value    { background: #f0fff4; color: var(--green);     padding: 3px 10px; border-radius: 5px; }
.syn-label {
  font-size: 0.6rem;
  color: var(--muted);
  text-align: center;
  margin-top: 3px;
  font-family: 'Nunito', sans-serif;
}

/* ── Icon circle ─────────────────────────────────────────── */
.icon-circle {
  width: 44px; height: 44px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.3rem;
  flex-shrink: 0;
}
.ic-red    { background: var(--red-soft); }
.ic-navy   { background: #eef0f8; }
.ic-green  { background: #f0fff4; }
.ic-orange { background: #fffaf0; }
.ic-blue   { background: #ebf8ff; }

/* ── Grid helpers ────────────────────────────────────────── */
.g2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.g3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; }
.g4 { display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 8px; }
.flex-row { display: flex; gap: 10px; align-items: flex-start; }
.flex-col  { display: flex; flex-direction: column; gap: 8px; }

/* ── Typography ──────────────────────────────────────────── */
.slide-h1 { font-size: 1.5rem; font-weight: 900; color: var(--navy); line-height: 1.2; }
.slide-h2 { font-size: 1.1rem; font-weight: 800; color: var(--navy); }
.slide-h3 { font-size: 0.9rem; font-weight: 700; color: var(--navy-mid); }
.body-text { font-size: 0.78rem; color: var(--slate); line-height: 1.6; }
.small-text{ font-size: 0.68rem; color: var(--muted); }
.highlight  { color: var(--red); font-weight: 800; }
.mono       { font-family: 'Fira Code', monospace; }

/* ── Callout ─────────────────────────────────────────────── */
.callout {
  display: flex; gap: 10px; align-items: flex-start;
  padding: 10px 14px;
  border-radius: var(--radius);
  font-size: 0.75rem;
}
.callout-info    { background: #ebf8ff; border: 1px solid var(--blue); }
.callout-warn    { background: #fffaf0; border: 1px solid var(--orange); }
.callout-success { background: #f0fff4; border: 1px solid var(--green); }
.callout-danger  { background: var(--red-soft); border: 1px solid var(--red); }
.callout-icon    { font-size: 1rem; margin-top: 1px; }

/* ── Progress bar ────────────────────────────────────────── */
.topic-progress {
  display: flex; gap: 5px; align-items: center;
}
.tp-dot {
  width: 28px; height: 6px; border-radius: 3px;
  background: var(--border);
}
.tp-dot.active { background: var(--red); }
.tp-dot.done   { background: var(--red-dark); }
</style>

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — WHAT IS PYTHON?
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Introduction to Python">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">What is <span class="highlight">Python?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

<div v-click class="card-navy" style="border-radius:10px;">
  <div style="font-size:.82rem;line-height:1.6;color:#e2e8f0;">Python is a <strong style="color:#ff9a9a;">high-level, interpreted, general-purpose</strong> programming language designed for <strong style="color:#a8ff78;">readability</strong> and <strong style="color:#a8ff78;">simplicity</strong>.</div>
</div>

<div v-click class="card card-red">
  <div style="display:flex;gap:8px;align-items:center;">
    <div>
      <div class="slide-h3">Created by Guido van Rossum</div>
      <div class="small-text">First released in <strong>1991</strong> · Named after <em>Monty Python</em></div>
    </div>
  </div>
</div>

<div v-click class="callout callout-success">
  <div><strong>Key idea:</strong> Write <em>less code</em>, do <em>more things</em>. Python reads almost like plain English!</div>
</div>

</div>

<div class="flex-col">

<div v-click class="slide-h3" style="margin-bottom:8px;">Where is Python used?</div>

<div v-click class="card" style="margin-bottom:6px;display:flex;gap:10px;align-items:center;">
  <div class="icon-circle ic-blue">🤖</div>
  <div><div class="slide-h3">AI &amp; Machine Learning</div><div class="small-text">TensorFlow, PyTorch, scikit-learn</div></div>
</div>

<div v-click class="card" style="margin-bottom:6px;display:flex;gap:10px;align-items:center;">
  <div class="icon-circle ic-green">🌐</div>
  <div><div class="slide-h3">Web Development</div><div class="small-text">Django, Flask, FastAPI</div></div>
</div>

<div v-click class="card" style="margin-bottom:6px;display:flex;gap:10px;align-items:center;">
  <div class="icon-circle ic-orange">🔬</div>
  <div><div class="slide-h3">Data Science</div><div class="small-text">Pandas, NumPy, Matplotlib</div></div>
</div>

<div v-click class="card" style="display:flex;gap:10px;align-items:center;">
  <div class="icon-circle ic-red">⚙️</div>
  <div><div class="slide-h3">Automation &amp; Scripting</div><div class="small-text">System tasks, bots, testing</div></div>
</div>

</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — PYTHON TIMELINE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Introduction to Python — A Brief History">
  <template #content>
<div class="slide-h1" style="margin-bottom:16px;">Python's <span class="highlight">Timeline</span></div>

<div style="position:relative;padding-left:24px;">
  <!-- vertical line -->
  <div style="position:absolute;left:18px;top:0;bottom:0;width:3px;background:linear-gradient(to bottom,#ef5050,#3182ce);border-radius:2px;"></div>

  <div v-click style="display:flex;gap:14px;align-items:flex-start;margin-bottom:14px;position:relative;">
    <div style="position:absolute;left:-14px;width:16px;height:16px;border-radius:50%;background:#ef5050;border:1px solid #fff;box-shadow:0 0 0 2px #ef5050;top:2px;"></div>
    <div style="padding-left:18px;">
      <div style="display:flex;align-items:center;gap:8px;">
        <span class="pill pill-red">1989–1991</span>
        <span class="slide-h3">Birth of Python</span>
      </div>
      <div class="body-text">Guido van Rossum begins work on Python as a hobby project. <strong>Python 0.9.0</strong> released in 1991.</div>
    </div>
  </div>

  <div v-click style="display:flex;gap:14px;align-items:flex-start;margin-bottom:14px;position:relative;">
    <div style="position:absolute;left:-14px;width:16px;height:16px;border-radius:50%;background:#dd6b20;border:1px solid #fff;box-shadow:0 0 0 2px #dd6b20;top:2px;"></div>
    <div style="padding-left:18px;">
      <div style="display:flex;align-items:center;gap:8px;">
        <span class="pill pill-orange">2000</span>
        <span class="slide-h3">Python 2.0</span>
      </div>
      <div class="body-text">Major release with list comprehensions and garbage collection. Widely adopted.</div>
    </div>
  </div>

  <div v-click style="display:flex;gap:14px;align-items:flex-start;margin-bottom:14px;position:relative;">
    <div style="position:absolute;left:-14px;width:16px;height:16px;border-radius:50%;background:#3182ce;border:1px solid #fff;box-shadow:0 0 0 2px #3182ce;top:2px;"></div>
    <div style="padding-left:18px;">
      <div style="display:flex;align-items:center;gap:8px;">
        <span class="pill pill-blue">2008</span>
        <span class="slide-h3">Python 3.0</span>
      </div>
      <div class="body-text">Major redesign — better Unicode support, cleaner syntax. <strong>This is what we use today!</strong></div>
    </div>
  </div>

  <div v-click style="display:flex;gap:14px;align-items:flex-start;position:relative;">
    <div style="position:absolute;left:-14px;width:16px;height:16px;border-radius:50%;background:#38a169;border:1px solid #fff;box-shadow:0 0 0 2px #38a169;top:2px;"></div>
    <div style="padding-left:18px;">
      <div style="display:flex;align-items:center;gap:8px;">
        <span class="pill pill-green">2024+</span>
        <span class="slide-h3">Python Today</span>
      </div>
      <div class="body-text">Python 3.12+ — fastest growing language, #1 on TIOBE Index, dominates AI/ML world.</div>
    </div>
  </div>

</div>

<div v-click style="margin-top:14px;" class="callout callout-warn">
  <div><strong>Note:</strong> Python 2 is officially <strong>retired (2020)</strong>. Always use <strong>Python 3.x</strong> for new projects.</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — FEATURES OVERVIEW
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Features of Python">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">Why Python is <span class="highlight">Awesome</span></div>

<div class="g3" style="gap:10px;">

<div v-click class="card" style="border:1px solid #ef5050;">
  <div style="font-size:1.6rem;margin-bottom:6px;">📖</div>
  <div class="slide-h3" style="margin-bottom:4px;">Easy to Read</div>
  <div class="small-text">Syntax resembles plain English. No messy curly braces or semicolons!</div>
</div>

<div v-click class="card" style="border:1px solid #3182ce;">
  <div style="font-size:1.6rem;margin-bottom:6px;">⚡</div>
  <div class="slide-h3" style="margin-bottom:4px;">Interpreted</div>
  <div class="small-text">Code runs line-by-line. No compilation step needed.</div>
</div>

<div v-click class="card" style="border:1px solid #38a169;">
  <div style="font-size:1.6rem;margin-bottom:6px;">🌐</div>
  <div class="slide-h3" style="margin-bottom:4px;">Cross-Platform</div>
  <div class="small-text">Write once, run on Windows, Mac, Linux, Raspberry Pi...</div>
</div>

<div v-click class="card" style="border:1px solid #dd6b20;">
  <div style="font-size:1.6rem;margin-bottom:6px;">🔓</div>
  <div class="slide-h3" style="margin-bottom:4px;">Open Source</div>
  <div class="small-text">Free forever. Huge community of millions of developers.</div>
</div>

<div v-click class="card" style="border:1px solid #9f7aea;">
  <div style="font-size:1.6rem;margin-bottom:6px;">📦</div>
  <div class="slide-h3" style="margin-bottom:4px;">Rich Libraries</div>
  <div class="small-text">300,000+ packages on PyPI. There's a library for everything.</div>
</div>

<div v-click class="card" style="border:1px solid #d69e2e;">
  <div style="font-size:1.6rem;margin-bottom:6px;">🧩</div>
  <div class="slide-h3" style="margin-bottom:4px;">Versatile</div>
  <div class="small-text">Web, AI, data, games, automation — Python does it all.</div>
</div>

</div>

<div v-click style="margin-top:10px;" class="callout callout-info">
  <div>Python's guiding principle: <strong>"There should be one — and preferably only one — obvious way to do it."</strong> (The Zen of Python)</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — PYTHON vs OTHER LANGUAGES (Comparison)
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Features of Python — Comparison">
  <template #content>
<div v-click class="slide-h1" style="margin-bottom:12px;">Python <span class="highlight">vs</span> Other Languages</div>

<div>
<table class="cmp-table">
  <thead>
    <tr v-after>
      <th>Feature</th>
      <th>🐍 Python</th>
      <th>☕ Java</th>
      <th>⚙️ C++</th>
    </tr>
  </thead>
  <tbody>
    <tr v-click>
      <td><strong>Syntax Simplicity</strong></td>
      <td><span class="yes">★★★★★</span></td>
      <td><span style="color:#dd6b20;">★★★☆☆</span></td>
      <td><span class="no">★★☆☆☆</span></td>
    </tr>
    <tr v-click>
      <td><strong>Compilation needed?</strong></td>
      <td><span class="yes">No (Interpreted)</span></td>
      <td><span class="no">Yes (JVM)</span></td>
      <td><span class="no">Yes (Compiled)</span></td>
    </tr>
    <tr v-click>
      <td><strong>Type Declaration</strong></td>
      <td><span class="yes">Optional (Dynamic)</span></td>
      <td><span class="no">Required (Static)</span></td>
      <td><span class="no">Required (Static)</span></td>
    </tr>
    <tr v-click>
      <td><strong>Beginner Friendly</strong></td>
      <td><span class="yes">Very Easy</span></td>
      <td><span style="color:#dd6b20;">Moderate</span></td>
      <td><span class="no">Difficult</span></td>
    </tr>
    <tr v-click>
      <td><strong>Lines for "Hello World"</strong></td>
      <td><span class="yes">1 line</span></td>
      <td><span class="no">~5 lines</span></td>
      <td><span class="no">~5 lines</span></td>
    </tr>
  </tbody>
</table>
</div>

<div v-after class="g2" style="gap:10px;margin-top:12px;">
<div class="card card-green">
  <div class="small-text"><strong>Python:</strong> <span class="mono">print("Hello World")</span> — just one line!</div>
</div>
<div class="card card-red">
  <div class="small-text"><strong>Java:</strong> needs class, main method, System.out.println — 5+ lines for the same result.</div>
</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — INTERPRETED vs COMPILED
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Features of Python — Interpreted Language">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Compiled vs <span class="highlight">Interpreted</span></div>

<div class="g2" style="gap:16px;align-items:start;">

<div>
<div class="slide-h3" style="margin-bottom:8px;color:#c73c3c;">Compiled Languages (C, C++, Java)</div>
<div style="background:#fff;border:1px solid var(--border);border-radius:10px;padding:14px;">
  <div class="step-flow" style="flex-direction:column;align-items:flex-start;gap:8px;">
    <div v-click class="step-box" style="width:100%;text-align:left;"><strong>1.</strong> Write source code (.c / .java)</div>
    <div v-after class="step-box" style="width:100%;text-align:left;"><strong>2.</strong> Compiler translates entire code</div>
    <div v-after class="step-box" style="width:100%;text-align:left;"><strong>3.</strong> Generates machine code / bytecode</div>
    <div v-after class="step-box active" style="width:100%;text-align:left;"><strong>4.</strong> Run the compiled binary</div>
  </div>
  <div class="small-text" style="margin-top:8px;">⏱ Slower to develop, but faster execution</div>
</div>
</div>

<div>
<div class="slide-h3" style="margin-bottom:8px;color:#38a169;">Interpreted Language (Python)</div>
<div style="background:#fff;border:1px solid var(--border);border-radius:10px;padding:14px;">
  <div class="step-flow" style="flex-direction:column;align-items:flex-start;gap:8px;">
    <div v-click class="step-box" style="width:100%;text-align:left;border-color:#38a169;"><strong>1.</strong> Write source code (.py)</div>
    <div v-after class="step-box" style="width:100%;text-align:left;border-color:#38a169;"><strong>2.</strong> Python interpreter reads line by line</div>
    <div v-after class="step-box active" style="width:100%;text-align:left;border-color:#38a169;background:#f0fff4;color:#276749;"><strong>3.</strong> Execute immediately!</div>
  </div>
  <div class="small-text" style="margin-top:8px;">⚡ Faster to develop, easier to debug</div>
</div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — YOUR FIRST PYTHON PROGRAM
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Running Python — Your First Program" starterCode='# write your code here'>
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Your <span class="highlight">First Program</span> 🎉</div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div style="width:500px; height:280px;"><JavaRunner/></div>
</div>

<div>
  <!-- <div class="slide-h3" style="margin-bottom:8px;">Output</div>
  <div v-click class="output-box">
    Hello, World!<br>
    I am learning Python!
  </div> -->

  <div style="margin-top:12px;">
    <div v-click class="slide-h3" style="margin-bottom:8px;">Code Walkthrough</div>
    <div class="flex-col" style="gap:6px;">
      <div class="card card-red" v-click>
        <div class="small-text"><span class="mono">#</span> — Lines starting with <strong>#</strong> are comments. Python skips them.</div>
      </div>
      <div class="card card-blue" v-click>
        <div class="small-text"><span class="mono">print()</span> — Displays whatever is inside the brackets.</div>
      </div>
      <div class="card card-green" v-click>
        <div class="small-text"><span class="mono">"..."</span> — Double quotes wrap a string (text) value.</div>
      </div>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — ACTIVITY 1
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Activity — Try It Yourself!">
  <template #content>

<div class="slide-h1" style="margin-bottom:14px;">Try It <span class="highlight">Yourself!</span></div>

<div class="activity-box">
  <div class="act-title">Activity 1: Your First Python Program</div>

  <div class="act-task" v-click>
    <strong>Task 1:</strong> Print your name:
    <div class="mono" style="margin-top:5px;color:#a8ff78;font-size:.75rem;">print("My name is [Your Name]")</div>
    <div class="hint">Expected: Your name should appear on screen!</div>
  </div>

  <div class="act-task" v-click>
    <strong>Task 2:</strong> Print your college name and year:
    <div class="mono" style="margin-top:5px;color:#a8ff78;font-size:.75rem;">print("I study at [Your College Name]")<br>print("Year: [2024]")</div>
    <div class="hint">Try using multiple print() calls!</div>
  </div>

  <div class="act-task" v-click>
    <strong>Bonus:</strong> What happens when you type this?
    <div class="mono" style="margin-top:5px;color:#ffd166;font-size:.75rem;">print("Line 1")
print()
print("Line 3")</div>
    <div class="hint">Hint: What does print() with no argument do?</div>
  </div>

</div>
  </template>
</Slide2>

---
transition: fade
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — SECTION DIVIDER: SYNTAX RULES
═══════════════════════════════════════════════════════ -->

<div style="background:linear-gradient(135deg,#744210,#dd6b20); height:65vh; margin:-24px; margin-top:1px; display:flex; flex-direction:column; align-items:center; justify-content:center; text-align:center;">
<div v-after style="font-size:3.5rem;margin-bottom:10px;">📐</div>
<h2 v-after style="color:#fff;font-size:2.2rem;font-weight:900;margin-bottom:10px;">Python Syntax Rules</h2>
<p v-after style="color:rgba(255,255,255,.75);font-size:.88rem;max-width:420px;">The grammar of Python — master these and you're unstoppable!</p>

<div v-after style="display:flex;gap:8px;flex-wrap:wrap;justify-content:center;margin-top:20px;max-width:500px;">
  <span class="pill" style="background:rgba(255,255,255,.15);color:#fff;">Indentation</span>
  <span class="pill" style="background:rgba(255,255,255,.15);color:#fff;">Comments</span>
  <span class="pill" style="background:rgba(255,255,255,.15);color:#fff;">Variables</span>
  <span class="pill" style="background:rgba(255,255,255,.15);color:#fff;">Data Types</span>
  <span class="pill" style="background:rgba(255,255,255,.15);color:#fff;">Naming Rules</span>
  <span class="pill" style="background:rgba(255,255,255,.15);color:#fff;">Case Sensitivity</span>
</div>

</div>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — INDENTATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Indentation">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Rule #1: <span class="highlight">Indentation</span> Matters!</div>

<div class="card card-blue" style="margin-bottom:12px;" v-click>
  <div><strong>Python uses indentation instead of { } braces</strong> to define code blocks. Getting this wrong causes errors!</div>
</div>

<div class="g2" style="gap:14px;">

<div>
  <div class="slide-h3" style="color:#c73c3c;margin-bottom:6px;">Wrong — IndentationError!</div>

```python 
# Missing indentation — will CRASH!
if 5 > 2:
print("Five is greater")  # Error!
```

  <div v-click class="card card-red">
    IndentationError: expected an indented block
  </div>
</div>

<div>
  <div class="slide-h3" style="color:#38a169;margin-bottom:6px;">Correct — Uses 4 Spaces!</div>

```python {all}
# Proper indentation — works perfectly!
if 5 > 2:
    print("Five is greater")

# Nested indentation
for i in range(3):
    if i > 0:
        print(i)
```

  <div v-click class="card card-green">
    Five is greater<br>
    1<br>
    2
  </div>
</div>

</div>

<div v-after class="g2" style="gap:10px;margin-top:10px;">
<div class="card card-green">
  <div class="small-text">Use <strong>4 spaces</strong> per indentation level (PEP 8 standard)</div>
</div>
<div class="card card-red">
  <div class="small-text">Never mix <strong>tabs and spaces</strong> in the same file — causes TabError!</div>
</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — COMMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Comments">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Rule #2: <span class="highlight">Comments</span></div>

<div class="body-text" style="margin-bottom:12px;">Comments are notes for humans — Python completely ignores them during execution.</div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Single-line Comment <span class="mono" style="color:#ef5050;">#</span></div>

```python {1,2,4|all}
# This is a single-line comment
# Comments start with the # symbol

name = "Alice"   # inline comment too!
age  = 20        # this is her age
```

  <div v-click class="callout callout-info" style="margin-top:8px;">
    <div>Use <span class="mono">#</span> for short explanations on a single line.</div>
  </div>
</div>

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Multi-line Comment <span class="mono" style="color:#ef5050;">"""..."""</span></div>

```python {1,2,3,4,5|all}
"""
This is a multi-line comment.
Also called a docstring.
Used to document functions & modules.
"""

def greet():
    """This function prints a greeting."""
    print("Hello!")
```

  <div v-click class="callout callout-warn" style="margin-top:8px;">
    <div>Triple quotes <span class="mono">"""</span> are technically <strong>strings</strong>, but used as multiline comments when not assigned.</div>
  </div>
</div>

</div>

<div v-click class="callout callout-success" style="margin-top:10px;">
  <div><strong>Best practice:</strong> Write comments that explain <em>WHY</em> you wrote the code, not just <em>WHAT</em> it does. Good code is self-explanatory!</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — VARIABLES & DATA TYPES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Variables & Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Rule #3: <span class="highlight">Variables</span> &amp; Data Types</div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Declaring Variables</div>
  <div class="card card-blue" style="margin-bottom:8px;">
    <div class="small-text">In Python, <strong>no need to declare a type</strong> — just assign a value!</div>
  </div>

```python {1|2|3|4|5|all}
name    = "Alice"     # str  → text
age     = 20          # int  → whole number
gpa     = 9.5         # float → decimal
is_pass = True        # bool → True/False
nothing = None        # NoneType → no value
```

  <div v-click style="margin-top:8px;">
    <div class="slide-h3" style="margin-bottom:4px;">Syntax Diagram</div>
    <div class="card" style="padding:10px;">
      <div class="syntax-row">
        <div>
          <div class="syn-varname">name</div>
          <div class="syn-label">Variable</div>
        </div>
        <div>
          <div class="syn-operator">=</div>
          <div class="syn-label">Assignment</div>
        </div>
        <div>
          <div class="syn-value">"Alice"</div>
          <div class="syn-label">Value</div>
        </div>
      </div>
    </div>
  </div>
</div>

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Built-in Data Types</div>

  <div class="flex-col" style="gap:7px;">
    <div v-click class="card" style="display:flex;justify-content:space-between;align-items:center;padding:8px 14px;">
      <div><span class="pill pill-red">str</span> <span class="small-text" style="margin-left:6px;">Text / String</span></div>
      <span class="mono small-text">"Hello", 'World'</span>
    </div>
    <div v-after class="card" style="display:flex;justify-content:space-between;align-items:center;padding:8px 14px;">
      <div><span class="pill pill-blue">int</span> <span class="small-text" style="margin-left:6px;">Integer</span></div>
      <span class="mono small-text">42, -10, 0</span>
    </div>
    <div v-after class="card" style="display:flex;justify-content:space-between;align-items:center;padding:8px 14px;">
      <div><span class="pill pill-navy">float</span> <span class="small-text" style="margin-left:6px;">Decimal Number</span></div>
      <span class="mono small-text">3.14, -2.5</span>
    </div>
    <div v-after class="card" style="display:flex;justify-content:space-between;align-items:center;padding:8px 14px;">
      <div><span class="pill pill-green">bool</span> <span class="small-text" style="margin-left:6px;">Boolean</span></div>
      <span class="mono small-text">True, False</span>
    </div>
    <div v-after class="card" style="display:flex;justify-content:space-between;align-items:center;padding:8px 14px;">
      <div><span class="pill pill-orange">NoneType</span> <span class="small-text" style="margin-left:6px;">No value</span></div>
      <span class="mono small-text">None</span>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — type() & dynamic typing
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Dynamic Typing">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Dynamic Typing</span> — Python's Superpower</div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Using <span class="mono">type()</span> to check types</div>

```python {1,2|3,4|5,6|7,8|all}
x = 10
print(type(x))       # <class 'int'>

x = "Hello"
print(type(x))       # <class 'str'>

x = 3.14
print(type(x))       # <class 'float'>
```

  <div v-click class="card card-green">
    &lt;class 'int'&gt;<br>
    &lt;class 'str'&gt;<br>
    &lt;class 'float'&gt;
  </div>

  <div v-after class="callout callout-warn" style="margin-top:8px;">
    <div>The <strong>same variable</strong> can hold different types at different times — that's <em>dynamic typing!</em></div>
  </div>
</div>

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Multiple Assignment</div>

```python {1|2|3|4|5|all}
# Assign multiple variables at once
a, b, c = 10, 20, 30

# Same value to multiple variables
x = y = z = 0

# Swap values (Python magic!)
a, b = b, a
print(a, b)   # 20 10
```

  <div v-click class="card card-green"">
    20 10
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 19 — NAMING RULES & CASE SENSITIVITY
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Rule #4: <span class="highlight">Naming Rules</span> &amp; Case Sensitivity</div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:8px;">Variable Naming Rules</div>
  <div class="flex-col" style="gap:7px;">
    <div v-click class="card card-green">
      <div class="small-text">Can use: <span class="mono">letters, digits, underscore _</span></div>
    </div>
    <div v-click class="card card-green">
      <div class="small-text">Must <strong>start with a letter or underscore</strong>, NOT a digit</div>
    </div>
    <div v-click class="card card-red">
      <div class="small-text">Cannot use spaces or special characters: <span class="mono">$ @ ! - #</span></div>
    </div>
    <div v-click class="card card-red">
      <div class="small-text">Cannot use Python keywords: <span class="mono">if, for, while, class, def...</span></div>
    </div>
  </div>

  <div v-click class="g2" style="gap:6px;margin-top:10px;">
    <div>
      <div class="small-text" style="color:#38a169;font-weight:700;margin-bottom:4px;">Valid Names</div>
      <div class="output-box" style="background:#f0fff4;color:#276749;border-left-color:#38a169;font-size:.7rem;">
        my_name<br>
        _score<br>
        studentAge<br>
        roll2024
      </div>
    </div>
    <div>
      <div class="small-text" style="color:#c53030;font-weight:700;margin-bottom:4px;">Invalid Names</div>
      <div class="output-box" style="background:#fff5f5;color:#c53030;border-left-color:#c53030;font-size:.7rem;">
        2roll &nbsp;← starts with digit<br>
        my-name ← hyphen not allowed<br>
        my name ← space not allowed<br>
        if &nbsp;&nbsp;&nbsp;&nbsp;← reserved keyword
      </div>
    </div>
  </div>
</div>

<div>
  <div class="slide-h3" style="margin-bottom:8px;">Python is Case-Sensitive!</div>

```python {1,2,3|5,6,7|all}
# These are THREE different variables!
name  = "Alice"
Name  = "Bob"
NAME  = "Charlie"

print(name)   # Alice
print(Name)   # Bob
print(NAME)   # Charlie
```

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    Alice<br>Bob<br>Charlie
  </div>

  <div v-after class="callout callout-danger" style="margin-top:8px;">
    <div><strong>Common mistake!</strong> <span class="mono">print</span> ≠ <span class="mono">Print</span> ≠ <span class="mono">PRINT</span>. Only lowercase <span class="mono">print</span> works!</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — INPUT / OUTPUT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Input & Output">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Rule #5: <span class="highlight">Input</span> &amp; <span class="highlight">Output</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Output with <span class="mono">print()</span></div>

```python {1|2|3|4|5|all}
# Simple output
print("Welcome to Python!")

# Print variable
age = 20
print("I am", age, "years old")

# f-string (modern way)
name = "Alice"
print(f"Hello, {name}! You are {age}.")
```

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    Welcome to Python!<br>
    I am 20 years old<br>
    Hello, Alice! You are 20.
  </div>
</div>

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Input with <span class="mono">input()</span></div>

```python {1|2|3|4|5|all}
# Get user input
name = input("Enter your name: ")
print("Hello,", name)

# Convert input to number
age = int(input("Enter your age: "))
print("Next year you'll be", age + 1)
```

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    Enter your name: <span style="color:#ffd166;">Alice</span><br>
    Hello, Alice<br>
    Enter your age: <span style="color:#ffd166;">20</span><br>
    Next year you'll be 21
  </div>

  <div v-after class="callout callout-warn" style="margin-top:8px;">
    <div><span class="mono">input()</span> always returns a <strong>string</strong>. Use <span class="mono">int()</span> or <span class="mono">float()</span> to convert numbers!</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 21 — KEYWORDS & RESERVED WORDS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Keywords">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Python <span class="highlight">Keywords</span> — Reserved Words</div>

<div class="body-text" style="margin-bottom:10px;" v-click>
  Keywords are <strong>reserved words</strong> with special meaning in Python. You <strong>cannot</strong> use them as variable names.
</div>

<div v-click class="card" style="margin-bottom:12px;">
  <div style="display:flex;flex-wrap:wrap;gap:6px;">
    <span class="pill pill-red">False</span>
    <span class="pill pill-red">None</span>
    <span class="pill pill-red">True</span>
    <span class="pill pill-navy">and</span>
    <span class="pill pill-navy">as</span>
    <span class="pill pill-navy">assert</span>
    <span class="pill pill-navy">async</span>
    <span class="pill pill-navy">await</span>
    <span class="pill pill-blue">break</span>
    <span class="pill pill-blue">class</span>
    <span class="pill pill-blue">continue</span>
    <span class="pill pill-blue">def</span>
    <span class="pill pill-blue">del</span>
    <span class="pill pill-green">elif</span>
    <span class="pill pill-green">else</span>
    <span class="pill pill-green">except</span>
    <span class="pill pill-green">finally</span>
    <span class="pill pill-green">for</span>
    <span class="pill pill-green">from</span>
    <span class="pill pill-orange">global</span>
    <span class="pill pill-orange">if</span>
    <span class="pill pill-orange">import</span>
    <span class="pill pill-orange">in</span>
    <span class="pill pill-orange">is</span>
    <span class="pill pill-orange">lambda</span>
    <span class="pill pill-navy">not</span>
    <span class="pill pill-navy">or</span>
    <span class="pill pill-navy">pass</span>
    <span class="pill pill-navy">raise</span>
    <span class="pill pill-navy">return</span>
    <span class="pill pill-navy">try</span>
    <span class="pill pill-navy">while</span>
    <span class="pill pill-navy">with</span>
    <span class="pill pill-navy">yield</span>
  </div>
</div>

<div class="g2" style="gap:10px;">
<div v-click>

```python
# Wrong — using keyword as variable!
if = 10       # SyntaxError!
for = "loop"  # SyntaxError!
```

</div>
<div v-click>

```python
# Correct — different names
if_value = 10     # add suffix
loop_name = "for" # rename it
```

</div>
</div>

<div v-after class="callout callout-info" style="margin-top:10px;">
  <div>Run <span class="mono">import keyword; print(keyword.kwlist)</span> to see all 35 Python keywords!</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 22 — COMPLETE EXAMPLE PROGRAM
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Full Example">
  <template #content>

<div class="section-label">04 · Syntax Rules</div>
<div class="slide-h1" style="margin-bottom:10px;">Putting It All <span class="highlight">Together</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:6px;">🎓 Student Profile Program</div>

```python {1,2|4,5,6,7|9,10,11|13,14,15,16|all}
# Student Profile Program
# Uses: variables, input, output, comments

# Get student info
name   = input("Enter your name: ")
age    = int(input("Enter your age: "))
marks  = float(input("Enter your marks: "))

# Calculate grade
if marks >= 90:
    grade = "A+"
elif marks >= 75:
    grade = "A"
else:
    grade = "B"

# Display result
print(f"\n--- Student Profile ---")
print(f"Name  : {name}")
print(f"Age   : {age} years")
print(f"Marks : {marks}")
print(f"Grade : {grade}")
```

</div>

<div>
  <div class="slide-h3" style="margin-bottom:6px;">📤 Sample Output</div>
  <div v-click class="output-box" style="font-size:.72rem;margin-bottom:10px;">
    Enter your name: <span style="color:#ffd166;">Alice</span><br>
    Enter your age: <span style="color:#ffd166;">19</span><br>
    Enter your marks: <span style="color:#ffd166;">92.5</span><br>
    <br>
    --- Student Profile ---<br>
    Name  : Alice<br>
    Age   : 19 years<br>
    Marks : 92.5<br>
    Grade : A+
  </div>

  <div v-after class="flex-col" style="gap:6px;">
    <div class="card card-red"><div class="small-text">🔴 <strong>Line 2–3:</strong> Comments explain the program</div></div>
    <div v-after class="card card-blue"><div class="small-text">🔵 <strong>Line 5–7:</strong> Variables with different types</div></div>
    <div v-after class="card card-orange"><div class="small-text">🟠 <strong>Line 10–15:</strong> Indented if/elif/else block</div></div>
    <div v-after class="card card-green"><div class="small-text">🟢 <strong>Line 18–22:</strong> f-strings for clean output</div></div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 23 — ACTIVITY 2: MINI PROJECT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Activity — Syntax Practice">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">🏋️ <span class="highlight">Syntax Challenge!</span></div>

<div class="activity-box">
  <div class="act-title">Activity 2: Fix & Build</div>

  <div class="act-task" v-click>
    <strong>Part A — Spot the Error</strong> Fix the bugs in this code:
    <div class="mono" style="margin-top:5px;color:#ff9a9a;font-size:.72rem;">
      Name = input("Enter name ")<br>
      Age = INT(Input("Enter age: "))<br>
      print(f"Hi {name}, you are {Age} old")
    </div>
    <div class="hint">Hint: Check case sensitivity and correct function names!</div>
  </div>

  <div class="act-task" v-click>
    <strong>Part B — Build It</strong> Write a program that:
    <div style="margin-top:6px;display:flex;flex-direction:column;gap:3px;">
      <div class="mono" style="color:#a8ff78;font-size:.72rem;">1. Asks for your city name</div>
      <div class="mono" style="color:#a8ff78;font-size:.72rem;">2. Asks for the temperature (float)</div>
      <div class="mono" style="color:#a8ff78;font-size:.72rem;">3. Prints: "It is 32.5°C in Chennai"</div>
    </div>
    <div class="hint">Use f-strings for formatted output!</div>
  </div>

  <div class="act-task" v-click>
    <strong>Bonus — type() Detective</strong>
    <div class="mono" style="margin-top:5px;color:#ffd166;font-size:.72rem;">x = input("Type something: ")<br>print(type(x))</div>
    <div class="hint">What type does input() always return? Try entering a number — surprise!</div>
  </div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 24 — SYNTAX SUMMARY / CHEAT SHEET
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax — Quick Reference">
  <template #content>
<div v-click class="slide-h1" style="margin-bottom:12px;">📋 Python Syntax <span class="highlight">Cheat Sheet</span></div>

<div class="g2" style="gap:12px;">

<div class="flex-col" style="gap:8px;">
  <div class="slide-h3" v-click>Rules at a Glance</div>

  <div v-after class="card" style="padding:10px 14px;border:1px solid #ef5050;">
    <div class="mono small-text" style="color:#c73c3c;margin-bottom:2px;"># Comment</div>
    <div class="small-text">Single-line comment using <strong>#</strong></div>
  </div>
  <div v-after class="card" style="padding:10px 14px;border:1px solid #3182ce;">
    <div class="mono small-text" style="color:#2b6cb0;margin-bottom:2px;">x = 10 &nbsp;&nbsp; name = "Alice"</div>
    <div class="small-text">Variable assignment — no type needed</div>
  </div>
  <div v-after class="card" style="padding:10px 14px;border:1px solid #38a169;">
    <div class="mono small-text" style="color:#276749;margin-bottom:2px;">print("Hello") &nbsp; print(x)</div>
    <div class="small-text">Output to screen</div>
  </div>
  <div v-after class="card" style="padding:10px 14px;border:1px solid #dd6b20;">
    <div class="mono small-text" style="color:#c05621;margin-bottom:2px;">x = input("Prompt: ")</div>
    <div class="small-text">Get input from user (always a string)</div>
  </div>
  <div v-after class="card" style="padding:10px 14px;border:1px solid #9f7aea;">
    <div class="mono small-text" style="color:#6b46c1;margin-bottom:2px;">    [4 spaces indentation]</div>
    <div class="small-text">Indentation defines code blocks</div>
  </div>
</div>

<div class="flex-col" style="gap:8px;">
  <div class="slide-h3" v-click>Data Types Quick View</div>

  <div v-after style="background:#1a1f36;border-radius:10px;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#636e80;"># Data Types</span><br>
    <span style="color:#61dafb;">x</span> = <span style="color:#ffd166;">42</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># int</span><br>
    <span style="color:#61dafb;">y</span> = <span style="color:#ffd166;">3.14</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># float</span><br>
    <span style="color:#61dafb;">s</span> = <span style="color:#a8ff78;">"Hello"</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># str</span><br>
    <span style="color:#61dafb;">b</span> = <span style="color:#f6c90e;">True</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># bool</span><br>
    <span style="color:#61dafb;">n</span> = <span style="color:#f6c90e;">None</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># NoneType</span><br>
    <br>
    <span style="color:#636e80;"># Check type</span><br>
    <span style="color:#a8ff78;">print</span>(<span style="color:#a8ff78;">type</span>(<span style="color:#61dafb;">x</span>))&nbsp;&nbsp;<span style="color:#636e80;"># &lt;class 'int'&gt;</span>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: fade
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 25 — TOPIC SUMMARY
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Basics & Syntax — Summary">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What You've <span class="highlight">Learned</span> Today 🎉</div>

<div class="g2" style="gap:12px;">

<div class="flex-col" style="gap:8px;">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #ef5050;">
    <div class="icon-circle ic-red" style="flex-shrink:0;">🐍</div>
    <div>
      <div class="slide-h3">Introduction to Python</div>
      <div class="small-text">High-level, interpreted, general-purpose. Created 1991 by Guido van Rossum.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #3182ce;">
    <div class="icon-circle ic-blue" style="flex-shrink:0;">⚡</div>
    <div>
      <div class="slide-h3">Features of Python</div>
      <div class="small-text">Simple, interpreted, cross-platform, open source, rich libraries.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #38a169;">
    <div class="icon-circle ic-green" style="flex-shrink:0;">▶️</div>
    <div>
      <div class="slide-h3">Running Python Programs</div>
      <div class="small-text">REPL, script files (.py), and IDEs like VS Code &amp; PyCharm.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #dd6b20;">
    <div class="icon-circle ic-orange" style="flex-shrink:0;">📐</div>
    <div>
      <div class="slide-h3">Python Syntax Rules</div>
      <div class="small-text">Indentation, comments, variables, data types, naming rules, case sensitivity.</div>
    </div>
  </div>

</div>

<div class="flex-col" style="gap:10px;">

  <div v-click class="card-navy" style="border-radius:10px;padding:14px 18px;">
    <div style="font-size:.7rem;text-transform:uppercase;letter-spacing:1px;color:rgba(255,255,255,.5);margin-bottom:8px;">Key Takeaways</div>
    <div style="display:flex;flex-direction:column;gap:7px;font-size:.76rem;color:#e2e8f0;line-height:1.5;">
      <div v-after>🔹 Python is beginner-friendly and industry-ready</div>
      <div v-after>🔹 No compilation — write and run instantly</div>
      <div v-after>🔹 Indentation is NOT optional in Python</div>
      <div v-after>🔹 Dynamic typing — no need to declare types</div>
      <div v-after>🔹 <span class="mono" style="color:#a8ff78;">print()</span> for output, <span class="mono" style="color:#a8ff78;">input()</span> for input</div>
    </div>
  </div>
</div>
</div>
  </template>
</Slide2>
