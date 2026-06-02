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
