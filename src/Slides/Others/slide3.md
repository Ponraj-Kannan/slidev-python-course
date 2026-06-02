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

<Slide2 topic="while Loop — Syntax and Execution">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">while</span> Loop — Syntax &amp; Flow</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

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

  <div v-click style="margin-top:8px; border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
    <div class="section-label" style="margin-bottom:6px;">Syntax Parts</div>
    <div style="display:flex;flex-direction:column;gap:4px;">
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

<div class="flex-col">
  <div v-click class="section-label">Execution Flowchart</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:10px 0;">
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

<Slide2 topic="while Loop — Trace & Infinite Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">while Loop — <span class="highlight">Tracing</span> &amp; Infinite Loop</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div class="section-label">Step-by-Step Trace: counter = 1 to 5</div>

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

<div class="flex-col">
  <div v-click class="section-label">Infinite while Loop — Danger Zone!</div>

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
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — FOR LOOP: SYNTAX + STRING ITERATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="for Loop — Syntax &amp; String Iteration">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">for</span> Loop — Syntax &amp; Iterating Strings</div>

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

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — FOR LOOP: LIST ITERATION + RANGE()
═══════════════════════════════════════════════════════ -->

<Slide2 topic="for Loop — Lists &amp; range()">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">for</span> Loop — Lists &amp; <span class="highlight">range()</span></div>

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
    <div style="display:flex;gap:4px;align-items:center;flex-wrap:wrap;">
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

<Slide2 topic="range() — start, stop, step">
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

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — while vs for COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="while Loop vs for Loop — Comparison">
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

<Slide2 topic="Nested Loops — Syntax &amp; Execution">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Nested</span> Loops</div>

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

  <div v-click class="card card-blue" style="margin-top:8px;">
    <div class="small-text"><strong>Pattern: Star Triangle</strong></div>
    <div style="background:#f6f8fa;border-radius:6px;border:1px solid #e1e4e8;padding:8px 12px;margin-top:6px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.8;">
      <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">5</span>):<br>
      <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"* "</span> * <span style="color:#0e6ead;">i</span>)</span>
      <div style="color:#2d7a00;margin-top:6px;">*<br>* *<br>* * *<br>* * * *</div>
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
     SLIDE 14 — break AND continue STATEMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Loop Control — break &amp; continue">
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

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — pass STATEMENT + break/continue/pass COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Loop Control — pass &amp; Comparison">
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

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — PRACTICAL EXAMPLES: SUM + TABLE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Examples — Sum &amp; Multiplication Table">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical <span class="highlight">Examples</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 1: Sum of 1 to N</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Sum of numbers 1 to n</span><br>
    <span style="color:#0e6ead;">n</span> = <span style="color:#b45309;">5</span><br>
    <span style="color:#0e6ead;">total</span> = <span style="color:#b45309;">0</span><br>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">n</span>+<span style="color:#b45309;">1</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">total</span> += <span style="color:#0e6ead;">i</span></span>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Sum ="</span>, <span style="color:#0e6ead;">total</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">Sum = 15</div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Accumulation Trace</div>
    <table class="trace-table" style="font-size:.65rem;">
      <thead><tr><th>i</th><th>total += i</th><th>total</th></tr></thead>
      <tbody>
        <tr><td>1</td><td>0 + 1</td><td>1</td></tr>
        <tr><td>2</td><td>1 + 2</td><td>3</td></tr>
        <tr><td>3</td><td>3 + 3</td><td>6</td></tr>
        <tr><td>4</td><td>6 + 4</td><td>10</td></tr>
        <tr class="hl"><td>5</td><td>10 + 5</td><td><strong>15</strong></td></tr>
      </tbody>
    </table>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 2: Multiplication Table</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Multiplication table of n</span><br>
    <span style="color:#0e6ead;">n</span> = <span style="color:#b45309;">3</span><br>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">11</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>, <span style="color:#2d7a00;">"x"</span>, <span style="color:#0e6ead;">i</span>, <span style="color:#2d7a00;">"="</span>, <span style="color:#0e6ead;">n</span>*<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.68rem;line-height:1.6;">
    3 x 1 = 3 &nbsp; 3 x 2 = 6 &nbsp; 3 x 3 = 9<br>
    3 x 4 = 12 &nbsp; 3 x 5 = 15 &nbsp; 3 x 6 = 18<br>
    3 x 7 = 21 &nbsp; 3 x 8 = 24 &nbsp; 3 x 9 = 27 &nbsp; 3 x 10 = 30
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div><strong>Try it:</strong> Change <span class="mono">n = 3</span> to any number and run the same loop — the table changes automatically.</div>
  </div>
