---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 24 — MATCH CASE EXECUTION DIAGRAM
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">match-case <span class="highlight">Execution Flow</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:8px;">
  <div class="slide-h3" v-click>How Python processes match</div>

  <div v-after style="display:flex;flex-direction:column;gap:4px;">
    <div style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">1</div>
      <div class="flow-v-box" style="flex:1;background:#ebf8ff;border:1px solid #3182ce;color:#2b6cb0;">Evaluate the match variable</div>
    </div>
    <div style="padding-left:13px;color:var(--muted);">▼</div>
    <div v-after style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">2</div>
      <div class="flow-v-box" style="flex:1;background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);">Compare against case 1 pattern</div>
    </div>
    <div style="padding-left:13px;display:flex;gap:20px;">
      <div style="font-size:.65rem;color:var(--green);font-weight:800;">MATCH → run block, STOP</div>
      <div style="font-size:.65rem;color:var(--red);font-weight:800;">NO MATCH → try next case ▼</div>
    </div>
    <div v-after style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">3</div>
      <div class="flow-v-box" style="flex:1;background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);">Compare against case 2 pattern</div>
    </div>
    <div style="padding-left:13px;color:var(--muted);">▼ ... repeat ...</div>
    <div v-after style="display:flex;align-items:center;gap:8px;">
      <div class="badge-num">N</div>
      <div class="flow-v-box" style="flex:1;background:#faf5ff;border:2px solid #805ad5;color:#553c9a;">case _ (wildcard — no match found)</div>
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div>Only <strong>one</strong> case block runs per match statement — Python stops as soon as a match is found!</div>
  </div>
</div>

</div>
  </template>
</Slide2>
