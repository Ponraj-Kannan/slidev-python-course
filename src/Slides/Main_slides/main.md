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
  <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
    Python is a <strong style="color:var(--red);">high-level, interpreted, general-purpose</strong> programming language designed for <strong style="color:var(--green);">readability</strong> and <strong style="color:var(--green);">simplicity</strong>.
  </div>
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

  <div style="display:flex;flex-direction:column;gap:6px;">
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

<Slide
  topic="Python Variables"
  sub-topic="Test Yourself!"  
/>

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

<Slide
  topic="Python Variables"
  sub-topic="Test Yourself!"  
/>

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

<Slide
  topic="Python Variables"
  sub-topic="Test Yourself!"  
/>

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

<Slide
  topic="Variable Naming Rules"
  sub-topic="Test Yourself!"  
/>

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

<Slide
  topic="Variable Naming Rules"
  sub-topic="Test Yourself!"  
/>

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

<Slide
  topic="Python Syntax"
  sub-topic="Test Yourself!"  
/>

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
    <span style="color:#0e6ead;">c2</span> = <span style="color:#b45309;">2</span> - <span style="color:#b45309;">1j</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c1</span>.real)  <span style="color:#6b7280;"># 3.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c1</span>.imag)  <span style="color:#6b7280;"># 4.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">c1</span>)) <span style="color:#6b7280;"># &lt;class 'complex'&gt;</span>
  </div>

  <div v-click style="margin-top:6px;">
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — SEQUENCE TYPE: str
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — SEQUENCE TYPE: list
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — SEQUENCE TYPE: tuple
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — BOOLEAN TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

  <div style="margin-top:8px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Value</th><th>bool(value)</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono">0, 0.0, "", None</td><td class="no">False</td></tr>
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — SET TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — DICTIONARY TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 19 — NONE TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

  <div style="display:flex;flex-direction:column;gap:6px;">
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
      <thead v-after><tr><th>Value</th><th>bool()</th><th>Meaning</th></tr></thead>
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

<Slide
  topic="Data Types"
  sub-topic="Test Yourself!"  
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — DATA TYPE COMPARISON TABLE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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

<Slide2 topic="Type Checking & Conversion">
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

  <div style="display:flex;flex-direction:column;gap:6px;">
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
  topic="Type Checking & Conversion"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Read a character from the user and print its ASCII value, whether it is uppercase, lowercase, or a digit, and its opposite-case character (if it is a letter).' },
  { text: '<b>Input:</b> <code>Enter a character: G</code>' },
  { text: '<b>Expected Output:</b><br><code>ASCII value : 71</code><br><code>Type        : Uppercase letter</code><br><code>Lowercase   : g</code>' },
  { text: '<b>Note:</b> Use ASCII ranges to classify — uppercase: 65–90, lowercase: 97–122, digits: 48–57.' },
  // { text: '<b>Hint:</b> Read with <code>sc.next().charAt(0)</code>. Cast to <code>int</code> for ASCII. Check ranges with <code>if</code>. Convert case by adding or subtracting 32 with <code>(char)</code> cast.', highlight: true },
]
</script>

<Slide
  topic="Type Checking & Conversion"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Encrypt a single character by shifting it by 3 positions forward in ASCII (Caesar cipher). Decrypt it by shifting back by 3.' },
  { text: '<b>Input (hardcoded):</b> <code>char ch = \'H\'</code>' },
  { text: '<b>Expected Output:</b><br><code>Original  : H</code><br><code>Encrypted : K</code><br><code>Decrypted : H</code>' },
  { text: '<b>Note:</b> Encryption adds 3 to the ASCII value: <code>\'H\'</code> (72) + 3 = 75 = <code>\'K\'</code>. Decryption subtracts 3.' },
  // { text: '<b>Hint:</b> Use <code>(char)(ch + 3)</code> to encrypt and <code>(char)(encrypted - 3)</code> to decrypt. The <code>(char)</code> cast converts the integer result back to a character.', highlight: true },
]
</script>

<Slide
  topic="Type Checking & Conversion"
  sub-topic="Practice Problem"
  :contents="contents"
/>


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

  .flow-v-box {
  padding: 6px 18px;
  border-radius: 8px;
  font-size: 0.72rem;
  font-weight: 700;
  text-align: center;
  min-width: 120px;
}

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
.card-navy   { background: #2f4469ff; color: var(--navy); border: 1px solid #c5cde8; border-radius: var(--radius); padding: 14px 18px; }
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
     SLIDE 4 — IF STATEMENT: WHAT IS IT?
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">What is an <span class="highlight">if Statement?</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card-navy" style="border-radius:10px;">
      <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
        An <strong style="color:var(--red);">if statement</strong> lets your program make decisions — it runs a block of code <strong style="color:var(--green);">only when</strong> a condition evaluates to <span style="color:var(--yellow);">True</span>.
      </div>
  </div>

  <div v-click class="callout callout-info">
    <div>Think of it like a <strong>security guard</strong> — only people who meet the condition get inside!</div>
  </div>

  <div v-click class="card" style="border:1px solid #ef5050;">
    <div class="slide-h3" style="margin-bottom:8px;">Real-life Analogy</div>
    <div class="body-text">
      <strong>IF</strong> it is raining<br>
      &nbsp;&nbsp;&nbsp;&nbsp;→ Take an umbrella ☂️<br>
      <span class="small-text">(do nothing if it is NOT raining)</span>
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Key rule:</strong> If the condition is <strong>False</strong>, Python completely <em>skips</em> the indented block.</div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div class="slide-h3" v-click style="margin-bottom:4px;">How Python evaluates a condition</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;">
    <div class="flow-v-box" style="background:#ebf8ff;border:1px solid #3182ce;color:#2b6cb0;">▶ Program reaches if statement</div>
    <div class="flow-v-arrow">▼</div>
    <div class="flow-v-box" style="background:var(--red-soft);border:2px solid var(--red);color:var(--red-dark);">🔎 Evaluate the condition</div>
    <div style="display:flex;gap:20px;align-items:flex-start;margin-top:4px;">
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--green);">TRUE</div>
        <div class="flow-v-arrow" style="color:var(--green);">▼</div>
        <div class="flow-v-box" style="background:#f0fff4;border:1px solid var(--green);color:var(--green);min-width:100px;">Run the block</div>
      </div>
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--red);">FALSE</div>
        <div class="flow-v-arrow" style="color:var(--red);">▼</div>
        <div class="flow-v-box" style="background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);min-width:100px;">Skip the block</div>
      </div>
    </div>
    <div class="flow-v-arrow" style="margin-top:4px;">▼</div>
    <div class="flow-v-box" style="background:#fffff0;border:1px solid var(--yellow);color:#744210;">Continue program</div>
  </div>
</div>

</div>
  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — IF SYNTAX DIAGRAM
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:14px;">if Statement <span class="highlight">Syntax</span></div>

<div class="g2" style="gap:16px;">

<div class="flex-col" style="gap:12px;">
  <div class="slide-h3" v-click>Syntax Breakdown</div>

  <div v-after style="background:#1a1f36;border-radius:10px;padding:14px 18px;font-family:'Fira Code',monospace;font-size:.82rem;line-height:2;">
    <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">condition</span><span style="color:#f1fa8c;">:</span><br>
    <span style="color:#636e80;">&nbsp;&nbsp;&nbsp;&nbsp;# indented block</span><br>
    <span style="color:#a8ff78;">&nbsp;&nbsp;&nbsp;&nbsp;statement_1</span><br>
    <span style="color:#a8ff78;">&nbsp;&nbsp;&nbsp;&nbsp;statement_2</span>
  </div>

  <div v-click style="display:flex;flex-direction:column;gap:8px;">
    <div class="syntax-row">
      <div>
        <div class="syn-keyword">if</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-varname">condition</div>
        <div class="syn-label">True or False</div>
      </div>
      <div>
        <div class="syn-colon">:</div>
        <div class="syn-label">required!</div>
      </div>
    </div>
    <div class="syntax-row" style="margin-left:20px;">
      <div>
        <div class="syn-body">indented statements</div>
        <div class="syn-label">4 spaces / 1 tab</div>
      </div>
    </div>
  </div>

  

  <div v-click class="callout callout-danger">
    <div>Never forget the <strong>colon :</strong> after the condition — Python will throw a <strong>SyntaxError</strong>!</div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div class="slide-h3" v-click style="margin-bottom:4px;">How Python evaluates a condition</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;">
    <div class="flow-v-box" style="background:#ebf8ff;border:1px solid #3182ce;color:#2b6cb0;">▶ Program reaches if statement</div>
    <div class="flow-v-arrow">▼</div>
    <div class="flow-v-box" style="background:var(--red-soft);border:2px solid var(--red);color:var(--red-dark);">🔎 Evaluate the condition</div>
    <div style="display:flex;gap:20px;align-items:flex-start;margin-top:4px;">
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--green);">TRUE</div>
        <div class="flow-v-arrow" style="color:var(--green);">▼</div>
        <div class="flow-v-box" style="background:#f0fff4;border:1px solid var(--green);color:var(--green);min-width:100px;">Run the block</div>
      </div>
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--red);">FALSE</div>
        <div class="flow-v-arrow" style="color:var(--red);">▼</div>
        <div class="flow-v-box" style="background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);min-width:100px;">Skip the block</div>
      </div>
    </div>
    <div class="flow-v-arrow" style="margin-top:4px;">▼</div>
    <div class="flow-v-box" style="background:#fffff0;border:1px solid var(--yellow);color:#744210;">Continue program</div>
  </div>
