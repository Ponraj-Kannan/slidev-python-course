<Slide2 topic="List Methods III — sort / reverse / copy">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">List Methods — <span class="highlight">Part 3</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">S</div>
    <div>
      <div class="slide-h3 mono">sort()</div>
      <div class="small-text">Sorts the list in place — modifies the original.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">3</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">2</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">sort</span>()<br>
    <span style="color:#6b7280;"># [1, 2, 3, 4]</span><br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">sort</span>(<span style="color:#0e6ead;">reverse</span>=<span style="color:#c49a00;">True</span>)<br>
    <span style="color:#6b7280;"># [4, 3, 2, 1]</span>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">R</div>
    <div>
      <div class="slide-h3 mono">reverse()</div>
      <div class="small-text">Flips the order of items in place.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">reverse</span>()<br>
    <span style="color:#6b7280;"># [3, 2, 1]</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">C</div>
    <div>
      <div class="slide-h3 mono">copy()</div>
      <div class="small-text">Returns a shallow copy — independent from the original.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">a</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#0e6ead;">a</span>.<span style="color:#0e6ead;">copy</span>()<br>
    <span style="color:#0e6ead;">b</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#b45309;">4</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>)  <span style="color:#6b7280;"># [1, 2, 3]</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">b</span>)  <span style="color:#6b7280;"># [1, 2, 3, 4]</span>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:4px;font-size:.7rem;">
    <div><strong>Warning:</strong> <span class="mono">b = a</span> does NOT copy — both names point to the same list. Use <span class="mono">a.copy()</span>.</div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><span class="mono">sorted(list)</span> returns a NEW sorted list — original stays untouched.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
