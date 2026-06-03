<Slide2 topic="List Methods I — append / insert / extend / remove">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">List Methods — <span class="highlight">Part 1</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">A</div>
    <div>
      <div class="slide-h3 mono">append(x)</div>
      <div class="small-text">Adds <span class="mono">x</span> to the end of the list.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#b45309;">3</span>)<br>
    <span style="color:#6b7280;"># [1, 2, 3]</span>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">I</div>
    <div>
      <div class="slide-h3 mono">insert(i, x)</div>
      <div class="small-text">Adds <span class="mono">x</span> at index <span class="mono">i</span>; later items shift right.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">insert</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">99</span>)<br>
    <span style="color:#6b7280;"># [1, 99, 2, 3]</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">E</div>
    <div>
      <div class="slide-h3 mono">extend(iter)</div>
      <div class="small-text">Appends each item of an iterable.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">extend</span>([<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>])<br>
    <span style="color:#6b7280;"># [1, 2, 3, 4]</span>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
    <div class="icon-circle ic-red">R</div>
    <div>
      <div class="slide-h3 mono">remove(x)</div>
      <div class="small-text">Removes the first item that equals <span class="mono">x</span>.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">remove</span>(<span style="color:#b45309;">2</span>)<br>
    <span style="color:#6b7280;"># [1, 2, 3]</span>
  </div>
</div>

</div>

  </template>
</Slide2>