</div>
</div>
  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — ELSE STATEMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">The <span class="highlight">else</span> Statement</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--yellow);">else</strong> is the <strong style="color:var(--green);">final catch-all</strong>. It runs when <em>every</em> previous condition is False. It has <strong style="color:var(--red);">no condition</strong> of its own.
    </div>
</div>

  <div v-click class="card" style="border:1px solid var(--green);">
    <div class="slide-h3" style="margin-bottom:8px;">Syntax</div>
    <div style="font-family:'Fira Code',monospace;font-size:.78rem;line-height:1.9;background:#f7f8fc;padding:8px;border-radius:6px;">
      <span style="color:#ff79c6;">if</span> condition:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;...<br>
      <span style="color:#ffd166;">else</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># runs when everything else is False</span>
    </div>
  </div>

  <div v-click class="callout callout-info">
    <div><strong>else</strong> never has a condition. It cannot be used alone — it always follows an <code>if</code>.</div>
  </div>
</div>
<div class="flex-col" style="gap:10px;">
  <div class="slide-h3" v-click style="margin-bottom:4px;">How Python evaluates a condition</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;">
    <div class="flow-v-box" style="background:#ebf8ff;border:1px solid #3182ce;color:#2b6cb0;">▶ Program reaches if statement</div>
    <div class="flow-v-arrow">▼</div>
    <div class="flow-v-box" style="background:var(--red-soft);border:2px solid var(--red);color:var(--red-dark);">🔎 Evaluate the condition</div>
    <div style="display:flex;gap:20px;align-items:flex-start;margin-top:4px;">
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--green);">TRUE</div>
        <div class="flow-v-arrow" style="color:var(--green);">▼</div>
        <div class="flow-v-box" style="background:#f0fff4;border:1px solid var(--green);color:var(--green);min-width:100px;">Runs if block</div>
      </div>
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--red);">FALSE</div>
        <div class="flow-v-arrow" style="color:var(--red);">▼</div>
        <div class="flow-v-box" style="background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);min-width:100px;">Runs else block</div>
      </div>
    </div>
    <div class="flow-v-arrow" style="margin-top:4px;">▼</div>
    <div class="flow-v-box" style="background:#fffff0;border:1px solid var(--yellow);color:#744210;">Continue program</div>
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
  { text: 'Determine whether a given integer <b>N</b> is <b>Odd or Even</b>.' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: 'Check if a person is <b>eligible to vote based on their age</b>. (age &gt;= 18 → Eligible, otherwise Not eligible).' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — ELIF STATEMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">The <span class="highlight">elif</span> Statement</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--blue);">elif</strong> = "else if" — it checks a new condition <strong style="color:var(--green);">only when the previous if (or elif) was False</strong>. You can chain as many elif blocks as you need.
    </div>
</div>

  <div v-click class="card" style="border:1px solid var(--green);">
    <div class="slide-h3" style="margin-bottom:8px;">Syntax</div>
    <div style="font-family:'Fira Code',monospace;font-size:.78rem;line-height:1.9;background:#f7f8fc;padding:8px;border-radius:6px;">
      <span style="color:#ff79c6;">if</span> condition:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;...<br>
      <span style="color:green;">elif</span> condition:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;...<br>
      <span style="color:#ffd166;">else</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># runs when everything else is False</span>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div v-click style="display:flex;flex-direction:column;align-items:center;gap:4px;">
    <div class="slide-h3" style="margin-bottom:30px; ">How Python evaluates a condition</div>
    <div class="flow-v-box" style="background:var(--red-soft);border:2px solid var(--red);color:var(--red-dark);">if condition1?</div>
    <div style="display:flex;width:100%;justify-content:space-between;padding:0 20px;">
      <div style="font-size:.68rem;font-weight:800;color:var(--green);">TRUE → run block 1</div>
      <div style="font-size:.68rem;font-weight:800;color:var(--red);">FALSE ↓</div>
    </div>
    <div class="flow-v-box" style="background:#ebf8ff;border:2px solid var(--blue);color:#2b6cb0;">elif condition2?</div>
    <div style="display:flex;width:100%;justify-content:space-between;padding:0 20px;">
      <div style="font-size:.68rem;font-weight:800;color:var(--green);">TRUE → run block 2</div>
      <div style="font-size:.68rem;font-weight:800;color:var(--red);">FALSE ↓</div>
    </div>
    <div class="flow-v-box" style="background:#fffaf0;border:2px solid var(--orange);color:#c05621;">elif condition3?</div>
    <div class="flow-v-arrow">▼</div>
    <div class="flow-v-box" style="background:#f0fff4;border:1px solid var(--green);color:var(--green);">Continue program</div>
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
  { text: 'Determine whether a given integer <b>N</b> is <b>Positive</b>, <b>Negative</b>, or <b>Zero</b>.' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: 'Assign a grade to a student based on their marks.' },
  { text: 'Mark &gt;= 90 → Print <b>A</b>' },
  { text: 'Mark &gt;= 80 → Print <b>B</b>' },
  { text: 'Mark &gt;= 70 → Print <b>C</b>' },
  { text: 'Mark &gt;= 60 → Print <b>D</b>' },
  { text: 'Else → Print <b>F</b>' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---


<!-- ═══════════════════════════════════════════════════════
     SLIDE 11 — ELSE WITHOUT ELIF
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">else</span> Without elif</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
<div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      You can use <strong style="color:var(--blue);">if + else</strong> directly without any <code>elif</code>. This is a simple two-way branch — either the condition is met, or it isn't.
    </div>
</div>
</div>
<div class="flex-col" style="gap:10px;">
<div v-click style="display:flex;flex-direction:column;align-items:center;gap:6px;">
    <div class="slide-h3" v-click style="margin-bottom:4px;">How Python evaluates a condition</div>
    <div class="flow-v-box" style="background:var(--red-soft);border:2px solid var(--red);color:var(--red-dark);">🔎 Evaluate condition</div>
    <div style="display:flex;gap:40px;">
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--green);">TRUE</div>
        <div class="flow-v-box" style="background:#f0fff4;border:1px solid var(--green);color:var(--green);min-width:90px;">if block runs</div>
      </div>
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--red);">FALSE</div>
        <div class="flow-v-box" style="background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);min-width:90px;">else block runs</div>
      </div>
    </div>
    <div class="flow-v-box" style="background:#fffff0;border:1px solid var(--yellow);color:#744210;margin-top:4px;">Program continues</div>
  </div>
  </div>

</div>
  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — ELSE AS FALLBACK
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">else</span> as a Fallback Safety Net</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      The <strong style="color:var(--yellow);">else</strong> block acts as a <strong style="color:var(--green);">fallback</strong> — it handles every case that wasn't caught by any <code>if</code> or <code>elif</code>. It ensures no user input is left unhandled.
    </div>
</div>
</div>
<div class="flex-col" style="gap:10px;">
<div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">Why use else as fallback?</div>
    <div class="flex-col" style="gap:6px;margin-top:8px;">
      <div class="body-text">Prevents program from silently ignoring unknown inputs</div>
      <div class="body-text">Provides meaningful error/default messages</div>
      <div class="body-text">Makes code more robust and user-friendly</div>
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div>Always add an <strong>else</strong> when handling user input — they might enter something unexpected!</div>
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
  { text: '<b>Problem:</b> Take a temperature as input and print the appropriate weather advice based on the temperature range using <code>if-elif-else</code> conditions. If the input is outside the valid range, print an invalid data message.' },
  { text: '<b>Input:</b> <code>38</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Very Hot! Stay hydrated</code><br><br><b>More Test Cases:</b><br><code>36 - 50 &nbsp;→ Very Hot! Stay hydrated</code><br><code>26 - 35 &nbsp;→ Warm and pleasant</code><br><code>16 - 25 &nbsp;→ Cool, carry a jacket</code><br><code>0 &nbsp;- 15 &nbsp;→ Very Cold!</code><br><code>-1 or 51+ → Invalid data!</code>'
  }
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — SHORTHAND IF...ELSE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">Shorthand <span class="highlight">if ... else</span> (Ternary)</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
<div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--yellow);">one-line if-else</strong> (called a ternary expression). Useful when you want to assign a value or print based on a condition — without writing a full 4-line block.
    </div>
