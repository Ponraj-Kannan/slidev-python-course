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

.slidev-layout {
  font-family: 'Nunito', sans-serif;
  background: var(--bg);
  color: var(--navy);
}

/* ── Top navbar ──────────────────────────────────────────── */
.slide-navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 0 12px 0;
  margin-bottom: 14px;
  border-bottom: 1px solid var(--red);
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
.card-red    { background: var(--red-soft);  border: 1px solid var(--red); border-radius: var(--radius); padding: 14px 18px; }
.card-navy   { background: #f0f4ff; color: var(--navy); border: 1px solid #c5cde8; border-radius: var(--radius); padding: 14px 18px; }
.card-green  { background: #f0fff4; border: 1px solid var(--green); border-radius: var(--radius); padding: 14px 18px; }
.card-blue   { background: #ebf8ff; border: 1px solid var(--blue);  border-radius: var(--radius); padding: 14px 18px; }
.card-orange { background: #fffaf0; border: 1px solid var(--orange); border-radius: var(--radius); padding: 14px 18px; }

/* ── Pill ────────────────────────────────────────────────── */
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
.pill-yellow { background: #fffff0;          color: var(--yellow); }

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
  background: #f6f8fa;
  color: #2d7a00;
  font-family: 'Fira Code', monospace;
  font-size: 0.78rem;
  border-radius: var(--radius);
  padding: 14px 18px;
  border: 1px solid #c8e6c9;
  line-height: 1.7;
}
.output-box .prompt  { color: #0e6ead; }
.output-box .comment { color: #6b7280; }

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
}
.step-box.active { border-color: var(--red); background: var(--red-soft); color: var(--red-dark); }
.step-arrow { color: var(--muted); font-size: 1.1rem; font-weight: 900; }

/* ── Comparison table ────────────────────────────────────── */
.cmp-table { width: 100%; border-collapse: collapse; font-size: 0.75rem; }
.cmp-table th {
  background: var(--slate);
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
  background: #f0f4ff;
  color: var(--navy);
  border: 1px solid #c5cde8;
  border-radius: var(--radius-lg);
  padding: 20px 24px;
}
.activity-box .act-title {
  font-size: 1rem;
  font-weight: 800;
  color: var(--orange);
  margin-bottom: 10px;
}
.activity-box .act-task {
  background: #ffffff;
  border-radius: var(--radius);
  padding: 10px 14px;
  font-size: 0.78rem;
  margin-bottom: 8px;
  border: 1px solid #c5cde8;
}
.activity-box .hint {
  font-size: 0.68rem;
  color: var(--muted);
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
.syn-label    { font-size: 0.6rem; color: var(--muted); text-align: center; margin-top: 3px; font-family: 'Nunito', sans-serif; }

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
.slide-h1  { font-size: 1.5rem; font-weight: 900; color: var(--navy); line-height: 1.2; }
.slide-h2  { font-size: 1.1rem; font-weight: 800; color: var(--navy); }
.slide-h3  { font-size: 0.9rem; font-weight: 700; color: var(--navy-mid); }
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

/* ── Progress dots ────────────────────────────────────────── */
.topic-progress { display: flex; gap: 5px; align-items: center; }
.tp-dot { width: 28px; height: 6px; border-radius: 3px; background: var(--border); }
.tp-dot.active { background: var(--red); }
.tp-dot.done   { background: var(--red-dark); }

/* ── Trace table ─────────────────────────────────────────── */
.trace-table { width: 100%; border-collapse: collapse; font-size: 0.72rem; font-family: 'Fira Code', monospace; }
.trace-table th { background: var(--slate); color: #fff; padding: 6px 10px; text-align: center; font-weight: 700; }
.trace-table td { padding: 6px 10px; border-bottom: 1px solid var(--border); text-align: center; }
.trace-table tr:nth-child(even) td { background: #f7f8fc; }
.trace-table .hl { background: var(--red-soft); color: var(--red-dark); font-weight: 700; }

/* ── Flowchart nodes ──────────────────────────────────────── */
.flow-node {
  padding: 8px 16px;
  border-radius: 8px;
  font-size: 0.72rem;
  font-weight: 700;
  text-align: center;
  border: 2px solid transparent;
}
.flow-start  { background: var(--navy-mid); color: #fff; border-radius: 20px; }
.flow-cond   { background: #fffaf0; color: var(--orange); border-color: var(--orange); }
.flow-body   { background: var(--red-soft); color: var(--red-dark); border-color: var(--red); }
.flow-end    { background: #f0fff4; color: var(--green); border-color: var(--green); border-radius: 20px; }
.flow-arrow  { text-align: center; color: var(--muted); font-size: 1rem; font-weight: 900; line-height: 1; }

/* ── Memory box ──────────────────────────────────────────── */
.mem-box {
  border: 2px solid var(--border);
  border-radius: var(--radius);
  overflow: hidden;
  font-family: 'Fira Code', monospace;
  font-size: 0.72rem;
}
.mem-box .mem-header {
  background: var(--slate);
  color: #fff;
  padding: 4px 12px;
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 1px;
  text-transform: uppercase;
}
.mem-box .mem-row {
  display: flex;
  align-items: stretch;
  border-bottom: 1px solid var(--border);
}
.mem-box .mem-row:last-child { border-bottom: none; }
.mem-box .mem-addr {
  background: #f0f4ff;
  color: var(--navy-mid);
  padding: 6px 10px;
  font-size: 0.62rem;
  min-width: 80px;
  border-right: 1px solid var(--border);
  display: flex; align-items: center;
}
.mem-box .mem-name {
  background: var(--red-soft);
  color: var(--red-dark);
  padding: 6px 10px;
  font-weight: 700;
  min-width: 70px;
  border-right: 1px solid var(--border);
  display: flex; align-items: center;
}
.mem-box .mem-val {
  background: #f0fff4;
  color: var(--green);
  padding: 6px 12px;
  font-weight: 700;
  flex: 1;
  display: flex; align-items: center;
}
.mem-box .mem-type {
  background: #fffaf0;
  color: var(--orange);
  padding: 6px 10px;
  font-size: 0.62rem;
  min-width: 60px;
  border-left: 1px solid var(--border);
  display: flex; align-items: center;
}
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

<Slide2 topic="Introduction to Python">
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

<Slide2 topic="Getting Started with Python" starterCode='# write your code here'>
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">First Program</span> in Python🎉</div>

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
transition: fade
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Write your very first Python program! Use the <code>print()</code> function to display your name on the screen.' },
  {
    text: '<b>Expected Output:</b><br><code>My name is [Your Name]</code>'
  },
  {
    text: '<b>Note:</b> Use the <code>print()</code> function and pass your name as a <b>string</b> inside double quotes <code>" "</code>. Replace <code>[Your Name]</code> with your actual name. A string is any text written inside quotes.'
  },
  // { text: '<b>Hint:</b> Type <code>print("My name is John")</code> — Replace <code>John</code> with your own name — Run the program and your name should appear on screen!', highlight: true },
]
</script>

<Slide
  topic="Getting Started with Python"
  sub-topic="Practice problem"
  :contents="contents"
/>

---
transition: fade
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Use <b>multiple</b> <code>print()</code> statements to display your college name and current year on separate lines.' },
  {
    text: '<b>Expected Output:</b><br><code>I study at [Your College Name]</code><br><code>Year: [2024]</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> Each <code>print()</code> call automatically moves to a <b>new line</b> after printing. This means calling <code>print()</code> twice will produce two separate lines of output — no extra steps needed.'
  // },
  {
    text: '<b>Note:</b> Write <b>two separate</b> <code>print()</code> statements, one for your college name and one for the year. Replace <code>[Your College Name]</code> with your actual college name and <code>[2024]</code> with the current year. Each string must be wrapped in double quotes <code>" "</code>.'
  },
  // { text: '<b>Hint:</b> Type <code>print("I study at ABC College")</code> on the first line — Then <code>print("Year: 2024")</code> on the next line — Each print() moves to a new line automatically!', highlight: true },
]
</script>

<Slide
  topic="Getting Started with Python"
  sub-topic="Practice problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — INDENTATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Indentation</span> Matters!</div>

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

<Slide
  topic="Python Syntax"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---


<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — COMMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Comments">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">Comments</span></div>

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

<Slide
  topic="Python Comments"
  sub-topic="Test Yourself!"  
/>

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

<Slide2 topic="Dynamic Typing">
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

<Slide
  topic="Dynamic Typing"
  sub-topic="Test Yourself!"  
/>

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

<Slide
  topic="Getting Started with Python"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — INPUT / OUTPUT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Input & Output">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Input</span> &amp; <span class="highlight">Output</span></div>

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

<Slide2 topic="Python Keywords">
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

<Slide
  topic="Python Keywords"
  sub-topic="Test Yourself!"  
/>

---
theme: default
title: Python Variables & Data Types
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

<!-- ═══════════════════════════════════════════════════════
     SLIDE 1 — TITLE SLIDE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Fundamentals">
  <template #content>

<div style="display:flex;flex-direction:column;align-items:center;justify-content:center;height:100%;gap:18px;text-align:center;">

  <div style="background:var(--red);color:#fff;border-radius:12px;padding:8px 24px;font-size:0.7rem;font-weight:800;letter-spacing:2px;text-transform:uppercase;">Python Fundamentals</div>

  <div style="font-size:2.4rem;font-weight:900;color:var(--navy);line-height:1.15;">
    Variables, Naming Rules<br>&amp; <span style="color:var(--red);">Data Types</span>
  </div>

  <div style="font-size:0.85rem;color:var(--muted);max-width:520px;line-height:1.7;">
    Understanding how Python stores, names, and types data — the foundation of every program you write.
  </div>

  <div style="display:flex;gap:10px;flex-wrap:wrap;justify-content:center;margin-top:6px;">
    <span class="pill pill-red">Variables</span>
    <span class="pill pill-navy">Naming Rules</span>
    <span class="pill pill-blue">Data Types</span>
    <span class="pill pill-green">Memory Model</span>
    <span class="pill pill-orange">Best Practices</span>
  </div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 2 — INTRODUCTION TO VARIABLES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is a <span class="highlight">Variable?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">variable</strong> is a <strong style="color:var(--green);">named storage location</strong> in memory that holds a value. You can think of it as a labelled box that stores data your program can use and change.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Real-World Analogy:</strong> A variable is like a labelled jar — the label is the variable name, and what's inside the jar is the value.</div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;">
    <span style="color:#6b7280;"># Creating variables</span><br>
    <span style="color:#0e6ead;">name</span> = <span style="color:#2d7a00;">"Alice"</span><br>
    <span style="color:#0e6ead;">age</span> = <span style="color:#b45309;">20</span><br>
    <span style="color:#0e6ead;">marks</span> = <span style="color:#b45309;">95.5</span>
  </div>

  <div v-click class="card card-green">
    <div class="small-text"><strong>Key idea:</strong> Variables let you store data with a meaningful name so you can reuse it anywhere in your program.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Variable as a Labelled Box</div>

  <div v-after style="display:flex;flex-direction:column;gap:8px;">
    <div style="display:flex;align-items:center;gap:10px;">
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:10px;padding:10px 18px;min-width:80px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Label</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--red-dark);font-size:.85rem;">name</div>
      </div>
      <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">→</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:10px;padding:10px 18px;flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Value</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--green);font-size:.85rem;">"Alice"</div>
      </div>
    </div>
    <div style="display:flex;align-items:center;gap:10px;">
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:10px;padding:10px 18px;min-width:80px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Label</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--red-dark);font-size:.85rem;">age</div>
      </div>
      <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">→</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:10px;padding:10px 18px;flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Value</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--green);font-size:.85rem;">20</div>
      </div>
    </div>
    <div style="display:flex;align-items:center;gap:10px;">
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:10px;padding:10px 18px;min-width:80px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Label</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--red-dark);font-size:.85rem;">marks</div>
      </div>
      <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">→</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:10px;padding:10px 18px;flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Value</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--green);font-size:.85rem;">95.5</div>
      </div>
    </div>
  </div>

  <div v-click class="card card-blue" style="margin-top:4px;">
    <div class="small-text"><strong>Python is dynamic:</strong> You do NOT need to declare a type — Python figures it out automatically!</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 3 — WHAT HAPPENS WHEN A VARIABLE IS CREATED
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">What Happens When a Variable is <span class="highlight">Created?</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Assignment Statement</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.82rem;line-height:2.2;">
    <span style="color:#0e6ead;">score</span> <span style="color:#c49a00;">=</span> <span style="color:#b45309;">42</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Step-by-Step: What Python Does</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div style="display:flex;align-items:flex-start;gap:10px;" v-click>
      <div style="background:var(--red);color:#fff;border-radius:50%;width:24px;height:24px;display:flex;align-items:center;justify-content:center;font-size:.7rem;font-weight:800;flex-shrink:0;">1</div>
      <div class="body-text"><strong>Evaluates</strong> the right side: the value <span class="mono" style="color:var(--green);">42</span> is created in memory.</div>
    </div>
    <div style="display:flex;align-items:flex-start;gap:10px;" v-click>
      <div style="background:var(--blue);color:#fff;border-radius:50%;width:24px;height:24px;display:flex;align-items:center;justify-content:center;font-size:.7rem;font-weight:800;flex-shrink:0;">2</div>
      <div class="body-text"><strong>Allocates memory</strong> at a specific address (e.g. <span class="mono" style="color:var(--muted);">0x7f3a</span>) to store the value.</div>
    </div>
    <div style="display:flex;align-items:flex-start;gap:10px;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:50%;width:24px;height:24px;display:flex;align-items:center;justify-content:center;font-size:.7rem;font-weight:800;flex-shrink:0;">3</div>
      <div class="body-text"><strong>Binds the name</strong> <span class="mono" style="color:var(--red-dark);">score</span> to that memory address — the name now <em>points</em> to the value.</div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:4px;">
    <div>In Python, variables are <strong>references</strong> (pointers) to objects in memory — not containers that hold values directly.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Memory Visualization</div>

  <div v-after class="mem-box">
    <div class="mem-header">Python Memory (RAM)</div>
    <div class="mem-row">
      <div class="mem-addr">0x7f3a</div>
      <div class="mem-name">score</div>
      <div class="mem-val">42</div>
      <div class="mem-type">int</div>
    </div>
  </div>

  <div v-click style="display:flex;flex-direction:column;align-items:center;gap:4px;margin-top:8px;">
    <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:8px;padding:8px 20px;font-family:'Fira Code',monospace;font-size:.78rem;font-weight:700;color:#2b6cb0;">score</div>
    <div style="font-size:.65rem;color:var(--muted);">variable name (label)</div>
    <div style="color:var(--muted);font-size:1.2rem;">↓</div>
    <div style="background:#f0f4ff;border:2px solid var(--navy-mid);border-radius:8px;padding:4px 14px;font-size:.62rem;color:var(--navy-mid);font-family:'Fira Code',monospace;">0x7f3a (memory address)</div>
    <div style="color:var(--muted);font-size:1.2rem;">↓</div>
    <div style="background:#f0fff4;border:2px solid var(--green);border-radius:8px;padding:8px 20px;font-family:'Fira Code',monospace;font-size:.85rem;font-weight:700;color:var(--green);">42</div>
    <div style="font-size:.65rem;color:var(--muted);">actual value (int object)</div>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px;">
    <div class="small-text">Use <span class="mono">id(score)</span> in Python to see the actual memory address of any variable!</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — VARIABLE DECLARATION & ASSIGNMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Variable <span class="highlight">Declaration</span> &amp; <span class="highlight">Assignment</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Syntax Structure</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px;font-family:'Fira Code',monospace;font-size:.85rem;line-height:2.2;">
    <span style="color:#0e6ead;">variable_name</span> <span style="color:#c49a00;">=</span> <span style="color:#2d7a00;">value</span>
  </div>

  <div v-click style="margin-top:6px;display:flex;flex-direction:column;gap:6px;border:1px solid #e1e4e8;padding:10px;border-radius:10px;">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-varname">variable_name</span>
      <span class="body-text">The label/identifier for the stored value</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-operator">=</span>
      <span class="body-text">Assignment operator (not equality!)</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-value">value</span>
      <span class="body-text">The data to store (number, text, etc.)</span>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div><strong>Note:</strong> In Python, <span class="mono">=</span> means <em>assignment</em>. It means "store this value". It does NOT mean "is equal to" like in math.</div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Assignment Flow</div>
  <div v-after style="display:flex;align-items:center;gap:6px;flex-wrap:wrap;">
    <div class="step-box active">Write Name</div>
    <div class="step-arrow">→</div>
    <div class="step-box active">= operator</div>
    <div class="step-arrow">→</div>
    <div class="step-box active">Provide Value</div>
    <div class="step-arrow">→</div>
    <div class="step-box" style="border-color:var(--green);background:#f0fff4;color:var(--green);">Stored!</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># Integer</span><br>
    <span style="color:#0e6ead;">age</span> <span style="color:#c49a00;">=</span> <span style="color:#b45309;">25</span><br>
    <span style="color:#6b7280;"># Float</span><br>
    <span style="color:#0e6ead;">price</span> <span style="color:#c49a00;">=</span> <span style="color:#b45309;">99.99</span><br>
    <span style="color:#6b7280;"># String</span><br>
    <span style="color:#0e6ead;">city</span> <span style="color:#c49a00;">=</span> <span style="color:#2d7a00;">"Chennai"</span><br>
    <span style="color:#6b7280;"># Boolean</span><br>
    <span style="color:#0e6ead;">is_student</span> <span style="color:#c49a00;">=</span> <span style="color:#ef5050;">True</span>
  </div>

  <div v-click class="mem-box" style="margin-top:6px;">
    <div class="mem-header">Memory After Assignment</div>
    <div class="mem-row">
      <div class="mem-name">age</div>
      <div class="mem-val">25</div>
      <div class="mem-type">int</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">price</div>
      <div class="mem-val">99.99</div>
      <div class="mem-type">float</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">city</div>
      <div class="mem-val">"Chennai"</div>
      <div class="mem-type">str</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">is_student</div>
      <div class="mem-val">True</div>
      <div class="mem-type">bool</div>
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
     SLIDE 5 — MULTIPLE & SAME VALUE ASSIGNMENT + REASSIGNMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Multiple</span> Assignment &amp; <span class="highlight">Reassignment</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-navy">Multiple Variable Assignment</span>
  </div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># Assign different values in one line</span><br>
    <span style="color:#0e6ead;">x</span>, <span style="color:#c49a00;">y</span>, <span style="color:#2d7a00;">z</span> <span style="color:#ef5050;">=</span> <span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>, <span style="color:#c49a00;">y</span>, <span style="color:#2d7a00;">z</span>) <span style="color:#6b7280;"># 10 20 30</span>
  </div>
  <div v-click class="output-box" style="font-size:.72rem;">10 &nbsp; 20 &nbsp; 30</div>

  <div v-click style="display:flex;gap:8px;align-items:center;margin-top:8px;">
    <span class="pill pill-green">Same Value to Multiple Variables</span>
  </div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># All three get the same value</span><br>
    <span style="color:#0e6ead;">a</span> = <span style="color:#c49a00;">b</span> = <span style="color:#2d7a00;">c</span> = <span style="color:#b45309;">100</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#c49a00;">b</span>, <span style="color:#2d7a00;">c</span>) <span style="color:#6b7280;"># 100 100 100</span>
  </div>
  <div v-click class="output-box" style="font-size:.72rem;">100 &nbsp; 100 &nbsp; 100</div>

</div>

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-red">Variable Reassignment</span>
  </div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">score</span> = <span style="color:#b45309;">50</span>   <span style="color:#6b7280;"># first assignment</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">score</span>) <span style="color:#6b7280;"># 50</span><br>
    <span style="color:#0e6ead;">score</span> = <span style="color:#b45309;">95</span>   <span style="color:#6b7280;"># reassignment</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">score</span>) <span style="color:#6b7280;"># 95</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Reassignment Memory Diagram</div>
    <div style="display:flex;gap:12px;align-items:flex-start;">
      <div style="flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);margin-bottom:4px;">Before</div>
        <div class="mem-box">
          <div class="mem-row">
            <div class="mem-name">score</div>
            <div class="mem-val">50</div>
          </div>
        </div>
      </div>
      <div style="font-size:1.4rem;color:var(--muted);padding-top:20px;">→</div>
      <div style="flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);margin-bottom:4px;">After score = 95</div>
        <div class="mem-box">
          <div class="mem-row">
            <div class="mem-name">score</div>
            <div class="mem-val" style="color:var(--orange);">95</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Python can also <strong>change the type</strong> on reassignment: <span class="mono">x = 5</span> then <span class="mono">x = "hello"</span> is perfectly valid!</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 6 — DELETING & SWAPPING VARIABLES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Deleting</span> &amp; <span class="highlight">Swapping</span> Variables</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-red">Deleting a Variable — del</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">10</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>) <span style="color:#6b7280;"># 10</span><br>
    <span style="color:#ef5050;">del</span> <span style="color:#0e6ead;">x</span>    <span style="color:#6b7280;"># removes the variable</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>) <span style="color:#6b7280;"># NameError!</span>
  </div>

  <div v-click class="callout callout-danger">
    <div>After <span class="mono" style="color:var(--red-dark);">del x</span>, accessing <span class="mono">x</span> raises a <strong>NameError</strong> — the name no longer exists in memory.</div>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Memory After del</div>
    <div style="display:flex;gap:12px;align-items:center;">
      <div class="mem-box" style="flex:1;">
        <div class="mem-header">Before del x</div>
        <div class="mem-row">
          <div class="mem-name">x</div>
          <div class="mem-val">10</div>
          <div class="mem-type">int</div>
        </div>
      </div>
      <div style="font-size:1.4rem;color:var(--muted);">→</div>
      <div class="mem-box" style="flex:1;">
        <div class="mem-header">After del x</div>
        <div class="mem-row">
          <div style="padding:8px 12px;font-size:.68rem;color:var(--muted);font-style:italic;flex:1;">x is gone — NameError</div>
        </div>
      </div>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-green">Swapping Variables</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">a</span> = <span style="color:#b45309;">5</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">10</span><br>
    <span style="color:#6b7280;"># Python's elegant one-liner swap</span><br>
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#0e6ead;">b</span>, <span style="color:#0e6ead;">a</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>) <span style="color:#6b7280;"># 10  5</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">10 &nbsp; 5</div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Swap Visualization</div>
    <div style="display:flex;gap:8px;align-items:center;flex-wrap:wrap;">
      <div style="text-align:center;">
        <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">a = 5</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">Before</div>
      </div>
      <div style="font-size:1.2rem;color:var(--muted);">⇄</div>
      <div style="text-align:center;">
        <div style="background:#f0fff4;border:2px solid var(--green);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">b = 10</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">Before</div>
      </div>
      <div style="color:var(--muted);font-size:1rem;font-weight:700;">→</div>
      <div style="text-align:center;">
        <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">a = 10</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">After</div>
      </div>
      <div style="font-size:1.2rem;color:var(--muted);">⇄</div>
      <div style="text-align:center;">
        <div style="background:#f0fff4;border:2px solid var(--green);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">b = 5</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">After</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div>Python's tuple unpacking makes swapping <strong>a single line</strong> — no temporary variable needed, unlike other languages!</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — VARIABLE NAMING RULES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Variable Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Rules for <span class="highlight">Naming Variables</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">The Rules</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 1</div>
      <div class="body-text">Must start with a <strong>letter</strong> (a–z, A–Z) or an <strong>underscore</strong> ( _ )</div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 2</div>
      <div class="body-text">Can contain letters, digits (0–9), and underscores — <strong>no spaces</strong></div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 3</div>
      <div class="body-text"><strong>Cannot start with a digit</strong> — <span class="mono" style="color:var(--red-dark);">2name</span> is invalid</div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 4</div>
      <div class="body-text"><strong>No special characters</strong>: @, #, $, !, -, spaces are not allowed</div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--red);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 5</div>
      <div class="body-text"><strong>Cannot be a reserved keyword</strong> — e.g. <span class="mono" style="color:var(--red-dark);">for</span>, <span class="mono" style="color:var(--red-dark);">if</span>, <span class="mono" style="color:var(--red-dark);">class</span></div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--blue);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 6</div>
      <div class="body-text">Variable names are <strong>case-sensitive</strong> — <span class="mono">Name</span> ≠ <span class="mono">name</span></div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Valid vs Invalid Names</div>

  <div >
    <table class="cmp-table">
      <thead v-click>
        <tr><th>Name</th><th>Valid?</th><th>Reason</th></tr>
      </thead>
      <tbody>
        <tr v-click><td class="mono">student_name</td><td class="yes">✔ Valid</td><td>Letters + underscore</td></tr>
        <tr v-click><td class="mono">_age</td><td class="yes">✔ Valid</td><td>Starts with underscore</td></tr>
        <tr v-click><td class="mono">score2</td><td class="yes">✔ Valid</td><td>Letter first, digit after</td></tr>
        <tr v-click><td class="mono">2score</td><td class="no">✘ Invalid</td><td>Starts with digit</td></tr>
        <tr v-click><td class="mono">my-name</td><td class="no">✘ Invalid</td><td>Contains hyphen</td></tr>
        <tr v-click><td class="mono">for</td><td class="no">✘ Invalid</td><td>Reserved keyword</td></tr>
        <tr v-click><td class="mono">my name</td><td class="no">✘ Invalid</td><td>Contains space</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — CASE SENSITIVITY & RESERVED KEYWORDS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Variable Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Case Sensitivity</span> &amp; Reserved <span class="highlight">Keywords</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      Python is <strong style="color:var(--red);">case-sensitive</strong>. <span class="mono">Name</span>, <span class="mono">name</span>, and <span class="mono">NAME</span> are <strong>three different variables</strong>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">name</span> = <span style="color:#2d7a00;">"Alice"</span><br>
    <span style="color:#c49a00;">Name</span> = <span style="color:#2d7a00;">"Bob"</span><br>
    <span style="color:#ef5050;">NAME</span> = <span style="color:#2d7a00;">"Charlie"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#c49a00;">Name</span>, <span style="color:#ef5050;">NAME</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">Alice &nbsp; Bob &nbsp; Charlie</div>

  <div v-click class="callout callout-warn" style="margin-top:4px;">
    <div><strong>Beginner Trap:</strong> Writing <span class="mono">Print()</span> instead of <span class="mono" style="color:var(--green);">print()</span> gives a NameError because Python is case-sensitive!</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Python Reserved Keywords</div>
  <div v-click class="small-text" style="margin-bottom:6px;">These cannot be used as variable names</div>

  <div style="display:flex;gap:4px;flex-wrap:wrap;">
    <span v-click style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">False</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">True</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">None</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">and</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">or</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">not</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">if</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">elif</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">else</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">for</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">while</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">break</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">continue</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">pass</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">def</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">class</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">return</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">import</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">from</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">in</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">is</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">lambda</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">try</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">except</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">with</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">del</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">global</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">yield</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">raise</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">assert</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:8px;">
    <div>Run <span class="mono">help("keywords")</span> in Python to see the full list of all reserved keywords.</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — NAMING CONVENTIONS & BEST PRACTICES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Variable Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Naming <span class="highlight">Conventions</span> &amp; Best Practices</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Python Naming Conventions</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-green">snake_case</span>
        <div class="body-text">Use for variables & functions — <span class="mono" style="color:var(--green);">student_name</span>, <span class="mono" style="color:var(--green);">total_score</span></div>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-navy">UPPER_CASE</span>
        <div class="body-text">Use for constants — <span class="mono" style="color:var(--navy-mid);">MAX_SIZE</span>, <span class="mono" style="color:var(--navy-mid);">PI</span></div>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-blue">PascalCase</span>
        <div class="body-text">Use for class names — <span class="mono" style="color:var(--blue);">StudentRecord</span>, <span class="mono" style="color:var(--blue);">BankAccount</span></div>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-orange">_single</span>
        <div class="body-text">Leading underscore = internal/private use — <span class="mono" style="color:var(--orange);">_helper</span></div>
      </div>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Good vs Bad Naming</div>

  <div>
    <table class="cmp-table">
      <thead v-click>
        <tr><th>❌ Bad Name</th><th>✔ Good Name</th><th>Why Better</th></tr>
      </thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);">x</td><td class="mono" style="color:var(--green);">student_age</td><td>Descriptive</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">a1</td><td class="mono" style="color:var(--green);">total_marks</td><td>Meaningful</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">myVar</td><td class="mono" style="color:var(--green);">my_var</td><td>PEP 8 style</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">temp</td><td class="mono" style="color:var(--green);">temperature_c</td><td>Clear unit</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">data2</td><td class="mono" style="color:var(--green);">sales_data</td><td>Context clear</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-success" style="margin-top:8px;">
    <div><strong>Golden Rule:</strong> A good variable name tells you <em>what</em> it stores without needing a comment. Code is read more than it is written!</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — INTRODUCTION TO DATA TYPES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Introduction to <span class="highlight">Data Types</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">data type</strong> tells Python <strong style="color:var(--green);">what kind of value</strong> a variable holds and what <strong>operations</strong> can be performed on it.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Why it matters:</strong> You can add two numbers, but not a number and a word. Data types enforce this — they prevent nonsense operations.</div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># Python knows the type automatically</span><br>
    <span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">10</span>          <span style="color:#6b7280;"># int</span><br>
    <span style="color:#0e6ead;">y</span> = <span style="color:#b45309;">3.14</span>       <span style="color:#6b7280;"># float</span><br>
    <span style="color:#0e6ead;">z</span> = <span style="color:#2d7a00;">"hello"</span>     <span style="color:#6b7280;"># str</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">x</span>))  <span style="color:#6b7280;"># &lt;class 'int'&gt;</span>
  </div>

</div>

<div class="flex-col">
  <div class="section-label" v-click>Python Data Types Overview</div>

  <div style="display:flex;flex-direction:column;gap:5px;">
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-red">int</span>
      <span class="pill pill-red">float</span>
      <span class="pill pill-red">complex</span>
      <span class="small-text" style="align-self:center;">— Numeric</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-blue">str</span>
      <span class="pill pill-blue">list</span>
      <span class="pill pill-blue">tuple</span>
      <span class="small-text" style="align-self:center;">— Sequence</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-green">bool</span>
      <span class="small-text" style="align-self:center;">— Boolean</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-orange">set</span>
      <span class="small-text" style="align-self:center;">— Set</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-navy">dict</span>
      <span class="small-text" style="align-self:center;">— Dictionary</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill" style="background:#f0e6ff;color:#6b21a8;">None</span>
      <span class="small-text" style="align-self:center;">— NoneType</span>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Use <span class="mono">type(variable)</span> to check the data type of any variable at any time.</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 11 — NUMERIC TYPES: int
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Numeric Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Numeric Type — <span class="highlight">int</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">int</strong> stores <strong>whole numbers</strong> — positive, negative, or zero — with no decimal point. No size limit in Python!
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Syntax &amp; Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">age</span>       = <span style="color:#b45309;">25</span><br>
    <span style="color:#0e6ead;">population</span> = <span style="color:#b45309;">1400000000</span><br>
    <span style="color:#0e6ead;">temp</span>       = <span style="color:#b45309;">-10</span><br>
    <span style="color:#0e6ead;">zero</span>       = <span style="color:#b45309;">0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">age</span>)) <span style="color:#6b7280;"># &lt;class 'int'&gt;</span>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Operations</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#b45309;">10</span> + <span style="color:#b45309;">3</span>  = <span style="color:#2d7a00;">13</span> &nbsp;&nbsp;
    <span style="color:#b45309;">10</span> - <span style="color:#b45309;">3</span>  = <span style="color:#2d7a00;">7</span><br>
    <span style="color:#b45309;">10</span> * <span style="color:#b45309;">3</span>  = <span style="color:#2d7a00;">30</span> &nbsp;&nbsp;
    <span style="color:#b45309;">10</span> // <span style="color:#b45309;">3</span> = <span style="color:#2d7a00;">3</span> <span style="color:#6b7280;">(floor div)</span><br>
    <span style="color:#b45309;">10</span> % <span style="color:#b45309;">3</span>  = <span style="color:#2d7a00;">1</span> &nbsp;&nbsp;
    <span style="color:#b45309;">2</span> ** <span style="color:#b45309;">10</span> = <span style="color:#2d7a00;">1024</span>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Memory Visualization</div>
  <div v-after class="mem-box">
    <div class="mem-header">Variable → Type → Value</div>
    <div class="mem-row">
      <div class="mem-name">age</div>
      <div class="mem-val">25</div>
      <div class="mem-type">int</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">temp</div>
      <div class="mem-val">-10</div>
      <div class="mem-type">int</div>
    </div>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Number Line Visualization</div>
    <div style="background:#f7f8fc;border-radius:8px;padding:10px 14px;border:1px solid var(--border);">
      <div style="display:flex;align-items:center;gap:2px;overflow-x:auto;">
        <div style="font-size:.62rem;color:var(--muted);font-family:'Fira Code',monospace;">…</div>
        <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:#2b6cb0;">-3</div>
        <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:#2b6cb0;">-2</div>
        <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:#2b6cb0;">-1</div>
        <div style="background:var(--navy-mid);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:#fff;">0</div>
        <div style="background:#f0fff4;border:2px solid var(--green);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:var(--green);">1</div>
        <div style="background:#f0fff4;border:1px solid var(--green);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:var(--green);">2</div>
        <div style="background:#f0fff4;border:1px solid var(--green);border-radius:4px;padding:3px 7px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;color:var(--green);">3</div>
        <div style="font-size:.62rem;color:var(--muted);font-family:'Fira Code',monospace;">…∞</div>
      </div>
      <div style="font-size:.6rem;color:var(--muted);margin-top:4px;">int spans all whole numbers — no decimal, no limit</div>
    </div>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px;">
    <div class="small-text"><strong>Real-world use:</strong> Counting items, loop counters, student roll numbers, population, scores</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — NUMERIC TYPES: float & complex
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Numeric Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Numeric Types — <span class="highlight">float</span> &amp; <span class="highlight">complex</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-blue">float</span>
    <span class="body-text">Numbers with a decimal point</span>
  </div>

  <div v-after class="card-navy" style="border-radius:8px;font-size:.78rem;line-height:1.5;color:var(--slate);">
    Stores <strong>real numbers</strong> — numbers with a fractional part. Used for measurements, prices, and scientific values.
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:4px;">
    <span style="color:#0e6ead;">price</span>  = <span style="color:#b45309;">99.99</span><br>
    <span style="color:#0e6ead;">pi</span>     = <span style="color:#b45309;">3.14159</span><br>
    <span style="color:#0e6ead;">weight</span> = <span style="color:#b45309;">-4.5</span><br>
    <span style="color:#0e6ead;">sci</span>    = <span style="color:#b45309;">1.5e3</span>   <span style="color:#6b7280;"># = 1500.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">pi</span>)) <span style="color:#6b7280;"># &lt;class 'float'&gt;</span>
  </div>

  <div v-click class="mem-box" style="margin-top:4px;">
    <div class="mem-header">float in Memory</div>
    <div class="mem-row">
      <div class="mem-name">price</div>
      <div class="mem-val">99.99</div>
      <div class="mem-type">float</div>
    </div>
  </div>

  <div v-click class="card card-green" style="margin-top:4px;">
    <div class="small-text"><strong>Real-world use:</strong> Prices, temperatures, GPS coordinates, scientific measurements</div>
  </div>

</div>

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-orange">complex</span>
    <span class="body-text">Numbers with real + imaginary part</span>
  </div>

  <div v-after class="card-orange" style="border-radius:8px;font-size:.78rem;line-height:1.5;color:var(--slate);">
    Stores <strong>complex numbers</strong> in the form <span class="mono">a + bj</span>. Used in engineering, physics, and signal processing.
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:4px;">
    <span style="color:#0e6ead;">c1</span> = <span style="color:#b45309;">3</span> + <span style="color:#b45309;">4j</span><br>
    <span style="color:#0e6ead;">c2</span> = <span style="color:#b45309;">2</span> - <span style="color:#b45309;">1j</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c1</span>.real)  <span style="color:#6b7280;"># 3.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c1</span>.imag)  <span style="color:#6b7280;"># 4.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">c1</span>)) <span style="color:#6b7280;"># &lt;class 'complex'&gt;</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Complex Number Visualization</div>
    <div style="background:#f7f8fc;border-radius:8px;padding:10px 14px;border:1px solid var(--border);font-size:.72rem;">
      <div style="display:flex;gap:8px;align-items:center;font-family:'Fira Code',monospace;">
        <span style="background:var(--red-soft);color:var(--red-dark);border-radius:6px;padding:4px 12px;font-weight:700;">3</span>
        <span style="color:var(--muted);">+</span>
        <span style="background:#ebf8ff;color:#2b6cb0;border-radius:6px;padding:4px 12px;font-weight:700;">4j</span>
      </div>
      <div style="display:flex;gap:30px;margin-top:4px;">
        <div style="font-size:.6rem;color:var(--red-dark);font-weight:700;">Real part</div>
        <div style="font-size:.6rem;color:#2b6cb0;font-weight:700;">Imaginary part</div>
      </div>
    </div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Real-world use:</strong> Signal processing, electrical engineering, physics simulations</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — SEQUENCE TYPE: str
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Sequence Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Sequence Type — <span class="highlight">str</span> (String)</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">str</strong> stores a <strong>sequence of characters</strong> — text enclosed in single (<span class="mono">'</span>) or double (<span class="mono">"</span>) quotes.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">name</span>     = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#0e6ead;">greeting</span> = <span style="color:#2d7a00;">'Hello!'</span><br>
    <span style="color:#0e6ead;">multi</span>    = <span style="color:#2d7a00;">"""Line 1<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Line 2"""</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>[<span style="color:#b45309;">0</span>])   <span style="color:#6b7280;"># P</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">name</span>)) <span style="color:#6b7280;"># 6</span>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Character Index Visualization</div>
  <div v-after style="display:flex;gap:3px;flex-wrap:wrap;">
    <div v-click style="text-align:center;">
      <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);font-size:.85rem;">P</div>
      <div style="font-size:.55rem;color:var(--muted);">0</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.85rem;">y</div>
      <div style="font-size:.55rem;color:var(--muted);">1</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);font-size:.85rem;">t</div>
      <div style="font-size:.55rem;color:var(--muted);">2</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#fffaf0;border:2px solid var(--orange);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);font-size:.85rem;">h</div>
      <div style="font-size:.55rem;color:var(--muted);">3</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);font-size:.85rem;">o</div>
      <div style="font-size:.55rem;color:var(--muted);">4</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.85rem;">n</div>
      <div style="font-size:.55rem;color:var(--muted);">5</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common String Operations</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Hello World"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.upper())    <span style="color:#6b7280;"># HELLO WORLD</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.lower())    <span style="color:#6b7280;"># hello world</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>:<span style="color:#b45309;">5</span>])     <span style="color:#6b7280;"># Hello</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.replace(<span style="color:#2d7a00;">"World"</span>, <span style="color:#2d7a00;">"Python"</span>))<br>
    <span style="color:#6b7280;"># Hello Python</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;margin-top:4px;">
    HELLO WORLD<br>
    hello world<br>
    Hello<br>
    Hello Python
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Strings are <strong>immutable</strong> — you cannot change a character in-place. You must create a new string.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="small-text"><strong>Real-world use:</strong> Names, messages, file paths, user input, text processing</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — SEQUENCE TYPE: list
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Sequence Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Sequence Type — <span class="highlight">list</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">list</strong> stores an <strong>ordered, mutable collection</strong> of items. Items can be of different types. Defined using square brackets <span class="mono">[ ]</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <span style="color:#0e6ead;">scores</span> = [<span style="color:#b45309;">85</span>, <span style="color:#b45309;">92</span>, <span style="color:#b45309;">78</span>, <span style="color:#b45309;">95</span>]<br>
    <span style="color:#0e6ead;">mixed</span>  = [<span style="color:#b45309;">1</span>, <span style="color:#2d7a00;">"hello"</span>, <span style="color:#ef5050;">True</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fruits</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># apple</span><br>
    <span style="color:#0e6ead;">fruits</span>[<span style="color:#b45309;">1</span>] = <span style="color:#2d7a00;">"mango"</span> <span style="color:#6b7280;"># mutable!</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">List Index Visualization</div>
    <div style="display:flex;gap:3px;align-items:center;flex-wrap:wrap;">
      <div style="text-align:center;"><div style="background:var(--red-soft);border:2px solid var(--red);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);font-size:.72rem;">"apple"</div><div style="font-size:.55rem;color:var(--muted);">index 0</div></div>
      <div style="text-align:center;"><div style="background:#f0fff4;border:2px solid var(--green);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);font-size:.72rem;">"banana"</div><div style="font-size:.55rem;color:var(--muted);">index 1</div></div>
      <div style="text-align:center;"><div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.72rem;">"cherry"</div><div style="font-size:.55rem;color:var(--muted);">index 2</div></div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common List Operations</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#0e6ead;">nums</span> = [<span style="color:#b45309;">3</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">5</span>]<br>
    <span style="color:#0e6ead;">nums</span>.append(<span style="color:#b45309;">9</span>)   <span style="color:#6b7280;"># add to end</span><br>
    <span style="color:#0e6ead;">nums</span>.remove(<span style="color:#b45309;">1</span>)   <span style="color:#6b7280;"># remove first 1</span><br>
    <span style="color:#0e6ead;">nums</span>.sort()       <span style="color:#6b7280;"># sort in place</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">nums</span>))  <span style="color:#6b7280;"># 5</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">nums</span>[<span style="color:#b45309;">-1</span>])   <span style="color:#6b7280;"># last element</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;margin-top:4px;">
    5 &nbsp; &nbsp; 9
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.68rem;">
      <thead v-click><tr><th>Feature</th><th>list</th></tr></thead>
      <tbody>
        <tr v-click><td>Ordered</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Mutable (changeable)</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Allows duplicates</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Mixed types allowed</td><td class="yes">Yes</td></tr>
      </tbody>
    </table>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — SEQUENCE TYPE: tuple
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Sequence Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Sequence Type — <span class="highlight">tuple</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">tuple</strong> stores an <strong>ordered, immutable collection</strong> of items. Once created, the values <strong>cannot be changed</strong>. Defined using parentheses <span class="mono">( )</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">coords</span>  = (<span style="color:#b45309;">10.5</span>, <span style="color:#b45309;">20.3</span>)<br>
    <span style="color:#0e6ead;">rgb</span>     = (<span style="color:#b45309;">255</span>, <span style="color:#b45309;">128</span>, <span style="color:#b45309;">0</span>)<br>
    <span style="color:#0e6ead;">single</span>  = (<span style="color:#b45309;">42</span>,)   <span style="color:#6b7280;"># note trailing comma</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">coords</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># 10.5</span><br>
    <span style="color:#6b7280;"># coords[0] = 5  → TypeError!</span>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div>Tuples are <strong>immutable</strong> — any attempt to modify them raises a <span class="mono">TypeError</span>. This is intentional and useful!</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">list vs tuple Comparison</div>

  <div >
    <table class="cmp-table">
      <thead>
        <tr v-click><th>Feature</th><th>list</th><th>tuple</th></tr>
      </thead>
      <tbody>
        <tr v-click><td>Syntax</td><td class="mono">[ ]</td><td class="mono">( )</td></tr>
        <tr v-click><td>Mutable</td><td class="yes">Yes</td><td class="no">No</td></tr>
        <tr v-click><td>Ordered</td><td class="yes">Yes</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Allows duplicates</td><td class="yes">Yes</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Speed</td><td>Slower</td><td class="yes">Faster</td></tr>
        <tr v-click><td>Use case</td><td>Dynamic data</td><td>Fixed data</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Tuple Memory Visualization</div>
    <div style="display:flex;gap:3px;align-items:center;">
      <div style="text-align:center;"><div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.78rem;">10.5</div><div style="font-size:.55rem;color:var(--muted);">[0] 🔒</div></div>
      <div style="text-align:center;"><div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.78rem;">20.3</div><div style="font-size:.55rem;color:var(--muted);">[1] 🔒</div></div>
      <div style="font-size:.68rem;color:var(--red-dark);font-weight:700;margin-left:6px;">immutable</div>
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
     SLIDE 16 — BOOLEAN TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Boolean Type — <span class="highlight">bool</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">bool</strong> stores only <strong>two values</strong>: <span class="mono" style="color:var(--green);">True</span> or <span class="mono" style="color:var(--red-dark);">False</span>. Used for conditions and logical decisions.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">is_raining</span> = <span style="color:#ef5050;">True</span><br>
    <span style="color:#0e6ead;">is_adult</span>   = <span style="color:#b45309;">18</span> >= <span style="color:#b45309;">18</span>   <span style="color:#6b7280;"># True</span><br>
    <span style="color:#0e6ead;">is_even</span>    = <span style="color:#b45309;">7</span> % <span style="color:#b45309;">2</span> == <span style="color:#b45309;">0</span>  <span style="color:#6b7280;"># False</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">is_raining</span>)) <span style="color:#6b7280;"># &lt;class 'bool'&gt;</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">bool Visualization</div>
    <div style="display:flex;gap:12px;">
      <div style="background:#f0fff4;border:3px solid var(--green);border-radius:12px;padding:14px 24px;text-align:center;flex:1;">
        <div style="font-family:'Fira Code',monospace;font-size:1.2rem;font-weight:800;color:var(--green);">True</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:4px;">= 1 in int</div>
      </div>
      <div style="background:var(--red-soft);border:3px solid var(--red);border-radius:12px;padding:14px 24px;text-align:center;flex:1;">
        <div style="font-family:'Fira Code',monospace;font-size:1.2rem;font-weight:800;color:var(--red-dark);">False</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:4px;">= 0 in int</div>
      </div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Boolean in Conditions</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">logged_in</span> = <span style="color:#ef5050;">True</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">logged_in</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Welcome back!"</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;margin-top:4px;">Welcome back!</div>

  <div style="margin-top:8px;">
    <div  v-click class="section-label" style="margin-bottom:6px;">Truthy &amp; Falsy Values</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Value</th><th>bool(value)</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono">0, 0.0, ""</td><td class="no">False</td></tr>
        <tr v-click><td class="mono">None</td><td class="no">False</td></tr>
        <tr v-click><td class="mono">[], {}, ()</td><td class="no">False</td></tr>
        <tr v-click><td>Any non-zero number</td><td class="yes">True</td></tr>
        <tr v-click><td>Any non-empty string</td><td class="yes">True</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="card card-blue">
    <div class="small-text"><strong>Real-world use:</strong> Login state, flags, form validation, any yes/no decision</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — SET TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Set Type — <span class="highlight">set</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">set</strong> stores an <strong>unordered collection of unique items</strong>. Duplicates are automatically removed. Defined with curly braces <span class="mono">{ }</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">colors</span> = {<span style="color:#2d7a00;">"red"</span>, <span style="color:#2d7a00;">"blue"</span>, <span style="color:#2d7a00;">"green"</span>}<br>
    <span style="color:#6b7280;"># Duplicates removed automatically</span><br>
    <span style="color:#0e6ead;">nums</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">nums</span>) <span style="color:#6b7280;"># {1, 2, 3, 4}</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">nums</span>)) <span style="color:#6b7280;"># &lt;class 'set'&gt;</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;margin-top:4px;">{1, 2, 3, 4}</div>

  <div v-click style="margin-top:4px;">
    <div class="section-label" style="margin-bottom:6px;">Set Operations</div>
    <div style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">A</span> = {<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">3</span>} &nbsp;<span style="color:#0e6ead;">B</span> = {<span style="color:#b45309;">3</span>,<span style="color:#b45309;">4</span>,<span style="color:#b45309;">5</span>}<br>
      <span style="color:#0e6ead;">A</span> | <span style="color:#0e6ead;">B</span> <span style="color:#6b7280;"># union: {1,2,3,4,5}</span><br>
      <span style="color:#0e6ead;">A</span> & <span style="color:#0e6ead;">B</span> <span style="color:#6b7280;"># intersection: {3}</span><br>
      <span style="color:#0e6ead;">A</span> - <span style="color:#0e6ead;">B</span> <span style="color:#6b7280;"># difference: {1,2}</span>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Set Uniqueness Visualization</div>

  <div v-after style="background:#f7f8fc;border-radius:10px;border:1px solid var(--border);padding:14px;">
    <div style="font-size:.65rem;color:var(--muted);margin-bottom:8px;font-family:'Fira Code',monospace;">Input: {1, 2, 2, 3, 3, 4}</div>
    <div style="display:flex;align-items:center;gap:6px;flex-wrap:wrap;margin-bottom:8px;">
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:#2b6cb0;">1</div>
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--red-dark);">2</div>
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--red-dark);">2 ✗</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--green);">3</div>
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--red-dark);">3 ✗</div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--orange);">4</div>
    </div>
    <div style="font-size:.7rem;color:var(--muted);">↓</div>
    <div style="font-size:.65rem;color:var(--muted);margin-top:4px;font-family:'Fira Code',monospace;">Result: {1, 2, 3, 4}  (duplicates removed)</div>
  </div>

  <div style="margin-top:8px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Feature</th><th>set</th></tr></thead>
      <tbody>
        <tr v-click><td>Ordered</td><td class="no">No</td></tr>
        <tr v-click><td>Allows duplicates</td><td class="no">No</td></tr>
        <tr v-click><td>Mutable</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Indexing</td><td class="no">No</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — DICTIONARY TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Dictionary Type — <span class="highlight">dict</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">dict</strong> stores data as <strong>key-value pairs</strong>. Keys must be unique. Access values using their key — like a real dictionary where a word is the key and definition is the value.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">student</span> = {<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Alice"</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"age"</span>:  <span style="color:#b45309;">21</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"marks"</span>: <span style="color:#b45309;">95.5</span></span>
    }<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"name"</span>])  <span style="color:#6b7280;"># Alice</span>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Key-Value Visualization</div>
  <div v-after style="display:flex;flex-direction:column;gap:4px;">
    <div style="display:flex;align-items:center;gap:8px;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">"name"</div>
      <div style="color:var(--muted);font-weight:700;">→</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--green);">"Alice"</div>
    </div>
    <div style="display:flex;align-items:center;gap:8px;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">"age"</div>
      <div style="color:var(--muted);font-weight:700;">→</div>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:#2b6cb0;">21</div>
    </div>
    <div style="display:flex;align-items:center;gap:8px;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">"marks"</div>
      <div style="color:var(--muted);font-weight:700;">→</div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--orange);">95.5</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common dict Operations</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># Add / update</span><br>
    <span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"grade"</span>] = <span style="color:#2d7a00;">"A"</span><br>
    <span style="color:#6b7280;"># Delete</span><br>
    <span style="color:#ef5050;">del</span> <span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"age"</span>]<br>
    <span style="color:#6b7280;"># Check key exists</span><br>
    <span style="color:#2d7a00;">"name"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">student</span>  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#6b7280;"># Iterate</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">k</span>, <span style="color:#0e6ead;">v</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">student</span>.items():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">k</span>, <span style="color:#2d7a00;">"→"</span>, <span style="color:#0e6ead;">v</span>)</span>
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Feature</th><th>dict</th></tr></thead>
      <tbody>
        <tr v-click><td>Ordered (Python 3.7+)</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Mutable</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Duplicate keys</td><td class="no">No</td></tr>
        <tr v-click><td>Duplicate values</td><td class="yes">Yes</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 19 — NONE TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">None Type — <span class="highlight">NoneType</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">None</strong> represents the <strong>absence of a value</strong> or a null/empty state. It is Python's way of saying "nothing here". There is only <strong>one</strong> None object in Python.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">result</span> = <span style="color:#ef5050;">None</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>)          <span style="color:#6b7280;"># None</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">result</span>))    <span style="color:#6b7280;"># &lt;class 'NoneType'&gt;</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span> <span style="color:#ef5050;">is</span> <span style="color:#ef5050;">None</span>) <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;margin-top:4px;">
    None<br>
    &lt;class 'NoneType'&gt;<br>
    True
  </div>

  <div v-click class="callout callout-warn" style="margin-top:4px;">
    <div>Always use <span class="mono">x <strong>is</strong> None</span> (not <span class="mono">x == None</span>) to check for None. This is the Pythonic best practice.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common Use Cases for None</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div v-click class="card" style="padding:10px 14px;">
      <div class="body-text"><strong>Function with no return value</strong></div>
      <div style="background:#f6f8fa;border-radius:6px;padding:8px;font-family:'Fira Code',monospace;font-size:.7rem;margin-top:6px;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#2d7a00;">greet</span>():<br>
        <span style="padding-left:16px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hello"</span>)</span>
        <span style="color:#0e6ead;">x</span> = <span style="color:#2d7a00;">greet</span>() <span style="color:#6b7280;"># x is None</span>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div class="body-text"><strong>Default parameter / placeholder</strong></div>
      <div style="background:#f6f8fa;border-radius:6px;padding:8px;font-family:'Fira Code',monospace;font-size:.7rem;margin-top:6px;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#2d7a00;">connect</span>(<span style="color:#0e6ead;">host</span>=<span style="color:#ef5050;">None</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">host</span> <span style="color:#ef5050;">is</span> <span style="color:#ef5050;">None</span>:</span>
        <span style="padding-left:32px;display:block;"><span style="color:#0e6ead;">host</span> = <span style="color:#2d7a00;">"localhost"</span></span>
      </div>
    </div>
  </div>

  <div style="margin-top:8px;">
    <div v-click class="section-label" style="margin-bottom:6px;">None vs False vs 0</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Value</th><th>bool()</th><th>Meaning</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:#6b21a8;">None</td><td class="no">False</td><td>No value at all</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">False</td><td class="no">False</td><td>Explicitly false</td></tr>
        <tr v-click><td class="mono" style="color:var(--orange);">0</td><td class="no">False</td><td>Numeric zero</td></tr>
        <tr v-click><td class="mono" style="color:var(--green);">True</td><td class="yes">True</td><td>Explicitly true</td></tr>
      </tbody>
    </table>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — DATA TYPE COMPARISON TABLE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Data Type <span class="highlight">Comparison</span> &amp; Hierarchy</div>

<div class="flex-col" style="gap:12px;">

  <div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead>
        <tr><th>Type</th><th>Category</th><th>Mutable</th><th>Ordered</th><th>Duplicates</th><th>Example</th></tr>
      </thead>
      <tbody>
        <tr v-click><td><span class="pill pill-red" style="font-size:.6rem;padding:2px 8px;">int</span></td><td>Numeric</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">42</td></tr>
        <tr v-click><td><span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">float</span></td><td>Numeric</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">3.14</td></tr>
        <tr v-click><td><span class="pill" style="background:#fffaf0;color:var(--orange);font-size:.6rem;padding:2px 8px;">complex</span></td><td>Numeric</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">2+3j</td></tr>
        <tr v-click><td><span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">str</span></td><td>Sequence</td><td class="no">No</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="mono" style="color:var(--green);">"hi"</td></tr>
        <tr v-click><td><span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">list</span></td><td>Sequence</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="mono" style="color:var(--green);">[1,2]</td></tr>
        <tr v-click><td><span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">tuple</span></td><td>Sequence</td><td class="no">No</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="mono" style="color:var(--green);">(1,2)</td></tr>
        <tr v-click><td><span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">bool</span></td><td>Boolean</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">True</td></tr>
        <tr v-click><td><span class="pill pill-orange" style="font-size:.6rem;padding:2px 8px;">set</span></td><td>Set</td><td class="yes">Yes</td><td class="no">No</td><td class="no">No</td><td class="mono" style="color:var(--green);">{1,2}</td></tr>
        <tr v-click><td><span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">dict</span></td><td>Mapping</td><td class="yes">Yes</td><td class="yes">Yes</td><td>Keys: No</td><td class="mono" style="color:var(--green);">{"k":v}</td></tr>
        <tr v-click><td><span class="pill" style="background:#f0e6ff;color:#6b21a8;font-size:.6rem;padding:2px 8px;">None</span></td><td>NoneType</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">None</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:8px;">Type Hierarchy Visual</div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;">
      <div style="background:#f0f4ff;border:1px solid #c5cde8;border-radius:10px;padding:8px 14px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;margin-bottom:4px;">NUMERIC</div>
        <div style="display:flex;gap:4px;">
          <span class="pill pill-red" style="font-size:.6rem;padding:2px 8px;">int</span>
          <span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">float</span>
          <span class="pill pill-orange" style="font-size:.6rem;padding:2px 8px;">complex</span>
        </div>
      </div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:10px;padding:8px 14px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;margin-bottom:4px;">SEQUENCE</div>
        <div style="display:flex;gap:4px;">
          <span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">str</span>
          <span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">list</span>
          <span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">tuple</span>
        </div>
      </div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:10px;padding:8px 14px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;margin-bottom:4px;">OTHER</div>
        <div style="display:flex;gap:4px;">
          <span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">bool</span>
          <span class="pill pill-orange" style="font-size:.6rem;padding:2px 8px;">set</span>
          <span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">dict</span>
          <span class="pill" style="background:#f0e6ff;color:#6b21a8;font-size:.6rem;padding:2px 8px;">None</span>
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
     SLIDE 21 — TYPE CHECKING & CONVERSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Type <span class="highlight">Checking</span> &amp; <span class="highlight">Conversion</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Checking Data Types</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;">
    <span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">42</span><br>
    <span style="color:#0e6ead;">y</span> = <span style="color:#2d7a00;">"hello"</span><br>
    <span style="color:#0e6ead;">z</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">x</span>))   <span style="color:#6b7280;"># &lt;class 'int'&gt;</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">y</span>))   <span style="color:#6b7280;"># &lt;class 'str'&gt;</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">isinstance</span>(<span style="color:#0e6ead;">z</span>, <span style="color:#ef5050;">list</span>)) <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Type Conversion (Casting)</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;">
    <span style="color:#0e6ead;">a</span> = <span style="color:#ef5050;">int</span>(<span style="color:#2d7a00;">"42"</span>)    <span style="color:#6b7280;"># str → int  : 42</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#ef5050;">float</span>(<span style="color:#b45309;">5</span>)    <span style="color:#6b7280;"># int → float: 5.0</span><br>
    <span style="color:#0e6ead;">c</span> = <span style="color:#ef5050;">str</span>(<span style="color:#b45309;">99</span>)     <span style="color:#6b7280;"># int → str  : "99"</span><br>
    <span style="color:#0e6ead;">d</span> = <span style="color:#ef5050;">list</span>((<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>)) <span style="color:#6b7280;"># tuple → list</span><br>
    <span style="color:#0e6ead;">e</span> = <span style="color:#ef5050;">bool</span>(<span style="color:#b45309;">0</span>)    <span style="color:#6b7280;"># int → bool : False</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Conversion Flow Diagram</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div style="display:flex;align-items:center;gap:6px;" v-click>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:#2b6cb0;min-width:60px;text-align:center;">"42"</div>
      <div style="font-size:.65rem;color:var(--muted);">str</div>
      <div style="color:var(--muted);">→ int() →</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);">42</div>
      <div style="font-size:.65rem;color:var(--muted);">int</div>
    </div>
    <div style="display:flex;align-items:center;gap:6px;" v-click>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">5</div>
      <div style="font-size:.65rem;color:var(--muted);">int</div>
      <div style="color:var(--muted);">→ float() →</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--green);">5.0</div>
      <div style="font-size:.65rem;color:var(--muted);">float</div>
    </div>
    <div style="display:flex;align-items:center;gap:6px;" v-click>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">99</div>
      <div style="font-size:.65rem;color:var(--muted);">int</div>
      <div style="color:var(--muted);">→ str() →</div>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:#2b6cb0;">"99"</div>
      <div style="font-size:.65rem;color:var(--muted);">str</div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:8px;">
    <div><strong>Invalid conversion raises ValueError!</strong> <span class="mono">int("hello")</span> → ValueError: invalid literal</div>
  </div>

  <div v-click class="card card-green" style="margin-top:6px;">
    <div class="small-text"><strong>Best practice:</strong> Wrap type conversions in <span class="mono">try/except</span> blocks to handle invalid inputs gracefully.</div>
  </div>

