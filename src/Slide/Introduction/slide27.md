---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 11 — NUMERIC TYPES: int
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
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