</div>
  <div v-click class="card" style="border:1px solid var(--green);">
    <div class="slide-h3" style="margin-bottom:8px;">Syntax Pattern</div>
    <div class="syntax-row" style="flex-wrap:wrap;gap:6px;">
      <div>
        <div class="syn-value">result_if_true</div>
        <div class="syn-label">runs when True</div>
      </div>
      <div>
        <div class="syn-keyword">if</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-varname">condition</div>
        <div class="syn-label">evaluated</div>
      </div>
      <div>
        <div class="syn-keyword" style="background:#fffff0;color:#744210;">else</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-body">result_if_false</div>
        <div class="syn-label">runs when False</div>
      </div>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-warn">
    <div>Use shorthand only for <strong>simple</strong> conditions. For complex logic, stick with the full if-else form for readability.</div>
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
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Test Yourself"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — NESTED IF
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">Nested <span class="highlight">if</span> Statements</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
<div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      Placing an <strong style="color:var(--green);">if statement inside another if</strong> creates a nested structure. The inner if only runs when the outer condition is True.
    </div>
</div>

  <div v-click class="card card-orange">
    <div class="slide-h3" style="margin-bottom:6px;">Visual Structure</div>
    <div style="font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;background:#fff8f0;padding:8px;border-radius:6px;">
      <span style="color:#dd6b20;">if</span> level_1_condition:<br>
      <span style="background:rgba(221,107,32,.15);display:inline-block;width:95%;padding-left:4px;border-left:3px solid #dd6b20;">
        &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#3182ce;">if</span> level_2_condition:<br>
        <span style="background:rgba(49,130,206,.15);display:inline-block;width:88%;margin-left:8px;padding-left:4px;border-left:3px solid #3182ce;">
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#38a169;">→ innermost block</span>
        </span>
      </span>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
<div v-click class="callout callout-warn">
    <div>Avoid nesting more than <strong>2–3 levels</strong> deep — code becomes hard to read. Consider using <strong>logical operators</strong> (and, or) instead.</div>
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
  { text: 'Given a character <b>ch</b>, determine if it is a <b>Vowel</b>, <b>Consonant</b>, or <b>Not an Alphabet</b>.' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: 'Given three integers <b>a</b>, <b>b</b>, and <b>c</b>, find and print the <b>maximum value</b>.' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — PASS STATEMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">The <span class="highlight">pass</span> Statement</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
<div v-click class="callout callout-info">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      Python requires every block to have at least one statement. <strong style="color:var(--yellow);">pass</strong> is a legal <strong style="color:var(--green);">do-nothing</strong> statement that keeps the code syntactically valid without performing any action.
    </div>
</div>
</div>

<div class="flex-col" style="gap:10px;">
<div v-click class="card card-red">
    <div class="slide-h3" style="color:var(--red-dark);">❌ Without pass — SyntaxError!</div>
    <div style="font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;background:#fff;padding:8px;border-radius:6px;margin-top:6px;">
      <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ef5050;"># empty block → SyntaxError!</span>
    </div>
  </div>
  <div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">✅ With pass — Valid!</div>
    <div style="font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;background:#fff;padding:8px;border-radius:6px;margin-top:6px;">
      <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ffd166;">pass</span>&nbsp;&nbsp;<span style="color:#636e80;"># placeholder — valid!</span>
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
     SLIDE 21 — PASS vs COMMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:14px;"><span class="highlight">pass</span> vs Comments — What's the Difference?</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card card-orange">
    <div style="display:flex;gap:10px;align-items:center;margin-bottom:8px;">
      <div class="slide-h2">pass — A Statement</div>
    </div>
    <div class="flex-col" style="gap:6px;">
      <div class="body-text">Recognized by the Python <strong>interpreter</strong></div>
      <div class="body-text">Keeps a code block <strong>syntactically valid</strong></div>
      <div class="body-text">Executes (does nothing) at <strong>runtime</strong></div>
      <div class="body-text">can be used in if, loops, functions, classes</div>
    </div>
  </div>

  <div v-click style="background:#ffffff;border-radius:10px;padding:12px 18px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;">
    <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ffd166;">pass</span>&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;">← valid, interpreter sees this</span>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div v-click class="card card-blue">
    <div style="display:flex;gap:10px;align-items:center;margin-bottom:8px;">
      <div class="slide-h2">Comments — Not Code</div>
    </div>
    <div class="flex-col" style="gap:6px;">
      <div class="body-text"><strong>Ignored</strong> by the Python interpreter</div>
      <div class="body-text">Cannot replace a required statement</div>
      <div class="body-text">Used to explain code for humans</div>
      <div class="body-text">Does NOT count as a block statement</div>
    </div>
  </div>

  <div v-click style="background:#ffffff;border-radius:10px;padding:12px 18px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;">
    <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># comment only → SyntaxError!</span>
  </div>
</div>

</div>

<div style="margin-top:12px;">
  <table class="cmp-table" >
    <tr v-click>
      <th>Feature</th>
      <th>pass</th>
      <th># Comment</th>
    </tr>
    <tr v-click>
      <td>Seen by interpreter</td>
      <td class="yes">✅ Yes</td>
      <td class="no">❌ No</td>
    </tr>
    <tr v-click>
      <td>Fills empty block</td>
      <td class="yes">✅ Yes</td>
      <td class="no">❌ No</td>
    </tr>
    <tr v-click>
      <td>Explains code to humans</td>
      <td class="no">❌ No</td>
      <td class="yes">✅ Yes</td>
    </tr>
    <tr v-click>
      <td>Used together?</td>
      <td colspan="2" style="text-align:center;" class="yes">✅ Yes — use both! <code>pass  # TODO: implement</code></td>
    </tr>
  </table>
</div>
  </template>
</Slide2>

---
transition: slide-up
---

<script setup>
const contents = [
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Test Yourself"
  :contents="contents"
/>

---
transition: fade
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 23 — MATCH CASE SYNTAX
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">match <span class="highlight">case</span> — Syntax</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card-navy">
    <div style="font-size:.72rem;text-transform:uppercase;letter-spacing:1px;color:rgba(255,255,255,.5);margin-bottom:6px;">Syntax</div>
    <div style="font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;margin-top:4px;">
      <span style="color:#ffd166;">match</span> <span style="color:#61dafb;">variable</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">value_1</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#e2e8f0;">...</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">value_2</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#e2e8f0;">...</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#ff9900;">_</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># default (wildcard)</span>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
   <div v-click class="syntax-row">
      <div>
        <div class="syn-keyword" style="background:#faf5ff;color:#553c9a;">match</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-varname">variable</div>
        <div class="syn-label">value to check</div>
      </div>
      <div>
        <div class="syn-colon">:</div>
        <div class="syn-label">required</div>
      </div>
    </div>
    <div v-click class="syntax-row" style="margin-left:20px;">
      <div>
        <div class="syn-keyword" style="background:#f0fff4;color:#276749;">case</div>
        <div class="syn-label">each pattern</div>
      </div>
      <div>
        <div class="syn-value">value</div>
        <div class="syn-label">pattern to match</div>
      </div>
      <div>
        <div class="syn-operator">_</div>
        <div class="syn-label">wildcard/default</div>
      </div>
    </div>
    <div v-click class="callout callout-info">
    <div>The <strong>_ (underscore)</strong> is the wildcard — it matches <em>anything</em> that didn't match earlier cases. Like the <strong>else</strong> in if-elif-else.</div>
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
  { text: '<b>Problem:</b> Take a traffic signal color as input and use a <code>match</code> statement to print the correct action for each signal — <b>Stop</b>, <b>Slow down</b>, <b>Go</b>, or an <b>Unknown signal</b> message for anything else.' },
  { text: '<b>Input:</b> <code>green</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Go!</code><br><br><b>More Test Cases:</b><br><code>red &nbsp;&nbsp;→ Stop!</code><br><code>yellow → Slow down!</code><br><code>blue &nbsp;→ Unknown signal!</code>'
  }
  // { text: '<b>Hint:</b> Start with <code>signal = input()</code> — Then <code>match signal:</code> — Add <code>case "red": print("🔴 Stop!")</code>, <code>case "yellow": print("🟡 Slow down!")</code>, <code>case "green": print("🟢 Go!")</code>, and <code>case _: print("❓ Unknown signal!")</code>', highlight: true },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 24 — MATCH CASE EXECUTION DIAGRAM
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">match-case <span class="highlight">Execution Flow</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:8px;">
  <div class="slide-h3" v-click>How Python processes match</div>

  <div v-after style="display:flex;flex-direction:column;gap:4px;">
    <div style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">1</div>
      <div class="flow-v-box" style="flex:1;background:#ebf8ff;border:1px solid #3182ce;color:#2b6cb0;">Evaluate the match variable</div>
    </div>
    <div style="padding-left:13px;color:var(--muted);">▼</div>
    <div v-after style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">2</div>
      <div class="flow-v-box" style="flex:1;background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);">Compare against case 1 pattern</div>
    </div>
    <div style="padding-left:13px;display:flex;gap:20px;">
      <div style="font-size:.65rem;color:var(--green);font-weight:800;">MATCH → run block, STOP</div>
      <div style="font-size:.65rem;color:var(--red);font-weight:800;">NO MATCH → try next case ▼</div>
    </div>
    <div v-after style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">3</div>
      <div class="flow-v-box" style="flex:1;background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);">Compare against case 2 pattern</div>
    </div>
    <div style="padding-left:13px;color:var(--muted);">▼ ... repeat ...</div>
    <div v-after style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">N</div>
      <div class="flow-v-box" style="flex:1;background:#faf5ff;border:2px solid #805ad5;color:#553c9a;">case _ (wildcard — no match found)</div>
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div>Only <strong>one</strong> case block runs per match statement — Python stops as soon as a match is found!</div>
  </div>
</div>

</div>
  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 25 — IF-ELIF-ELSE vs MATCH-CASE COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:14px;">if-elif-else  <span class="highlight">vs</span>  match-case</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:8px;">
  <div class="pill pill-red" style="margin-bottom:4px;border: 1px solid #bc2f41ff;">if-elif-else Approach</div>
  <div v-click style="background:#1a1f36;border-radius:10px;padding:12px 18px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.85;">
    <span style="color:#61dafb;">day</span> = <span style="color:#f1fa8c;">"Monday"</span><br><br>
    <span style="color:#ff79c6;">if</span>   <span style="color:#61dafb;">day</span> == <span style="color:#f1fa8c;">"Monday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Start of work week"</span>)<br>
    <span style="color:#61dafb;">elif</span> <span style="color:#61dafb;">day</span> == <span style="color:#f1fa8c;">"Friday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Weekend soon!"</span>)<br>
    <span style="color:#61dafb;">elif</span> <span style="color:#61dafb;">day</span> == <span style="color:#f1fa8c;">"Sunday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Rest day"</span>)<br>
    <span style="color:#ffd166;">else</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Weekday"</span>)
  </div>
