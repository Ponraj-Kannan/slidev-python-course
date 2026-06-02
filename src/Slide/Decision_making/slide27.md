---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 29 — QUICK REFERENCE CHEAT SHEET
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements — Quick Reference">
  <template #content>
<div class="slide-h1" style="margin-bottom:12px;">📋 Conditional Statements <span class="highlight">Cheat Sheet</span></div>

<div style="margin-top:10px;">
  <table class="cmp-table">
    <tr><th>Keyword</th><th>Purpose</th><th>Has condition?</th><th>Can use alone?</th></tr>
    <tr v-click ><td class="mono" style="color:var(--red-dark);">if</td><td>First condition check</td><td class="yes">✅ Yes</td><td class="yes">✅ Yes</td></tr>
    <tr v-click ><td class="mono" style="color:#2b6cb0;">elif</td><td>Additional condition</td><td class="yes">✅ Yes</td><td class="no">❌ Needs if first</td></tr>
    <tr v-click ><td class="mono" style="color:#744210;">else</td><td>Default fallback</td><td class="no">❌ No condition</td><td class="no">❌ Needs if first</td></tr>
    <tr v-click ><td class="mono" style="color:#553c9a;">match</td><td>Pattern matching</td><td class="yes">✅ Yes (value)</td><td class="yes">✅ Yes</td></tr>
    <tr v-click ><td class="mono" style="color:#276749;">pass</td><td>Empty placeholder</td><td class="no">❌ No</td><td class="no">❌ Inside a block</td></tr>
  </table>
</div>
  </template>
</Slide2>
