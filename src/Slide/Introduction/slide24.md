---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — NAMING CONVENTIONS & BEST PRACTICES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Variable Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Naming <span class="highlight">Conventions</span> &amp; Best Practices</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Python Naming Conventions</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-green">snake_case</span>
        <div class="body-text">Use for variables & functions — <span class="mono" style="color:var(--green);">student_name</span>, <span class="mono" style="color:var(--green);">total_score</span></div>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-navy">UPPER_CASE</span>
        <div class="body-text">Use for constants — <span class="mono" style="color:var(--navy-mid);">MAX_SIZE</span>, <span class="mono" style="color:var(--navy-mid);">PI</span></div>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-blue">PascalCase</span>
        <div class="body-text">Use for class names — <span class="mono" style="color:var(--blue);">StudentRecord</span>, <span class="mono" style="color:var(--blue);">BankAccount</span></div>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div style="display:flex;gap:10px;align-items:center;">
        <span class="pill pill-orange">_single</span>
        <div class="body-text">Leading underscore = internal/private use — <span class="mono" style="color:var(--orange);">_helper</span></div>
      </div>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Good vs Bad Naming</div>

  <div>
    <table class="cmp-table">
      <thead v-click>
        <tr><th>❌ Bad Name</th><th>✔ Good Name</th><th>Why Better</th></tr>
      </thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);">x</td><td class="mono" style="color:var(--green);">student_age</td><td>Descriptive</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">a1</td><td class="mono" style="color:var(--green);">total_marks</td><td>Meaningful</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">myVar</td><td class="mono" style="color:var(--green);">my_var</td><td>PEP 8 style</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">temp</td><td class="mono" style="color:var(--green);">temperature_c</td><td>Clear unit</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">data2</td><td class="mono" style="color:var(--green);">sales_data</td><td>Context clear</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-success" style="margin-top:8px;">
    <div><strong>Golden Rule:</strong> A good variable name tells you <em>what</em> it stores without needing a comment. Code is read more than it is written!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
