---
theme: default
title: Python Basics & Syntax
titleTemplate: '%s — Python Fundamentals'
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
transition: slide-left
mdc: true
colorSchema: light
fonts:
  sans: 'Nunito'
  mono: 'Fira Code'
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — IF STATEMENT: WHAT IS IT?
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">What is an <span class="highlight">if Statement?</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      An <strong style="color:var(--red);">if statement</strong> lets your program make decisions — it runs a block of code <strong style="color:var(--green);">only when</strong> a condition evaluates to <span style="color:var(--yellow);">True</span>.
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div>Think of it like a <strong>security guard</strong> — only people who meet the condition get inside!</div>
  </div>

  <div v-click class="card" style="border:1px solid #ef5050;">
    <div class="slide-h3" style="margin-bottom:8px;">Real-life Analogy</div>
    <div class="body-text">
      <strong>IF</strong> it is raining<br>
      &nbsp;&nbsp;&nbsp;&nbsp;→ Take an umbrella ☂️<br>
      <span class="small-text">(do nothing if it is NOT raining)</span>
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Key rule:</strong> If the condition is <strong>False</strong>, Python completely <em>skips</em> the indented block.</div>
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
        <div class="flow-v-box" style="background:#f0fff4;border:1px solid var(--green);color:var(--green);min-width:100px;">Run the block</div>
      </div>
      <div class="flex-col" style="align-items:center;gap:4px;">
        <div style="font-size:.7rem;font-weight:800;color:var(--red);">FALSE</div>
        <div class="flow-v-arrow" style="color:var(--red);">▼</div>
        <div class="flow-v-box" style="background:var(--red-soft);border:1px solid var(--red);color:var(--red-dark);min-width:100px;">Skip the block</div>
      </div>
    </div>
    <div class="flow-v-arrow" style="margin-top:4px;">▼</div>
    <div class="flow-v-box" style="background:#fffff0;border:1px solid var(--yellow);color:#744210;">Continue program</div>
  </div>
</div>

</div>
  </template>
</Slide2>
