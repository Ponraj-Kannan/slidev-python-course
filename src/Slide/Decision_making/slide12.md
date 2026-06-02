---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — SHORTHAND IF...ELSE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">Shorthand <span class="highlight">if ... else</span> (Ternary)</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--yellow);">one-line if-else</strong> (called a ternary expression). Useful when you want to assign a value or print based on a condition — without writing a full 4-line block.
    </div>
  </div>

  <div v-click class="card" style="border:1px solid var(--green);">
    <div class="slide-h3" style="margin-bottom:8px;">Syntax Pattern</div>
    <div class="syntax-row" style="flex-wrap:wrap;gap:6px;">
      <div>
        <div class="syn-value">result_if_true</div>
        <div class="syn-label">runs when True</div>
      </div>
      <div>
        <div class="syn-keyword">if</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-varname">condition</div>
        <div class="syn-label">evaluated</div>
      </div>
      <div>
        <div class="syn-keyword" style="background:#fffff0;color:#744210;">else</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-body">result_if_false</div>
        <div class="syn-label">runs when False</div>
      </div>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-warn">
    <div>Use shorthand only for <strong>simple</strong> conditions. For complex logic, stick with the full if-else form for readability.</div>
  </div>
</div>
</div>
  </template>
</Slide2>
