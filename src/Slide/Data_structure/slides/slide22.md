<Slide2 topic="Tuple Methods, Packing &amp; Unpacking">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Tuple <span class="highlight">Methods</span> &amp; <span class="highlight">Packing</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Only Two Methods</div>

  <table v-after class="cmp-table">
    <thead>
      <tr><th>Method</th><th>Purpose</th><th>Returns</th></tr>
    </thead>
    <tbody>
      <tr><td class="mono">count(x)</td><td>How many times <span class="mono">x</span> appears</td><td>int</td></tr>
      <tr><td class="mono">index(x)</td><td>Position of first <span class="mono">x</span></td><td>int</td></tr>
    </tbody>
  </table>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">t</span> = (<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">2</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>.<span style="color:#0e6ead;">count</span>(<span style="color:#b45309;">2</span>))  <span style="color:#6b7280;"># 3</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>.<span style="color:#0e6ead;">index</span>(<span style="color:#b45309;">3</span>))  <span style="color:#6b7280;"># 3</span>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Tuples have fewer methods because they can't be modified.</div>
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div>Use <span class="mono">*rest</span> to capture leftover items into a list.</div>
  </div>
</div>

<div class="flex-col" style="margin-top:-30px">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Packing</div>
    <div class="small-text" style="margin-top:4px;">Put many values into a single tuple.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># packing</span><br>
    <span style="color:#0e6ead;">person</span> = <span style="color:#2d7a00;">"Anu"</span>, <span style="color:#b45309;">19</span>, <span style="color:#b45309;">85.5</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">person</span>)<br>
    <span style="color:#6b7280;"># ('Anu', 19, 85.5)</span>
  </div>

  <div v-click class="card card-green" style="text-align:center;margin-top:4px;">
    <div class="slide-h2" style="color:var(--green);">Unpacking</div>
    <div class="small-text" style="margin-top:4px;">Spread a tuple into separate variables.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># unpacking</span><br>
    <span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>, <span style="color:#0e6ead;">cgpa</span> = <span style="color:#0e6ead;">person</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>, <span style="color:#0e6ead;">cgpa</span>)<br>
    <span style="color:#6b7280;"># Anu 19 85.5</span>
  </div>
</div>

</div>

  </template>
</Slide2>
