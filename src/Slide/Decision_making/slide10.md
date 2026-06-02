---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — ELSE AS FALLBACK
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">else</span> as a Fallback Safety Net</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      The <strong style="color:var(--yellow);">else</strong> block acts as a <strong style="color:var(--green);">fallback</strong> — it handles every case that wasn't caught by any <code>if</code> or <code>elif</code>. It ensures no user input is left unhandled.
    </div>
  </div>
</div>
<div class="flex-col" style="gap:10px;">
<div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">Why use else as fallback?</div>
    <div class="flex-col" style="gap:6px;margin-top:8px;">
      <div class="body-text">Prevents program from silently ignoring unknown inputs</div>
      <div class="body-text">Provides meaningful error/default messages</div>
      <div class="body-text">Makes code more robust and user-friendly</div>
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div>Always add an <strong>else</strong> when handling user input — they might enter something unexpected!</div>
  </div>
  </div>
</div>
  </template>
</Slide2>
