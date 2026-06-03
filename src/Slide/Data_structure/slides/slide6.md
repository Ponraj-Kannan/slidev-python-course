<Slide2 topic="Features of Lists">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Features of a <span class="highlight">List</span></div>

<div class="g4" style="gap:10px;">

  <div v-click class="card card-red" style="text-align:center;">
    <div class="icon-circle ic-red" style="margin:0 auto 6px;">O</div>
    <div class="slide-h3" style="color:var(--red-dark);">Ordered</div>
    <div class="small-text" style="margin-top:4px;">Items keep the order in which they are inserted.</div>
  </div>

  <div v-click class="card card-blue" style="text-align:center;">
    <div class="icon-circle ic-blue" style="margin:0 auto 6px;">M</div>
    <div class="slide-h3" style="color:var(--blue);">Mutable</div>
    <div class="small-text" style="margin-top:4px;">Items can be added, changed, or removed.</div>
  </div>

  <div v-click class="card card-green" style="text-align:center;">
    <div class="icon-circle ic-green" style="margin:0 auto 6px;">D</div>
    <div class="slide-h3" style="color:var(--green);">Duplicates OK</div>
    <div class="small-text" style="margin-top:4px;">The same value can appear many times.</div>
  </div>

  <div v-click class="card card-orange" style="text-align:center;">
    <div class="icon-circle ic-orange" style="margin:0 auto 6px;">X</div>
    <div class="slide-h3" style="color:var(--orange);">Mixed Types</div>
    <div class="small-text" style="margin-top:4px;">Strings, numbers, lists — all together.</div>
  </div>

</div>

<div v-click style="margin-top:12px;">
  <div class="section-label" style="margin-bottom:6px;">Each Feature in Code</div>
  <div class="g2" style="gap:10px;">
    <div class="code-block">
      <span style="color:#6b7280;"># Ordered + duplicates</span><br>
      <span style="color:#0e6ead;">a</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>)<br>
      <span style="color:#6b7280;"># [1, 2, 2, 3]</span>
    </div>
    <div class="code-block">
      <span style="color:#6b7280;"># Mutable + mixed types</span><br>
      <span style="color:#0e6ead;">b</span> = [<span style="color:#2d7a00;">"Anu"</span>, <span style="color:#b45309;">19</span>, <span style="color:#c49a00;">True</span>]<br>
      <span style="color:#0e6ead;">b</span>[<span style="color:#b45309;">0</span>] = <span style="color:#2d7a00;">"Ravi"</span>  <span style="color:#6b7280;"># change</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">b</span>)
    </div>
  </div>
</div>

  </template>
</Slide2>
