<Slide2 topic="Tuples — Practical Examples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Tuples — <span class="highlight">Practical</span> Examples</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 1 — Function Returning Tuple</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">min_max</span>(<span style="color:#0e6ead;">nums</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">min</span>(<span style="color:#0e6ead;">nums</span>), <span style="color:#2d7a00;">max</span>(<span style="color:#0e6ead;">nums</span>)</span>
    <br>
    <span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">high</span> = <span style="color:#0e6ead;">min_max</span>([<span style="color:#b45309;">5</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">9</span>, <span style="color:#b45309;">1</span>])<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">low</span>, <span style="color:#0e6ead;">high</span>)
  </div>

  <div v-click class="output-box">1 9</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Swap Variables</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span><br>
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#0e6ead;">b</span>, <span style="color:#0e6ead;">a</span>   <span style="color:#6b7280;"># swap</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>)
  </div>

  <div v-click class="output-box">20 10</div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Tuple vs List</div>

  <table v-after class="cmp-table">
    <thead>
      <tr><th>Property</th><th>List</th><th>Tuple</th></tr>
    </thead>
    <tbody>
      <tr><td>Syntax</td><td class="mono">[1,2]</td><td class="mono">(1,2)</td></tr>
      <tr><td>Mutable</td><td class="yes">Yes</td><td class="no">No</td></tr>
      <tr><td>Speed</td><td>Slower</td><td class="yes">Faster</td></tr>
      <tr><td>Methods</td><td>11+</td><td>Only 2</td></tr>
      <tr><td>Memory</td><td>More</td><td class="yes">Less</td></tr>
    </tbody>
  </table>

  <div v-click class="section-label" style="margin-top:6px;">Example 3 — RGB Colors</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">red</span>   = (<span style="color:#b45309;">255</span>, <span style="color:#b45309;">0</span>, <span style="color:#b45309;">0</span>)<br>
    <span style="color:#0e6ead;">green</span> = (<span style="color:#b45309;">0</span>, <span style="color:#b45309;">255</span>, <span style="color:#b45309;">0</span>)<br>
    <span style="color:#0e6ead;">blue</span>  = (<span style="color:#b45309;">0</span>, <span style="color:#b45309;">0</span>, <span style="color:#b45309;">255</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">red</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># 255</span>
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div>Tuples are perfect for <strong>fixed records</strong> that should never change.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
