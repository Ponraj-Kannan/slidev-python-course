<Slide2 topic="Creating Lists">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Creating</span> Lists</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Four Common Ways</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Empty list</span><br>
    <span style="color:#0e6ead;">a</span> = []<br>
    <br>
    <span style="color:#6b7280;"># List with values</span><br>
    <span style="color:#0e6ead;">b</span> = [<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>]<br>
    <br>
    <span style="color:#6b7280;"># Mixed data types</span><br>
    <span style="color:#0e6ead;">c</span> = [<span style="color:#2d7a00;">"Anu"</span>, <span style="color:#b45309;">19</span>, <span style="color:#b45309;">90.5</span>]<br>
    <br>
    <span style="color:#6b7280;"># Using list() constructor</span><br>
    <span style="color:#0e6ead;">d</span> = <span style="color:#2d7a00;">list</span>(<span style="color:#2d7a00;">"abc"</span>)
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Nested Lists (list inside list)</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Each row is a sub-list</span><br>
    <span style="color:#0e6ead;">matrix</span> = [<br>
    <span style="padding-left:20px;display:block;">[<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>],</span>
    <span style="padding-left:20px;display:block;">[<span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>, <span style="color:#b45309;">6</span>],</span>
    <span style="padding-left:20px;display:block;">[<span style="color:#b45309;">7</span>, <span style="color:#b45309;">8</span>, <span style="color:#b45309;">9</span>]</span>
    ]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">matrix</span>[<span style="color:#b45309;">1</span>][<span style="color:#b45309;">2</span>])
    <span style="color:#6b7280;"># 6</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Matrix Visualization</div>
    <div style="display:grid;grid-template-columns:repeat(3,38px);gap:4px;justify-content:start;">
      <div class="idx-cell">1</div><div class="idx-cell">2</div><div class="idx-cell">3</div>
      <div class="idx-cell">4</div><div class="idx-cell">5</div><div class="idx-cell hl">6</div>
      <div class="idx-cell">7</div><div class="idx-cell">8</div><div class="idx-cell">9</div>
    </div>
    <div class="small-text" style="margin:-120px 0px 100px 150px;"><span class="mono">matrix[1][2]</span> -> row 1, column 2 -> 6</div>
  </div>
</div>

</div>

  </template>
</Slide2>
