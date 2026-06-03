<Slide2 topic="Removing Elements from Sets">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Removing</span> Elements from a Set</div>

<table class="cmp-table">
  <thead>
    <tr><th>Method</th><th>What it does</th><th>If missing</th></tr>
  </thead>
  <tbody>
    <tr v-click><td class="mono">remove(x)</td><td>Removes <span class="mono">x</span></td><td class="no">Raises KeyError</td></tr>
    <tr v-click><td class="mono">discard(x)</td><td>Removes <span class="mono">x</span></td><td class="yes">Silently does nothing</td></tr>
    <tr v-click><td class="mono">pop()</td><td>Removes an arbitrary item</td><td class="no">Raises KeyError if empty</td></tr>
    <tr v-click><td class="mono">clear()</td><td>Empties the set</td><td>—</td></tr>
  </tbody>
</table>

<div v-click style="margin-top:10px;">
  <div class="g2" style="gap:10px;">
    <div class="code-block">
      <span style="color:#0e6ead;">s</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>}<br>
      <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">remove</span>(<span style="color:#b45309;">2</span>)<br>
      <span style="color:#6b7280;"># {1, 3, 4}</span><br>
      <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">discard</span>(<span style="color:#b45309;">99</span>) <span style="color:#6b7280;"># no error</span><br>
    </div>
    <div class="code-block">
      <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">pop</span>()      <span style="color:#6b7280;"># removes some item</span><br>
      <span style="color:#0e6ead;">s</span>.<span style="color:#0e6ead;">clear</span>()<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>)<br>
      <span style="color:#6b7280;"># set()</span>
    </div>
  </div>
</div>

<div v-click class="callout callout-warn" style="margin-top:10px;font-size:.7rem;">
  <div><strong>pop()</strong> on a set is non-deterministic — Python may remove any item, since order is undefined.</div>
</div>

  </template>
</Slide2>
