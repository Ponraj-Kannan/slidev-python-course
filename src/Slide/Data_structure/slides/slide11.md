<Slide2 topic="Removing Elements">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Removing</span> Elements from a List</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Four Ways to Remove</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>, <span style="color:#b45309;">40</span>]<br>
    <br>
    <span style="color:#6b7280;"># by value</span><br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">remove</span>(<span style="color:#b45309;">20</span>)<br>
    <span style="color:#6b7280;"># [10, 30, 40]</span><br>
    <br>
    <span style="color:#6b7280;"># pop last (default)</span><br>
    <span style="color:#0e6ead;">x</span> = <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">pop</span>()<br>
    <span style="color:#6b7280;"># x=40, n=[10, 30]</span><br>
    <br>
    <span style="color:#6b7280;"># pop by index</span><br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">pop</span>(<span style="color:#b45309;">0</span>)<br>
    <span style="color:#6b7280;"># n = [30]</span><br>
    <br>
    <span style="color:#6b7280;"># clear all</span><br>
    <span style="color:#0e6ead;">n</span>.<span style="color:#0e6ead;">clear</span>()<br>
    <span style="color:#6b7280;"># n = []</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Method Quick Reference</div>

  <table v-after class="cmp-table">
    <thead>
      <tr><th>Method</th><th>What it removes</th><th>Returns</th></tr>
    </thead>
    <tbody>
      <tr><td class="mono">remove(x)</td><td>First occurrence of value x</td><td>None</td></tr>
      <tr><td class="mono">pop()</td><td>Last item</td><td>Removed item</td></tr>
      <tr><td class="mono">pop(i)</td><td>Item at index i</td><td>Removed item</td></tr>
      <tr><td class="mono">del list[i]</td><td>Item at index i</td><td>—</td></tr>
      <tr><td class="mono">clear()</td><td>All items</td><td>None</td></tr>
    </tbody>
  </table>

  <div v-click class="callout callout-danger" style="margin-top:6px;font-size:.7rem;">
    <div><span class="mono">remove(x)</span> with a missing x raises <strong>ValueError</strong>.</div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><span class="mono">del</span> is a keyword, not a method — works on any indexable object.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
