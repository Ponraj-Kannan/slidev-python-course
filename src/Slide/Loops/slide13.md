---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — NESTED LOOPS: SYNTAX + EXECUTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Nested Loops">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Nested</span> Loops — Syntax &amp; Execution</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Syntax &amp; Example</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Outer loop</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>):<br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Inner loop</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">for</span> <span style="color:#c49a00;">j</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>):</span>
    <span style="padding-left:40px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>, <span style="color:#2d7a00;">"x"</span>, <span style="color:#c49a00;">j</span>, <span style="color:#2d7a00;">"="</span>, <span style="color:#0e6ead;">i</span>*<span style="color:#c49a00;">j</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.7rem;">
    1 x 1 = 1 &nbsp; 1 x 2 = 2 &nbsp; 1 x 3 = 3<br>
    2 x 1 = 2 &nbsp; 2 x 2 = 4 &nbsp; 2 x 3 = 6<br>
    3 x 1 = 3 &nbsp; 3 x 2 = 6 &nbsp; 3 x 3 = 9
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div>For every 1 run of the outer loop, the inner loop runs <strong>completely</strong> — all its iterations.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Execution Visualization (i x j iterations)</div>

  <div v-after style="overflow-x:auto;">
    <table class="trace-table" style="font-size:.68rem;">
      <thead>
        <tr><th>Outer (i)</th><th>Inner (j)</th><th>i * j</th><th>Total Count</th></tr>
      </thead>
      <tbody>
        <tr><td>1</td><td>1, 2, 3</td><td>1, 2, 3</td><td>3 runs</td></tr>
        <tr><td>2</td><td>1, 2, 3</td><td>2, 4, 6</td><td>3 runs</td></tr>
        <tr><td>3</td><td>1, 2, 3</td><td>3, 6, 9</td><td>3 runs</td></tr>
        <tr class="hl"><td colspan="3"><strong>Total iterations</strong></td><td><strong>9 runs</strong></td></tr>
      </tbody>
    </table>
  </div>
    <!-- <div v-click class="small-text" style="margin-top:10px;"><strong>Pattern: Star Triangle</strong></div>
    <div v-after style="background:#f6f8fa;border-radius:6px;border:1px solid #e1e4e8;padding:8px 12px;margin-top:6px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.8;">
      <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">5</span>):<br>
      <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"* "</span> * <span style="color:#0e6ead;">i</span>)</span>
      <div style="color:#2d7a00;margin-top:6px;">*<br>* *<br>* * *<br>* * * *</div>
    </div> -->
</div>

</div>

  </template>
</Slide2>