</div>

<div class="flex-col" style="gap:8px;">
  <div  class="pill pill-green" style="margin-bottom:4px; border: 1px solid #168b53ff;">match-case Approach</div>
  <div v-click style="background:#1a1f36;border-radius:10px;padding:12px 18px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.85;">
    <span style="color:#61dafb;">day</span> = <span style="color:#f1fa8c;">"Monday"</span><br><br>
    <span style="color:#ffd166;">match</span> <span style="color:#61dafb;">day</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Monday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Start of work week"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Friday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Weekend soon!"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Sunday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Rest day"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#ff9900;">_</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"Weekday"</span>)
  </div>
</div>

</div>

<div style="margin-top:10px;">
  <table class="cmp-table">
    <tr v-click>
      <th>Feature</th>
      <th>if-elif-else</th>
      <th>match-case</th>
    </tr>
    <tr v-click>
      <td>Python version</td>
      <td>All versions</td>
      <td class="yes">3.10+ only</td>
    </tr>
    <tr v-click>
      <td>Range conditions (>, &lt;)</td>
      <td class="yes">✅ Yes</td>
      <td class="no">❌ Not directly</td>
    </tr>
    <tr v-click>
      <td>Exact value matching</td>
      <td>✅ Yes</td>
      <td class="yes">✅ Cleaner syntax</td>
    </tr>
    <tr v-click>
      <td>Default handler</td>
      <td><code>else:</code></td>
      <td class="yes"><code>case _:</code></td>
    </tr>
    <tr v-click>
      <td>Best for</td>
      <td>Complex conditions, ranges</td>
      <td class="yes">Multiple exact values</td>
    </tr>
  </table>
</div>
  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 26 — MATCH CASE WITH MULTIPLE VALUES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">match-case — <span class="highlight">Multiple Values</span> per Case</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
</div>
<div class="flex-col" style="gap:10px;">
<div v-click style="background:#1a1f36;border-radius:10px;padding:14px 18px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.9;">
    <span style="color:#61dafb;">day</span> = <span style="color:#f1fa8c;">"Saturday"</span><br><br>
    <span style="color:#ffd166;">match</span> <span style="color:#61dafb;">day</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Saturday"</span> <span style="color:#ff9900;">|</span> <span style="color:#f1fa8c;">"Sunday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"🎉 It's the weekend!"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Monday"</span> <span style="color:#ff9900;">|</span> <span style="color:#f1fa8c;">"Friday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"📅 Start/end of week"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#ff9900;">_</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"💼 Regular weekday"</span>)
  </div>

  <div v-click class="output-box">
    <span class="prompt">day = "Saturday" → </span>🎉 It's the weekend!<br>
    <span class="prompt">day = "Tuesday"  → </span>💼 Regular weekday
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
  { text: '<b>Problem:</b> Take an HTTP status code as input and use a <code>match</code> statement to print the correct status message. Handle multiple codes in a single <code>case</code> using the <code>|</code> operator.' },
  { text: '<b>Input:</b> <code>404</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Not Found</code><br><br><b>More Test Cases:</b><br><code>200 or 201 → Success!</code><br><code>400 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ Bad Request</code><br><code>500 or 503 → Server Error</code><br><code>999 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ Unknown status</code>'
  }
]
</script>

<Slide
  topic="Match Case"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a student\'s name and marks as input. Use <code>if-elif-else</code> to determine the grade and <code>match-case</code> to determine the status. Print a formatted report card.' },
  { text: '<b>Input:</b><br><code>Enter student name: Priya</code><br><code>Enter marks (0-100): 85</code>' },
  {
    text: '<b>Expected Output:</b><br><code>--- Report Card ---</code><br><code>Name &nbsp;: Priya</code><br><code>Marks : 85</code><br><code>Grade : A — Distinction</code><br><br><b>Grade Ranges:</b><br><code>90 - 100 → A+ — Distinction</code><br><code>80 - 89 &nbsp;→ A &nbsp;— Distinction</code><br><code>70 - 79 &nbsp;→ B &nbsp;— Pass</code><br><code>50 - 69 &nbsp;→ C &nbsp;— Pass</code><br><code>0 &nbsp;- 49 &nbsp;→ F &nbsp;— Fail</code>'
  },
  {
    text: '<b>Key Concepts:</b> Use <code>if-elif-else</code> to assign a grade letter based on mark ranges — conditions must be checked <b>highest to lowest</b>. Then use <code>match grade:</code> with the <code>|</code> operator to group grades into a status — <code>case "A+" | "A":</code> for Distinction, <code>case "B" | "C":</code> for Pass, and <code>case _:</code> for Fail. Finally, use <b>f-strings</b> to print the formatted report card.'
  }
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 29 — QUICK REFERENCE CHEAT SHEET
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements — Quick Reference">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">📋 Conditional Statements <span class="highlight">Cheat Sheet</span></div>

<div style="margin-top:10px;">
  <table class="cmp-table">
    <tr><th>Keyword</th><th>Purpose</th><th>Has condition?</th><th>Can use alone?</th></tr>
    <tr v-click ><td class="mono" style="color:var(--red-dark);">if</td><td>First condition check</td><td class="yes">✅ Yes</td><td class="yes">✅ Yes</td></tr>
    <tr v-click ><td class="mono" style="color:#2b6cb0;">elif</td><td>Additional condition</td><td class="yes">✅ Yes</td><td class="no">❌ Needs if first</td></tr>
    <tr v-click ><td class="mono" style="color:#744210;">else</td><td>Default fallback</td><td class="no">❌ No condition</td><td class="no">❌ Needs if first</td></tr>
    <tr v-click ><td class="mono" style="color:#553c9a;">match</td><td>Pattern matching</td><td class="yes">✅ Yes (value)</td><td class="yes">✅ Yes</td></tr>
    <tr v-click ><td class="mono" style="color:#276749;">pass</td><td>Empty placeholder</td><td class="no">❌ No</td><td class="no">❌ Inside a block</td></tr>
  </table>
