---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 21 — ARITHMETIC OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Arithmetic <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Arithmetic operators</strong> perform <strong>mathematical calculations</strong> on numeric values — just like a calculator!
    </div>
  </div>

  <div>
    <table class="cmp-table" style="font-size:.72rem;margin-top:6px;">
      <thead v-click><tr><th>Operator</th><th>Name</th><th>Example</th><th>Result</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">+</td><td>Addition</td><td class="mono">10 + 3</td><td class="mono yes">13</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">-</td><td>Subtraction</td><td class="mono">10 - 3</td><td class="mono yes">7</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">*</td><td>Multiplication</td><td class="mono">10 * 3</td><td class="mono yes">30</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">/</td><td>Division</td><td class="mono">10 / 3</td><td class="mono yes">3.333…</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">//</td><td>Floor Division</td><td class="mono">10 // 3</td><td class="mono yes">3</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">%</td><td>Modulus</td><td class="mono">10 % 3</td><td class="mono yes">1</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">**</td><td>Exponentiation</td><td class="mono">2 ** 8</td><td class="mono yes">256</td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Code Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">10</span>, <span style="color:#b45309;">3</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> + <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># 13</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> - <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># 7</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> * <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># 30</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> / <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># 3.3333333333333335</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> // <span style="color:#0e6ead;">b</span>) <span style="color:#6b7280;"># 3   ← drops decimal</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> % <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># 1   ← remainder</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">2</span> ** <span style="color:#b45309;">8</span>) <span style="color:#6b7280;"># 256 ← 2 to the power 8</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div><strong>Note:</strong> <span class="mono">/</span> always returns a <span class="mono">float</span>. Use <span class="mono">//</span> for integer (floor) division. The <span class="mono">%</span> operator is handy for checking even/odd: <span class="mono">n % 2 == 0</span>.</div>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px;">
    <div class="small-text"><strong>Real-world use:</strong> Calculating bills, area/perimeter, interest rates, scores, and scientific formulas</div>
  </div>

</div>

</div>

  </template>
</Slide2>
