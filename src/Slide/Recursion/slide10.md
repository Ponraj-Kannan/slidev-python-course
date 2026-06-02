---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — RECURSION VS ITERATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursion vs Iteration">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Recursion</span> vs <span class="highlight">Iteration</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Side-by-Side — Sum of N Numbers</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="flex-col">
      <div class="section-label" style="color:var(--blue);">Iteration</div>
      <div class="code-block" style="font-size:.68rem;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_iter</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#0e6ead;">total</span> = <span style="color:#b45309;">0</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>,<span style="color:#0e6ead;">n</span>+<span style="color:#b45309;">1</span>):</span>
        <span style="padding-left:32px;display:block;"><span style="color:#0e6ead;">total</span> += <span style="color:#0e6ead;">i</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">total</span></span>
      </div>
    </div>
    <div class="flex-col">
      <div class="section-label" style="color:var(--red);">Recursion</div>
      <div class="code-block" style="font-size:.68rem;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_rec</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
        <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">sum_rec</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
      </div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Both produce the same result</div>
  <div v-after class="output-box" style="font-size:.72rem;">
    sum_iter(5) = 15<br>
    sum_rec(5) = 15
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Detailed Comparison Table</div>
  <div v-after>
    <table class="cmp-table">
      <thead><tr><th>Feature</th><th>Recursion</th><th>Iteration</th></tr></thead>
      <tbody>
        <tr>
          <td>Code length</td>
          <td class="yes">Usually shorter</td>
          <td>Longer</td>
        </tr>
        <tr>
          <td>Readability</td>
          <td class="yes">High (for math)</td>
          <td>Moderate</td>
        </tr>
        <tr>
          <td>Memory usage</td>
          <td class="no">More (call stack)</td>
          <td class="yes">Less</td>
        </tr>
        <tr>
          <td>Speed</td>
          <td class="no">Slower</td>
          <td class="yes">Faster</td>
        </tr>
        <tr>
          <td>Stack overflow risk</td>
          <td class="no">Yes</td>
          <td class="yes">No</td>
        </tr>
        <tr>
          <td>Base case needed</td>
          <td class="no">Yes</td>
          <td class="yes">No</td>
        </tr>
        <tr>
          <td>Best for</td>
          <td>Trees, DFS, Math</td>
          <td>Simple loops</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;font-size:.7rem; margin-bottom:40px;">
    <div><strong>When to choose recursion:</strong> When the problem is naturally tree-shaped or divide-and-conquer in nature.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
