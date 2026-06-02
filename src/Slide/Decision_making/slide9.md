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
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      You can use <strong style="color:var(--blue);">if + else</strong> directly without any <code>elif</code>. This is a simple two-way branch — either the condition is met, or it isn't.
    </div>
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
