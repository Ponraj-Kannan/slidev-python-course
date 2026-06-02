---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 23 — COMPARISON (RELATIONAL) OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Comparison <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Comparison operators</strong> compare two values and always return a <strong>Boolean</strong> result — either <span class="mono" style="color:var(--green);">True</span> or <span class="mono" style="color:var(--red-dark);">False</span>.
    </div>
  </div>

  <div>
    <table class="cmp-table" style="font-size:.72rem;margin-top:6px;">
      <thead v-click><tr><th>Operator</th><th>Meaning</th><th>Example</th><th>Result</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">==</td><td>Equal to</td><td class="mono">5 == 5</td><td class="yes">True</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">!=</td><td>Not equal to</td><td class="mono">5 != 3</td><td class="yes">True</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&gt;</td><td>Greater than</td><td class="mono">7 > 4</td><td class="yes">True</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&lt;</td><td>Less than</td><td class="mono">3 < 9</td><td class="yes">True</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&gt;=</td><td>Greater than or equal</td><td class="mono">5 >= 5</td><td class="yes">True</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:700;">&lt;=</td><td>Less than or equal</td><td class="mono">4 <= 3</td><td class="no">False</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:6px;">
    <div><strong>Common mistake:</strong> Don't confuse <span class="mono">==</span> (comparison) with <span class="mono">=</span> (assignment). They are completely different!</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Code Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">10</span>, <span style="color:#b45309;">7</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> == <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># False</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> != <span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> > <span style="color:#0e6ead;">b</span>)   <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> >= <span style="color:#b45309;">10</span>)  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">b</span> < <span style="color:#b45309;">5</span>)   <span style="color:#6b7280;"># False</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Used in Conditions</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:4px;">
    <span style="color:#0e6ead;">age</span> = <span style="color:#b45309;">20</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">age</span> >= <span style="color:#b45309;">18</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Adult"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Minor"</span>)</span>
    <span style="color:#6b7280;"># Adult</span>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Login validation, grade checks, age verification, sorting, filtering data</div>
  </div>

</div>

</div>

  </template>
</Slide2>
