---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 26 — MATCH CASE WITH MULTIPLE VALUES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">match-case — <span class="highlight">Multiple Values</span> per Case</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="callout callout-info">
    <div style="font-size:.78rem;line-height:1.6;color:var(--slate);">
      You can match <strong style="color:var(--yellow);">multiple values</strong> in a single case using the <strong style="color:var(--green);">| (pipe)</strong> operator — like saying "match this OR that".
    </div>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
<div v-click style="background:#1a1f36;border-radius:10px;padding:14px 18px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.9;">
    <span style="color:#61dafb;">day</span> = <span style="color:#f1fa8c;">"Saturday"</span><br><br>
    <span style="color:#ffd166;">match</span> <span style="color:#61dafb;">day</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Saturday"</span> <span style="color:#ff9900;">|</span> <span style="color:#f1fa8c;">"Sunday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"🎉 It's the weekend!"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#f1fa8c;">"Monday"</span> <span style="color:#ff9900;">|</span> <span style="color:#f1fa8c;">"Friday"</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"📅 Start/end of week"</span>)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">case</span> <span style="color:#ff9900;">_</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#a8ff78;">print</span>(<span style="color:#f1fa8c;">"💼 Regular weekday"</span>)
  </div>

  <div v-click class="output-box">
    <span class="prompt">day = "Saturday" → </span>🎉 It's the weekend!<br>
    <span class="prompt">day = "Tuesday"  → </span>💼 Regular weekday
  </div>
</div>

</div>
  </template>
</Slide2>
