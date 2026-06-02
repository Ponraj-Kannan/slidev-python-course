---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — BASE CASE AND RECURSIVE CASE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Base Case and Recursive Case">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Base Case</span> &amp; <span class="highlight">Recursive Case</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">Base Case</div>
    <div class="small-text" style="margin-top:4px;">The <strong>termination condition</strong>. Returns a value directly — no more recursive calls.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># Base case example</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>):<br>
    <span style="padding-left:20px;display:block;background:#f0fff4;border-left:3px solid var(--green);"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">exp</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># BASE CASE</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">base</span> * <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>-<span style="color:#b45309;">1</span>)</span>
  </div>

  <div v-click class="callout callout-danger">
    <div><strong>Missing base case = RecursionError!</strong> Python raises <span class="mono">RecursionError: maximum recursion depth exceeded</span> after ~1000 calls.</div>
  </div>

  <div v-click class="card-green" style="font-size:.75rem;">
    <strong>Good base cases check for:</strong>
    <div style="margin-top:6px;display:flex;flex-direction:column;gap:3px;">
      <div><span class="pill pill-green">n == 0</span> for counting down</div>
      <div><span class="pill pill-green">n == 1</span> for multiplication-based</div>
      <div><span class="pill pill-green">len(s) == 0</span> for strings/lists</div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Recursive Case</div>
    <div class="small-text" style="margin-top:4px;">The step that makes the problem <strong>smaller</strong> and calls the function again.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">exp</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;background:#ebf8ff;border-left:3px solid var(--blue);"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">base</span> * <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>-<span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># RECURSIVE</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">power</span>(<span style="color:#b45309;">2</span>, <span style="color:#b45309;">4</span>))
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Base vs Recursive Comparison</div>
  <div v-after>
    <table class="cmp-table" style="margin-bottom:40px;">
      <thead><tr><th>Aspect</th><th>Base Case</th><th>Recursive Case</th></tr></thead>
      <tbody>
        <tr><td>Purpose</td><td>Stop recursion</td><td>Shrink the problem</td></tr>
        <tr><td>Returns</td><td class="yes">Direct value</td><td>Function call</td></tr>
        <tr><td>Required?</td><td class="yes">Always</td><td class="yes">Always</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>
