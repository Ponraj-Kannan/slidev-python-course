---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 25 — BITWISE OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Bitwise <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Bitwise operators</strong> work directly on the <strong>binary bits</strong> (0s and 1s) of integers. Python converts numbers to binary, applies the operation, then converts back.
    </div>
  </div>

  <div>
    <table class="cmp-table" style="font-size:.7rem;margin-top:6px;">
      <thead v-click><tr><th>Operator</th><th>Name</th><th>Example</th><th>Result</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&amp;</td><td>AND</td><td class="mono">5 &amp; 3</td><td class="mono yes">1</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">|</td><td>OR</td><td class="mono">5 | 3</td><td class="mono yes">7</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">^</td><td>XOR</td><td class="mono">5 ^ 3</td><td class="mono yes">6</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">~</td><td>NOT (Complement)</td><td class="mono">~5</td><td class="mono yes">-6</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&lt;&lt;</td><td>Left Shift</td><td class="mono">5 &lt;&lt; 1</td><td class="mono yes">10</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&gt;&gt;</td><td>Right Shift</td><td class="mono">5 &gt;&gt; 1</td><td class="mono yes">2</td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Binary Visualization: 5 &amp; 3</div>

  <div v-after style="background:#f7f8fc;border-radius:10px;border:1px solid var(--border);padding:12px 14px;">
    <div style="font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;">
      <div style="display:flex;align-items:center;gap:8px;">
        <span style="color:var(--muted);min-width:14px;">5</span>
        <span style="color:var(--muted);">=&nbsp;</span>
        <span style="background:var(--red-soft);border:1px solid var(--red);border-radius:4px;padding:2px 8px;color:var(--red-dark);font-weight:700;">0101</span>
      </div>
      <div style="display:flex;align-items:center;gap:8px; margin-top:5px;">
        <span style="color:var(--muted);min-width:14px;">3</span>
        <span style="color:var(--muted);">=&nbsp;</span>
        <span style="background:#ebf8ff;border:1px solid var(--blue);border-radius:4px;padding:2px 8px;color:#2b6cb0;font-weight:700;">0011</span>
      </div>
      <div style="border-top:1px dashed var(--border);margin:4px 0;"></div>
      <div style="display:flex;align-items:center;gap:8px;">
        <span style="color:var(--muted);min-width:14px;font-size:.6rem;">AND</span>
        <span style="color:var(--muted);">= </span>
        <span style="background:#f0fff4;border:1px solid var(--green);border-radius:4px;padding:2px 8px;color:var(--green);font-weight:700;">0001</span>
        <span style="color:var(--green);font-weight:700;">= 1</span>
      </div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Code Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">5</span>, <span style="color:#b45309;">3</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> &amp; <span style="color:#0e6ead;">b</span>)   <span style="color:#6b7280;"># 1  (AND)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> | <span style="color:#0e6ead;">b</span>)   <span style="color:#6b7280;"># 7  (OR)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> ^ <span style="color:#0e6ead;">b</span>)   <span style="color:#6b7280;"># 6  (XOR)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> &lt;&lt; <span style="color:#b45309;">1</span>)  <span style="color:#6b7280;"># 10 (×2)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> &gt;&gt; <span style="color:#b45309;">1</span>)  <span style="color:#6b7280;"># 2  (÷2)</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div><strong>Tip:</strong> Left shift <span class="mono">&lt;&lt; n</span> multiplies by 2ⁿ. Right shift <span class="mono">&gt;&gt; n</span> divides by 2ⁿ. Very fast operations in memory!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
