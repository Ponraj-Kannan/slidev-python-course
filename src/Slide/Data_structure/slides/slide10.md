<Slide2 topic="Updating &amp; Adding to Lists">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Updating</span> &amp; <span class="highlight">Adding</span> Elements</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Update by Index</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">items</span> = [<span style="color:#2d7a00;">"pen"</span>, <span style="color:#2d7a00;">"book"</span>, <span style="color:#2d7a00;">"bag"</span>]<br>
    <span style="color:#0e6ead;">items</span>[<span style="color:#b45309;">1</span>] = <span style="color:#2d7a00;">"notebook"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">items</span>)
  </div>

  <div v-click class="output-box">['pen', 'notebook', 'bag']</div>

  <div v-click class="card card-green" style="text-align:center;margin-top:4px;">
    <div class="slide-h2" style="color:var(--green);">Update a Slice</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>]<br>
    <span style="color:#0e6ead;">n</span>[<span style="color:#b45309;">1</span>:<span style="color:#b45309;">3</span>] = [<span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>)  <span style="color:#6b7280;"># [1, 20, 30, 4]</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-orange" style="text-align:center;">
    <div class="slide-h2" style="color:var(--orange);">Adding Elements</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># append() — add at end</span><br>
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#b45309;">3</span>)<br>
    <span style="color:#6b7280;"># n = [1, 2, 3]</span><br>
    <br>
    <span style="color:#6b7280;"># insert() — at position</span><br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">insert</span>(<span style="color:#b45309;">0</span>, <span style="color:#b45309;">99</span>)<br>
    <span style="color:#6b7280;"># n = [99, 1, 2, 3]</span><br>
    <br>
    <span style="color:#6b7280;"># extend() — many items</span><br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">extend</span>([<span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>])<br>
    <span style="color:#6b7280;"># n = [99, 1, 2, 3, 4, 5]</span>
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;margin-top:4px;">
    <div><strong>Tip:</strong> <span class="mono">append([4,5])</span> adds the list as one item. Use <span class="mono">extend</span> to flatten.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
