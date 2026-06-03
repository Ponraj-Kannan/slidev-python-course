<Slide2 topic="List Methods II — pop / clear / index / count">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">List Methods — <span class="highlight">Part 2</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
    <div class="icon-circle ic-red">P</div>
    <div>
      <div class="slide-h3 mono">pop(i = -1)</div>
      <div class="small-text">Removes and returns item at index <span class="mono">i</span> (default: last).</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>]<br>
    <span style="color:#0e6ead;">x</span> = <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">pop</span>()<br>
    <span style="color:#6b7280;"># x=30, n=[10, 20]</span>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">C</div>
    <div>
      <div class="slide-h3 mono">clear()</div>
      <div class="small-text">Removes every element — list becomes empty.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">clear</span>()<br>
    <span style="color:#6b7280;"># n = []</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">I</div>
    <div>
      <div class="slide-h3 mono">index(x)</div>
      <div class="small-text">Returns position of the first match of <span class="mono">x</span>.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#2d7a00;">"a"</span>, <span style="color:#2d7a00;">"b"</span>, <span style="color:#2d7a00;">"c"</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">index</span>(<span style="color:#2d7a00;">"b"</span>))<br>
    <span style="color:#6b7280;"># 1</span>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">C</div>
    <div>
      <div class="slide-h3 mono">count(x)</div>
      <div class="small-text">How many times <span class="mono">x</span> appears.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">2</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">count</span>(<span style="color:#b45309;">2</span>))<br>
    <span style="color:#6b7280;"># 3</span>
  </div>
</div>

</div>

  </template>
</Slide2>