</div>
  </template>
</Slide2>



---
theme: default
title: Python Looping Statements
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

/* ── Loop trace table ─────────────────────────────────────── */
.trace-table { width: 100%; border-collapse: collapse; font-size: 0.72rem; font-family: 'Fira Code', monospace; }
.trace-table th { background: var(--slate); color: #fff; padding: 6px 10px; text-align: center; font-weight: 700; }
.trace-table td { padding: 6px 10px; border-bottom: 1px solid var(--border); text-align: center; }
.trace-table tr:nth-child(even) td { background: #f7f8fc; }
.trace-table .hl { background: var(--slate); color: var(--red-dark); font-weight: 700; }

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
.flow-cond   { background: #fffaf0; color: var(--orange); border-color: var(--orange); transform: rotate(0deg); }
.flow-body   { background: var(--red-soft); color: var(--red-dark); border-color: var(--red); }
.flow-end    { background: #f0fff4; color: var(--green); border-color: var(--green); border-radius: 20px; }
.flow-arrow  { text-align: center; color: var(--muted); font-size: 1rem; font-weight: 900; line-height: 1; }
</style>


<!-- ═══════════════════════════════════════════════════════
     SLIDE 2 — WHAT IS A LOOP & WHY DO WE NEED IT?
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Introduction to Loops">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is a <span class="highlight">Loop ?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">loop</strong> is a programming construct that <strong style="color:var(--green);">repeats a block of code</strong> multiple times — until a condition becomes false or the sequence is exhausted.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Without a loop:</strong> Printing 1 to 100 requires 100 print() statements. With a loop — just 3 lines!</div>
  </div>

  <div v-click class="card card-red" style="margin-top:4px;">
    <div class="slide-h3" style="margin-bottom:6px;">Real-World Analogy</div>
    <div class="body-text">A washing machine runs the wash cycle <strong>repeatedly</strong> until the timer ends. That is exactly what a loop does in code.</div>
  </div>

  <div v-click class="card card-green">
    <div class="small-text"><strong>Key benefit:</strong> Write code <strong>once</strong>, execute it <strong>n</strong> times — reduces repetition and errors.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="slide-h3" style="margin-bottom:8px;">Without Loop vs With Loop</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.8;">
    <div style="color:#6b7280;margin-bottom:4px;"># Without loop — repetitive!</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">1</span>)</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">2</span>)</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">3</span>)</div>
    <div style="color:#6b7280;">... 97 more lines ...</div>
    <br>
    <div style="color:#6b7280;"># With loop — clean and smart!</div>
    <div><span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">101</span>):</div>
    <div style="padding-left:20px;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Types of Loops in Python:</strong></div>
    <div style="display:flex;gap:8px;margin-top:6px;flex-wrap:wrap;">
      <span class="pill pill-red">while loop</span>
      <span class="pill pill-blue">for loop</span>
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
     SLIDE 4 — WHILE LOOP: SYNTAX + FLOWCHART
═══════════════════════════════════════════════════════ -->

<Slide2 topic="While Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">While</span> Loop — Syntax &amp; Flow</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">Syntax Diagram</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px 18px;font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;">
    <span style="color:#6b7280;"># Initialize variable</span><br>
    <span style="color:#0e6ead;">counter</span> = <span style="color:#b45309;">1</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">&lt;=</span> <span style="color:#b45309;">5</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">counter</span>)</span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Update variable</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">+=</span> <span style="color:#b45309;">1</span></span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Syntax Parts</div>
    <div style="display:flex;flex-direction:column;gap:4px;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-keyword">while</span>
        <span class="body-text">Keyword that starts the loop</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-value">condition</span>
        <span class="body-text">Boolean expression checked each time</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-varname">body</span>
        <span class="body-text">Indented block — runs while TRUE</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-operator">update</span>
        <span class="body-text">Change variable to avoid infinite loop</span>
      </div>
    </div>
  </div>

</div>

<div class="flex-col" >
  <div v-click class="section-label">Execution Flowchart</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:10px 0;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
    <div class="flow-node flow-start" style="width:140px;">START</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node" style="background:#ebf8ff;border:2px solid #3182ce;color:#2b6cb0;width:180px;font-size:.7rem;">Initialize: counter = 1</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-cond" style="width:180px;">counter &lt;= 5 ?</div>
    <div style="display:flex;align-items:flex-start;gap:16px;width:260px;">
      <div style="display:flex;flex-direction:column;align-items:center;gap:4px;margin-left:10px;">
        <div style="font-size:.6rem;color:var(--green);font-weight:700;">TRUE</div>
        <div class="flow-arrow">&#x25BC;</div>
        <div class="flow-node flow-body" style="width:110px;font-size:.65rem;">print(counter)<br>counter += 1</div>
        <div class="flow-arrow">&#x21B1;</div>
        <div style="font-size:.6rem;color:var(--muted);font-weight:700;text-align:center;">Back to<br>condition</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;gap:4px;padding-top:18px;">
        <div style="font-size:.6rem;color:var(--red);font-weight:700;">FALSE</div>
        <div class="flow-arrow">&#x25BC;</div>
        <div class="flow-node flow-end" style="width:80px;">END</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div><strong>Always update</strong> the loop variable inside the body — otherwise the loop runs forever!</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — WHILE LOOP TRACING + INFINITE LOOP
═══════════════════════════════════════════════════════ -->

<Slide2 topic="While Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">While Loop — <span class="highlight">Tracing</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <!-- <div v-click class="section-label">Infinite while Loop — Danger Zone!</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.75rem;line-height:1.9;">
    <span style="color:#6b7280;"># Intentional infinite loop</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#c49a00;">True</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">user</span> = <span style="color:#2d7a00;">input</span>(<span style="color:#2d7a00;">"Enter 'quit' to stop: "</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">user</span> == <span style="color:#2d7a00;">"quit"</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">break</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"You said:"</span>, <span style="color:#0e6ead;">user</span>)</span>
  </div>
  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>while True:</strong> runs forever. Use <span class="mono" style="color:var(--red-dark);">break</span> to exit, or ensure the condition eventually becomes False.</div>
  </div>
  <div v-click class="card card-red" style="margin-top:4px;">
    <div class="small-text"><strong>Common mistake:</strong> Forgetting to update the counter variable inside the loop body.</div>
  </div> -->
  <div v-click class="section-label">Syntax Diagram</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px 18px;font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;">
    <span style="color:#6b7280;"># Initialize variable</span><br>
    <span style="color:#0e6ead;">counter</span> = <span style="color:#b45309;">1</span><br>
    <br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">&lt;=</span> <span style="color:#b45309;">5</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">counter</span>)</span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Update variable</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">+=</span> <span style="color:#b45309;">1</span></span>
  </div>
  <!-- <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    <span class="comment"># Output</span><br>
    1 &nbsp;2 &nbsp;3 &nbsp;4 &nbsp;5
  </div> -->
</div>
<div class="flex-col">
  <div v-after class="section-label">Step-by-Step Trace: counter = 1 to 5</div>
  <div>
    <table class="trace-table">
      <thead v-after  >
        <tr><th>Iteration</th><th>counter</th><th>Condition (counter &lt;= 5)</th><th>Output</th></tr>
      </thead>
      <tbody>
        <tr v-click><td>1</td><td>1</td><td class="yes">True</td><td>1</td></tr>
        <tr v-click><td>2</td><td>2</td><td class="yes">True</td><td>2</td></tr>
        <tr v-click><td>3</td><td>3</td><td class="yes">True</td><td>3</td></tr>
        <tr v-click><td>4</td><td>4</td><td class="yes">True</td><td>4</td></tr>
        <tr v-click><td>5</td><td>5</td><td class="yes">True</td><td>5</td></tr>
        <tr v-click class="hl"><td>6</td><td>6</td><td class="no">False</td><td>Exit</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    <span class="comment"># Output</span><br>
    1 &nbsp;2 &nbsp;3 &nbsp;4 &nbsp;5
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
  { text: '<b>Problem:</b> Print all odd numbers from 1 to 20 using a while loop.' },
  { text: '<b>Input:</b> No input required. The range is fixed from <code>1</code> to <code>20</code>.' },
  {
    text: '<b>Expected Output:</b><br><code>1</code><br><code>3</code><br><code>5</code><br><code>7</code><br><code>9</code><br><code>11</code><br><code>13</code><br><code>15</code><br><code>17</code><br><code>19</code>'
  },
  // {
  //   text: '<b>Note:</b> Use a <b>while</b> loop starting from <code>1</code>. Print the number if it is odd, then increment by <code>1</code> each iteration. The loop should run as long as the number is less than or equal to <code>20</code>.'
  // },
  // { text: '<b>Hint:</b> Use <code>while (n <= 20)</code>. Inside the loop, check <code>if (n % 2 !== 0)</code> to identify odd numbers, then print <code>n</code> and increment with <code>n++</code>.', highlight: true },
]
</script>

<Slide
  topic="While Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a number as input and repeatedly divide it by 9 until the result becomes a single digit (less than 10). Print the result after each division.' },
  { text: '<b>Input:</b> <code>729</code>' },
  { text: '<b>Expected Output:</b><br><code>729 / 9 = 81</code><br><code>81 / 9 = 9</code><br><code>Result: 9</code>' },
  // { text: '<b>Note:</b> Use a <b>while</b> loop. The loop should continue as long as the number is greater than or equal to 10.' },
  // { text: '<b>Hint:</b> Use <code>while (n >= 10)</code> and divide <code>n = n / 9</code> inside the loop. Print the value of <code>n</code> after each step.', highlight: true },
]
</script>

<Slide
  topic="While Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>


---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — FOR LOOP: SYNTAX + STRING ITERATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="For Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">For</span> Loop — Syntax &amp; Iterating Strings</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Syntax Structure</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px;font-family:'Fira Code',monospace;font-size:.8rem;line-height:2;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">variable</span> <span style="color:#ef5050;">in</span> <span style="color:#c49a00;">sequence</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;color:#2d7a00;">body of loop</span>
  </div>

  <div v-click style="margin-top:6px;display:flex;flex-direction:column;gap:6px;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-keyword">for</span>
      <span class="body-text">Loop keyword</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-varname">variable</span>
      <span class="body-text">Takes each item from the sequence</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-keyword">in</span>
      <span class="body-text">Membership operator — part of for syntax</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-value">sequence</span>
      <span class="body-text">String, list, range, tuple etc.</span>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div>The <span class="mono">for</span> loop automatically stops when all items in the sequence are exhausted. No need to update a counter!</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Iterating Through a String</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.75rem;line-height:1.9;">
    <span style="color:#6b7280;"># Each character of the string</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">"Python"</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">ch</span>)</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Iteration Visualization</div>
    <div style="display:flex;gap:4px;flex-wrap:wrap;">
      <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:var(--red-dark);">P</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=0</div>
      </div>
      <div v-after style="background:#ebf8ff;border:2px solid #3182ce;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#2b6cb0;">y</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=1</div>
      </div>
      <div v-after style="background:#f0fff4;border:2px solid #38a169;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#276749;">t</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=2</div>
      </div>
      <div v-after style="background:#fffaf0;border:2px solid #dd6b20;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#c05621;">h</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=3</div>
      </div>
      <div v-after style="background:#fde8e8;border:2px solid #ef5050;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#c73c3c;">o</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=4</div>
      </div>
      <div v-after style="background:#ebf8ff;border:2px solid #3182ce;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#2b6cb0;">n</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=5</div>
      </div>
    </div>
  </div>

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    P &nbsp;y &nbsp;t &nbsp;h &nbsp;o &nbsp;n
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
  { text: '<b>Problem:</b> Take a string as input and count the total number of <b>vowels</b> (<code>a, e, i, o, u</code>) in it. Print the count.' },
  { text: '<b>Input:</b> <code>hello world</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Number of vowels: 3</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> Loop through each <b>character</b> in the string one by one using a <code>for</code> loop. Check if the character is a vowel by using the <code>in</code> operator against the string <code>"aeiou"</code>. Use a <b>counter variable</b> starting at <code>0</code> and increment it each time a vowel is found. Use <code>.lower()</code> to handle both uppercase and lowercase letters correctly.'
  // },
  // {
  //   text: '<b>Note:</b> Use <code>for ch in string:</code> to iterate over each character. Inside the loop, check <code>if ch.lower() in "aeiou":</code> and increment the counter. After the loop ends, print the final count.'
  // },
  // { text: '<b>Hint:</b> Start with <code>count = 0</code> — Use <code>for ch in text:</code> — Check <code>if ch.lower() in "aeiou":</code> then <code>count += 1</code> — Finally <code>print("Number of vowels:", count)</code>.', highlight: true },
]
</script>

<Slide
  topic="For Loop"
  sub-topic="String Iteration — Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — FOR LOOP: LIST ITERATION + RANGE()
═══════════════════════════════════════════════════════ -->

<Slide2 topic="For Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">For</span> Loop — Lists &amp; <span class="highlight">range()</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Iterating Through a List</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.75rem;line-height:1.9;">
    <span style="color:#6b7280;"># Loop through a list</span><br>
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">fruit</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">fruits</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"I like"</span>, <span style="color:#0e6ead;">fruit</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    I like apple<br>
    I like banana<br>
    I like cherry
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">List Iteration Visual</div>
    <div style="display:flex;gap:4px;align-items:center;flex-wrap:wrap;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
      <div style="background:#ebf8ff;border:2px solid #3182ce;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:#2b6cb0;">apple</div>
      <div style="color:var(--muted);font-size:1rem;">&#x2192;</div>
      <div style="background:#f0fff4;border:2px solid #38a169;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:#276749;">banana</div>
      <div style="color:var(--muted);font-size:1rem;">&#x2192;</div>
      <div style="background:#fde8e8;border:2px solid #ef5050;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:#c73c3c;">cherry</div>
      <div style="color:var(--muted);font-size:1rem;">&#x2192;</div>
      <div style="background:#e2e8f0;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:var(--muted)">Done</div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">range() Function</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># range(stop) — 0 to stop-1</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">5</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># Output: 0 1 2 3 4</span><br><br>
    <span style="color:#6b7280;"># range(start, stop)</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># Output: 1 2 3 4 5</span>
  </div>

  <div style="margin-top:6px;">
    <div v-click class="section-label" style="margin-bottom:6px;">range() Sequence Visualization</div>
    <div v-after style="background:#f7f8fc;border-radius:8px;padding:8px 12px;border:1px solid var(--border);">
      <div style="font-size:.65rem;color:var(--muted);margin-bottom:4px;font-family:'Fira Code',monospace;">range(1, 6) generates:</div>
      <div style="display:flex;gap:6px;">
        <div v-click style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">1</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">2</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">3</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">4</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">5</div>
        <div v-after style="background:#e2e8f0;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:var(--muted)">stop</div>
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
     SLIDE 9 — range(start, stop, step) IN DETAIL
═══════════════════════════════════════════════════════ -->

<Slide2 topic="For Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">range()</span> — start, stop, step</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Full Syntax</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px;font-family:'Fira Code',monospace;font-size:.76rem;line-height:2;">
    <span style="color:#2d7a00;">range</span>(<span style="color:#ef5050;">start</span>, <span style="color:#b45309;">stop</span>, <span style="color:#0e6ead;">step</span>)
  </div>

  <div v-click style="margin-top:8px;display:flex;flex-direction:column;gap:5px;">
    <div class="card" style="padding:8px 14px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-keyword">start</span>
        <span class="body-text">Where to begin (default: 0)</span>
      </div>
    </div>
    <div class="card" style="padding:8px 14px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-value">stop</span>
        <span class="body-text">Where to end (not included)</span>
      </div>
    </div>
    <div class="card" style="padding:8px 14px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-operator">step</span>
        <span class="body-text">How much to jump (default: 1)</span>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Step can be <strong>negative</strong> to count backwards! <span class="mono">range(10, 0, -1)</span></div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Examples with Visualization</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># Step = 2 (even numbers)</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">0</span>, <span style="color:#b45309;">10</span>, <span style="color:#b45309;">2</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># 0 2 4 6 8</span><br><br>
    <span style="color:#6b7280;"># Countdown (negative step)</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">5</span>, <span style="color:#b45309;">0</span>, <span style="color:#b45309;">-1</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># 5 4 3 2 1</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Step=2 Visualization: range(0,10,2)</div>
    <div style="background:#f7f8fc;border-radius:8px;padding:8px 12px;border:1px solid var(--border);display:flex;gap:4px;flex-wrap:wrap;align-items:center;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">0</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">2</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">4</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">6</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">8</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:#e2e8f0;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:var(--muted)">10 = stop</div>
    </div>
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
  { text: '<b>Problem:</b> Print the multiplication table of 7 for numbers 1 through 10 using <code>range(1, 11)</code>.' },
  { text: '<b>Input:</b> No input required. The multiplier is fixed as <code>7</code> and the range is <code>1</code> to <code>10</code>.' },
  {
    text: '<b>Expected Output:</b><br><code>7 x 1 = 7</code><br><code>7 x 2 = 14</code><br><code>7 x 3 = 21</code><br><code>7 x 4 = 28</code><br><code>7 x 5 = 35</code><br><code>7 x 6 = 42</code><br><code>7 x 7 = 49</code><br><code>7 x 8 = 56</code><br><code>7 x 9 = 63</code><br><code>7 x 10 = 70</code>'
  },
  {
    text: '<b>Note:</b> Use a <b>for</b> loop with <code>range(1, 11)</code> to iterate from <code>1</code> to <code>10</code>. For each value of <code>i</code>, calculate <code>7 * i</code> and print it in the format <code>7 x i = result</code>.'
  },
  // { text: '<b>Hint:</b> Use <code>for i in range(1, 11):</code> and inside the loop print <code>f"7 x {i} = {7 * i}"</code> using an f-string.', highlight: true },
]
</script>

<Slide
  topic="For Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Calculate and print the sum of all even numbers between 1 and 50.' },
  { text: '<b>Expected Output:</b> <code>Sum of even numbers = 650</code>' },
  { text: '<b>Note:</b> Use a <b>for</b> loop. A number is even if <code>number % 2 == 0</code>.' },
  // { text: '<b>Hint:</b> Declare a variable <code>sum = 0</code> before the loop. Inside the loop, check if <code>i % 2 == 0</code> and add <code>i</code> to <code>sum</code>. Print <code>sum</code> after the loop.', highlight: true },
]
</script>

