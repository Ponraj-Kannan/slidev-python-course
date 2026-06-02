---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — INTRODUCTION TO DATA TYPES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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