</div>

</div>

  </template>
</Slide2>

---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — PRACTICAL EXAMPLES: PATTERNS + STRING
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Examples — Patterns &amp; String Traversal">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical <span class="highlight">Examples</span> — Patterns &amp; Strings</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 3: Right Triangle Pattern</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"*"</span> * <span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.8rem;line-height:2.0;">
    *<br>**<br>***<br>****<br>*****
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>How it works:</strong> <span class="mono">"*" * i</span> repeats the star character <span class="mono">i</span> times per row.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 4: Count Vowels in a String</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># Count vowels using for loop</span><br>
    <span style="color:#0e6ead;">word</span> = <span style="color:#2d7a00;">"programming"</span><br>
    <span style="color:#0e6ead;">count</span> = <span style="color:#b45309;">0</span><br>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">word</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">"aeiou"</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#0e6ead;">count</span> += <span style="color:#b45309;">1</span></span>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Vowels:"</span>, <span style="color:#0e6ead;">count</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">Vowels: 3 &nbsp;<span class="comment"># o, a, i</span></div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Character Scan Visualization</div>
    <div style="display:flex;gap:3px;flex-wrap:wrap;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);" title="consonant">p</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);">r</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--green);">o</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);">g</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--green);">a</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);">m</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);">m</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--green);">i</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);">n</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:5px;padding:4px 7px;font-family:'Fira Code',monospace;font-size:.7rem;font-weight:700;color:var(--red-dark);">g</div>
    </div>
    <div style="margin-top:5px;display:flex;gap:10px;">
      <div style="display:flex;align-items:center;gap:4px;font-size:.62rem;"><div style="width:10px;height:10px;background:#f0fff4;border:1px solid var(--green);border-radius:2px;"></div><span>Vowel (counted)</span></div>
      <div style="display:flex;align-items:center;gap:4px;font-size:.62rem;"><div style="width:10px;height:10px;background:var(--red-soft);border:1px solid var(--red);border-radius:2px;"></div><span>Consonant (skipped)</span></div>
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
     SLIDE 19 — ACTIVITY / MINI CHALLENGE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Activity — Loop Challenges">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Loop <span class="highlight">Challenges</span> — Try It!</div>

<div class="activity-box">
  <div class="act-title">Practice Exercises</div>

  <div class="g2" style="gap:10px;">

  <div class="flex-col" style="gap:8px;">
    <div class="act-task" v-click>
      <strong>Challenge 1 — while Loop</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Print odd numbers from 1 to 20 using a while loop.
      </div>
      <div class="hint">Hint: use the condition <span style="color:#b45309;">i % 2 != 0</span></div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 2 — for + range()</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Print the multiplication table of 7 using range(1, 11).
      </div>
      <div class="hint">Hint: print(7, "x", i, "=", 7*i)</div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 3 — Nested Loops</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Print this pattern using nested for loops:<br>
        1<br>1 2<br>1 2 3<br>1 2 3 4
      </div>
      <div class="hint">Hint: outer loop rows, inner loop columns</div>
    </div>
  </div>

  <div class="flex-col" style="gap:8px;">
    <div class="act-task" v-click>
      <strong>Challenge 4 — break</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Loop through numbers 1 to 20. Stop when you find the first number divisible by both 3 and 5. Print it.
      </div>
      <div class="hint">Hint: use <span style="color:#b45309;">if n % 3 == 0 and n % 5 == 0: break</span></div>
    </div>
    <div class="act-task" v-click>
      <strong>Challenge 5 — continue</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Loop 1 to 10. Skip multiples of 3. Print the rest.
      </div>
      <div class="hint">Hint: <span style="color:#b45309;">if i % 3 == 0: continue</span></div>
    </div>
    <div class="act-task" v-click>
      <strong>Bonus — Menu Loop</strong>
      <div style="margin-top:5px;color:#2d7a00;font-family:'Fira Code',monospace;font-size:.7rem;">
        Build a while loop menu: 1=Hello, 2=Bye, 3=Quit. Keep asking until user types 3.
      </div>
      <div class="hint">Hint: while True: with if/elif/break</div>
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