<Slide
  topic="For Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>



---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — while vs for COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Comparison">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">while</span> Loop vs <span class="highlight">for</span> Loop</div>

<div >
<table class="cmp-table">
  <thead>
    <tr>
      <th>Feature</th>
      <th>while Loop</th>
      <th>for Loop</th>
    </tr>
  </thead>
  <tbody>
    <tr v-click>
      <td><strong>Use when</strong></td>
      <td>Number of iterations is <strong>unknown</strong></td>
      <td>Number of iterations is <strong>known</strong></td>
    </tr>
    <tr v-click>
      <td><strong>Condition</strong></td>
      <td>Custom boolean condition</td>
      <td>Iterates over a sequence</td>
    </tr>
    <tr v-click>
      <td><strong>Counter update</strong></td>
      <td class="no">Manual — must do it yourself</td>
      <td class="yes">Automatic</td>
    </tr>
    <tr v-click>
      <td><strong>Risk of infinite loop</strong></td>
      <td class="no">Higher (if update is missed)</td>
      <td class="yes">Lower</td>
    </tr>
    <tr v-click>
      <td><strong>Typical use case</strong></td>
      <td>Menu-driven programs, user input</td>
      <td>Traversing lists, strings, ranges</td>
    </tr>
  </tbody>
</table>
</div>

