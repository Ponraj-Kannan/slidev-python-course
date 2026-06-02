---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — PASS STATEMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">The <span class="highlight">pass</span> Statement</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      Python requires every block to have at least one statement. <strong style="color:var(--yellow);">pass</strong> is a legal <strong style="color:var(--green);">do-nothing</strong> statement that keeps the code syntactically valid without performing any action.
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
<div v-click class="card card-red">
    <div class="slide-h3" style="color:var(--red-dark);">❌ Without pass — SyntaxError!</div>
    <div style="font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;background:#fff;padding:8px;border-radius:6px;margin-top:6px;">
      <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ef5050;"># empty block → SyntaxError!</span>
    </div>
  </div>
  <div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">✅ With pass — Valid!</div>
    <div style="font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;background:#fff;padding:8px;border-radius:6px;margin-top:6px;">
      <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ffd166;">pass</span>&nbsp;&nbsp;<span style="color:#636e80;"># placeholder — valid!</span>
    </div>
  </div>
</div>

</div>
  </template>
</Slide2>
