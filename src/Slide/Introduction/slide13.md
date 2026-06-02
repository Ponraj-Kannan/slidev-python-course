---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 2 — INTRODUCTION TO VARIABLES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is a <span class="highlight">Variable?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">variable</strong> is a <strong style="color:var(--green);">named storage location</strong> in memory that holds a value. You can think of it as a labelled box that stores data your program can use and change.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Real-World Analogy:</strong> A variable is like a labelled jar — the label is the variable name, and what's inside the jar is the value.</div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;">
    <span style="color:#6b7280;"># Creating variables</span><br>
    <span style="color:#0e6ead;">name</span> = <span style="color:#2d7a00;">"Alice"</span><br>
    <span style="color:#0e6ead;">age</span> = <span style="color:#b45309;">20</span><br>
    <span style="color:#0e6ead;">marks</span> = <span style="color:#b45309;">95.5</span>
  </div>

  <div v-click class="card card-green">
    <div class="small-text"><strong>Key idea:</strong> Variables let you store data with a meaningful name so you can reuse it anywhere in your program.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Variable as a Labelled Box</div>

  <div v-after style="display:flex;flex-direction:column;gap:8px;">
    <div style="display:flex;align-items:center;gap:10px;">
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:10px;padding:10px 18px;min-width:80px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Label</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--red-dark);font-size:.85rem;">name</div>
      </div>
      <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">→</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:10px;padding:10px 18px;flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Value</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--green);font-size:.85rem;">"Alice"</div>
      </div>
    </div>
    <div style="display:flex;align-items:center;gap:10px;">
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:10px;padding:10px 18px;min-width:80px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Label</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--red-dark);font-size:.85rem;">age</div>
      </div>
      <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">→</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:10px;padding:10px 18px;flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Value</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--green);font-size:.85rem;">20</div>
      </div>
    </div>
    <div style="display:flex;align-items:center;gap:10px;">
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:10px;padding:10px 18px;min-width:80px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Label</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--red-dark);font-size:.85rem;">marks</div>
      </div>
      <div style="color:var(--muted);font-size:1.2rem;font-weight:900;">→</div>
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:10px;padding:10px 18px;flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px;">Value</div>
        <div style="font-family:'Fira Code',monospace;font-weight:800;color:var(--green);font-size:.85rem;">95.5</div>
      </div>
    </div>
  </div>

  <div v-click class="card card-blue" style="margin-top:4px;">
    <div class="small-text"><strong>Python is dynamic:</strong> You do NOT need to declare a type — Python figures it out automatically!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