<div class="g2" style="gap:10px;margin-top:12px;">

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <div style="color:#ef5050;font-weight:700;margin-bottom:6px;">while loop</div>
    <span style="color:#0e6ead;">i</span> = <span style="color:#b45309;">1</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">i</span> &lt;= <span style="color:#b45309;">5</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">i</span> += <span style="color:#b45309;">1</span></span>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <div style="color:#2d7a00;font-weight:700;margin-bottom:6px;">for loop — same result, less code</div>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

</div>

  </template>
</Slide2>


---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — NESTED LOOPS: SYNTAX + EXECUTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Nested Loops">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Nested</span> Loops — Syntax &amp; Execution</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Syntax &amp; Example</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Outer loop</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>):<br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Inner loop</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">for</span> <span style="color:#c49a00;">j</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>):</span>
    <span style="padding-left:40px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>, <span style="color:#2d7a00;">"x"</span>, <span style="color:#c49a00;">j</span>, <span style="color:#2d7a00;">"="</span>, <span style="color:#0e6ead;">i</span>*<span style="color:#c49a00;">j</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.7rem;">
    1 x 1 = 1 &nbsp; 1 x 2 = 2 &nbsp; 1 x 3 = 3<br>
    2 x 1 = 2 &nbsp; 2 x 2 = 4 &nbsp; 2 x 3 = 6<br>
    3 x 1 = 3 &nbsp; 3 x 2 = 6 &nbsp; 3 x 3 = 9
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div>For every 1 run of the outer loop, the inner loop runs <strong>completely</strong> — all its iterations.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Execution Visualization (i x j iterations)</div>

  <div v-after style="overflow-x:auto;">
    <table class="trace-table" style="font-size:.68rem;">
      <thead>
        <tr><th>Outer (i)</th><th>Inner (j)</th><th>i * j</th><th>Total Count</th></tr>
      </thead>
      <tbody>
        <tr><td>1</td><td>1, 2, 3</td><td>1, 2, 3</td><td>3 runs</td></tr>
        <tr><td>2</td><td>1, 2, 3</td><td>2, 4, 6</td><td>3 runs</td></tr>
        <tr><td>3</td><td>1, 2, 3</td><td>3, 6, 9</td><td>3 runs</td></tr>
        <tr class="hl"><td colspan="3"><strong>Total iterations</strong></td><td><strong>9 runs</strong></td></tr>
      </tbody>
    </table>
  </div>
    <!-- <div v-click class="small-text" style="margin-top:10px;"><strong>Pattern: Star Triangle</strong></div>
    <div v-after style="background:#f6f8fa;border-radius:6px;border:1px solid #e1e4e8;padding:8px 12px;margin-top:6px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.8;">
      <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">5</span>):<br>
      <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"* "</span> * <span style="color:#0e6ead;">i</span>)</span>
      <div style="color:#2d7a00;margin-top:6px;">*<br>* *<br>* * *<br>* * * *</div>
    </div> -->
</div>

</div>

  </template>
</Slide2>


---
transition: slide-up
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> Display the following number grid pattern using a nested loop.' },
  {
    label: 'Expected Output',
    text: '1 2 3\n4 5 6\n7 8 9',
    codeEditor: true,
    lang: 'java',
  },
  { text: '<b>Note:</b> Use a nested <b>for</b> loop. The outer loop controls the rows and the inner loop controls the columns.' },
  // { text: '<b>Hint:</b> Declare a variable <code>num = 1</code> before both loops. Inside the inner loop, print <code>num</code> and increment it. Use <code>System.out.println()</code> after the inner loop to move to the next row.', highlight: true },
]
</script>

<Slide
  topic="Nested Loops"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Print a number triangle pattern using nested <b>for</b> loops.' },
  {
    text: '<b>Expected Output:</b><br><code>1</code><br><code>1 2</code><br><code>1 2 3</code><br><code>1 2 3 4</code>'
  },
  // {
  //   text: '<b>Pattern Logic:</b> The pattern has <b>4 rows</b>. Row 1 prints <code>1</code>, row 2 prints <code>1 2</code>, row 3 prints <code>1 2 3</code>, and row 4 prints <code>1 2 3 4</code>. Notice that row number <code>i</code> always prints numbers from <code>1</code> up to <code>i</code>.'
  // },
  // {
  //   text: '<b>Note:</b> Use an <b>outer loop</b> with <code>range(1, 5)</code> to control the <b>row number</b>. Use an <b>inner loop</b> with <code>range(1, i + 1)</code> to print numbers in each row. Use <code>end=" "</code> to print numbers on the same line, separated by spaces.'
  // },
  // { text: '<b>Hint:</b> Outer loop: <code>for i in range(1, 5):</code> — Inner loop: <code>for j in range(1, i + 1): print(j, end=" ")</code> — After the inner loop, add <code>print()</code> to move to the next line.', highlight: true },
]
</script>

