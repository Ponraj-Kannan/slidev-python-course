---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 22 — ASSIGNMENT OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Assignment <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Assignment operators</strong> store a value in a variable. The compound ones (<span class="mono">+=</span>, <span class="mono">-=</span>, …) are <strong>shorthand</strong> that combine an operation with assignment.
    </div>
  </div>

  <div>
    <table class="cmp-table" style="font-size:.7rem;margin-top:6px;">
      <thead v-click><tr><th>Operator</th><th>Example</th><th>Equivalent to</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">=</td><td class="mono">x = 5</td><td class="mono">x = 5</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">+=</td><td class="mono">x += 3</td><td class="mono">x = x + 3</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">-=</td><td class="mono">x -= 2</td><td class="mono">x = x - 2</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">*=</td><td class="mono">x *= 4</td><td class="mono">x = x * 4</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">/=</td><td class="mono">x /= 2</td><td class="mono">x = x / 2</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">//=</td><td class="mono">x //= 3</td><td class="mono">x = x // 3</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">%=</td><td class="mono">x %= 3</td><td class="mono">x = x % 3</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">**=</td><td class="mono">x **= 2</td><td class="mono">x = x ** 2</td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Code Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">10</span><br>
    <span style="color:#0e6ead;">x</span> += <span style="color:#b45309;">5</span>  <span style="color:#6b7280;"># x is now 15</span><br>
    <span style="color:#0e6ead;">x</span> -= <span style="color:#b45309;">3</span>  <span style="color:#6b7280;"># x is now 12</span><br>
    <span style="color:#0e6ead;">x</span> *= <span style="color:#b45309;">2</span>  <span style="color:#6b7280;"># x is now 24</span><br>
    <span style="color:#0e6ead;">x</span> //= <span style="color:#b45309;">4</span> <span style="color:#6b7280;"># x is now 6</span><br>
    <span style="color:#0e6ead;">x</span> **= <span style="color:#b45309;">2</span> <span style="color:#6b7280;"># x is now 36</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>)    <span style="color:#6b7280;"># 36</span>
  </div>

  <div style="margin-top:8px; margin-bottom:40px">
    <div v-click class="section-label" style="margin-bottom:6px;">Step-by-Step Trace</div>
    <table class="trace-table">
      <thead>
        <tr v-after><th>Statement</th><th>x value</th></tr>
      </thead>
      <tbody>
        <tr v-click><td class="mono">x = 10</td><td class="mono h2">10</td></tr>
        <tr v-click><td class="mono">x += 5</td><td class="mono h2">15</td></tr>
        <tr v-click><td class="mono">x -= 3</td><td class="mono h2">12</td></tr>
        <tr v-click><td class="mono">x *= 2</td><td class="mono h2">24</td></tr>
        <tr v-click><td class="mono">x //= 4</td><td class="mono h2">6</td></tr>
        <tr v-click><td class="mono">x **= 2</td><td class="mono h2">36</td></tr>
      </tbody>
    </table>
  </div>
</div>
</div>
  </template>
</Slide2>
