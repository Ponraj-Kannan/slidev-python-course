<Slide2 topic="Dictionary Methods Quick Reference">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Dictionary <span class="highlight">Methods</span></div>

<table class="cmp-table">
  <thead>
    <tr><th>Method</th><th>Description</th><th>Example</th></tr>
  </thead>
  <tbody>
    <tr v-click><td class="mono">keys()</td><td>All keys</td><td class="mono">d.keys()</td></tr>
    <tr v-click><td class="mono">values()</td><td>All values</td><td class="mono">d.values()</td></tr>
    <tr v-click><td class="mono">items()</td><td>All (key, value) pairs</td><td class="mono">d.items()</td></tr>
    <tr v-click><td class="mono">get(k, default)</td><td>Safe value lookup</td><td class="mono">d.get("x", 0)</td></tr>
    <tr v-click><td class="mono">update(other)</td><td>Merge another dict</td><td class="mono">d.update(d2)</td></tr>
    <tr v-click><td class="mono">pop(k)</td><td>Remove key &amp; return value</td><td class="mono">d.pop("a")</td></tr>
    <tr v-click><td class="mono">popitem()</td><td>Remove last inserted item</td><td class="mono">d.popitem()</td></tr>
    <tr v-click><td class="mono">clear()</td><td>Empty the dict</td><td class="mono">d.clear()</td></tr>
    <tr v-click><td class="mono">copy()</td><td>Shallow copy</td><td class="mono">d.copy()</td></tr>
  </tbody>
</table>

<div v-click class="callout callout-info" style="margin-top:10px;font-size:.7rem;">
  <div><span class="mono">keys()</span>, <span class="mono">values()</span> and <span class="mono">items()</span> return view objects — they update live with the dict.</div>
</div>

  </template>
</Slide2>
