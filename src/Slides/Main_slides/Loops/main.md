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