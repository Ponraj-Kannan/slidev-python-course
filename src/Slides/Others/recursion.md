---
theme: default
title: Python Recursion
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
   GLOBAL DESIGN SYSTEM — Python Recursion
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

/* ── Recursion tree node ─────────────────────────────────── */
.rec-tree {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
}
.rec-node {
  padding: 5px 14px;
  border-radius: 20px;
  font-family: 'Fira Code', monospace;
  font-size: 0.68rem;
  font-weight: 700;
  border: 2px solid transparent;
  white-space: nowrap;
}
.rec-node-call   { background: #ebf8ff; border-color: var(--blue);   color: #2b6cb0; }
.rec-node-base   { background: #f0fff4; border-color: var(--green);  color: #276749; }
.rec-node-return { background: #faf5ff; border-color: var(--purple); color: #553c9a; }
.rec-connector   { color: var(--muted); font-size: 0.9rem; font-weight: 900; }
</style>



<!-- ═══════════════════════════════════════════════════════
     SLIDE 2 — INTRODUCTION TO RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Introduction to Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is <span class="highlight">Recursion ?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Recursion</strong> is a technique where a function <strong style="color:var(--green);">calls itself</strong> to solve a smaller version of the same problem — until it reaches a <strong style="color:var(--blue);">stopping condition</strong>.
    </div>
  </div>
  <div v-click class="callout callout-success">
    <div><strong>Key idea:</strong> Recursion breaks a big problem into a <strong>smaller version of itself</strong>, solves the smallest case, then builds back up.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">The Two Essential Parts</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="card-green" style="text-align:center;">
      <div class="slide-h3" style="color:var(--green);">Base Case</div>
      <div class="small-text" style="margin-top:4px;">The condition where recursion <strong>stops</strong>. Without it — infinite loop!</div>
    </div>
    <div class="card-blue" style="text-align:center;">
      <div class="slide-h3" style="color:var(--blue);">Recursive Case</div>
      <div class="small-text" style="margin-top:4px;">The step where the function <strong>calls itself</strong> with a smaller input.</div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Simplest Recursive Function</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Countdown using recursion</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">countdown</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;">
      <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># base case</span>
    </span>
    <span style="padding-left:40px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Go!"</span>)</span>
    <span style="padding-left:20px;display:block;">
      <span style="color:#ef5050;">else</span>: <span style="color:#6b7280;"># recursive case</span>
    </span>
    <span style="padding-left:40px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>)</span>
    <span style="padding-left:40px;display:block;"><span style="color:#0e6ead;">countdown</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#0e6ead;">countdown</span>(<span style="color:#b45309;">3</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    3<br>2<br>1<br>Go!
  </div>

</div>
</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 3 — WHAT IS A RECURSIVE FUNCTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="What is a Recursive Function">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">What is a <span class="highlight">Recursive Function ?</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label" style="margin-top:6px;">Syntax Structure</div>

  <div v-after class="code-block" style="font-size:.78rem;line-height:2;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">function_name</span>(<span style="color:#c49a00;">parameters</span>)<span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Base Case — stopping condition</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">base_condition</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">base_value</span></span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Recursive Case — calls itself</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">function_name</span>(<span style="color:#0e6ead;">smaller_input</span>)</span>
  </div>

  <div v-click style="margin-top:4px; border:1px solid #e1e4e8; padding:10px; border-radius:10px;">
    <div class="section-label" style="margin-bottom:6px;">Syntax Parts</div>
    <div style="display:flex;flex-direction:column;gap:5px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-keyword">def</span>
        <span class="body-text">Starts the function definition</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-varname">base_condition</span>
        <span class="body-text">When to stop calling itself</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-operator">return base_value</span>
        <span class="body-text">Return a direct answer at the base</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-value">function_name(smaller_input)</span>
        <span class="body-text">The recursive call with reduced input</span>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example — Sum of n Numbers</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># sum_n(3) = 3 + 2 + 1 = 6</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># recursive call</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sum_n</span>(<span style="color:#b45309;">3</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">6</div>

  <div v-click class="section-label" style="margin-top:6px;">How It Unfolds</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:3px;padding:6px 0;">
    <div class="flow-node flow-call" style="width:220px;">sum_n(3) = 3 + sum_n(2)</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:220px;">sum_n(2) = 2 + sum_n(1)</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:220px;">sum_n(1) = 1 + sum_n(0)</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-end" style="width:220px;">sum_n(0) = 0 (base case)</div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:4px;font-size:.7rem;">
    <div>Each call <strong>waits</strong> for the next one to complete before returning its own result.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — HOW RECURSION WORKS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="How Recursion Works — Execution Model">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">How <span class="highlight">Recursion Works</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Two Phases of Recursion</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="card-blue" style="text-align:center;">
      <div class="slide-h3" style="color:var(--blue);">Winding Phase</div>
      <div class="small-text" style="margin-top:4px;">Function keeps calling itself — frames pile up on the stack.</div>
    </div>
    <div class="card-purple" style="text-align:center;">
      <div class="slide-h3" style="color:var(--purple);">Unwinding Phase</div>
      <div class="small-text" style="margin-top:4px;">Base case hit — frames return values and pop off one by one.</div>
    </div>
  </div>

  <div v-click class="code-block" style="margin-top:6px;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">4</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">24</div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Think of recursion in two directions:</strong> DOWN (calling) and UP (returning). Results travel back up the chain.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Step-by-Step — factorial(4)</div>

  <div style="display:flex;flex-direction:column;gap:3px;padding:6px 0;">
    <div v-click style="display:flex;align-items:center;gap:6px;">
      <div class="flow-node flow-call" style="flex:1;">factorial(4)</div>
      <div class="small-text">&#x2192; 4 * factorial(3)</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:14px;">
      <div class="flow-node flow-call" style="flex:1;">factorial(3)</div>
      <div class="small-text">&#x2192; 3 * factorial(2)</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:28px;">
      <div class="flow-node flow-call" style="flex:1;">factorial(2)</div>
      <div class="small-text">&#x2192; 2 * factorial(1)</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:42px;">
      <div class="flow-node flow-end" style="flex:1;">factorial(1) = 1</div>
      <div class="small-text">Base case!</div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Unwinding — returning values</div>

  <div style="display:flex;flex-direction:column;gap:3px;padding:4px 0;">
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:28px;">
      <div class="flow-node flow-return" style="flex:1;">factorial(2) = 2 * 1 = 2</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:14px;">
      <div class="flow-node flow-return" style="flex:1;">factorial(3) = 3 * 2 = 6</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;">
      <div class="flow-node flow-body" style="flex:1;">factorial(4) = 4 * 6 = <strong>24</strong></div>
    </div>
  </div>

  <div v-click class="card card-green" style="margin-top:4px;">
    <div class="small-text"><strong>Pattern:</strong> <span class="pill pill-blue">Down</span> divides the problem. <span class="pill pill-purple">Up</span> combines the answers.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — BASE CASE AND RECURSIVE CASE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Base Case and Recursive Case">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Base Case</span> &amp; <span class="highlight">Recursive Case</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">Base Case</div>
    <div class="small-text" style="margin-top:4px;">The <strong>termination condition</strong>. Returns a value directly — no more recursive calls.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># Base case example</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>):<br>
    <span style="padding-left:20px;display:block;background:#f0fff4;border-left:3px solid var(--green);"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">exp</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># BASE CASE</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">base</span> * <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>-<span style="color:#b45309;">1</span>)</span>
  </div>

  <div v-click class="callout callout-danger">
    <div><strong>Missing base case = RecursionError!</strong> Python raises <span class="mono">RecursionError: maximum recursion depth exceeded</span> after ~1000 calls.</div>
  </div>

  <div v-click class="card-green" style="font-size:.75rem;">
    <strong>Good base cases check for:</strong>
    <div style="margin-top:6px;display:flex;flex-direction:column;gap:3px;">
      <div><span class="pill pill-green">n == 0</span> for counting down</div>
      <div><span class="pill pill-green">n == 1</span> for multiplication-based</div>
      <div><span class="pill pill-green">len(s) == 0</span> for strings/lists</div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Recursive Case</div>
    <div class="small-text" style="margin-top:4px;">The step that makes the problem <strong>smaller</strong> and calls the function again.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">exp</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;background:#ebf8ff;border-left:3px solid var(--blue);"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">base</span> * <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>-<span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># RECURSIVE</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">power</span>(<span style="color:#b45309;">2</span>, <span style="color:#b45309;">4</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">16</div>

  <div v-click class="section-label" style="margin-top:4px;">Base vs Recursive Comparison</div>
  <div v-after>
    <table class="cmp-table">
      <thead><tr><th>Aspect</th><th>Base Case</th><th>Recursive Case</th></tr></thead>
      <tbody>
        <tr><td>Purpose</td><td>Stop recursion</td><td>Shrink the problem</td></tr>
        <tr><td>Returns</td><td class="yes">Direct value</td><td>Function call</td></tr>
        <tr><td>Required?</td><td class="yes">Always</td><td class="yes">Always</td></tr>
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
     SLIDE 6 — FUNCTION CALL STACK
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Function Call Stack in Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Function <span class="highlight">Call Stack</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.7;color:var(--slate);">
      The <strong style="color:var(--red);">call stack</strong> is a memory structure that tracks all active function calls. Each call gets a <strong style="color:var(--blue);">stack frame</strong> storing its local variables and return address.
    </div>
  </div>

  <div v-click class="code-block" style="margin-top:4px;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>: <span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">3</span>)
  </div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Stack overflow risk!</strong> Deep recursion fills up the stack. Python's default limit is around <strong>1000</strong> frames. Use <span class="mono">sys.setrecursionlimit()</span> carefully.</div>
  </div>

  <div v-click class="card-orange" style="font-size:.75rem;">
    <strong>Each stack frame stores:</strong>
    <div style="display:flex;gap:6px;flex-wrap:wrap;margin-top:6px;">
      <span class="pill pill-orange">local variables</span>
      <span class="pill pill-blue">parameter values</span>
      <span class="pill pill-purple">return address</span>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Stack Growth — factorial(3)</div>

  <div v-after style="background:#f7f8fc;border:1px solid var(--border);border-radius:10px;padding:12px 16px;">
    <div class="small-text" style="text-align:center;margin-bottom:8px;font-weight:700;">CALL STACK (grows downward)</div>
    <div v-click class="stack-frame top">factorial(3) &nbsp; n=3 &nbsp; waiting...</div>
    <div v-click class="stack-frame middle">factorial(2) &nbsp; n=2 &nbsp; waiting...</div>
    <div v-click class="stack-frame" style="border-color:var(--blue);background:#ebf8ff;color:#2b6cb0;">factorial(1) &nbsp; n=1 &nbsp; returns 1</div>
    <div class="small-text" style="text-align:center;margin-top:8px;">&#x25B2; Stack unwinds from here</div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Stack Unwinding</div>

  <div v-after style="background:#f7f8fc;border:1px solid var(--border);border-radius:10px;padding:12px 16px;">
    <div class="stack-frame done">factorial(1) = 1 &nbsp; popped</div>
    <div class="stack-frame done">factorial(2) = 2*1 = 2 &nbsp; popped</div>
    <div class="stack-frame done">factorial(3) = 3*2 = 6 &nbsp; popped</div>
    <div class="small-text" style="text-align:center;margin-top:8px;color:var(--green);font-weight:700;">Final result: 6</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — RECURSIVE FLOW EXECUTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursive Flow — Step-by-Step Execution">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Recursive <span class="highlight">Flow Execution</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example — Reverse a String</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">reverse</span>(<span style="color:#0e6ead;">s</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">s</span>) == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">""</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">reverse</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>:]) + <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>]</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">reverse</span>(<span style="color:#2d7a00;">"ABC"</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">CBA</div>

  <div v-click class="section-label" style="margin-top:6px;">Execution Trace Table</div>

  <div v-after>
    <table class="trace-table">
      <thead><tr><th>Call</th><th>Input s</th><th>Action</th><th>Returns</th></tr></thead>
      <tbody>
        <tr><td>1st</td><td>"ABC"</td><td>reverse("BC") + "A"</td><td>waits</td></tr>
        <tr><td>2nd</td><td>"BC"</td><td>reverse("C") + "B"</td><td>waits</td></tr>
        <tr><td>3rd</td><td>"C"</td><td>reverse("") + "C"</td><td>waits</td></tr>
        <tr class="hl"><td>4th</td><td>""</td><td>base case</td><td class="hl">""</td></tr>
        <tr><td>3rd</td><td>unwind</td><td>"" + "C"</td><td>"C"</td></tr>
        <tr><td>2nd</td><td>unwind</td><td>"C" + "B"</td><td>"CB"</td></tr>
        <tr><td>1st</td><td>unwind</td><td>"CB" + "A"</td><td class="hl">"CBA"</td></tr>
      </tbody>
    </table>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Complete Execution Flow Diagram</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:3px;padding:4px 0;">
    <div class="flow-node flow-start" style="width:240px;">reverse("ABC")</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:240px;">reverse("BC") + "A"</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:240px;">reverse("C") + "B"</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:240px;">reverse("") + "C"</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-end" style="width:240px;">returns "" (base case)</div>
    <div class="flow-arrow">&#x25B2;</div>
    <div class="flow-node flow-return" style="width:240px;">returns "C"</div>
    <div class="flow-arrow">&#x25B2;</div>
    <div class="flow-node flow-return" style="width:240px;">returns "CB"</div>
    <div class="flow-arrow">&#x25B2;</div>
    <div class="flow-node flow-body" style="width:240px;">returns "CBA"</div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;font-size:.7rem;">
    <div>The recursive calls go <strong>down</strong> until base case, then results are <strong>assembled on the way back up</strong>.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — ADVANTAGES OF RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Advantages of Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">Advantages</span> of Recursion</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">C</div>
    <div>
      <div class="slide-h3">Clean &amp; Elegant Code</div>
      <div class="small-text">Complex problems become short, readable, and mathematically clean.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">S</div>
    <div>
      <div class="slide-h3">Solves Naturally Recursive Problems</div>
      <div class="small-text">Trees, graphs, and divide-and-conquer algorithms are naturally recursive.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--purple);">
    <div class="icon-circle ic-purple">D</div>
    <div>
      <div class="slide-h3">Divide and Conquer</div>
      <div class="small-text">Break a big problem into identical smaller sub-problems effortlessly.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">R</div>
    <div>
      <div class="slide-h3">Reduces Code Length</div>
      <div class="small-text">Tower of Hanoi needs 4 lines recursively — dozens iteratively.</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Recursion vs Loop — Code Length</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="flex-col">
      <div class="section-label" style="color:var(--red);">Factorial — Loop</div>
      <div class="code-block" style="font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fact_loop</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#0e6ead;">result</span> = <span style="color:#b45309;">1</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">n</span>+<span style="color:#b45309;">1</span>):</span>
        <span style="padding-left:32px;display:block;"><span style="color:#0e6ead;">result</span> *= <span style="color:#0e6ead;">i</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">result</span></span>
      </div>
    </div>
    <div class="flex-col">
      <div class="section-label" style="color:var(--green);">Factorial — Recursion</div>
      <div class="code-block" style="font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fact_rec</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
        <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">fact_rec</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;font-size:.7rem;">
    <div>Recursion perfectly mirrors the <strong>mathematical definition</strong>: n! = n * (n-1)!</div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Best-Use Cases for Recursion</div>
  <div v-after style="display:flex;flex-wrap:wrap;gap:6px;margin-top:4px;">
    <span class="pill pill-blue">Tree traversal</span>
    <span class="pill pill-green">Sorting algorithms</span>
    <span class="pill pill-purple">Fibonacci</span>
    <span class="pill pill-orange">Tower of Hanoi</span>
    <span class="pill pill-red">Binary search</span>
    <span class="pill pill-navy">Maze solving</span>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — DISADVANTAGES OF RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Disadvantages of Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">Disadvantages</span> of Recursion</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
    <div class="icon-circle ic-red">M</div>
    <div>
      <div class="slide-h3">High Memory Usage</div>
      <div class="small-text">Each recursive call uses a stack frame. Deep recursion can consume a lot of memory.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">S</div>
    <div>
      <div class="slide-h3">Stack Overflow Risk</div>
      <div class="small-text">Python has a recursion depth limit (~1000). Exceeding it causes <span class="mono" style="font-size:.65rem;">RecursionError</span>.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--yellow);">
    <div class="icon-circle" style="background:#fefcbf;color:#b7791f;">T</div>
    <div>
      <div class="slide-h3">Repeated Calculations</div>
      <div class="small-text">Without memoization, Fibonacci recomputes the same values many times.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--purple);">
    <div class="icon-circle ic-purple">D</div>
    <div>
      <div class="slide-h3">Harder to Debug</div>
      <div class="small-text">Tracing multiple nested calls is trickier than a simple loop.</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common Error — Infinite Recursion</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># WRONG — missing base case!</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad_count</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">bad_count</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># never stops!</span></span>
    <br>
    <span style="color:#0e6ead;">bad_count</span>(<span style="color:#b45309;">5</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;border-color:#f5c6cb;color:#721c24;background:#fff5f5;">
    5, 4, 3, 2, 1, 0, -1, -2 ... <br>
    RecursionError: maximum recursion depth exceeded
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Recursion Depth Demo</div>

  <div v-after class="code-block" style="font-size:.68rem;">
    <span style="color:#ef5050;">import</span> <span style="color:#0e6ead;">sys</span><br>
    <span style="color:#6b7280;"># Check current limit</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sys</span>.<span style="color:#0e6ead;">getrecursionlimit</span>())
    <span style="color:#6b7280;">  # 1000</span><br>
    <span style="color:#6b7280;"># Change limit (use with care!)</span><br>
    <span style="color:#0e6ead;">sys</span>.<span style="color:#0e6ead;">setrecursionlimit</span>(<span style="color:#b45309;">2000</span>)
  </div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Rule of thumb:</strong> If a loop can solve the problem easily — prefer the loop. Use recursion when it simplifies the logic significantly.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — RECURSION VS ITERATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursion vs Iteration">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Recursion</span> vs <span class="highlight">Iteration</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Side-by-Side — Sum of N Numbers</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="flex-col">
      <div class="section-label" style="color:var(--blue);">Iteration</div>
      <div class="code-block" style="font-size:.68rem;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_iter</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#0e6ead;">total</span> = <span style="color:#b45309;">0</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>,<span style="color:#0e6ead;">n</span>+<span style="color:#b45309;">1</span>):</span>
        <span style="padding-left:32px;display:block;"><span style="color:#0e6ead;">total</span> += <span style="color:#0e6ead;">i</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">total</span></span>
      </div>
    </div>
    <div class="flex-col">
      <div class="section-label" style="color:var(--red);">Recursion</div>
      <div class="code-block" style="font-size:.68rem;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_rec</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
        <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">sum_rec</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
      </div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Both produce the same result</div>
  <div v-after class="output-box" style="font-size:.72rem;">
    sum_iter(5) = 15<br>
    sum_rec(5) = 15
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Detailed Comparison Table</div>
  <div v-after>
    <table class="cmp-table">
      <thead><tr><th>Feature</th><th>Recursion</th><th>Iteration</th></tr></thead>
      <tbody>
        <tr>
          <td>Code length</td>
          <td class="yes">Usually shorter</td>
          <td>Longer</td>
        </tr>
        <tr>
          <td>Readability</td>
          <td class="yes">High (for math)</td>
          <td>Moderate</td>
        </tr>
        <tr>
          <td>Memory usage</td>
          <td class="no">More (call stack)</td>
          <td class="yes">Less</td>
        </tr>
        <tr>
          <td>Speed</td>
          <td class="no">Slower</td>
          <td class="yes">Faster</td>
        </tr>
        <tr>
          <td>Stack overflow risk</td>
          <td class="no">Yes</td>
          <td class="yes">No</td>
        </tr>
        <tr>
          <td>Base case needed</td>
          <td class="no">Yes</td>
          <td class="yes">No</td>
        </tr>
        <tr>
          <td>Best for</td>
          <td>Trees, DFS, Math</td>
          <td>Simple loops</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;font-size:.7rem;">
    <div><strong>When to choose recursion:</strong> When the problem is naturally tree-shaped or divide-and-conquer in nature.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 11 — DIRECT RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Direct Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Direct</span> Recursion</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.7;color:var(--slate);">
      <strong style="color:var(--red);">Direct recursion</strong> occurs when a function <strong style="color:var(--green);">calls itself directly</strong> within its own body. This is the most common and simplest form of recursion.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Flow Diagram — Direct</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:8px 0;">
    <div class="flow-node flow-start" style="width:200px;">func_A called</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-body" style="width:200px;">executes body...</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:200px;">calls func_A again</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-cond" style="width:200px;">base case reached?</div>
    <div style="display:flex;gap:20px;margin-top:4px;">
      <div style="display:flex;flex-direction:column;align-items:center;gap:2px;">
        <div class="small-text">YES</div>
        <div class="flow-node flow-end" style="width:100px;">return</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;gap:2px;">
        <div class="small-text">NO</div>
        <div class="flow-node flow-call" style="width:100px;">recurse</div>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 1 — Countdown</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">countdown</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt; <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">countdown</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># calls itself!</span></span>
    <br>
    <span style="color:#0e6ead;">countdown</span>(<span style="color:#b45309;">3</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">3 &nbsp; 2 &nbsp; 1 &nbsp; 0</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Sum of Digits</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">digit_sum</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> % <span style="color:#b45309;">10</span> + <span style="color:#0e6ead;">digit_sum</span>(<span style="color:#0e6ead;">n</span> // <span style="color:#b45309;">10</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">digit_sum</span>(<span style="color:#b45309;">123</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">6 &nbsp;<span class="comment"># 1 + 2 + 3 = 6</span></div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div><strong>Direct recursion</strong> is clean and easy to trace — the function only depends on itself.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — INDIRECT RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Indirect Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Indirect</span> Recursion</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.7;color:var(--slate);">
      <strong style="color:var(--red);">Indirect recursion</strong> occurs when <strong style="color:var(--blue);">Function A calls Function B</strong>, and <strong style="color:var(--green);">Function B calls Function A</strong> — forming a cycle.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Indirect Recursion Flow</div>

  <div v-after style="display:flex;justify-content:center;align-items:center;gap:20px;padding:14px;background:#f7f8fc;border:1px solid var(--border);border-radius:10px;">
    <div style="display:flex;flex-direction:column;align-items:center;gap:4px;">
      <div class="flow-node flow-call" style="width:110px;">func_A(n)</div>
      <div class="small-text" style="font-size:.6rem;text-align:center;">calls func_B</div>
    </div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:4px;">
      <div style="color:var(--blue);font-size:1.3rem;font-weight:900;">&#x21C4;</div>
      <div class="small-text" style="font-size:.6rem;">mutual calls</div>
    </div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:4px;">
      <div class="flow-node flow-return" style="width:110px;">func_B(n)</div>
      <div class="small-text" style="font-size:.6rem;text-align:center;">calls func_A</div>
    </div>
  </div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Important:</strong> Both functions must have proper base cases — otherwise infinite mutual calling occurs.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example — is_even / is_odd</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Indirect recursion example</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">is_even</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#ef5050;">True</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">is_odd</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># calls is_odd!</span></span>
    <br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">is_odd</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#ef5050;">False</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">is_even</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># calls is_even!</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">is_even</span>(<span style="color:#b45309;">4</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">is_odd</span>(<span style="color:#b45309;">3</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    True<br>
    True
  </div>

  <div v-click class="section-label" style="margin-top:6px;">How is_even(4) Runs</div>
  <div v-after style="display:flex;flex-wrap:wrap;gap:4px;align-items:center;font-size:.68rem;font-family:'Fira Code',monospace;">
    <span class="pill pill-blue">is_even(4)</span>
    <span>&#x2192;</span>
    <span class="pill pill-purple">is_odd(3)</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">is_even(2)</span>
    <span>&#x2192;</span>
    <span class="pill pill-purple">is_odd(1)</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">is_even(0)</span>
    <span>&#x2192;</span>
    <span class="pill pill-green">True</span>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — TAIL RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Tail Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Tail</span> Recursion</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.7;color:var(--slate);">
      A function is <strong style="color:var(--red);">tail recursive</strong> when the <strong style="color:var(--green);">recursive call is the last operation</strong> in the function — no pending computation after it returns.
    </div>
  </div>

  <div v-click class="g2" style="gap:8px;margin-top:4px;">
    <div class="card-red">
      <div class="slide-h3">NOT Tail Recursive</div>
      <div class="small-text" style="margin-top:4px;">There is a pending multiply after the call returns.</div>
    </div>
    <div class="card-green">
      <div class="slide-h3">Tail Recursive</div>
      <div class="small-text" style="margin-top:4px;">The recursive call IS the last thing done — nothing pending.</div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">NOT Tail Recursive (standard factorial)</div>

  <div v-after class="code-block" style="font-size:.7rem;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>: <span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <span style="color:#6b7280;">#       ^ must multiply after call returns</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Tail Recursive Version</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Tail recursive — accumulator carries result</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>, <span style="color:#0e6ead;">acc</span>=<span style="color:#b45309;">1</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">acc</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">n</span>*<span style="color:#0e6ead;">acc</span>) <span style="color:#6b7280;"># LAST op</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">5</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">120</div>

  <div v-click class="section-label" style="margin-top:6px;">Comparison</div>
  <div v-after>
    <table class="cmp-table">
      <thead><tr><th>Aspect</th><th>Normal Recursion</th><th>Tail Recursion</th></tr></thead>
      <tbody>
        <tr><td>Pending operation</td><td class="no">Yes (e.g. n*...)</td><td class="yes">None</td></tr>
        <tr><td>Stack frames</td><td class="no">All kept alive</td><td class="yes">Can be reused</td></tr>
        <tr><td>Memory</td><td class="no">O(n)</td><td class="yes">O(1) if optimized</td></tr>
        <tr><td>Accumulator needed</td><td>No</td><td>Yes</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><strong>Note:</strong> Python does not optimize tail recursion automatically, but the pattern is still a good practice for clarity.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — RECURSIVE PROBLEM SOLVING
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursive Problem Solving Strategy">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Recursive <span class="highlight">Problem Solving</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">3-Step Strategy</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
      <div class="icon-circle ic-red" style="font-size:.9rem;">1</div>
      <div>
        <div class="slide-h3">Identify the Base Case</div>
        <div class="small-text">When is the answer trivially known? (n==0, empty list, single char)</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
      <div class="icon-circle ic-blue" style="font-size:.9rem;">2</div>
      <div>
        <div class="slide-h3">Define the Recursive Case</div>
        <div class="small-text">How does the current problem relate to a smaller version of itself?</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
      <div class="icon-circle ic-green" style="font-size:.9rem;">3</div>
      <div>
        <div class="slide-h3">Trust the Recursion</div>
        <div class="small-text">Assume the recursive call works correctly and build your solution around it.</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><strong>Tip:</strong> Write the base case first, then the recursive case. Never start coding from the recursive case.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Apply the Strategy — Fibonacci</div>

  <div v-after class="card-navy" style="border-radius:10px;font-size:.75rem;line-height:1.7;">
    <strong>Step 1 — Base:</strong> fib(0) = 0, fib(1) = 1<br>
    <strong>Step 2 — Recursive:</strong> fib(n) = fib(n-1) + fib(n-2)<br>
    <strong>Step 3 — Trust:</strong> Call fib(n-1) and fib(n-2) and add them.
  </div>

  <div v-click class="code-block" style="margin-top:6px;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt;= <span style="color:#b45309;">1</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) + <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">2</span>)</span>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">7</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">i</span>), <span style="color:#0e6ead;">end</span>=<span style="color:#2d7a00;">" "</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">0  1  1  2  3  5  8</div>

  <div v-click class="section-label" style="margin-top:6px;">Fibonacci Recursion Tree</div>
  <div v-after style="text-align:center;font-family:'Fira Code',monospace;font-size:.64rem;line-height:2;background:#f7f8fc;border:1px solid var(--border);border-radius:8px;padding:6px;">
    <div><span style="color:#2b6cb0;font-weight:700;">fib(4)</span></div>
    <div><span style="color:#2b6cb0;">fib(3)</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; + &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:#2b6cb0;">fib(2)</span></div>
    <div><span style="color:#dd6b20;">fib(2)</span> + <span style="color:#dd6b20;">fib(1)</span> &nbsp;&nbsp; <span style="color:#dd6b20;">fib(1)</span> + <span style="color:#dd6b20;">fib(0)</span></div>
    <div><span style="color:#276749;font-weight:700;">1+1</span> &nbsp;&nbsp;&nbsp; <span style="color:#276749;font-weight:700;">1</span> &nbsp;&nbsp;&nbsp; <span style="color:#276749;font-weight:700;">1</span> &nbsp;&nbsp;&nbsp; <span style="color:#276749;font-weight:700;">0</span></div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — DEBUGGING RECURSIVE FUNCTIONS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Debugging Recursive Functions">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Debugging</span> Recursive Functions</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Common Mistakes</div>

  <div v-after class="flex-col" style="gap:6px;">
    <div class="card" style="border:1px solid var(--red);font-size:.75rem;">
      <strong style="color:var(--red);">Mistake 1 — Missing base case</strong>
      <div class="code-block" style="margin-top:6px;font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># never stops</span></span>
      </div>
    </div>
    <div class="card" style="border:1px solid var(--orange);font-size:.75rem;">
      <strong style="color:var(--orange);">Mistake 2 — Wrong base condition</strong>
      <div class="code-block" style="margin-top:6px;font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">-1</span>: <span style="color:#6b7280;"># skips n=0!</span></span>
        <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
      </div>
    </div>
    <div class="card" style="border:1px solid var(--purple);font-size:.75rem;">
      <strong style="color:var(--purple);">Mistake 3 — Not reducing input</strong>
      <div class="code-block" style="margin-top:6px;font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>: <span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>) <span style="color:#6b7280;"># n not shrinking!</span></span>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Debugging Technique — Add print()</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#6b7280;"># Debug: trace calls</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Called: factorial({<span style="color:#0e6ead;">n</span>})"</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Returning: {<span style="color:#0e6ead;">result</span>} for n={<span style="color:#0e6ead;">n</span>}"</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">result</span></span>
  </div>

  <div v-click class="output-box" style="font-size:.68rem;line-height:1.8;">
    Called: factorial(3)<br>
    Called: factorial(2)<br>
    Called: factorial(1)<br>
    Returning: 1 for n=1<br>
    Returning: 2 for n=2<br>
    Returning: 6 for n=3
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div><strong>Debug Tips:</strong> <span class="pill pill-green">print at entry</span> <span class="pill pill-blue">print at return</span> <span class="pill pill-orange">use indent levels</span></div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — PRACTICAL PROGRAMS — FACTORIAL & FIBONACCI
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Programs — Factorial &amp; Fibonacci">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical <span class="highlight">Recursive Programs</span> — Part 1</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Program 1 — Factorial</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># n! = n × (n-1) × ... × 1</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span> <span style="color:#ef5050;">or</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">5</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">120</div>

  <div v-click class="section-label" style="margin-top:6px;">Execution: factorial(5)</div>
  <div v-after style="display:flex;flex-wrap:wrap;gap:4px;align-items:center;font-size:.65rem;font-family:'Fira Code',monospace;">
    <span class="pill pill-blue">5 × 4!</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">4 × 3!</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">3 × 2!</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">2 × 1!</span>
    <span>&#x2192;</span>
    <span class="pill pill-green">1</span>
    <span>&#x21D0;</span>
    <span class="pill pill-purple">120</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Program 2 — Fibonacci Series</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># fib(n) = fib(n-1) + fib(n-2)</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt;= <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) + <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">2</span>)</span>
    <br>
    <span style="color:#6b7280;"># Print first 8 fibonacci numbers</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">8</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">i</span>), <span style="color:#0e6ead;">end</span>=<span style="color:#2d7a00;">" "</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">0  1  1  2  3  5  8  13</div>

  <div v-click class="section-label" style="margin-top:6px;">Fibonacci — Each Term is Sum of Previous Two</div>
  <div v-after style="display:flex;gap:4px;flex-wrap:wrap;align-items:center;">
    <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">0</div>
    <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">1</div>
    <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">1</div>
    <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">2</div>
    <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">3</div>
    <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">5</div>
    <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">8</div>
    <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">13</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — PRACTICAL PROGRAMS — POWER & REVERSE STRING
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Programs — Power &amp; Reverse String">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical Programs — <span class="highlight">Part 2</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Program 3 — Power Calculation</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># base^exp using recursion</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">exp</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># anything^0 = 1</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">base</span> * <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">power</span>(<span style="color:#b45309;">2</span>, <span style="color:#b45309;">5</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">power</span>(<span style="color:#b45309;">3</span>, <span style="color:#b45309;">3</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    32 &nbsp;<span class="comment"># 2^5 = 2*2*2*2*2</span><br>
    27 &nbsp;<span class="comment"># 3^3 = 3*3*3</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">How power(2,4) works</div>
  <div v-after style="font-size:.68rem;font-family:'Fira Code',monospace;line-height:2;">
    <div><span class="pill pill-blue">power(2,4)</span> = 2 * power(2,3)</div>
    <div style="padding-left:14px;"><span class="pill pill-blue">power(2,3)</span> = 2 * power(2,2)</div>
    <div style="padding-left:28px;"><span class="pill pill-blue">power(2,2)</span> = 2 * power(2,1)</div>
    <div style="padding-left:42px;"><span class="pill pill-blue">power(2,1)</span> = 2 * power(2,0)</div>
    <div style="padding-left:56px;"><span class="pill pill-green">power(2,0)</span> = 1 (base)</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Program 4 — Reverse a String</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">reverse_str</span>(<span style="color:#0e6ead;">s</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">s</span>) == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">""</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">reverse_str</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>:]) + <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>]</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">reverse_str</span>(<span style="color:#2d7a00;">"Python"</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">reverse_str</span>(<span style="color:#2d7a00;">"Hello"</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    nohtyP<br>
    olleH
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Logic Visualization — "ABC"</div>
  <div v-after style="display:flex;flex-direction:column;gap:3px;font-size:.68rem;font-family:'Fira Code',monospace;">
    <div><span class="pill pill-blue">reverse("ABC")</span> = reverse("BC") + "A"</div>
    <div style="padding-left:14px;"><span class="pill pill-blue">reverse("BC")</span> = reverse("C") + "B"</div>
    <div style="padding-left:28px;"><span class="pill pill-blue">reverse("C")</span> = reverse("") + "C"</div>
    <div style="padding-left:42px;"><span class="pill pill-green">reverse("")</span> = "" (base)</div>
    <div style="color:var(--purple);font-weight:700;padding-left:14px;">= "" + "C" + "B" + "A" = "CBA"</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — PRACTICAL PROGRAMS — SUM & BINARY SEARCH
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Programs — Sum &amp; Binary Search">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical Programs — <span class="highlight">Part 3</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Program 5 — Sum of Numbers</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Sum 1 + 2 + ... + n</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sum_n</span>(<span style="color:#b45309;">5</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">15 &nbsp;<span class="comment"># 1+2+3+4+5</span></div>

  <div v-click class="section-label" style="margin-top:8px;">Trace — sum_n(4)</div>
  <div v-after>
    <table class="trace-table">
      <thead><tr><th>Call</th><th>n</th><th>Returns</th></tr></thead>
      <tbody>
        <tr><td>sum_n(4)</td><td>4</td><td>4 + sum_n(3) = 10</td></tr>
        <tr><td>sum_n(3)</td><td>3</td><td>3 + sum_n(2) = 6</td></tr>
        <tr><td>sum_n(2)</td><td>2</td><td>2 + sum_n(1) = 3</td></tr>
        <tr><td>sum_n(1)</td><td>1</td><td>1 + sum_n(0) = 1</td></tr>
        <tr class="hl"><td>sum_n(0)</td><td>0</td><td>0 (base case)</td></tr>
      </tbody>
    </table>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Program 6 — Recursive Binary Search</div>

  <div v-after class="code-block" style="font-size:.68rem;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">arr</span>, <span style="color:#0e6ead;">target</span>, <span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">high</span>):<br>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">low</span> &gt; <span style="color:#0e6ead;">high</span>: <span style="color:#6b7280;"># base: not found</span></span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> -<span style="color:#b45309;">1</span></span>
    <span style="padding-left:16px;display:block;"><span style="color:#0e6ead;">mid</span> = (<span style="color:#0e6ead;">low</span> + <span style="color:#0e6ead;">high</span>) // <span style="color:#b45309;">2</span></span>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">arr</span>[<span style="color:#0e6ead;">mid</span>] == <span style="color:#0e6ead;">target</span>: <span style="color:#6b7280;"># found!</span></span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">mid</span></span>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">elif</span> <span style="color:#0e6ead;">arr</span>[<span style="color:#0e6ead;">mid</span>] &lt; <span style="color:#0e6ead;">target</span>:</span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">arr</span>, <span style="color:#0e6ead;">target</span>, <span style="color:#0e6ead;">mid</span>+<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">high</span>)</span>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">else</span>:</span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">arr</span>, <span style="color:#0e6ead;">target</span>, <span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">mid</span>-<span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#0e6ead;">data</span> = [<span style="color:#b45309;">2</span>, <span style="color:#b45309;">5</span>, <span style="color:#b45309;">8</span>, <span style="color:#b45309;">12</span>, <span style="color:#b45309;">16</span>, <span style="color:#b45309;">23</span>, <span style="color:#b45309;">38</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">data</span>, <span style="color:#b45309;">12</span>, <span style="color:#b45309;">0</span>, <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">data</span>)-<span style="color:#b45309;">1</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">3 &nbsp;<span class="comment"># index 3</span></div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Binary search halves the search space each time — O(log n) efficiency. A perfect use case for recursion.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 19 — ACTIVITY / MINI CHALLENGES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Activity — Recursion Challenges">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Recursion <span class="highlight">Challenges</span> — Try It!</div>

<div class="activity-box">
  <div class="act-title">Practice Exercises</div>

  <div class="g2" style="gap:10px;">

  <div class="flex-col" style="gap:8px;">
    <div class="act-task" v-click>
      <strong>Challenge 1 — Countdown</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write a recursive function <span style="color:#b45309;">countdown(n)</span> that prints from n down to 0.
      </div>
      <div class="hint">Hint: base case is n &lt; 0</div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 2 — Factorial</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write <span style="color:#b45309;">factorial(n)</span> recursively. Test with factorial(6) = 720.
      </div>
      <div class="hint">Hint: base case n == 1 returns 1</div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 3 — Sum of List</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write <span style="color:#b45309;">sum_list(lst)</span> that returns the sum of all items in a list recursively.
      </div>
      <div class="hint">Hint: base case is empty list, return 0</div>
    </div>
  </div>

  <div class="flex-col" style="gap:8px;">
    <div class="act-task" v-click>
      <strong>Challenge 4 — Power</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write <span style="color:#b45309;">power(base, exp)</span> recursively. Test: power(3, 4) = 81.
      </div>
      <div class="hint">Hint: base case exp == 0 returns 1</div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 5 — Palindrome Check</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Write <span style="color:#b45309;">is_palindrome(s)</span> that checks if a string reads the same forwards and backwards.
      </div>
      <div class="hint">Hint: compare s[0] and s[-1], recurse on s[1:-1]</div>
    </div>
    <div class="act-task" v-click>
      <strong>Bonus — GCD</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Implement <span style="color:#b45309;">gcd(a, b)</span> using Euclid's algorithm recursively. gcd(48, 18) = 6.
      </div>
      <div class="hint">Hint: gcd(a, b) = gcd(b, a % b) ; base: b == 0 return a</div>
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
     SLIDE 20 — SUMMARY + QUICK REFERENCE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Recursion — Summary">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What You've <span class="highlight">Learned</span> Today</div>

<div class="g2" style="gap:12px;">

<div class="flex-col" style="gap:8px;">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
    <div class="icon-circle ic-red">R</div>
    <div>
      <div class="slide-h3">Recursion Concept</div>
      <div class="small-text">A function that calls itself with a <strong>base case</strong> to stop and a <strong>recursive case</strong> to shrink.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">S</div>
    <div>
      <div class="slide-h3">Call Stack</div>
      <div class="small-text">Each call gets a stack frame. Frames unwind when the base case is reached.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">T</div>
    <div>
      <div class="slide-h3">Types of Recursion</div>
      <div class="small-text">Direct, indirect, and tail recursion — each with its own structure and use case.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">P</div>
    <div>
      <div class="slide-h3">Practical Programs</div>
      <div class="small-text">Factorial, Fibonacci, power, reverse string, binary search — all solved recursively.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--purple);">
    <div class="icon-circle ic-purple">D</div>
    <div>
      <div class="slide-h3">Debugging &amp; Pitfalls</div>
      <div class="small-text">Missing base case, wrong condition, not reducing input — three common mistakes.</div>
    </div>
  </div>

</div>

<div class="flex-col" style="gap:10px;">

  <div v-click class="card-navy" style="border-radius:10px;padding:14px 18px;">
    <div style="font-size:.7rem;text-transform:uppercase;letter-spacing:1px;color:var(--muted);margin-bottom:8px;">Quick Reference Cheat Sheet</div>
    <div style="font-family:'Fira Code',monospace;font-size:.68rem;line-height:1.9;color:var(--navy);">
      <div v-after><span style="color:#ef5050;">def</span> func(n): <span style="color:#6b7280;"># define recursive fn</span></div>
      <div v-after>&nbsp;&nbsp;<span style="color:#ef5050;">if</span> n == 0: <span style="color:#ef5050;">return</span> val <span style="color:#6b7280;"># base case</span></div>
      <div v-after>&nbsp;&nbsp;<span style="color:#ef5050;">return</span> func(n-1) <span style="color:#6b7280;"># recursive call</span></div>
      <div v-after><span style="color:#ef5050;">import</span> sys <span style="color:#6b7280;"># depth control</span></div>
      <div v-after>sys.getrecursionlimit() <span style="color:#6b7280;"># 1000</span></div>
      <div v-after><span style="color:#6b7280;"># Direct: func calls itself</span></div>
      <div v-after><span style="color:#6b7280;"># Indirect: A calls B, B calls A</span></div>
      <div v-after><span style="color:#6b7280;"># Tail: recursive call is LAST op</span></div>
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div><strong>Remember:</strong> Every recursive function needs a <strong>base case</strong>. Without it, you get infinite recursion and a stack overflow.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="small-text"><strong>Next Step:</strong> Explore memoization and dynamic programming to optimize recursive solutions like Fibonacci.</div>
  </div>

</div>
</div>

  </template>
</Slide2>