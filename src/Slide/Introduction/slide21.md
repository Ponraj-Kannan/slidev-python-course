---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — VARIABLE NAMING RULES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Variable Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Rules for <span class="highlight">Naming Variables</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">The Rules</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 1</div>
      <div class="body-text">Must start with a <strong>letter</strong> (a–z, A–Z) or an <strong>underscore</strong> ( _ )</div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 2</div>
      <div class="body-text">Can contain letters, digits (0–9), and underscores — <strong>no spaces</strong></div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 3</div>
      <div class="body-text"><strong>Cannot start with a digit</strong> — <span class="mono" style="color:var(--red-dark);">2name</span> is invalid</div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--green);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 4</div>
      <div class="body-text"><strong>No special characters</strong>: @, #, $, !, -, spaces are not allowed</div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--red);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 5</div>
      <div class="body-text"><strong>Cannot be a reserved keyword</strong> — e.g. <span class="mono" style="color:var(--red-dark);">for</span>, <span class="mono" style="color:var(--red-dark);">if</span>, <span class="mono" style="color:var(--red-dark);">class</span></div>
    </div>
    <div style="display:flex;gap:10px;align-items:flex-start;" v-click>
      <div style="background:var(--blue);color:#fff;border-radius:6px;padding:3px 10px;font-size:.65rem;font-weight:800;flex-shrink:0;">RULE 6</div>
      <div class="body-text">Variable names are <strong>case-sensitive</strong> — <span class="mono">Name</span> ≠ <span class="mono">name</span></div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Valid vs Invalid Names</div>

  <div >
    <table class="cmp-table">
      <thead v-click>
        <tr><th>Name</th><th>Valid?</th><th>Reason</th></tr>
      </thead>
      <tbody>
        <tr v-click><td class="mono">student_name</td><td class="yes">✔ Valid</td><td>Letters + underscore</td></tr>
        <tr v-click><td class="mono">_age</td><td class="yes">✔ Valid</td><td>Starts with underscore</td></tr>
        <tr v-click><td class="mono">score2</td><td class="yes">✔ Valid</td><td>Letter first, digit after</td></tr>
        <tr v-click><td class="mono">2score</td><td class="no">✘ Invalid</td><td>Starts with digit</td></tr>
        <tr v-click><td class="mono">my-name</td><td class="no">✘ Invalid</td><td>Contains hyphen</td></tr>
        <tr v-click><td class="mono">for</td><td class="no">✘ Invalid</td><td>Reserved keyword</td></tr>
        <tr v-click><td class="mono">my name</td><td class="no">✘ Invalid</td><td>Contains space</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>
