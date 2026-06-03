<Slide2 topic="Adding Elements to Sets">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Adding</span> Elements to a Set</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">A</div>
    <div>
      <div class="slide-h3 mono">add(x)</div>
      <div class="small-text">Adds a single item. Ignored if already present.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">s</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>}<br>
    <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">add</span>(<span style="color:#b45309;">3</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>)<br>
    <span style="color:#6b7280;"># {1, 2, 3}</span><br>
    <br>
    <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">add</span>(<span style="color:#b45309;">2</span>)  <span style="color:#6b7280;"># silently ignored</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>)<br>
    <span style="color:#6b7280;"># {1, 2, 3}</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">U</div>
    <div>
      <div class="slide-h3 mono">update(iter)</div>
      <div class="small-text">Adds many items at once from any iterable.</div>
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">s</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>}<br>
    <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">update</span>([<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>])<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>)<br>
    <span style="color:#6b7280;"># {1, 2, 3, 4, 5}</span><br>
    <br>
    <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">update</span>(<span style="color:#2d7a00;">"ab"</span>)<br>
    <span style="color:#6b7280;"># adds 'a' and 'b'</span>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><span class="mono">update()</span> can take lists, tuples, sets, strings — anything iterable.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
