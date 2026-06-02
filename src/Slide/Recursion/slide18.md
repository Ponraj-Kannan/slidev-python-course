---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — PRACTICAL PROGRAMS — SUM & BINARY SEARCH
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Programs — Sum &amp; Binary Search">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical Programs — <span class="highlight">Part 3</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Program 5 — Sum of Numbers</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Sum 1 + 2 + ... + n</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sum_n</span>(<span style="color:#b45309;">5</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">15 &nbsp;<span class="comment"># 1+2+3+4+5</span></div>

  <div v-click class="section-label" style="margin-top:8px;">Trace — sum_n(4)</div>
  <div v-after>
    <table class="trace-table" style="margin-bottom:40px;">
      <thead><tr><th>Call</th><th>n</th><th>Returns</th></tr></thead>
      <tbody>
        <tr><td>sum_n(4)</td><td>4</td><td>4 + sum_n(3) = 10</td></tr>
        <tr><td>sum_n(3)</td><td>3</td><td>3 + sum_n(2) = 6</td></tr>
        <tr><td>sum_n(2)</td><td>2</td><td>2 + sum_n(1) = 3</td></tr>
        <tr><td>sum_n(1)</td><td>1</td><td>1 + sum_n(0) = 1</td></tr>
        <tr class="hl"><td>sum_n(0)</td><td>0</td><td>0 (base case)</td></tr>
      </tbody>
    </table>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Program 6 — Recursive Binary Search</div>

  <div v-after class="code-block" style="font-size:.68rem;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">arr</span>, <span style="color:#0e6ead;">target</span>, <span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">high</span>):<br>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">low</span> &gt; <span style="color:#0e6ead;">high</span>: <span style="color:#6b7280;"># base: not found</span></span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> -<span style="color:#b45309;">1</span></span>
    <span style="padding-left:16px;display:block;"><span style="color:#0e6ead;">mid</span> = (<span style="color:#0e6ead;">low</span> + <span style="color:#0e6ead;">high</span>) // <span style="color:#b45309;">2</span></span>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">arr</span>[<span style="color:#0e6ead;">mid</span>] == <span style="color:#0e6ead;">target</span>: <span style="color:#6b7280;"># found!</span></span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">mid</span></span>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">elif</span> <span style="color:#0e6ead;">arr</span>[<span style="color:#0e6ead;">mid</span>] &lt; <span style="color:#0e6ead;">target</span>:</span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">arr</span>, <span style="color:#0e6ead;">target</span>, <span style="color:#0e6ead;">mid</span>+<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">high</span>)</span>
    <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">else</span>:</span>
    <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">arr</span>, <span style="color:#0e6ead;">target</span>, <span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">mid</span>-<span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#0e6ead;">data</span> = [<span style="color:#b45309;">2</span>, <span style="color:#b45309;">5</span>, <span style="color:#b45309;">8</span>, <span style="color:#b45309;">12</span>, <span style="color:#b45309;">16</span>, <span style="color:#b45309;">23</span>, <span style="color:#b45309;">38</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">binary_search</span>(<span style="color:#0e6ead;">data</span>, <span style="color:#b45309;">12</span>, <span style="color:#b45309;">0</span>, <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">data</span>)-<span style="color:#b45309;">1</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">3 &nbsp;<span class="comment"># index 3</span></div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Binary search halves the search space each time — O(log n) efficiency. A perfect use case for recursion.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
