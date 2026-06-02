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
