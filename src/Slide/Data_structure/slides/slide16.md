<Slide2 topic="Lists — Practical Examples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Lists — <span class="highlight">Practical</span> Examples</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 1 — Average Marks</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">marks</span> = [<span style="color:#b45309;">82</span>, <span style="color:#b45309;">76</span>, <span style="color:#b45309;">91</span>, <span style="color:#b45309;">88</span>]<br>
    <span style="color:#0e6ead;">avg</span> = <span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">marks</span>) / <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">marks</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Average:"</span>, <span style="color:#0e6ead;">avg</span>)
  </div>

  <div v-click class="output-box">Average: 84.25</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Even Numbers</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>, <span style="color:#b45309;">6</span>]<br>
    <span style="color:#0e6ead;">even</span> = [<span style="color:#0e6ead;">x</span> <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">x</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">n</span> <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">x</span>%<span style="color:#b45309;">2</span>==<span style="color:#b45309;">0</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">even</span>)
  </div>

  <div v-click class="output-box">[2, 4, 6]</div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 3 — Shopping Cart</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">cart</span> = []<br>
    <span style="color:#0e6ead;">cart</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#2d7a00;">"Milk"</span>)<br>
    <span style="color:#0e6ead;">cart</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#2d7a00;">"Bread"</span>)<br>
    <span style="color:#0e6ead;">cart</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#2d7a00;">"Eggs"</span>)<br>
    <span style="color:#0e6ead;">cart</span>.<span style="color:#0e6ead;">remove</span>(<span style="color:#2d7a00;">"Bread"</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">cart</span>)
  </div>

  <div v-click class="output-box">['Milk', 'Eggs']</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 4 — Reverse a List</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">a</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>]<br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#0e6ead;">a</span>[::-<span style="color:#b45309;">1</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">b</span>)
  </div>

  <div v-click class="output-box">[4, 3, 2, 1]</div>
</div>

</div>

  </template>
</Slide2>
