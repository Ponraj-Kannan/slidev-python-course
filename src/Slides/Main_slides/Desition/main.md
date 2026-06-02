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
    <div style="font-size:.82rem;color:#e2e8f0;line-height:1.6;">An <strong style="color:#ff9a9a;">if statement</strong> lets your program make decisions — it runs a block of code <strong style="color:#a8ff78;">only when</strong> a condition evaluates to <span style="color:#ffd166;">True</span>.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;"><strong style="color:#ffd166;">else</strong> is the <strong style="color:#a8ff78;">final catch-all</strong>. It runs when <em>every</em> previous condition is False. It has <strong style="color:#ff9a9a;">no condition</strong> of its own.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;"><strong style="color:#61dafb;">elif</strong> = "else if" — it checks a new condition <strong style="color:#a8ff78;">only when the previous if (or elif) was False</strong>. You can chain as many elif blocks as you need.</div>
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
    <div>You can use <strong>if + else</strong> directly without any <code>elif</code>. This is a simple two-way branch — either the condition is met, or it isn't.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.72rem;text-transform:uppercase;letter-spacing:1px;color:rgba(255,255,255,.5);margin-bottom:6px;">Key Concept</div>
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;">The <strong style="color:#ffd166;">else</strong> block acts as a <strong style="color:#a8ff78;">fallback</strong> — it handles every case that wasn't caught by any <code>if</code> or <code>elif</code>. It ensures no user input is left unhandled.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;">A <strong style="color:#ffd166;">one-line if-else</strong> (called a ternary expression). Useful when you want to assign a value or print based on a condition — without writing a full 4-line block.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;">Placing an <strong style="color:#a8ff78;">if statement inside another if</strong> creates a nested structure. The inner if only runs when the outer condition is True.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;">Python requires every block to have at least one statement. <strong style="color:#ffd166;">pass</strong> is a legal <strong style="color:#a8ff78;">do-nothing</strong> statement that keeps the code syntactically valid without performing any action.</div>
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
  <div v-click class="card-navy">
    <div style="font-size:.72rem;text-transform:uppercase;letter-spacing:1px;color:rgba(255,255,255,.5);margin-bottom:6px;">OR Pattern in case</div>
    <div style="font-size:.78rem;color:#e2e8f0;line-height:1.6;">You can match <strong style="color:#ffd166;">multiple values</strong> in a single case using the <strong style="color:#a8ff78;">| (pipe)</strong> operator — like saying "match this OR that".</div>
  </div>
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

