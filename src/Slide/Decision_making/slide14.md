---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — NESTED IF
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">Nested <span class="highlight">if</span> Statements</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      Placing an <strong style="color:var(--green);">if statement inside another if</strong> creates a nested structure. The inner if only runs when the outer condition is True.
    </div>
  </div>

  <div v-click class="card card-orange">
    <div class="slide-h3" style="margin-bottom:6px;">Visual Structure</div>
    <div style="font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;background:#fff8f0;padding:8px;border-radius:6px;">
      <span style="color:#dd6b20;">if</span> level_1_condition:<br>
      <span style="background:rgba(221,107,32,.15);display:inline-block;width:95%;padding-left:4px;border-left:3px solid #dd6b20;">
        &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#3182ce;">if</span> level_2_condition:<br>
        <span style="background:rgba(49,130,206,.15);display:inline-block;width:88%;margin-left:8px;padding-left:4px;border-left:3px solid #3182ce;">
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#38a169;">→ innermost block</span>
        </span>
      </span>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
<div v-click class="callout callout-warn">
    <div>Avoid nesting more than <strong>2–3 levels</strong> deep — code becomes hard to read. Consider using <strong>logical operators</strong> (and, or) instead.</div>
  </div>
</div>

</div>
  </template>
</Slide2>