<Slide2 topic="Python Looping Statements — Summary">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What You've <span class="highlight">Learned</span> Today</div>

<div class="g2" style="gap:12px;">

<div class="flex-col" style="gap:8px;">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #ef5050;">
    <div class="icon-circle ic-red" style="flex-shrink:0;font-size:1rem;">&#x23F1;</div>
    <div>
      <div class="slide-h3">while Loop</div>
      <div class="small-text">Runs while a condition is True. Update counter to avoid infinite loop.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #3182ce;">
    <div class="icon-circle ic-blue" style="flex-shrink:0;font-size:1rem;">&#x1F504;</div>
    <div>
      <div class="slide-h3">for Loop + range()</div>
      <div class="small-text">Iterates over sequences: strings, lists, range(start, stop, step).</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #38a169;">
    <div class="icon-circle ic-green" style="flex-shrink:0;font-size:1rem;">&#x1F9F1;</div>
    <div>
      <div class="slide-h3">Nested Loops</div>
      <div class="small-text">Loop inside a loop. Inner loop runs fully for each outer iteration.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid #dd6b20;">
    <div class="icon-circle ic-orange" style="flex-shrink:0;font-size:1rem;">&#x1F6A6;</div>
    <div>
      <div class="slide-h3">break / continue / pass</div>
      <div class="small-text">Control loop flow: exit, skip, or placeholder.</div>
    </div>
  </div>

</div>

<div class="flex-col" style="gap:10px;">

  <div v-click class="card-navy" style="border-radius:10px;padding:14px 18px;">
    <div style="font-size:.7rem;text-transform:uppercase;letter-spacing:1px;color:var(--muted);margin-bottom:8px;">Quick Reference Cheat Sheet</div>
    <div style="font-family:'Fira Code',monospace;font-size:.68rem;line-height:1.9;color:var(--navy);">
      <div v-after><span style="color:#ef5050;">while</span> condition: <span style="color:#6b7280;"># condition-based</span></div>
      <div v-after><span style="color:#ef5050;">for</span> var <span style="color:#ef5050;">in</span> sequence: <span style="color:#6b7280;"># sequence-based</span></div>
      <div v-after><span style="color:#2d7a00;">range</span>(start, stop, step) <span style="color:#6b7280;"># number seq</span></div>
      <div v-after><span style="color:#ef5050;">break</span> <span style="color:#6b7280;"># exit loop</span></div>
      <div v-after><span style="color:#ef5050;">continue</span> <span style="color:#6b7280;"># skip iteration</span></div>
      <div v-after><span style="color:#ef5050;">pass</span> <span style="color:#6b7280;"># placeholder</span></div>
      <div v-after><span style="color:#ef5050;">else</span>: <span style="color:#6b7280;"># runs if no break</span></div>
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div><strong>Remember:</strong> Loops are the backbone of all repetitive logic in programming. Master them and you can solve almost any algorithmic problem!</div>
  </div>

</div>
</div>

  </template>
</Slide2>