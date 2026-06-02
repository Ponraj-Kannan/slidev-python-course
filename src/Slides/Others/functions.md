---
theme: default
title: Python Functions
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
  --purple:    #805ad5;
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
.card-purple { background: #faf5ff; border: 1px solid var(--purple); border-radius: var(--radius); padding: 14px 18px; }

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
.pill-purple { background: #faf5ff;          color: var(--purple); }

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

/* ── Code block ──────────────────────────────────────────── */
.code-block {
  background: #f6f8fa;
  border-radius: var(--radius);
  border: 1px solid #e1e4e8;
  padding: 14px 16px;
  font-family: 'Fira Code', monospace;
  font-size: 0.72rem;
  line-height: 1.9;
}

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
  font-size: 1.1rem;
  font-weight: 800;
  flex-shrink: 0;
}
.ic-red    { background: var(--red-soft); color: var(--red-dark); }
.ic-navy   { background: #eef0f8; color: var(--navy-mid); }
.ic-green  { background: #f0fff4; color: var(--green); }
.ic-orange { background: #fffaf0; color: var(--orange); }
.ic-blue   { background: #ebf8ff; color: var(--blue); }
.ic-purple { background: #faf5ff; color: var(--purple); }

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
.trace-table .hl { background: #fff5f5; color: var(--red-dark); font-weight: 700; }

/* ── Flow nodes ──────────────────────────────────────────── */
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
.flow-call   { background: #ebf8ff; color: var(--blue); border-color: var(--blue); }
.flow-return { background: #faf5ff; color: var(--purple); border-color: var(--purple); }
.flow-arrow  { text-align: center; color: var(--muted); font-size: 1rem; font-weight: 900; line-height: 1; }

/* ── Stack frame visualization ───────────────────────────── */
.stack-frame {
  background: var(--white);
  border: 2px solid var(--blue);
  border-radius: 6px;
  padding: 6px 12px;
  font-family: 'Fira Code', monospace;
  font-size: 0.7rem;
  margin-bottom: 4px;
  text-align: center;
  color: var(--navy);
}
.stack-frame.top    { border-color: var(--red); background: var(--red-soft); color: var(--red-dark); }
.stack-frame.done   { border-color: var(--green); background: #f0fff4; color: #276749; }
.stack-frame.middle { border-color: var(--orange); background: #fffaf0; color: #c05621; }

/* ── Memory box ──────────────────────────────────────────── */
.mem-box {
  background: var(--white);
  border: 1.5px solid var(--border);
  border-radius: 8px;
  padding: 8px 12px;
  font-family: 'Fira Code', monospace;
  font-size: 0.7rem;
}
.mem-box .mem-label {
  font-size: 0.6rem;
  font-weight: 800;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 4px;
}
.mem-local  { border-color: var(--blue); background: #ebf8ff; }
.mem-global { border-color: var(--green); background: #f0fff4; }
</style>


<!-- ═══════════════════════════════════════════════════════
     SLIDE 1 — TITLE / INTRODUCTION TO FUNCTIONS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Functions — Introduction">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is a <span class="highlight">Function ?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">function</strong> is a named block of code that performs a <strong style="color:var(--green);">specific task</strong>. You write it once and call it as many times as you need.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Without functions:</strong> The same logic is copy-pasted everywhere. With functions — write once, reuse anywhere!</div>
  </div>

  <div v-click class="card card-red" style="margin-top:4px;">
    <div class="slide-h3" style="margin-bottom:6px;">Real-World Analogy</div>
    <div class="body-text">A <strong>coffee machine</strong> takes inputs (beans, water), performs a task internally, and returns coffee. A function works the same way — inputs in, output out.</div>
  </div>

  <div v-click class="card card-green">
    <div class="small-text"><strong>Key benefit:</strong> Reusable code blocks make programs <strong>shorter</strong>, <strong>cleaner</strong>, and <strong>easier to maintain</strong>.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="slide-h3" style="margin-bottom:8px;">Without Function vs With Function</div>

  <div v-after class="code-block">
    <div style="color:#6b7280;margin-bottom:4px;"># Without function — repetitive!</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">10</span> + <span style="color:#b45309;">20</span>)</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">15</span> + <span style="color:#b45309;">25</span>)</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">30</span> + <span style="color:#b45309;">40</span>)</div>
    <br>
    <div style="color:#6b7280;"># With function — clean and reusable!</div>
    <div><span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">add</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>):</div>
    <div style="padding-left:20px;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">a</span> + <span style="color:#0e6ead;">b</span></div>
    <br>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">add</span>(<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>))</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">add</span>(<span style="color:#b45309;">15</span>, <span style="color:#b45309;">25</span>))</div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Two main types of Functions:</strong></div>
    <div style="display:flex;gap:8px;margin-top:6px;flex-wrap:wrap;">
      <span class="pill pill-red">Built-in Functions</span>
      <span class="pill pill-blue">User-defined Functions</span>
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
     SLIDE 2 — WHY FUNCTIONS ARE IMPORTANT & ADVANTAGES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Why Functions — Importance &amp; Advantages">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Why Use <span class="highlight">Functions ?</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Top Advantages</div>

  <div v-after class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-red">R</div>
    <div>
      <div class="slide-h3">Reusability</div>
      <div class="small-text">Write the logic once, call it many times — anywhere in the program.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-blue">M</div>
    <div>
      <div class="slide-h3">Modularity</div>
      <div class="small-text">Break a large program into small, manageable, named blocks.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-green">D</div>
    <div>
      <div class="slide-h3">Debugging Made Easy</div>
      <div class="small-text">Bugs are isolated to one function — easier to test and fix.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-orange">A</div>
    <div>
      <div class="slide-h3">Abstraction</div>
      <div class="small-text">Hide complex details. Just call the function — no need to know how it works inside.</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Real-World Comparison</div>

  <div v-after class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      Imagine building a <strong style="color:var(--red);">house</strong>. Would you make each brick from scratch? No — you reuse pre-made bricks. Functions are the <strong style="color:var(--green);">bricks</strong> of your program.
    </div>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Code Size Comparison</div>
    <table class="cmp-table">
      <thead>
        <tr><th>Approach</th><th>Lines for 5 calculations</th><th>Readability</th></tr>
      </thead>
      <tbody>
        <tr><td>Without function</td><td class="no">25+ lines</td><td class="no">Low</td></tr>
        <tr><td>With function</td><td class="yes">7 lines</td><td class="yes">High</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div><strong>Golden Rule:</strong> If you find yourself writing the same logic twice — turn it into a function!</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 3 — FUNCTION SYNTAX & DEFINING A FUNCTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Function Syntax &amp; Definition">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">def</span> — Function Syntax &amp; Definition</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Syntax Structure</div>

  <div v-after class="code-block" style="font-size:.78rem;line-height:2;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">function_name</span>(<span style="color:#c49a00;">parameters</span>)<span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># docstring (optional)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"""Description"""</span></span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># body of the function</span>
    <span style="padding-left:20px;display:block;color:#2d7a00;">statement(s)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">value</span></span>
  </div>

  <div v-click style="margin-top:8px; border:1px solid #e1e4e8; padding:10px; border-radius:10px;">
    <div class="section-label" style="margin-bottom:6px;">Syntax Parts</div>
    <div style="display:flex;flex-direction:column;gap:5px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-keyword">def</span>
        <span class="body-text">Keyword that starts a function definition</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-varname">function_name</span>
        <span class="body-text">A valid Python identifier (lowercase, underscores)</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-value">parameters</span>
        <span class="body-text">Inputs the function accepts (can be empty)</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-operator">return</span>
        <span class="body-text">Sends a value back to the caller (optional)</span>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Simple Example — greet()</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Define a function</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">greet</span>():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hello, Pythonist!"</span>)</span>
    <br>
    <span style="color:#6b7280;"># Call the function</span><br>
    <span style="color:#0e6ead;">greet</span>()
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">Hello, Pythonist!</div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Naming Rules</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead><tr><th>Rule</th><th>Example</th></tr></thead>
      <tbody>
        <tr><td>Must start with letter or _</td><td><span class="mono yes">add_two</span></td></tr>
        <tr><td>No digits at the start</td><td><span class="mono no">2add</span></td></tr>
        <tr><td>No spaces or hyphens</td><td><span class="mono no">add two</span></td></tr>
        <tr><td>Use lowercase + underscores</td><td><span class="mono yes">calculate_sum</span></td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>A function is just <strong>defined</strong> — it does <strong>not run</strong> until you <strong>call</strong> it.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — CALLING A FUNCTION & EXECUTION FLOW
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Calling a Function — Execution Flow">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Calling</span> a Function — Execution Flow</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example Code</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Step 1: define</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">add</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>):<br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Step 3: body runs</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">a</span> + <span style="color:#0e6ead;">b</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">result</span></span>
    <br>
    <span style="color:#6b7280;"># Step 2: call the function</span><br>
    <span style="color:#0e6ead;">total</span> = <span style="color:#0e6ead;">add</span>(<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Total ="</span>, <span style="color:#0e6ead;">total</span>)
  </div>

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">Total = 30</div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div>The order of execution is <strong>not</strong> top-to-bottom. Python jumps to the function only when it is called.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Execution Flow Diagram</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:8px 0;">
    <div class="flow-node flow-start" style="width:200px;">Program Start</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node" style="background:#ebf8ff;border:2px solid var(--blue);color:#2b6cb0;width:220px;font-size:.7rem;">total = add(10, 20)<br>(call detected)</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:220px;">Jump to add() body<br>a=10, b=20</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-body" style="width:220px;">result = 10 + 20<br>= 30</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-return" style="width:220px;">return 30 to caller</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-end" style="width:220px;">print(Total = 30)</div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Three stages of a function:</strong> <span class="pill pill-red">Define</span> <span class="pill pill-blue">Call</span> <span class="pill pill-green">Return</span></div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — PARAMETERS vs ARGUMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Parameters vs Arguments">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Parameters</span> vs <span class="highlight">Arguments</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Parameter</div>
    <div class="small-text" style="margin-top:4px;">Variable listed inside the parentheses in the <strong>function definition</strong>.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">greet</span>(<span style="background:#ebf8ff;padding:2px 6px;border-radius:4px;color:#2b6cb0;font-weight:700;">name</span>)<span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hi"</span>, <span style="color:#0e6ead;">name</span>)</span>
  </div>

  <div v-click class="small-text" style="text-align:center;color:var(--muted);">
    <span class="mono" style="background:#ebf8ff;padding:2px 6px;border-radius:4px;color:#2b6cb0;font-weight:700;">name</span> is a <strong>placeholder</strong> — it has no value until the function is called.
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-orange" style="text-align:center;">
    <div class="slide-h2" style="color:var(--orange);">Argument</div>
    <div class="small-text" style="margin-top:4px;">Actual value passed to the function during the <strong>function call</strong>.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">greet</span>(<span style="background:#fffaf0;padding:2px 6px;border-radius:4px;color:var(--orange);font-weight:700;">"Tina"</span>)<br>
    <span style="color:#0e6ead;">greet</span>(<span style="background:#fffaf0;padding:2px 6px;border-radius:4px;color:var(--orange);font-weight:700;">"Ravi"</span>)
  </div>

  <div v-click class="small-text" style="text-align:center;color:var(--muted);">
    <span class="mono" style="background:#fffaf0;padding:2px 6px;border-radius:4px;color:var(--orange);font-weight:700;">"Tina"</span> and <span class="mono" style="background:#fffaf0;padding:2px 6px;border-radius:4px;color:var(--orange);font-weight:700;">"Ravi"</span> are the actual values supplied at call time.
  </div>
</div>

</div>

<div v-click style="margin-top:12px;">
  <div class="section-label" style="margin-bottom:6px;">Parameter Passing Visualization</div>
  <div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap;justify-content:center;background:#f7f8fc;border-radius:10px;padding:12px;border:1px solid var(--border);">
    <div style="background:#fffaf0;border:2px solid var(--orange);border-radius:8px;padding:6px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">"Tina"</div>
    <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">&#x2192;</div>
    <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:8px;padding:6px 14px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">name</div>
    <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">&#x2192;</div>
    <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:6px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">print("Hi", name)</div>
    <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">&#x2192;</div>
    <div style="background:#f0fff4;border:2px solid var(--green);border-radius:8px;padding:6px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">Hi Tina</div>
  </div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 6 — POSITIONAL & KEYWORD ARGUMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Positional &amp; Keyword Arguments">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Positional</span> &amp; <span class="highlight">Keyword</span> Arguments</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red" style="text-align:center;">
    <div class="slide-h2" style="color:var(--red-dark);">Positional Arguments</div>
    <div class="small-text" style="margin-top:4px;">Values are matched to parameters by their <strong>order</strong>.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">student</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>)</span>
    <br>
    <span style="color:#0e6ead;">student</span>(<span style="color:#2d7a00;">"Anu"</span>, <span style="color:#b45309;">19</span>)<br>
    <span style="color:#6b7280;"># Anu 19</span>
  </div>

  <div v-click class="callout callout-danger" style="font-size:.7rem;">
    <div><strong>Wrong order = wrong result!</strong> <span class="mono">student(19, "Anu")</span> prints <span class="mono">19 Anu</span>.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Keyword Arguments</div>
    <div class="small-text" style="margin-top:4px;">Values are matched by <strong>name</strong> — order doesn't matter.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">student</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>)</span>
    <br>
    <span style="color:#0e6ead;">student</span>(<span style="color:#0e6ead;">age</span>=<span style="color:#b45309;">19</span>, <span style="color:#0e6ead;">name</span>=<span style="color:#2d7a00;">"Anu"</span>)<br>
    <span style="color:#6b7280;"># Anu 19 — order doesn't matter</span>
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div>Improves <strong>readability</strong> — you can see what each value means.</div>
  </div>
</div>

</div>

<div v-click style="margin-top:10px;">
  <div class="section-label" style="margin-bottom:6px;">Side-by-Side Comparison</div>
  <table class="cmp-table">
    <thead>
      <tr><th>Feature</th><th>Positional</th><th>Keyword</th></tr>
    </thead>
    <tbody>
      <tr><td>Matched by</td><td>Position / order</td><td>Parameter name</td></tr>
      <tr><td>Order matters?</td><td class="no">Yes</td><td class="yes">No</td></tr>
      <tr><td>Readability</td><td>Lower</td><td class="yes">Higher</td></tr>
    </tbody>
  </table>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — DEFAULT & VARIABLE-LENGTH ARGUMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Default &amp; Variable-Length Arguments">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Default</span> &amp; <span class="highlight">Variable-Length</span> Arguments</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">Default Arguments</div>
    <div class="small-text" style="margin-top:4px;">Parameter has a <strong>default value</strong> — used if no argument is passed.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">greet</span>(<span style="color:#0e6ead;">name</span>=<span style="color:#2d7a00;">"Friend"</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hello"</span>, <span style="color:#0e6ead;">name</span>)</span>
    <br>
    <span style="color:#0e6ead;">greet</span>()<span style="color:#6b7280;">         # Hello Friend</span><br>
    <span style="color:#0e6ead;">greet</span>(<span style="color:#2d7a00;">"Riya"</span>)<span style="color:#6b7280;">  # Hello Riya</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    Hello Friend<br>
    Hello Riya
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;font-size:.7rem;">
    <div><strong>Rule:</strong> Default parameters must come <strong>after</strong> non-default parameters in the definition.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-purple" style="text-align:center;">
    <div class="slide-h2" style="color:var(--purple);">Variable-Length Arguments (*args)</div>
    <div class="small-text" style="margin-top:4px;">Accept <strong>any number</strong> of positional arguments as a tuple.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">total</span>(<span style="color:var(--purple);font-weight:700;">*nums</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">nums</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">total</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">total</span>(<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>, <span style="color:#b45309;">40</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    6<br>
    100
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">How *args packs the values</div>
    <div style="display:flex;gap:6px;align-items:center;flex-wrap:wrap;background:#f7f8fc;border:1px solid var(--border);padding:8px 10px;border-radius:8px;">
      <span class="mono" style="font-size:.72rem;">total(1, 2, 3)</span>
      <span style="color:var(--muted);font-size:1rem;font-weight:900;">&#x2192;</span>
      <span class="mono" style="background:#faf5ff;border:1px solid var(--purple);padding:3px 8px;border-radius:6px;color:var(--purple);font-size:.72rem;">nums = (1, 2, 3)</span>
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
     SLIDE 8 — RETURN STATEMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Return Statement">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">return</span> Statement</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      The <strong style="color:var(--red);">return</strong> statement sends a value <strong style="color:var(--green);">back to the caller</strong> and immediately <strong>exits</strong> the function.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">square</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">n</span></span>
    <br>
    <span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">square</span>(<span style="color:#b45309;">5</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">25</div>

  <div v-click class="callout callout-info" style="margin-top:6px;font-size:.7rem;">
    <div>Without <strong>return</strong>, a function returns <span class="mono">None</span> by default.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Return Flow</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:6px 0;">
    <div class="flow-node flow-call" style="width:200px;">square(5)</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-body" style="width:200px;">n = 5<br>n * n = 25</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-return" style="width:200px;">return 25</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-end" style="width:200px;">result = 25</div>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px;">
    <div class="small-text"><strong>Important:</strong> Any code after the <span class="mono">return</span> inside the same function will <strong>never execute</strong>.</div>
  </div>

  <div v-click class="code-block" style="font-size:.7rem;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">test</span>():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">"Done"</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"This is unreachable"</span>) <span style="color:#6b7280;"># never runs</span></span>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — RETURNING MULTIPLE VALUES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Returning Multiple Values">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Returning <span class="highlight">Multiple Values</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      Python allows a function to return <strong style="color:var(--red);">more than one value</strong> — separated by commas. They are automatically packed into a <strong style="color:var(--green);">tuple</strong>.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">calc</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>):<br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># multiple return values</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">a</span>+<span style="color:#0e6ead;">b</span>, <span style="color:#0e6ead;">a</span>-<span style="color:#0e6ead;">b</span>, <span style="color:#0e6ead;">a</span>*<span style="color:#0e6ead;">b</span></span>
    <br>
    <span style="color:#0e6ead;">s</span>, <span style="color:#0e6ead;">d</span>, <span style="color:#0e6ead;">p</span> = <span style="color:#0e6ead;">calc</span>(<span style="color:#b45309;">10</span>, <span style="color:#b45309;">4</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>, <span style="color:#0e6ead;">d</span>, <span style="color:#0e6ead;">p</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">14 6 40</div>
</div>

<div class="flex-col">
  <div v-click class="section-label">How Multi-Return Works</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;padding:8px;background:#f7f8fc;border:1px solid var(--border);border-radius:10px;">
    <div style="font-size:.7rem;color:var(--muted);font-family:'Fira Code',monospace;">return a+b, a-b, a*b</div>
    <div style="color:var(--muted);font-size:1rem;font-weight:900;text-align:center;">&#x25BC;</div>
    <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-size:.72rem;color:#c05621;font-weight:700;text-align:center;">
      packed as tuple → (14, 6, 40)
    </div>
    <div style="color:var(--muted);font-size:1rem;font-weight:900;text-align:center;">&#x25BC;</div>
    <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-size:.72rem;color:#2b6cb0;font-weight:700;text-align:center;">
      unpacked: s=14, d=6, p=40
    </div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Tip:</strong> You can also receive all values as a tuple:</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;background:transparent;border:none;padding:0;">
      <span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">calc</span>(<span style="color:#b45309;">10</span>, <span style="color:#b45309;">4</span>)<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>) <span style="color:#6b7280;"># (14, 6, 40)</span>
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
     SLIDE 10 — SCOPE: LOCAL vs GLOBAL VARIABLES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Scope — Local vs Global Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Variable <span class="highlight">Scope</span> — Local vs Global</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Local Variable</div>
    <div class="small-text" style="margin-top:4px;">Declared <strong>inside</strong> a function. Lives only while the function runs.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">show</span>():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">10</span> <span style="color:#6b7280;"># local</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>)</span>
    <br>
    <span style="color:#0e6ead;">show</span>()<span style="color:#6b7280;">   # 10</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>) <span style="color:#6b7280;"># Error: x not defined</span>
  </div>

  <div v-click class="callout callout-danger" style="font-size:.7rem;">
    <div>Accessing a local variable outside its function causes a <strong>NameError</strong>.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">Global Variable</div>
    <div class="small-text" style="margin-top:4px;">Declared <strong>outside</strong> any function. Available everywhere.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">y</span> = <span style="color:#b45309;">100</span> <span style="color:#6b7280;"># global</span><br>
    <br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">show</span>():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">y</span>) <span style="color:#6b7280;"># accessible</span></span>
    <br>
    <span style="color:#0e6ead;">show</span>()<span style="color:#6b7280;">   # 100</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">y</span>) <span style="color:#6b7280;"># 100</span>
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div>Use the <span class="mono">global</span> keyword inside a function if you need to <strong>modify</strong> a global variable.</div>
  </div>
</div>

</div>

<div v-click style="margin-top:10px;">
  <div class="section-label" style="margin-bottom:6px;">Memory View — Local vs Global</div>
  <div class="g2" style="gap:10px;">
    <div class="mem-box mem-global">
      <div class="mem-label">Global Frame</div>
      <div><span style="color:var(--green);font-weight:700;">y</span> = 100</div>
      <div><span style="color:var(--green);font-weight:700;">show</span> = &lt;function&gt;</div>
    </div>
    <div class="mem-box mem-local">
      <div class="mem-label">Local Frame (show)</div>
      <div><span style="color:var(--blue);font-weight:700;">x</span> = 10 <span style="color:var(--muted);">(only here)</span></div>
      <div style="color:var(--muted);">vanishes when show() ends</div>
    </div>
  </div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 11 — RECURSIVE FUNCTIONS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursive Functions">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Recursive</span> Functions</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">recursive function</strong> is one that <strong style="color:var(--green);">calls itself</strong> — breaking a big problem into smaller similar problems.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># Factorial using recursion</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fact</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># base case</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span> <span style="color:#ef5050;">or</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># recursive case</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">fact</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fact</span>(<span style="color:#b45309;">4</span>))<span style="color:#6b7280;"> # 24</span>
  </div>

  <div v-click class="callout callout-danger" style="font-size:.7rem;">
    <div>Every recursive function <strong>must</strong> have a <strong>base case</strong> — otherwise it runs forever (stack overflow).</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Call Stack for fact(4)</div>

  <div v-after style="background:#f7f8fc;border:1px solid var(--border);border-radius:10px;padding:10px;">
    <div class="stack-frame top">fact(4) &nbsp;→ &nbsp; 4 * fact(3)</div>
    <div class="stack-frame middle">fact(3) &nbsp;→ &nbsp; 3 * fact(2)</div>
    <div class="stack-frame middle">fact(2) &nbsp;→ &nbsp; 2 * fact(1)</div>
    <div class="stack-frame done">fact(1) &nbsp;→ &nbsp; returns 1 (base)</div>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Unwinding the Stack</div>
    <table class="trace-table" style="font-size:.68rem;">
      <thead><tr><th>Call</th><th>Returns</th><th>Computes</th></tr></thead>
      <tbody>
        <tr><td>fact(1)</td><td>1</td><td>base case</td></tr>
        <tr><td>fact(2)</td><td>2</td><td>2 * 1</td></tr>
        <tr><td>fact(3)</td><td>6</td><td>3 * 2</td></tr>
        <tr class="hl"><td>fact(4)</td><td><strong>24</strong></td><td>4 * 6</td></tr>
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
     SLIDE 12 — LAMBDA FUNCTIONS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Lambda Functions">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Lambda</span> (Anonymous) Functions</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">lambda</strong> is a tiny <strong style="color:var(--green);">anonymous function</strong> written in one line — perfect for short, throwaway logic.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Syntax</div>

  <div v-after class="code-block" style="font-size:.78rem;line-height:2;">
    <span style="color:#ef5050;">lambda</span> <span style="color:#0e6ead;">arguments</span><span style="color:#1a1f36;">:</span> <span style="color:#2d7a00;">expression</span>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># Normal function</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">square</span>(<span style="color:#0e6ead;">x</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">x</span> * <span style="color:#0e6ead;">x</span></span>
    <br>
    <span style="color:#6b7280;"># Same logic using lambda</span><br>
    <span style="color:#0e6ead;">square</span> = <span style="color:#ef5050;">lambda</span> <span style="color:#0e6ead;">x</span>: <span style="color:#0e6ead;">x</span> * <span style="color:#0e6ead;">x</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">square</span>(<span style="color:#b45309;">5</span>)) <span style="color:#6b7280;"># 25</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Lambda with Built-ins</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Square every item using map()</span><br>
    <span style="color:#0e6ead;">nums</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>]<br>
    <span style="color:#0e6ead;">sq</span> = <span style="color:#2d7a00;">list</span>(<span style="color:#2d7a00;">map</span>(<span style="color:#ef5050;">lambda</span> <span style="color:#0e6ead;">x</span>: <span style="color:#0e6ead;">x</span>**<span style="color:#b45309;">2</span>, <span style="color:#0e6ead;">nums</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sq</span>) <span style="color:#6b7280;"># [1, 4, 9, 16]</span><br>
    <br>
    <span style="color:#6b7280;"># Filter even numbers</span><br>
    <span style="color:#0e6ead;">ev</span> = <span style="color:#2d7a00;">list</span>(<span style="color:#2d7a00;">filter</span>(<span style="color:#ef5050;">lambda</span> <span style="color:#0e6ead;">x</span>: <span style="color:#0e6ead;">x</span>%<span style="color:#b45309;">2</span>==<span style="color:#b45309;">0</span>, <span style="color:#0e6ead;">nums</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">ev</span>) <span style="color:#6b7280;"># [2, 4]</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Normal vs Lambda</div>

  <table v-after class="cmp-table" style="font-size:.7rem;">
    <thead>
      <tr><th>Feature</th><th>def</th><th>lambda</th></tr>
    </thead>
    <tbody>
      <tr><td>Has a name</td><td class="yes">Yes</td><td class="no">No</td></tr>
      <tr><td>Multiple lines</td><td class="yes">Yes</td><td class="no">No (single expression)</td></tr>
      <tr><td>Best for</td><td>Reusable logic</td><td>Short, one-off use</td></tr>
    </tbody>
  </table>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — BUILT-IN vs USER-DEFINED FUNCTIONS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Built-in vs User-defined Functions">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Built-in</span> vs <span class="highlight">User-defined</span> Functions</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Built-in Functions</div>
    <div class="small-text" style="margin-top:4px;">Already available in Python — no need to define them.</div>
  </div>

  <div v-click style="display:flex;gap:6px;flex-wrap:wrap;justify-content:center;margin-top:4px;">
    <span class="pill pill-blue mono">print()</span>
    <span class="pill pill-blue mono">len()</span>
    <span class="pill pill-blue mono">type()</span>
    <span class="pill pill-blue mono">input()</span>
    <span class="pill pill-blue mono">range()</span>
    <span class="pill pill-blue mono">int()</span>
    <span class="pill pill-blue mono">str()</span>
    <span class="pill pill-blue mono">sum()</span>
    <span class="pill pill-blue mono">max()</span>
    <span class="pill pill-blue mono">min()</span>
    <span class="pill pill-blue mono">abs()</span>
    <span class="pill pill-blue mono">sorted()</span>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">nums</span> = [<span style="color:#b45309;">5</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">9</span>, <span style="color:#b45309;">1</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">nums</span>))    <span style="color:#6b7280;"># 4</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">max</span>(<span style="color:#0e6ead;">nums</span>))    <span style="color:#6b7280;"># 9</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">nums</span>))    <span style="color:#6b7280;"># 17</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-orange" style="text-align:center;">
    <div class="slide-h2" style="color:var(--orange);">User-defined Functions</div>
    <div class="small-text" style="margin-top:4px;">Written by you using the <span class="mono">def</span> keyword.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">average</span>(<span style="color:#0e6ead;">items</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">items</span>) / <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">items</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">average</span>([<span style="color:#b45309;">10</span>,<span style="color:#b45309;">20</span>,<span style="color:#b45309;">30</span>]))<br>
    <span style="color:#6b7280;"># 20.0</span>
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div>You can combine both — your function can call built-in functions inside.</div>
  </div>

  <table v-click class="cmp-table" style="font-size:.7rem;">
    <thead>
      <tr><th>Type</th><th>Source</th><th>Examples</th></tr>
    </thead>
    <tbody>
      <tr><td>Built-in</td><td>Python core</td><td><span class="mono">print, len, sum</span></td></tr>
      <tr><td>User-defined</td><td>You write</td><td><span class="mono">average, greet</span></td></tr>
    </tbody>
  </table>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — PRACTICAL EXAMPLE: CALCULATOR & AREA
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Examples — Calculator &amp; Area">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical <span class="highlight">Examples</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 1: Mini Calculator</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">add</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>): <span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">a</span> + <span style="color:#0e6ead;">b</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sub</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>): <span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">a</span> - <span style="color:#0e6ead;">b</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">mul</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>): <span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">a</span> * <span style="color:#0e6ead;">b</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">div</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>): <span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">a</span> / <span style="color:#0e6ead;">b</span><br>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">add</span>(<span style="color:#b45309;">8</span>, <span style="color:#b45309;">2</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sub</span>(<span style="color:#b45309;">8</span>, <span style="color:#b45309;">2</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">mul</span>(<span style="color:#b45309;">8</span>, <span style="color:#b45309;">2</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">div</span>(<span style="color:#b45309;">8</span>, <span style="color:#b45309;">2</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    10<br>6<br>16<br>4.0
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 2: Area of Shapes</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">rect_area</span>(<span style="color:#0e6ead;">l</span>, <span style="color:#0e6ead;">w</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">l</span> * <span style="color:#0e6ead;">w</span></span>
    <br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">circle_area</span>(<span style="color:#0e6ead;">r</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">3.14</span> * <span style="color:#0e6ead;">r</span> * <span style="color:#0e6ead;">r</span></span>
    <br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">tri_area</span>(<span style="color:#0e6ead;">b</span>, <span style="color:#0e6ead;">h</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0.5</span> * <span style="color:#0e6ead;">b</span> * <span style="color:#0e6ead;">h</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">rect_area</span>(<span style="color:#b45309;">5</span>, <span style="color:#b45309;">3</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">circle_area</span>(<span style="color:#b45309;">4</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">tri_area</span>(<span style="color:#b45309;">6</span>, <span style="color:#b45309;">4</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    15<br>50.24<br>12.0
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — PRACTICAL EXAMPLE: FIBONACCI & MULTI-RETURN
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Examples — Fibonacci &amp; Multi-Return">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">More <span class="highlight">Examples</span> — Fibonacci &amp; Multi-Return</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 3: Fibonacci Series (Recursive)</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt;= <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) + <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">2</span>)</span>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">7</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">i</span>), <span style="color:#0e6ead;">end</span>=<span style="color:#2d7a00;">" "</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">0 1 1 2 3 5 8</div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Series Visualization</div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;">
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">0</div>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">1</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">1</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">2</div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">3</div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">5</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">8</div>
    </div>
    <div class="small-text" style="margin-top:4px;">Each term is the sum of the previous two.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 4: Min &amp; Max in One Call</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">min_max</span>(<span style="color:#0e6ead;">nums</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">min</span>(<span style="color:#0e6ead;">nums</span>), <span style="color:#2d7a00;">max</span>(<span style="color:#0e6ead;">nums</span>)</span>
    <br>
    <span style="color:#0e6ead;">data</span> = [<span style="color:#b45309;">4</span>, <span style="color:#b45309;">8</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">9</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">high</span> = <span style="color:#0e6ead;">min_max</span>(<span style="color:#0e6ead;">data</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Min:"</span>, <span style="color:#0e6ead;">low</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Max:"</span>, <span style="color:#0e6ead;">high</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    Min: 1<br>
    Max: 9
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;font-size:.7rem;">
    <div>Returning multiple values is a clean way to <strong>group related results</strong> from one function.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — ACTIVITY / MINI CHALLENGES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Activity — Function Challenges">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Function <span class="highlight">Challenges</span> — Try It!</div>

<div class="activity-box">
  <div class="act-title">Practice Exercises</div>

  <div class="g2" style="gap:10px;">

  <div class="flex-col" style="gap:8px;">
    <div class="act-task" v-click>
      <strong>Challenge 1 — Basic Function</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write a function <span style="color:#b45309;">greet(name)</span> that prints "Welcome, &lt;name&gt;!".
      </div>
      <div class="hint">Hint: use <span style="color:#b45309;">def</span> and <span style="color:#b45309;">print()</span></div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 2 — Return Value</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write a function <span style="color:#b45309;">cube(n)</span> that returns the cube of a number.
      </div>
      <div class="hint">Hint: return n * n * n</div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 3 — Default Argument</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Make a function <span style="color:#b45309;">power(base, exp=2)</span> that defaults to squaring.
      </div>
      <div class="hint">Hint: use base ** exp</div>
    </div>
  </div>

  <div class="flex-col" style="gap:8px;">
    <div class="act-task" v-click>
      <strong>Challenge 4 — Recursion</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write a recursive function <span style="color:#b45309;">sum_n(n)</span> to add numbers from 1 to n.
      </div>
      <div class="hint">Hint: base case n == 0 returns 0</div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 5 — Lambda</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Use a lambda inside map() to triple every item of [1, 2, 3, 4].
      </div>
      <div class="hint">Hint: lambda x: x * 3</div>
    </div>
    <div class="act-task" v-click>
      <strong>Bonus — *args</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write a function <span style="color:#b45309;">average(*nums)</span> that finds the average of any number of inputs.
      </div>
      <div class="hint">Hint: sum(nums) / len(nums)</div>
    </div>
  </div>
  </div>
</div>

  </template>
</Slide2>

---
transition: fade
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — SUMMARY + QUICK REFERENCE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Functions — Summary">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What You've <span class="highlight">Learned</span> Today</div>

<div class="g2" style="gap:12px;">

<div class="flex-col" style="gap:8px;">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
    <div class="icon-circle ic-red">F</div>
    <div>
      <div class="slide-h3">Define &amp; Call</div>
      <div class="small-text">Use <span class="mono">def</span> to create a function and call it by its name with parentheses.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">A</div>
    <div>
      <div class="slide-h3">Arguments &amp; Parameters</div>
      <div class="small-text">Positional, keyword, default, and <span class="mono">*args</span> — four flexible ways to pass values.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">R</div>
    <div>
      <div class="slide-h3">return Statement</div>
      <div class="small-text">Send one or more values back to the caller. Without it, function returns <span class="mono">None</span>.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">S</div>
    <div>
      <div class="slide-h3">Scope &amp; Recursion</div>
      <div class="small-text">Local stays inside, global is shared. Recursion calls itself — always with a base case.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--purple);">
    <div class="icon-circle ic-purple">L</div>
    <div>
      <div class="slide-h3">Lambda &amp; Built-ins</div>
      <div class="small-text">Lambdas for short tasks. Built-ins like <span class="mono">len, sum, map, filter</span> are always ready.</div>
    </div>
  </div>

</div>

<div class="flex-col" style="gap:10px;">

  <div v-click class="card-navy" style="border-radius:10px;padding:14px 18px;">
    <div style="font-size:.7rem;text-transform:uppercase;letter-spacing:1px;color:var(--muted);margin-bottom:8px;">Quick Reference Cheat Sheet</div>
    <div style="font-family:'Fira Code',monospace;font-size:.68rem;line-height:1.9;color:var(--navy);">
      <div v-after><span style="color:#ef5050;">def</span> name(params): <span style="color:#6b7280;"># define</span></div>
      <div v-after>name(args) <span style="color:#6b7280;"># call</span></div>
      <div v-after><span style="color:#ef5050;">return</span> value <span style="color:#6b7280;"># send back</span></div>
      <div v-after>name(a=1, b=2) <span style="color:#6b7280;"># keyword</span></div>
      <div v-after><span style="color:#ef5050;">def</span> f(x=10): <span style="color:#6b7280;"># default</span></div>
      <div v-after><span style="color:#ef5050;">def</span> f(*args): <span style="color:#6b7280;"># variable-length</span></div>
      <div v-after><span style="color:#ef5050;">lambda</span> x: x*x <span style="color:#6b7280;"># anonymous</span></div>
      <div v-after><span style="color:#ef5050;">global</span> name <span style="color:#6b7280;"># modify global</span></div>
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div><strong>Remember:</strong> Functions are the building blocks of every Python program. Master them and your code becomes cleaner, shorter, and easier to maintain.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="small-text"><strong>Next Step:</strong> Combine functions with loops, lists, and dictionaries to build full mini-projects like calculators, quiz apps, and number games.</div>
  </div>

</div>
</div>
  </template>
</Slide2>
