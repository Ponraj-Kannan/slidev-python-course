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
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--blue);">elif</strong> = "else if" — it checks a new condition <strong style="color:var(--green);">only when the previous if (or elif) was False</strong>. You can chain as many elif blocks as you need.
    </div>
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
