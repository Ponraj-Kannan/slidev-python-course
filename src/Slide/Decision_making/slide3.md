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
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--yellow);">else</strong> is the <strong style="color:var(--green);">final catch-all</strong>. It runs when <em>every</em> previous condition is False. It has <strong style="color:var(--red);">no condition</strong> of its own.
    </div>
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