</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Create variables for a student profile: <code>name</code> (string), <code>age</code> (int), <code>gpa</code> (float), <code>is_enrolled</code> (bool). Print each variable and its type using <code>type()</code>.' },
  { text: '<b>Expected Output:</b><br><code>Alice &lt;class \'str\'&gt;</code><br><code>20 &lt;class \'int\'&gt;</code><br><code>9.2 &lt;class \'float\'&gt;</code><br><code>True &lt;class \'bool\'&gt;</code>' },
  { text: '<b>Note:</b> Use <code>print(variable, type(variable))</code> to print the value and type together on one line.' },
]
</script>

<Slide
  topic="Variables & Data Types"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take two numbers as input, store them in variables <code>a</code> and <code>b</code>. Swap them <b>without using a third variable</b>. Print the values before and after swapping.' },
  { text: '<b>Input:</b> <code>a = 15</code>, <code>b = 30</code>' },
  { text: '<b>Expected Output:</b><br><code>Before: a = 15, b = 30</code><br><code>After:  a = 30, b = 15</code>' },
  { text: '<b>Note:</b> Use Python\'s one-liner swap: <code>a, b = b, a</code>.' },
]
</script>

<Slide
  topic="Python Variables"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Create a dictionary called <code>student</code> with keys: <code>name</code>, <code>roll_no</code>, <code>marks</code>, and <code>passed</code>. Print each key-value pair and the <b>data type of each value</b>.' },
  { text: '<b>Expected Output:</b><br><code>name: Alice — type: &lt;class \'str\'&gt;</code><br><code>roll_no: 101 — type: &lt;class \'int\'&gt;</code><br><code>marks: 87.5 — type: &lt;class \'float\'&gt;</code><br><code>passed: True — type: &lt;class \'bool\'&gt;</code>' },
  { text: '<b>Note:</b> Use a <b>for</b> loop with <code>.items()</code> to iterate over the dictionary and print each key, value, and type.' },
]
</script>

<Slide
  topic="Python Data Types"
  sub-topic="Practice Problem"
  :contents="contents"
/>