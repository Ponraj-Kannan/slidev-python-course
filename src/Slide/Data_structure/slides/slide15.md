<Slide2 topic="List Built-in Functions">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">List <span class="highlight">Functions</span> — Built-in Helpers</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Common Built-ins</div>

  <table v-after class="cmp-table">
    <thead>
      <tr><th>Function</th><th>Purpose</th></tr>
    </thead>
    <tbody>
      <tr><td class="mono">len(n)</td><td>Number of items</td></tr>
      <tr><td class="mono">min(n)</td><td>Smallest item</td></tr>
      <tr><td class="mono">max(n)</td><td>Largest item</td></tr>
      <tr><td class="mono">sum(n)</td><td>Total of numeric items</td></tr>
      <tr><td class="mono">sorted(n)</td><td>NEW sorted copy</td></tr>
      <tr><td class="mono">list(s)</td><td>Convert string / range to list</td></tr>
    </tbody>
  </table>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><span class="mono">sorted()</span> returns a new list. <span class="mono">list.sort()</span> modifies in place.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">In Action</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">marks</span> = [<span style="color:#b45309;">82</span>, <span style="color:#b45309;">76</span>, <span style="color:#b45309;">91</span>, <span style="color:#b45309;">88</span>]<br>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">marks</span>))      <span style="color:#6b7280;"># 4</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">min</span>(<span style="color:#0e6ead;">marks</span>))      <span style="color:#6b7280;"># 76</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">max</span>(<span style="color:#0e6ead;">marks</span>))      <span style="color:#6b7280;"># 91</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">marks</span>))      <span style="color:#6b7280;"># 337</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">marks</span>)/<span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">marks</span>))<br>
    <span style="color:#6b7280;"># 84.25 — average</span>
  </div>

  <div v-click class="output-box" style="margin-top:4px;">
    4<br>76<br>91<br>337<br>84.25
  </div>
</div>

</div>

  </template>
</Slide2>
