---
transition: fade
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 23 — MATCH CASE SYNTAX
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">match <span class="highlight">case</span> — Syntax</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card-navy">
    <div style="font-size:.72rem;text-transform:uppercase;letter-spacing:1px;color:rgba(255,255,255,.5);margin-bottom:6px;">Syntax</div>
    <div style="font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;margin-top:4px;">
      <span style="color:#ffd166;">match</span> <span style="color:#61dafb;">variable</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">value_1</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#e2e8f0;">...</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">value_2</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#e2e8f0;">...</span><br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#ff9900;">_</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># default (wildcard)</span>
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
   <div v-click class="syntax-row">
      <div>
        <div class="syn-keyword" style="background:#faf5ff;color:#553c9a;">match</div>
        <div class="syn-label">keyword</div>
      </div>
      <div>
        <div class="syn-varname">variable</div>
        <div class="syn-label">value to check</div>
      </div>
      <div>
        <div class="syn-colon">:</div>
        <div class="syn-label">required</div>
      </div>
    </div>
    <div v-click class="syntax-row" style="margin-left:20px;">
      <div>
        <div class="syn-keyword" style="background:#f0fff4;color:#276749;">case</div>
        <div class="syn-label">each pattern</div>
      </div>
      <div>
        <div class="syn-value">value</div>
        <div class="syn-label">pattern to match</div>
      </div>
      <div>
        <div class="syn-operator">_</div>
        <div class="syn-label">wildcard/default</div>
      </div>
    </div>
    <div v-click class="callout callout-info">
    <div>The <strong>_ (underscore)</strong> is the wildcard — it matches <em>anything</em> that didn't match earlier cases. Like the <strong>else</strong> in if-elif-else.</div>
  </div>

</div>

</div>
  </template>
</Slide2>