<Slide
  topic="Nested Loops"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — break AND continue STATEMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Loop Control">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">break</span> &amp; <span class="highlight">continue</span> Statements</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click style="display:flex;align-items:center;gap:8px;margin-bottom:8px;">
    <span style="background:var(--red);color:#fff;border-radius:6px;padding:3px 12px;font-family:'Fira Code',monospace;font-weight:700;font-size:.85rem;">break</span>
    <span class="body-text">— Exits the loop immediately</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">10</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> == <span style="color:#b45309;">5</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">break</span> <span style="color:#6b7280;"># stop at 5</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; <span style="color:#c0392b;">(stopped before 5)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:4px;">break Flow Diagram</div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
      <div class="flow-node flow-start" style="width:120px;">for i in range</div>
      <div class="flow-arrow">&#x25BC;</div>
      <div class="flow-node flow-cond" style="width:140px;font-size:.68rem;">i == 5 ?</div>
      <div style="display:flex;gap:20px;">
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--red);font-weight:700;">YES</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node flow-end" style="width:80px;font-size:.65rem;">Exit Loop</div>
        </div>
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--green);font-weight:700;">NO</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node flow-body" style="width:90px;font-size:.65rem;">print(i)</div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click style="display:flex;align-items:center;gap:8px;margin-bottom:8px;">
    <span style="background:var(--green);color:#fff;border-radius:6px;padding:3px 12px;font-family:'Fira Code',monospace;font-weight:700;font-size:.85rem;">continue</span>
    <span class="body-text">— Skips current iteration</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">8</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> % <span style="color:#b45309;">2</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">continue</span> <span style="color:#6b7280;"># skip even</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 3 &nbsp; 5 &nbsp; 7 &nbsp; <span style="color:#6b7280;">(even numbers skipped)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:4px;">continue Flow Diagram</div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
      <div class="flow-node flow-start" style="width:120px;">for i in range</div>
      <div class="flow-arrow">&#x25BC;</div>
      <div class="flow-node flow-cond" style="width:150px;font-size:.68rem;">i % 2 == 0 ?</div>
      <div style="display:flex;gap:20px;">
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--red);font-weight:700;">YES</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node" style="background:#fffaf0;border:1px solid var(--orange);color:var(--orange);width:90px;font-size:.65rem;">Skip → next i</div>
        </div>
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--green);font-weight:700;">NO</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node flow-body" style="width:90px;font-size:.65rem;">print(i)</div>
        </div>
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

<script setup>
const contents = [
  { text: '<b>Problem:</b> Loop through numbers from <code>1</code> to <code>20</code>. Find the <b>first</b> number that is divisible by both <code>3</code> and <code>5</code>. Print it and stop the loop immediately.' },
  {
    text: '<b>Expected Output:</b><br><code>15</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> A number is divisible by both <code>3</code> and <code>5</code> when <code>n % 3 == 0</code> <b>and</b> <code>n % 5 == 0</code>. Use the <b>modulo operator</b> <code>%</code> to check divisibility. Once found, use <code>break</code> to exit the loop immediately without checking remaining numbers.'
  // },
  {
    text: '<b>Note:</b> Use a <b>for</b> loop with <code>range(1, 21)</code> to go through numbers <code>1</code> to <code>20</code>. Inside the loop, use an <b>if</b> condition to check both divisibility conditions together using <code>and</code>. When the condition is met, <b>print</b> the number and <b>break</b> out of the loop.'
  },
  // { text: '<b>Hint:</b> Use <code>for n in range(1, 21):</code> — Inside, check <code>if n % 3 == 0 and n % 5 == 0:</code> — Then <code>print(n)</code> followed by <code>break</code> to stop the loop.', highlight: true },
]
</script>

<Slide
  topic="Loop Control"
  sub-topic="Practice Problem"
  :contents="contents"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — pass STATEMENT + break/continue/pass COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Loop Control">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">pass</span> Statement &amp; Complete Comparison</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click style="display:flex;align-items:center;gap:8px;margin-bottom:8px;">
    <span style="background:var(--yellow);color:#fff;border-radius:6px;padding:3px 12px;font-family:'Fira Code',monospace;font-weight:700;font-size:.85rem;">pass</span>
    <span class="body-text">— Placeholder, does nothing</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> == <span style="color:#b45309;">3</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">pass</span> <span style="color:#6b7280;"># nothing here yet</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5 &nbsp; <span style="color:#6b7280;">(all printed — pass does nothing)</span>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>pass</strong> is useful when you want an empty block syntactically — Python does not allow empty blocks!</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">break vs continue vs pass</div>

  <div>
    <table class="cmp-table">
      <thead v-after>
        <tr><th>Statement</th><th>Effect on Loop</th><th>Loop Continues?</th></tr>
      </thead>
      <tbody>
        <tr v-click>
          <td><span class="mono" style="color:var(--red-dark);font-weight:700;">break</span></td>
          <td>Exits the loop completely</td>
          <td class="no">No</td>
        </tr>
        <tr v-click>
          <td><span class="mono" style="color:var(--green);font-weight:700;">continue</span></td>
          <td>Skips the current iteration</td>
          <td class="yes">Yes (next iteration)</td>
        </tr>
        <tr v-click>
          <td><span class="mono" style="color:var(--yellow);font-weight:700;">pass</span></td>
          <td>Does nothing — placeholder</td>
          <td class="yes">Yes (normally)</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div v-click class="card card-navy" style="margin-top:10px;">
    <div style="font-size:.7rem;color:var(--slate);line-height:1.7;">
      <strong style="color:var(--red-dark);">break</strong> — "I found what I need, stop searching"<br>
      <strong style="color:var(--green);">continue</strong> — "Skip this one, check the next"<br>
      <strong style="color:var(--orange);">pass</strong> — "I'll fill this logic in later"
    </div>
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
  { text: '<b>Problem:</b> Display the following star pattern using a nested loop.' },
  {
    label: 'Expected Output',
    text: '*\n* *\n* * *\n* * * *\n* * * * *',
    codeEditor: true,
    lang: 'java',
  },
  { text: '<b>Note:</b> Use a nested <b>for</b> loop. Row 1 has 1 star, row 2 has 2 stars, and so on up to 5 rows.' },
  // { text: '<b>Hint:</b> The outer loop runs from <code>i = 1</code> to <code>5</code>. The inner loop runs from <code>j = 1</code> to <code>i</code>. Print <code>"* "</code> inside the inner loop and call <code>System.out.println()</code> after it.', highlight: true },
]
</script>

<Slide
  topic="Loop Control"
  sub-topic="Practice Problem"
/>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — else WITH LOOPS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="else with Loops">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">else</span> with Loops — Python's Unique Feature</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      The <strong style="color:var(--red);">else</strong> block after a loop runs <strong style="color:var(--green);">only when the loop completes normally</strong> — i.e., when the condition becomes False naturally, <strong>not</strong> when broken by <span class="mono" style="color:var(--red-dark);">break</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:6px;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Loop finished normally!"</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5<br>
    <span style="color:#b45309;">Loop finished normally!</span>
  </div>
</div>

<div class="flex-col">
  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># break prevents else from running</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> == <span style="color:#b45309;">3</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">break</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"This won't print!"</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; <span style="color:#c0392b;">(stopped by break — else skipped)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">When does else run?</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead><tr><th>Loop ends via</th><th>else runs?</th></tr></thead>
      <tbody>
        <tr><td>Condition became False (normal)</td><td class="yes">Yes</td></tr>
        <tr><td>Sequence exhausted (for loop)</td><td class="yes">Yes</td></tr>
        <tr><td>break statement</td><td class="no">No</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div><strong>Use case:</strong> Search loops — run else when item is NOT found after exhausting all elements.</div>
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
  { text: '<b>Problem:</b> Loop through numbers from <code>1</code> to <code>10</code> and search for the first number divisible by <code>4</code> and <code>6</code>. If found, print it and stop. If <b>no such number exists</b> in the range, print a not-found message.' },
  { text: '<b>Input:</b> No input required. The range is fixed from <code>1</code> to <code>10</code>.' },
  {
    text: '<b>Expected Output:</b><br><code>No number divisible by both 4 and 6 found in range.</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> In Python, a <code>for</code> loop can have an <b>else</b> block. The <code>else</code> runs <b>only if</b> the loop completes <b>without hitting a <code>break</code></b>. If <code>break</code> is executed, the <code>else</code> is <b>skipped</b>. This makes <code>for...else</code> perfect for <b>search problems</b> — use <code>break</code> on success and <code>else</code> to handle the "not found" case cleanly.'
  // },
  // {
  //   text: '<b>Note:</b> Use <code>for n in range(1, 11):</code> and check <code>if n % 4 == 0 and n % 6 == 0</code>. If true, print the number and <code>break</code>. Add an <code>else</code> block at the <b>same indentation as <code>for</code></b> (not inside it) to print the not-found message.'
  // },
  // { text: '<b>Hint:</b> Use <code>for n in range(1, 11):</code> — Check <code>if n % 4 == 0 and n % 6 == 0: print(n); break</code> — Then at the for level: <code>else: print("No number divisible by both 4 and 6 found in range.")</code>', highlight: true },
]
</script>

<Slide
  topic="else with Loops"
  sub-topic="Practice Problem"
  :contents="contents"
/>