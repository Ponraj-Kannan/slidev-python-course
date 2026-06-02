---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 28 — OPERATOR PRECEDENCE AND ASSOCIATIVITY
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Operator <span class="highlight">Precedence</span> &amp; Associativity</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Precedence</strong> determines <strong>which operator is evaluated first</strong> in an expression. Higher precedence = evaluated earlier (like BODMAS in maths!).
    </div>
  </div>

  <div>
    <table class="cmp-table" style="font-size:.68rem;margin-top:6px; margin-bottom:40px">
      <thead v-click><tr><th>Priority</th><th>Operator(s)</th><th>Description</th></tr></thead>
      <tbody>
        <tr v-click><td style="color:var(--red-dark);font-weight:700;">1 (Highest)</td><td class="mono">()</td><td>Parentheses</td></tr>
        <tr v-click><td style="color:var(--orange);font-weight:700;">2</td><td class="mono">**</td><td>Exponentiation</td></tr>
        <tr v-click><td style="color:var(--orange);font-weight:700;">3</td><td class="mono">+x, -x, ~x</td><td>Unary operators</td></tr>
        <tr v-click><td style="color:#d69e2e;font-weight:700;">4</td><td class="mono">* / // %</td><td>Multiply / Divide</td></tr>
        <tr v-click><td style="color:var(--green);font-weight:700;">5</td><td class="mono">+ -</td><td>Add / Subtract</td></tr>
        <tr v-click><td style="color:var(--green);font-weight:700;">6</td><td class="mono">&lt;&lt; &gt;&gt;</td><td>Bitwise Shift</td></tr>
        <tr v-click><td style="color:var(--blue);font-weight:700;">7</td><td class="mono">&amp; | ^</td><td>Bitwise</td></tr>
        <tr v-click><td style="color:var(--blue);font-weight:700;">8</td><td class="mono">== != &lt; &gt; &lt;= &gt;=</td><td>Comparison</td></tr>
        <tr v-click><td style="color:var(--navy-mid);font-weight:700;">9</td><td class="mono">not</td><td>Logical NOT</td></tr>
        <tr v-click><td style="color:var(--navy-mid);font-weight:700;">10</td><td class="mono">and</td><td>Logical AND</td></tr>
        <tr v-click><td style="color:var(--slate);font-weight:700;">11 (Lowest)</td><td class="mono">or</td><td>Logical OR</td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Precedence in Action</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Without parentheses</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">2</span> + <span style="color:#b45309;">3</span> * <span style="color:#b45309;">4</span>)     <span style="color:#6b7280;"># 14  (* before +)</span><br>
    <span style="color:#6b7280;"># With parentheses</span><br>
    <span style="color:#2d7a00;">print</span>((<span style="color:#b45309;">2</span> + <span style="color:#b45309;">3</span>) * <span style="color:#b45309;">4</span>)   <span style="color:#6b7280;"># 20  (+ forced first)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">2</span> ** <span style="color:#b45309;">3</span> ** <span style="color:#b45309;">2</span>)    <span style="color:#6b7280;"># 512 (** right-to-left)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">10</span> - <span style="color:#b45309;">3</span> - <span style="color:#b45309;">2</span>)    <span style="color:#6b7280;"># 5   (left-to-right)</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Associativity Rules</div>
  <div v-after style="display:flex;flex-direction:column;gap:4px;margin-top:4px;">
    <div class="card" style="padding:8px 12px;">
      <div style="font-size:.72rem;"><strong style="color:var(--green);">Left-to-Right:</strong> <span class="mono">+ - * / // %</span> — evaluated left to right</div>
    </div>
    <div class="card" style="padding:8px 12px;">
      <div style="font-size:.72rem;"><strong style="color:var(--orange);">Right-to-Left:</strong> <span class="mono">**</span> and unary — evaluated right to left</div>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div><strong>Golden rule:</strong> When in doubt, use <span class="mono">()</span> parentheses to make your intention clear and avoid bugs!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
