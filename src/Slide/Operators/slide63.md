---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 31 — SUMMARY: PYTHON OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Summary — Python <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">What We Covered</div>

  <div style="display:flex;flex-direction:column;gap:5px; margin-bottom:40px">
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill pill-red" style="flex-shrink:0;">Arithmetic</span>
      <span style="font-size:.72rem;color:var(--slate);">+  −  *  /  //  %  **  — Mathematical calculations</span>
    </div>
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill pill-blue" style="flex-shrink:0;">Assignment</span>
      <span style="font-size:.72rem;color:var(--slate);">=  +=  -=  *=  /=  //=  %=  **=  — Store &amp; update values</span>
    </div>
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill pill-orange" style="flex-shrink:0;">Comparison</span>
      <span style="font-size:.72rem;color:var(--slate);">==  !=  >  &lt;  >=  &lt;=  — Compare values → bool</span>
    </div>
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill pill-green" style="flex-shrink:0;">Logical</span>
      <span style="font-size:.72rem;color:var(--slate);">and  or  not  — Combine conditions</span>
    </div>
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill pill-navy" style="flex-shrink:0;">Bitwise</span>
      <span style="font-size:.72rem;color:var(--slate);">&amp;  |  ^  ~  &lt;&lt;  >>  — Bit-level operations</span>
    </div>
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill" style="background:#f0e6ff;color:#6b21a8;flex-shrink:0;">Membership</span>
      <span style="font-size:.72rem;color:var(--slate);">in  not in  — Check value in sequence</span>
    </div>
    <div v-click style="display:flex;gap:8px;align-items:flex-start;" class="card">
      <span class="pill" style="background:#fef9c3;color:#854d0e;flex-shrink:0;">Identity</span>
      <span style="font-size:.72rem;color:var(--slate);">is  is not  — Check same object in memory</span>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Key Takeaways</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div v-click class="callout callout-info">
      <div>Use <span class="mono">()</span> parentheses to control precedence and make code readable.</div>
    </div>
    <div v-click class="callout callout-warn">
      <div>Never confuse <span class="mono">==</span> (compare) with <span class="mono">=</span> (assign) — a classic beginner bug!</div>
    </div>
    <div v-click class="callout callout-success">
      <div>Prefer <span class="mono">is</span> / <span class="mono">is not</span> when checking for <span class="mono">None</span>; use <span class="mono">==</span> for value equality.</div>
    </div>
    <div v-click class="callout callout-danger">
      <div><span class="mono">/</span> always returns a float; use <span class="mono">//</span> for integer (floor) division.</div>
    </div>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Precedence Quick Tip</div>
    <div class="step-flow">
      <div class="step-box active">( )</div>
      <div class="step-arrow">→</div>
      <div class="step-box active">**</div>
      <div class="step-arrow">→</div>
      <div class="step-box active">* / % //</div>
      <div class="step-arrow">→</div>
      <div class="step-box active">+ -</div>
      <div class="step-arrow">→</div>
      <div class="step-box active">Comparisons</div>
      <div class="step-arrow">→</div>
      <div class="step-box active">not and or</div>
    </div>
  </div>

  <div v-click class="card-navy" style="margin-top:8px;border-radius:10px;">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Operators are everywhere</strong> — every calculation, condition, loop, and function call in Python uses them. Understanding operators means understanding Python logic! 🐍
    </div>
  </div>

</div>

</div>

  </template>
</Slide2>
